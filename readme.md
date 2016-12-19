# ansible_beats5_centos
This is playbook to install beats5 on CentOS6/7 servers.
I made this playbook in reference to the contents of the following official sites.
- https://www.elastic.co/guide/en/beats/libbeat/5.0/setup-repositories.html
- https://www.elastic.co/guide/en/beats/libbeat/5.0/getting-started.html

## Preparing for Step
### Elastisearch and Kibana
You must prepare for the environment of Elastisearch and Kibana.
For example, 
You can build environment in the following on Docker 
if you are the environment where you use docker-compose.

```
git clone https://github.com/tbuchi888/elasticsearch-kibana-docker-compose.git
cd elasticsearch-kibana-docker-compose
docker-compose up -d
```

### Set variables for your Elasticsearch
Please change variables of IPaddress or hostname and port for 
your Elasticsearch hosts on 'install_beats5_for_centos.yml'.

```
  vars:
# Set your own Elasticsearch hosts
    elasticsearch_host: 192.168.33.1
    elasticsearch_port: 9200
```

### Change hosts for your environment of servers
You must change inventory hosts file of Ansible for your environment of servers.

## Run Playbook
Run.

```
ansible-playbook -i hosts install_beats5_for_centos.yml -v
```

## Caution
### License and WITHOUT ANY WARRANTY
This program is free software; you can redistribute it and/or modify it under
the terms of the GNU General Public License as published by the Free Software
Foundation; either version 2 of the License, or (at your option) any later
version.

This program is distributed in the hope that it will be useful, but WITHOUT
ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS
FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with
this program. If not, see http://www.gnu.org/licenses/.
