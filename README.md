# Ingest Streaming Data into AWS using Kinesis Firehose

*Created by: Luca De Francesco*

## Introduction

This project consists of a step-by-step tutorial showing how to ingest streaming data in near real-time into AWS using Kinesis Firehose through Boto3 (AWS SDK for Python).


## Scenario

A climate sensor measures temperature-related data which are returned via a JSON API response. In order to process this data in near real-time, each measurement record should be ingested and stored in S3  for further processing. This can be achieved by a Kinesis Firehose delivery stream.

In order to make the steps more easily replicable and automatized, all the steps will be executed using AWS SDK for Python, called Boto3; this provides APIs allowing to control the AWS environment using Python.

The project can be easily replicated by the user, provided the following prerequisited are satisfied:
- The user has an AWS account and owns AWS credentials for programmatic access (AWS Access Key Id and AWS Secret Access Key).
- The user has Python and Boto3 installed on his own machine or on a virtual machine.


## Solution description

The solution is composed of the following steps:
- Create a configuration file where credentials and other parameters are stored
- Create an S3 bucket where the streaming data will be stored
- Create an Identity Access Management (IAM) role to allow Kinesis Firehose to write to S3
- Create a policy granting write permission into the S3 bucket created above
- Attach the policy to the IAM role
- Create a Firehose delivery stream
- Test the Firehose delivery stream.

### Requirements
- An AWS account should be set-up
- A AWS user with Admin permission (if not set up yet please refer here) should have been created and a set of credentials (Access Key ID and Secret Access Key) should be available
- Python and Boto3 (AWS SDK for Python) should be installed on the user's machine.

All the user-defined parameters will be read from a .cfg file named \texttt{dl.cfg}.

## Content of the Github Repository

This repository contains the following files:
- pipeline.ipynb: this Jupyter notebook proposes and execute the pipeline according; Python packages are loaded when they are needed (so that the user can easily understand for which scope they are used) and each code snippet is well-described with text cells
- main.py: this Python file is structured according to logical subroutines (one subroutine for each step of the pipeline)
- dl.cfg: contains all the parameters needed for the execution of the code (access_key_id and secret_access_key are intentionally obfuscated as they should never be exposed)

A post describing this project has been published on Medium. This can be found at: https://medium.com/@lucadefra92/ingesting-streaming-data-into-aws-using-kinesis-firehose-c160e077b541.
