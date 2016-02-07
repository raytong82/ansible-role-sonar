# Ansible Role: SonarQube

An Ansible Role that installs [SonarQube](http://www.sonarqube.org/) on RedHat/CentOS and Debian/Ubuntu Linux servers.

[![Build Status](https://travis-ci.org/raytong82/ansible-role-sonar.svg?branch=master)](https://travis-ci.org/raytong82/ansible-role-sonar)

## Requirements

Requires the `unzip` utility to be installed on the server. SonarQube 5.x+ requires Java 1.7+.

## Role Variables

Available variables are listed below, along with default values:

    workspace: /root

Directory where downloaded files will be temporarily stored.

    sonar_download_url: http://dist.sonar.codehaus.org/sonarqube-4.5.4.zip
    sonar_version_directory: sonarqube-4.5.4

The URL from which SonarQube will be downloaded, and the resulting directory name (should match the download archive, without the archive extension).

    sonar_jdbc_username: sonar
    sonar_jdbc_password: sonar
    
    sonar_jdbc_host: localhost
    sonar_jdbc_port: "3306"
    sonar_jdbc_database: sonar
    
    sonar_jdbc_allowed_hosts:
      - 127.0.0.1
      - ::1
      - localhost

JDBC settings for a connection to a jdbc database. Defaults presume the database resides on localhost and is only accessible on the SonarQube server itself.

## Example Playbook

    - hosts: all
      roles:
        - geerlingguy.sonar

## License

MIT / BSD

## Disclaimer

This project cloned from geerlingguy/ansible-role-sonar but included some refactoring to fit my own purposes, e.g.
- rename files from yml to yaml
- change from mysql to pgsql
- add sonar plugin install and upgrade

## Original Author Information

This role was created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
