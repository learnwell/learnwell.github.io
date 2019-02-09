---

layout: page
title: Docker Quickies
permalink: /blogging/
last_modified_at: December 24, 2018
tags: [blog, blogs, blogging, tip, tips, trick, tricks]

---

* [Quickstart](https://blog.usejournal.com/docker-for-developers-mongodb-6d8ab16e6e4d) mongodb locally
    ```
    docker run -d -p 27017:27017 --mount type=bind,source=$PWD/data/bin,destination=/data/bin mongo
    ```


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbODg5NDU5MzMxLC01NzI0Nzc0NDBdfQ==
-->