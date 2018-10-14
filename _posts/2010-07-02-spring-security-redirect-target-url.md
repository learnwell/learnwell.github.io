---

layout: post
title: Spring Security - Redirect back to target URL after successful authentication
author: pulkit
tags: [redirect, security, spring, spring security, target, target URL, url]

---

Most, if not all, users will bookmark their favorite pages in any online application. One would be hard pressed to find folks that bookmark the login pages!

When accessing application URLs directly, if a login page is presented to the web users, they expect to end up at their original destination rather than some application specified home page.

As the Spring Security framework has progressed it has supported this use-case in an evolving manner.

### Spring-Security 2.0.x

[SavedRequest](http://static.springsource.org/spring-security/site/docs/2.0.x/apidocs/org/springframework/security/ui/savedrequest/SavedRequest.html) is used by [AbstractProcessingFilter](http://static.springsource.org/spring-security/site/docs/2.0.x/apidocs/org/springframework/security/ui/AbstractProcessingFilter.html) and [SavedRequestAwareWrapper](http://static.springsource.org/spring-security/site/docs/2.0.x/apidocs/org/springframework/security/wrapper/SavedRequestAwareWrapper.html) to reproduce the request after successful authentication. An instance of this class is stored at the time of an authentication exception by [ExceptionTranslationFilter](http://static.springsource.org/spring-security/site/docs/2.0.x/apidocs/org/springframework/security/ui/ExceptionTranslationFilter.html)

1. If we look at the source code, it is easy to see that for an incoming unauthenticated user, the `ExceptionTranslationFilter`'s `sendStartAuthentication(...)` method will preserve the original request.

	```
	SavedRequest savedRequest = new SavedRequest(httpRequest, portResolver);
	
	httpRequest.getSession().setAttribute(AbstractProcessingFilter.SPRING_SECURITY_SAVED_REQUEST_KEY, savedRequest);
	```
1. And a successful authentication, <a href="http://static.springsource.org/spring-security/site/docs/2.0.x/apidocs/org/springframework/security/ui/webapp/AuthenticationProcessingFilter.html" target="_blank">AuthenticationProcessingFilter</a> will leverage its parent <a href="http://static.springsource.org/spring-security/site/docs/2.0.x/apidocs/org/springframework/security/ui/AbstractProcessingFilter.html" target="_blank">AbstractProcessingFilter</a>'s determineTargetUrl(...) method to determine if it should load the saved target URL 
	```
	String targetUrl = alwaysUseDefaultTargetUrl ? null : targetUrlResolver.determineTargetUrl(getSavedRequest(request), request, SecurityContextHolder.getContext().getAuthentication());
	```
1. So the only question remaining is how to set the `alwaysUseDefaultTargetUrl` property? <u><i>This can be done:</i></u>
	1. Simply via the http tag		
	```
	<http ...>
        ...
        <form-login ...
         always-use-default-target='false' />
    </http>
	```
	1. Or via the bean if your configuration happens to be more involved

	```
	<bean id="authenticationProcessingFilter"
	      class="org.springframework.security.ui.webapp.AuthenticationProcessingFilter">
	    <property name="alwaysUseDefaultTargetUrl" value="false" />
    </bean>
	```

### Spring-Security 3.0.x

Spring Security 3.0.x offers this out-of-the-box as well, have a look at this class: [SavedRequestAwareAuthenticationSuccessHandler](http://static.springsource.org/spring-security/site/docs/3.0.x/apidocs/org/springframework/security/web/authentication/SavedRequestAwareAuthenticationSuccessHandler.html)

Here's how it works:
* ExceptionTranslationFilter will save the original URL in a RequestCache before the user is sent/redirected to the appropriate location for authentication to happen.
* When the user has successful authenticated ... the Filter which extends AbstractAuthenticationProcessingFilter will be able to leverage this parent's already existing successfulAuthentication() method.
* The method will further call upon SavedRequestAwareAuthenticationSuccessHandler's onAuthenticationSuccess() to pull out the original URL from the cache where the user should now be redirected for a happy ending.

Here are the odd mistakes that one might make that will cause this well-oiled mechanism to breakdown:

* You have a Filter that redirects the user somehow before ExceptionTranslationFilter ever gets the chance to store the original URL in the HttpSessionRequestCache.
* Your Filter, neither extends AbstractAuthenticationProcessingFilter ... nor does it call a AuthenticationSuccessHandler like SavedRequestAwareAuthenticationSuccessHandler for doing this work explicitly.

> Written with [StackEdit](https://stackedit.io/).

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NDI3MTAyMDJdfQ==
-->