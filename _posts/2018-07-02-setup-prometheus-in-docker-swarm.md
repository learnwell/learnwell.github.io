---

layout: postMod1
title: Setup Prometheus with Docker Swarm
author: pulkit
last_modified_at: July 02, 2018
tags: [docker,swarm,prometheus,grafana]

---

Install Prometheus, grafana and exporters.

Benefit - no need to install exporters separately on each node when scaling up.
In docker-compose config we can put a global mode 
Two modes: **replicated** and **global**
Using swarm’s dns configuration, it is much easier to scrape the metrics

Didn’t want to do this because the recommendation is to put `pro+gra` stack outside the swarm cluster … unfortunately it made the app swarm cluster unstable. The swarm manager the CPU load went very high and stopped the docker engine
Next time tried to assign another node for that stack and isntall it there but it also failed because it too started crashing and the overall cluster became unstable as well

Then the manual approach, on another manager node, installed the exporters on each node which meant logging in to each manager via ssh and using the `CLI` to ask the exporters to come up. Previously the global mode of swarm brought them up on its own.

`docker-compose` only gives a warning when operating of the superset that is a stack file, it doesn’t fail outright.

> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbODY4NTE3NTQ4LDExMjUxNDM5NDBdfQ==
-->