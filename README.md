# DISS-CALM-ansible
Final year uni dissertation

Ansible playbooks to install and configure open source monitoring software

Uses an output file from Terraform to supply certain parameters

CI Pipeline would clone this repository to make playbooks available for a server config step

## About
Prometheus, Grafana, Logstash and Alertmanager are the primary playbooks which are ran directly e.g.:
```
ansible-playbook ansible/prometheus/install-prometheus.yaml
```
These playbooks import the other plays via import_playbook e.g.
```
import_playbook: ../nginx/install-nginx.yaml ip={{ prometheus_instance_ip }} port='9090' application='prometheus'
```

Prometheus/Alertmanager/Grafana login:
- username: CALMAdmin
- password: AdminPassword
