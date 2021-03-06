# Apache Airflow

## Installation

### PIP
```
$ pip install apache-airflow
```
or
```
$ pip install apache-airflow[postgres,s3]
```

### Docker
```
$ docker pull apache/airflow
```

## Quick Start
```
# airflow needs a home, ~/airflow is the default,
# but you can lay foundation somewhere else if you prefer
# (optional)
export AIRFLOW_HOME=~/airflow

# install from pypi using pip
pip install apache-airflow

# initialize the database
airflow initdb

# start the web server, default port is 8080
airflow webserver -p 8080

# start the scheduler
airflow scheduler

# visit localhost:8080 in the browser and enable the example dag in the home page
```

* http://www.marknagelberg.com/getting-started-with-airflow-using-docker/
