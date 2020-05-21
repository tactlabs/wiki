# Micro Brainstorming

**Note:** Do it quick but do it right!
### BRAINSTORMING IDEAS
-	Brainstorming combines a relaxed, informal approach to problem solving with lateral thinking.  
-	People should avoid criticizing or rewarding ideas. 
-	Brainstorming provides a free and open environment that encourages everyone to participate.
-	Groups of five to seven people are usually most effective.
-	Set up a comfortable environment for the session.
-	Clearly define the problem that you want to solve, and lay out any criteria that you must meet. 
-	Give people plenty of quiet time at the start of the session to write down as many of their own ideas as they can. 
-	If the brainstorming session is lengthy, take plenty of breaks so that people can continue to concentrate.



### Session : 1

**Date**: May 07, 2020 - Wednesday

**Title**: Dask Parallel Data Processing

**Participants**: Raja CSP, Suresh

#### Dask parallel data processing:
- Dynamic task scheduing
- Similar to Luigi
- Parallel with Numpy
- Parallel collections: Dataframes, Bags, Arrays
- Distributed tensorflow support - [Dask Tensorflow support](http://matthewrocklin.com/blog/work/2017/02/11/dask-tensorflow)
- Data loading support for Pytorch by using Worker
- Scaling - [Dask docs](https://docs.dask.org/en/latest/)


#### Ray Hyperparameter Tuning:
- Ray Docs - [Ray Docs](https://docs.dask.org/en/latest/)
- Ray Tuning - [Ray Tuning](https://docs.ray.io/en/latest/tune.html)




### Session : 2

**Date**: May 09, 2020 - Saturday

**Title**: ECS vs Lambda

**Participants**: Raja CSP, Suresh

**Summary**:
**ECS**:
- Relies on docker containers to run your application & Persistent
- Runs all time, so there is no warmup time
- ECS Tasks can also be configured to run on a schedule or as the result of CloudWatch events. This allows you to use ECS Tasks for jobs that do not require a persistent docker container,
- Fargate is billed on CPU and memory used per hour.
"Fargate is a good choice for consistent workloads or applications that want to use docker generally."

**Lambda**:
- Runs based on requested/invoked via
- No container support
  - There is warmup time required to boot
  - Limited to the runtimes and versions currently supported by Lambda
- Lambda is billed on a combination of the number of requests, memory, and seconds of function execution
"Good use cases for Lambda include unpredictable or inconsistent workloads and applications that can be easily expressed as a single function with predictable resource usage on each invocation.

Ref Links :

  * [Lambda vs Fargate](https://www.bluematador.com/blog/serverless-in-aws-lambda-vs-fargate)



### Session : 3

**Date**: May 18, 2020 - Monday

**Title**: Docker Compose and Remote DB

**Participants**: Raja CSP, Suresh, & Murali

**Summary**:
**Docker Compose vs Kubernetes**:
***Docker Compose***:
- Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services from your configuration.
- Compose has commands for managing the whole lifecycle of your application:
  - Start, stop, and rebuild services
  - View the status of running services
  - Stream the log output of running services
  - Run a one-off command on a service

***Kubernetes***:
- Kubernetes is a container orchestrator like Docker Swarm, Mesos Marathon, Amazon ECS, Hashicorp Nomad. Container orchestrators are the tools which group hosts together to form a cluster, and help us make sure applications:
  - are fault-tolerant,
  - can scale, and do this on-demand
  - use resources optimally
  - can discover other applications automatically, and communicate with each other
  - are accessible from the external world
  - can update/rollback without any downtime.


**Docker Compose vs Docker Swarm**:
***Similarities***:
- Both Docker Swarm and Docker-Compose have the following similarities:
  - They both take YAML formatted definitions of your application stack.
  - They are both meant to deal with multi-container applications (microservices)
  - They both have a scale parameter that allows you to run multiple containers of the same image allowing your microservice to scale horizontally.
  - They are both maintained by the same company, i.e, Docker, Inc.

***Differences***:
- The few differences between Docker Swarm and Docker-Compose:
  - Docker Swarm is used to scale your web app across one or more servers. Where as Docker-compose will simply run your web app on a single Docker host.
  - Scaling your web app Docker Swarm offers serious high availability and fault tolerance. Scaling your web app using Docker-Compose on a single host is useful only for testing and development.
  - Docker Swarm and related subcommands like Docker Swarm and Docker Stack are built into the Docker CLI itself. They are all part of the Docker binary that you call via your terminal.
  - Docker-Compose is standalone binary in and of itself.

**Kubernetes Small History**:
- The original codename for Kubernetes within Google was Project Seven of Nine, a reference to a Star Trek character of the same name that is a "friendlier" Borg.


**Remote RDS**:
- brainstorming on Docker-compose vs Kubernetes
- added inbound rule in RDS to connect from remote terminal/client
- Connected RDS db via tableplus and local terminal
- created test db and tested new db/tables via terminal


Ref Links :

  * [History of Kubernetes](https://blog.risingstack.com/the-history-of-kubernetes/)
  * [Landscape](https://landscape.cncf.io/)
  * [Docker compose ](https://linuxhint.com/docker_compose_vs_docker_swarm/)
  * [Introduction to Kubernetes](https://www.edx.org/course/introduction-to-kubernetes)
  * [What is the difference between Docker complse and Kubernetes](https://stackoverflow.com/questions/47536536/whats-the-difference-between-docker-compose-and-kubernetes)
  * [Docker Compose vs Mesos](https://stackshare.io/stackups/docker-compose-vs-mesos)
  * [Docker Swarm Kubernetes Apache Mesos](https://www.bogotobogo.com/DevOps/DevOps-Docker-Swarm-vs-Kubernetes-vs-Apache-Mesos.php)
