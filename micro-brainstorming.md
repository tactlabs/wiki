# Micro Brainstorming

**Note:** Do it quick but do it right!


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