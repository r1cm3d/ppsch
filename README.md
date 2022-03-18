# ppsch 

[![Twitter Follow](https://img.shields.io/twitter/follow/r1cm3d?style=social)](https://twitter.com/RMedeirosCosta)

**TL;DR:**
```console
./ppsch --table 'MY_DYNAMO_DB_TABLE' --days 10
```

## Prerequisites
[![aws-cli](https://img.shields.io/badge/aws--cli-2.4.26-yellow)](https://github.com/aws/aws-cli)
[![jq](https://github.com/stedolan/jq)](https://github.com/stedolan/jq)

## Table of Contents
* [TL;DR](#ppsch)
* [Prerequisites](#prerequisites)
* [About](#about-the-project)
* [Getting Help](#getting-help)

## About

This is script receives a file (stdin or by argument) and increases TTL attribute given an argument.

## Getting Help

```console
./ppsch --help
```

Help information will be displayed:

```console
ch: command-line interface to postpone authorizations scheduler
Usage:
      ppsch [ options ]
Options: 
       [ -v | --verbose ]: Run in verbose mode.
       [ -r | --region  ]: AWS region. Default is sa-east-1.
       [ -t | --table   ]: DynamoDB table. Default is Scheduler.
       [ -h | --help    ]: Displays help information for ppsch.
       [ -d | --days    ]: How many days to increase scheduler routine. When not specified, DEFAULT_DAYS will be used.
       [ -f | --file    ]: File path containing authorizations CIDs. Otherwise, stdin will be read.
Example:
      Read from stdin in verbose mode increasing scheduler to DEFAULT_DAYS:
      cat myFile | ppsch -v

      Read file '/tmp/cids' increasing ten days:
      ppsch -f '/tmp/cids' -d 10

      Read file '/tmp/cids' decreasing five days:
      ppsch -f '/tmp/cids' -d -5 
```
