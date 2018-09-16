# Ansible Role: ebpf exporter

[![Build Status](https://travis-ci.org/cloudalchemy/ansible-ebpf-exporter.svg?branch=master)](https://travis-ci.org/cloudalchemy/ansible-ebpf-exporter)
[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)
[![Ansible Role](https://img.shields.io/badge/ansible%20role-cloudalchemy.ebpf_exporter-blue.svg)](https://galaxy.ansible.com/cloudalchemy/ebpf-exporter/)
[![GitHub tag](https://img.shields.io/github/tag/cloudalchemy/ansible-ebpf-exporter.svg)](https://github.com/cloudalchemy/ansible-ebpf-exporter/tags)
[![IRC](https://img.shields.io/badge/irc.freeenode.net-%23cloudalchemy-yellow.svg)](https://kiwiirc.com/nextclient/#ircs://irc.freeenode.net/#cloudalchemy)

## DISCLAIMER

:construction: THIS REPOSITORY IS A WORK IN PROGRESS :construction:

## Description

Deploy cloudflare [ebpf exporter](https://github.com/cloudflare/ebpf_exporter) using ansible. More about eBPF: 
  - http://www.brendangregg.com/ebpf.html
  - https://www.iovisor.org/technology/ebpf

## Configuration

Due to nature of eBPF, configuration of this exporter might be tricky. To simplify this, cloudflare pubished some [examples in ebpf_exporter repository](https://github.com/cloudflare/ebpf_exporter/tree/master/examples)

## Requirements

- Ansible >= 2.4
- kernel >= 4.1
- go-lang on deployer machine
- libbcc on deployer machine

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `ebpf_exporter_web_listen_address` | "0.0.0.0:9100" | Address on which ebpf exporter will listen |

## Example

### Playbook

Use it in a playbook as follows:
```yaml
- hosts: all
  roles:
    - cloudalchemy.ebpf-exporter
```

### Demo site

We provide demo site for full monitoring solution based on prometheus and grafana. Repository with code and links to running instances is [available on github](https://github.com/cloudalchemy/demo-site) and site is hosted on [DigitalOcean](https://digitalocean.com).

## Local Testing

TODO

## CI

### SemaphoreCI

TODO

### TravisCI

Travis is used only on master branch to populate changelog and create new releases.

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
