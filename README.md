# Jobstats-DB

## Overview 
Provides scripts for building and populating a database for easy storage of Slurm job resource usage data.

## Installation

### Requirements
1. Python 3.5+ 
2. Slurm toolkit
3. MySQL/MariaDB
4. [jobstats](https://github.com/nauhpc/jobstats)

### Install
1. Clone and enter repository `git clone https://github.com/nauhpc/jobstats-db.git && cd jobstats-db`
2. Create database `jobstats`, with table `jobs`, or run `BuildDatabase`
3. Populate the database with pas slurm database with `FillDatabase <user> <pass> <host> <from> <to>`

## Daily Population of Database
Create a cron job to run `PopulateDatabase` daily, with today's date as `<from>`, and tomorrow's date as `<to>`

## Table Structure
| Field     | Type        | Null | Key | Default |
|-----------|-------------|------|-----|---------|
| username  | varchar(10) | NO   | PRI | NULL    |
| account   | varchar(20) | NO   | PRI | NULL    |
| date      | date        | NO   | PRI | NULL    |
| cores     | float       | YES  |     | NULL    |
| memory    | float       | YES  |     | NULL    |
| timelimit | float       | YES  |     | NULL    |
| total     | float       | YES  |     | NULL    |
| jobsum    | int(11)     | NO   |     | NULL    |

