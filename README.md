# Monitoring Automation with Ansible

## Overview
This repository contains Ansible playbooks and roles for automating the deployment of monitoring services, including:

- **Node Exporter** (for system metrics collection)
- **Prometheus** (for time-series data storage and monitoring)
- **Grafana** (for visualization and dashboards)

## Prerequisites
- Ansible installed on your control machine
- SSH access to target servers with root privileges
- Python installed on remote hosts

## Inventory Configuration
Define your target servers in an Ansible inventory file (e.g., `inventory.ini`):

```ini
[all]
192.168.1.10
192.168.1.11

[monitoring]
192.168.1.20
```

## How to Use

### 1. Clone the Repository
```sh
git clone https://github.com/ExStp/ansible-monitoring-grafana/tree/master
cd ansible-monitoring
```

### 2. Run the Playbook
To deploy monitoring services, execute:
```sh
ansible-playbook -i inventory.ini monitoring.yaml
```

To uninstall, modify `action` in `monitoring.yaml` or pass it as an extra variable:


## Roles Structure
```
roles/
  node_exporter/
    tasks/
      main.yml
  prometheus/
    tasks/
      main.yml
  grafana/
    tasks/
      main.yml
```

## Additional Notes
- Ensure firewall rules allow default necessary ports:
  - Prometheus: `9090`
  - Grafana: `3000`
  - Node Exporter: `9100`
- Customize configurations in `roles/*/defaults/main.yml`

## License
MIT

## Author
Ryabov Andrey
