# Attendance

Attendance is a microservice which is designed in Golang to manage employee's attendance information.

## Database

- [MySQL](../mysql) => Attendance application store information in MySQL database

## Environment Variable

|**ENVIRONMENT VARIABLE**|**DESCRIPTION**|
|------------------------|---------------|
| CONFIG_FILE | Path of configuration file |

## Endpoints

The available endpoints for this application are:-

|**ENDPOINT**|**REQUEST TYPE**|**DESCRIPTION**|
|------------|----------------|---------------|
| `/attendance/healthz` | GET | healthz endpoint checks the DB connectivity and tells that application is ready to serve the requests or not. |

## Quickstart

```yaml
# Application port on which application will listen
attendance:
  api_port: "8081"

# Mysql connection details
mysql:
  enabled: true
  db_name: "attendancedb"
  host: "mysql:3306"
  username: root
  password: password
```

## Run application Docker

- Install docker on your machine

- For building docker image
```shell
make build-image
```

- For running docker container with image build with above code and running on port 80
```shell
docker run -d -p 80:8081 opstree/empms-attendance:1.0
```

## Run application locally

- Setup/Install Go on your machine

```shell
# For compiling code
make build
```

```shell
# For running code locally
export CONFIG_FILE=/path/to/config.yaml
./attendance
```
