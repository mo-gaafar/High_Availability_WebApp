# High_Availability_WebApp

This is infrastructure as code for a high availability webapp. Built for Amazon Web Services (AWS).

This is a project for AWS Cloud DevOps Advanced Nanodegree by [EGFWD](https://www.egfwd.com/) and [Udacity](https://www.udacity.com/).

## 🔗 [Demo Server](http://serve-elast-6cerb1up6v7o-1489959176.us-east-1.elb.amazonaws.com/)

![Status Badge](https://img.shields.io/website?style=flat-square&up_message=online&url=http%3A%2F%2Fserve-elast-6cerb1up6v7o-1489959176.us-east-1.elb.amazonaws.com%2F)

## Diagram

![infra diagram](./diagrampreview.png)

[Visio Drawing Download](https://github.com/mo-gaafar/High_Availability_WebApp/blob/main/drawings/diagram.vsdx)

## Requirements

- Amazon Web Services Account
- AWS CLI

## Running the stack

### Step 1: Set up the parameters

Set up the server-parameters.json and network-parameters.json files. according to your own needs.. make sure the environment name is the same in both files

### Step 2: Create the network stack

```bash
aws cloudformation update-stack  --stack-name serverProject  --region us-east-1 --template-body file://network.yml --parameters file://network-parameters.json --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM"
```

### Step 3: Create the server stack

```bash
aws cloudformation update-stack  --stack-name serverProject  --region us-east-1 --template-body file://servers.yml --parameters file://server-parameters.json --capabilities "CAPABILITY_IAM" "CAPABILITY_NAMED_IAM"
```

## Useful Links

[AWS Resource and property reference](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
