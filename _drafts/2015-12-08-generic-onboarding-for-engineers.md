---

layout: post
title: Generic Onboading for Software Engineers
author: pulkit
tags: [onboard,FTE,new hire]

---

Pefecting newhire onboarding is essential for companies of any size. The template offered here provides a starting point for onboarding software engineers. You should hack on it and adjust it to fit the needs of your business.

### Accounts worth having/setting-up

1. Create new accounts at following websites, and download desktop and/or mobile apps (*recommended*):
	1. gDrive
		1. [ ] Get a company email account
		2. [ ] Search through all the technical goodness (knowledgebase)
		3. [ ] Use it for storage and for notes sharing
	2. Gitlab
		1. [ ] Use company email account and get access
	3. Github
		1. [ ] Create your own account
		2. [ ] Get access to company repos
	4. Lastpass or 1Pass
store all passwords using lastpass chrome extension
do not save passwords using native google chrome feature (insecure)
Slack
create account, download desktop and mobile apps
connect to team Shoppinpal
Skype
add team members as contacts
HubStaff
join using company email
Sourcetree
Clone your bitbucket repo in sourcetree desktop app
Flycut
for Mac users

Provision Access:
Added Kamal to the ShoppinPal organization’s team on GitHub.com: https://github.com/orgs/ShoppinPal/teams/developers

Dev environment setup:

Technology Stack Rampup:
Finish a course about using chrome dev tools, its completely free: https://www.codeschool.com/courses/discover-devtools, use your shoppinpal email account to signup/login.
GIT course from codeschool are optional:
[OPTIONAL] https://www.codeschool.com/paths/git
[REQUIRED] it is important to understanding the process in this article: 	http://nvie.com/posts/a-successful-git-branching-model/ … memorizing the commands is not important because those are part of the UI in SourceTree already as clickable buttons
An interesting idea: http://blog.rubydubee.com/git/2015/03/01/new-git-flow/
Goto: https://www.codeschool.com/paths/javascript, and finish the following tracks in given order. If at any time it asks for a paid account, let Pulkit know and he’ll assign you a license from the team membership. use your shoppinpal email account to signup/login.
JavaScript Language - all
Server-side Frameworks - all
Client-side Frameworks - only the following:
Shaping up with Angular.js
Staying Sharp with Angular.js
Promises as a concept
https://blog.risingstack.com/asynchronous-javascript
http://zpalexander.com/blog/javascript-promises-node-js/
https://spring.io/understanding/javascript-promises
http://alexperry.io/node/2015/03/25/promises-in-node.html
http://www.mattgreer.org/articles/promises-in-wicked-detail/
https://spion.github.io/posts/why-i-am-switching-to-promises.html
http://www.html5rocks.com/en/tutorials/es6/promises
MongoDb University course on mogno administration and also mongodb for nodejs: https://university.mongodb.com/?next=/courses/MongoDB/M101JS
Become familiar with https://training.shoppinpal.com/the-perfect-machine.html
Everything under “The Perfect Machine”
Setup a machine in the cloud
Make sure to “Setup box on Azure”
Make sure to Setup Dropbox on Azure“”
You can ignore everything under “Setup a machine in the cloud”
Familiarize yourself with “Long Running Sessions”
CodeSchool or PluralSight
Let us know if you want to use them and we’ll purchase a subscription if needed
LoopBack (software) by StrongLoop (company)
codio.com is a learning / teaching platform
it works in a browser by presenting a step-by-step guide on the left and the file editor and terminal on right
after you sign up for free on codio, go search in the ALL tab of modules under Courses sidebar menu
and look for “loopback” … it is the only course they have on loopback so should be easy to spot:

finish that course as an introduction to loopback and ask any questions if you have at these public support channels:
https://gitter.im/strongloop/loopback
https://groups.google.com/forum/#!forum/loopbackjs
Get used to IronWorker via a simple example: http://dev.iron.io/worker/getting_started/
Grunt / Gulp / Yeoman
Continuous Integration ( CI )
CodeShip
a lot is automated and it is their convenient workflows and integrations with IaaS and PaaS that stand out
but it is a pain if not impossible to do something that they haven’t provided a workflow for already like:
protractor end-2-end tests for AngularJS
building docker images - no support - true in 2015 Q3, wonder if anything has changed since?
deploying to GCP - true in 2015 Q3, wonder if anything has changed since?
what workarounds have we been able to do?
was able to add gcloud CLI
Jenkins
can do it all but a lot of trial and error and very manual
CircleCI
keep hearing good things about it constantly
it has IaaS and PaaS CLIs preinstalled, like gcloud
https://circleci.com/docs/environment#integration-tools
it has build numbers available as env variables, like CIRCLE_BUILD_NUM
https://circleci.com/docs/environment#env-vars
it has support for headless browser components used in for end-2-end tests ... built into it
phantomJs override: https://circleci.com/docs/configuration#machine
You can start a container running in detached mode with an exposed port serving your app. You can then run browser tests or other black box tests against the container
it has docker + GCP deployment available and more:
docker + GCP
https://circleci.com/docs/docker#google-compute-engine-and-kubernetes
https://github.com/circleci/docker-hello-google
docker + aws
https://circleci.com/docs/docker#aws-elastic-beanstalk
https://github.com/circleci/docker-hello
non-docker aws
https://circleci.com/docs/continuous-deployment-with-aws-codedeploy
Despite the default docker version in their machines being at 1.8, we have the option of moving up to 1.9 and beyond
https://discuss.circleci.com/t/docker-1-9-1-is-available/1009
https://discuss.circleci.com/t/docker-1-10-0-is-available-beta/2100
what are some shortcomings?
cannot segregate which sensitive env variables can be seen by which members of the team 
IaaS: GCP/GCE
Reference Articles:
NodeJS
http://blog.codeship.com/understanding-garbage-collection-in-node-js/
Dropbox account has 4 years worth of tech knowledge sharing videos but they aren’t very organized … there must be some really useful stuff in there for you to learn from.
Docker
First & foremost - you must understand the concept and difference between a docker container and a docker image
Then read up on articles that describe why docker is horrible, this will help you understand that it is not a “silver bullet” you will still struggle! So, you’ve got to be mentally prepared for that or choose a different solution. Here are some articles:
http://iops.io/blog/docker-hype/
Start getting hands-on:
https://docs.docker.com/mac/
https://serversforhackers.com/getting-started-with-docker
Understand what are some simple shortcomings of docker that other projects try to solve … even if you ultimately choose not to address those issue or use those projects:
http://phusion.github.io/baseimage-docker/#intro
Looking for a more complete base image, one that is ideal for Node.js web apps? Take a look at passenger-docker.
phusion/passenger-nodejs - Node.js 0.11
https://github.com/phusion/passenger-docker
Understand some of the basic gotchas:
Why does docker stop? Why won’t it keep running after I start my server via CMD in dockerfile in a detached state?
http://kimh.github.io/blog/en/docker/gotchas-in-writing-dockerfile-en/#hack_to_run_container_in_the_background
port mappings on a mac host will require extra work
http://webiphany.com/technology/2014/06/12/what-ip-do-i-access-when-using-docker-and-boot2docker.html
http://stackoverflow.com/questions/29808651/expose-docker-containers-application-port-to-host-on-windows-using-boot2docker
 docker-machine ls | awk '{print $5}' 
Understand the very basic optimization tricks
like cleaning APT and why it helps
https://intercityup.com/blog/downsizing-docker-containers.html
lots of tips:
http://jasonwilder.com/blog/2014/08/19/squashing-docker-images/
Find some useful reference sites
https://github.com/wsargent/docker-cheat-sheet
Docker labs: https://github.com/docker/labs
https://www.codeschool.com/courses/try-docker
https://training.shoppinpal.com/docker/docker-swarm.html
https://training.play-with-docker.com/
...



> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM4NTExNTc4NiwyOTM5MDE3MjZdfQ==
-->