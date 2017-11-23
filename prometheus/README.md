## Container monitoring

The `docker-compose.yml` file will spin up a [Grafana](https://grafana.com/) dashboard powered by [Prometheus](https://prometheus.io/). It uses [Cadvisor](https://github.com/google/cadvisor) to monitor the container metrics. You can also set up alerting using the included [Alert Manager](https://prometheus.io/docs/alerting/alertmanager/) container. 

## Set up Grafana admin password
Edit the `config.monitoring` file with the password you'd like to use to access the Grafana dashboard with the admin user.

## Deploy containers

`docker-compose up -d`