# PowerDNS with PostgreSQL backend deploy

![CI workflow](https://github.com/randsw/powernds-pgsql/actions/workflows/powerdns-ci-test.yaml/badge.svg)

## Deploy

### Start vagrant VM

`vagrant up`

### Deploy PowerDNS with PostgreSQL backend

`ansible-playbook -i inventories/powerdns/hosts.yml pdns-deploy.yml`
