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
2. Create `config.ini` and fill in the corresponding values
3. Create database `jobstats`, with table `jobs`, or run `BuildDatabase`
4. Populate the database with pas slurm database with `FillDatabase`

## Table Structure
| Field     | Type        | Null | Key | Default | Extra |
|-----------|-------------|------|-----|---------|-------|
| username  | varchar(10) | NO   | PRI | NULL    |       |
| account   | varchar(20) | NO   | PRI | NULL    |       |
| date      | date        | NO   | PRI | NULL    |       |
| idealcpu  | float       | YES  |     | NULL    |       |
| memoryreq | int(11)     | YES  |     | NULL    |       |
| tlimitreq | int(11)     | YES  |     | NULL    |       |
| cputime   | float       | YES  |     | NULL    |       |
| tlimituse | int(11)     | YES  |     | NULL    |       |
| memoryuse | int(11)     | YES  |     | NULL    |       |
| jobsum    | int(11)     | NO   |     | NULL    |       |
