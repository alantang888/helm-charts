# Grafana Dashboard Backup to Git

## Config values
| Key                               | Default                                      | Description                                                                                         |
|-----------------------------------|----------------------------------------------|-----------------------------------------------------------------------------------------------------|
| image.repo                        | alantang888/grafana-dashboard-backup         | Docker image repo                                                                                   |
| image.pullPolicy                  | IfNotPresent                                 | K8S image pull policy                                                                               |
| schedule                          | "0 0 * * *"                                  | Schedule for this cronjob run                                                                       |
| config.grafana.url                | https://grafana.yourdomain.com               | Grafana URL. You should override this                                                               |
| config.grafana.apiTokenSecretName | grafana-dashboard-backup                     | Secret name, which contain Grafana API token                                                        |
| config.grafana.apiTokenSecretKey  | grafana-token                                | Secret key, which contain Grafana API token on `config.grafana.apiTokenSecretName` secret           |
| git.url                           | https://yourdomain.com/grafana_dashboard.git | Git URL. Current only support HTTP. Not SSH (Just lazy to set SSH keys...)                          |
| git.username                      | yourgituser                                  | Git basic HTTP auth username                                                                        |
| git.passwdSecretName              | grafana-dashboard-backup                     | Secret name, which contain Git basic HTTP auth password                                             |
| git.passwdTokenSecretKey          | git-passwd                                   | Secret key, which contain Git basic HTTP auth password on `git.passwdSecretName` secret             |
| git.dirPrefix                     | ""                                           | Directory prefix on git repo. If set, this create create a directory between Git repo root and uid. |
