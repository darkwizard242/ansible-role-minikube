[![build-test](https://github.com/darkwizard242/ansible-role-minikube/workflows/build-and-test/badge.svg?branch=master)](https://github.com/darkwizard242/ansible-role-minikube/actions?query=workflow%3Abuild-and-test) [![release](https://github.com/darkwizard242/ansible-role-minikube/workflows/release/badge.svg)](https://github.com/darkwizard242/ansible-role-minikube/actions?query=workflow%3Arelease) ![Ansible Role](https://img.shields.io/ansible/role/d/darkwizard242/minikube) [![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-minikube&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=ansible-role-minikube) [![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-minikube&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=ansible-role-minikube) [![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-minikube&metric=security_rating)](https://sonarcloud.io/dashboard?id=ansible-role-minikube) ![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/darkwizard242/ansible-role-minikube?label=release) ![GitHub repo size](https://img.shields.io/github/repo-size/darkwizard242/ansible-role-minikube?color=orange&style=flat-square)

# Ansible Role: minikube

Role to install (_by default_) `minikube` on **Debian/Ubuntu** and **EL** systems. [minikube](https://minikube.sigs.k8s.io/) is a tool for running local Kubernetes Cluster.

## Requirements

None.

## Role Variables

Available variables are listed below (located in `defaults/main.yml`):

### Variables list:

```yaml
minikube_app: minikube
minikube_version: 1.33.1
minikube_os: linux
minikube_arch: amd64
minikube_dl_url: https://github.com/kubernetes/{{ minikube_app }}/releases/download/v{{ minikube_version }}/{{ minikube_app }}-{{ minikube_os }}-{{ minikube_arch }}
minikube_bin_path: "/usr/local/bin"
minikube_file_owner: root
minikube_file_group: root
minikube_file_mode: '0755'
```

### Variables table:

Variable            | Description
------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------
minikube_app        | Defines the app to install i.e. **minikube**
minikube_version    | Defined to dynamically fetch the desired version to install. Defaults to: **1.33.1**
minikube_os         | Defines os type. Defaults to: **linux**
minikube_arch       | Defines os architecture. Defaults to: **amd64**
minikube_dl_url     | Defines URL to download the minikube binary from.
minikube_bin_path   | Defined to dynamically set the appropriate path to store minikube binary into. Defaults to (as generally available on any user's PATH): **/usr/local/bin**
minikube_file_owner | Owner for the binary file of minikube.
minikube_file_group | Group for the binary file of minikube.
minikube_file_mode  | Mode for the binary file of minikube.

## Dependencies

None

## Example Playbook

For default behaviour of role (i.e. installation of **minikube**) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.minikube
```

For customizing behavior of role (i.e. specifying the desired **minikube** version) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.minikube
  vars:
    minikube_version: 1.23.0
```

For customizing behavior of role (i.e. placing binary of **minikube** package in different location) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.minikube
  vars:
    minikube_bin_path: /bin/
```

## License

[MIT](https://github.com/darkwizard242/ansible-role-minikube/blob/master/LICENSE)

## Author Information

This role was created by [Ali Muhammad](https://www.alimuhammad.dev/).
