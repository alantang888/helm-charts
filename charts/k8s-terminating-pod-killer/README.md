# K8S Terminating Pod Killer

Some rare case. Pod can stucking in terminating status.
Even over `terminationGracePeriodSeconds` those pod still can stucking here.
This app is for kill that kind of pod.

## Config values
| Key                         | Default                                | Description                                                                                          |
|-----------------------------|----------------------------------------|------------------------------------------------------------------------------------------------------|
| image.repo                  | alantang888/k8s-terminating-pod-killer | Docker image repo                                                                                    |
| image.pullPolicy            | IfNotPresent                           | K8S image pull policy                                                                                |
| schedule                    | "*/15 * * * *"                         | Schedule for this cronjob run                                                                        |
| targetNamespace             | default                                | Which namespace this app need to check and kill pod. Seperate by ','. `""` will check all namespaces |
| killMinute                  | 15                                     | How long time in minute after `terminationGracePeriodSeconds` should kill that pod                   |
| rbac.create                 | true                                   | Create server account, cluster role and cluster role binding                                         |
| rbac.serviceAccountOverride | default                                | Use this service account for cronjob. Only use when `rbac.create` is `false                          |
