# Datadog SQL Metrics
Export SQL query data as Datadog metrics.


## Installing

```console
$ helm upgrade --install datadog-sql-metrics $PWD
```

## Setup
Configure `database` paramter for your DB server. See `values.yaml` for examples.

### References
- [PostgreSQL](https://github.com/DataDog/integrations-core/blob/master/postgres/datadog_checks/postgres/data/conf.yaml.example)
- [MySQL](https://github.com/DataDog/integrations-core/blob/master/mysql/datadog_checks/mysql/data/conf.yaml.example)
- [SQL Server](https://github.com/DataDog/integrations-core/blob/master/sqlserver/datadog_checks/sqlserver/data/conf.yaml.example)


## Configuration

The following table lists has the configurable parameters.

| Parameter                             | Description                                      | Default                            |
| ------------------------------------- | ------------------------------------------------ | ---------------------------------- |
| `affinity`                            | Affinity                                         | `{}`                               |
| `cloudsqlproxy.enabled`               | Enable GCP Cloud SQL Auth proxy container        | `false`                            |
| `cloudsqlproxy.image.repository`      | Cloud SQL proxy image repository                 | `gcr.io/cloudsql-docker/gce-proxy` |
| `cloudsqlproxy.image.tag`             | Cloud SQL proxy image tag                        | `1.32.0`                           |
| `cloudsqlproxy.instance`              | Cloud SQL instance string                        | `project:region:database=tcp:5432` |
| `cloudsqlproxy.resources`             | Cloud SQL resources                              | `{}`                               |
| `cloudsqlproxy.serviceAcccountSecret` | Secret containing SA key                         | `''`                               |
| `datadog.apiKey`                      | Datadog API key                                  | `''`                               |
| `datadog.apiSecret`                   | Secret containing Datadog API key                | `''`                               |
| `datadog.logLevel`                    | Datadog log level                                | `INFO`                             |
| `database.config`                     | Database specific configuration                  | `{}`                               |
| `database.password`                   | Database password                                | `''`                               |
| `database.passwordSecret`             | Secret containing database password              | `''`                               |
| `database.type`                       | Database type (`mysql`, `postgres`, `sqlserver`) | `postgres`                         |
| `database.username`                   | Database username                                | `dbuser`                           |
| `image.pullPolicy`                    | Image pull policy                                | `IfNotPresent`                     |
| `image.repository`                    | Datadog image repository                         | `gcr.io/datadoghq/agent`           |
| `image.tag`                           | Image tag                                        | `7.39.0`                           |
| `imagePullSecrets`                    | Secret to pull from private registry             | `[]`                               |
| `podAnnotations`                      | Annotations to add to  pods                      | `{}`                               |
| `podSecurityContext`                  | Pod security context                             | `{}`                               |
| `resources`                           | Container resources                              | `{}`                               |
| `serviceAccount.annotations`          | Annotations to add to Kubernetes SA              | `{}`                               |
| `serviceAccount.create`               | Create Kubernetes SA                             | `true`                             |
| `serviceAccount.name`                 | Name to use for SA                               | `''`                               |
| `securityContext`                     | Container security context                       | `{}`                               |
| `service.port`                        | Service port                                     | `5555`                             |
| `service.type`                        | Service type                                     | `ClusterIP`                        |
| `nodeSelector`                        | Node selector                                    | `{}`                               |
| `tolerations`                         | Tolerations                                      | `{}`                               |

