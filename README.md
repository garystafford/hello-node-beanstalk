# Hello World Node/Beanstalk

Very simple Node.js/AWS Elastic Beanstalk application.

Objective is to create one app, `hello-node`, and two environments, `hello-node-v1` and `hello-node-v2`, using Elastic Beanstalk CLI (`eb`).

Also, project create an AWS SQS Queue, with alarms, as a demo of `.ebextensions` capabilities.

```bash
eb --help
eb init hello-node
eb create hello-node-v1
eb deploy hello-node-v1
eb open hello-node-v1

eb create hello-node-v2
eb deploy hello-node-v2

eb scale 2 hello-node-v1
eb scale 2 hello-node-v2

# source/destination
eb swap hello-node-v2 -n hello-node-v1

eb config save hello-node-v1 --cfg hello-node-v1-sc

eb terminate hello-node-v1 --force --verbose
eb terminate hello-node-v2 --force --verbose
```
