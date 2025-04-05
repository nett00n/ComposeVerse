# Compose Verse - a docker compose selfhosted awesome list

Here are located my attempts to deploy an kind of services.

- I use [Traefik](https://doc.traefik.io/traefik/) as a reverse proxy. Sample config is located [🔗 here](traefik/docker-compose.yml)
- I use [Cloudlare DNS](https://www.cloudflare.com/) and deploy it with [Terraform](https://www.terraform.io/)

  AFAIK [❔](https://www.wordnik.com/words/afaik) [Desec](https://desec.io/) and [IBM NS1](https://www.ibm.com/products/ns1-connect) can be conigured with terraform too: [\[Desec terraform module\]](https://registry.terraform.io/providers/Valodim/desec/latest/docs) [\[IBM NS1 terraform module\]](https://registry.terraform.io/providers/Valodim/desec/latest/docs)
- My docker stacks directory is mounted to `/Stacks`
- My data directory is mounted to `/Data`
- I use watchtower to update containers, which are safe to update
- At most cases environment must be conigured in `.env` file
- I use [dockge] on my development machine, so my compose files has this code, which renders URL to service dnamically in dockge WUI:

  ```yaml
  x-dockge:
    urls:
      - https://${SERVICE_NAME_OVERRIDE:-servicename}.${DOMAIN_NAME:-local}
  ```

## Docker Management

- [Dockge](https://github.com/louislam/dockge) - A fancy, easy-to-use and reactive self-hosted docker compose.yaml stack-oriented manager `MIT` `Golang, Typescript`

## Money, Budgeting & Management

Software and tools to help with resource and supply planning, including enterprise resource and supply planning (ERP).

Related: Money, Budgeting & Management, Inventory Management

- [ExpenseOwl](https://github.com/Tanq16/ExpenseOwl) - Extremely simple, self-hosted expense tracker with a beautiful UI.
  [🔗 Files](ExpenseOwl/docker-compose.yml) `MIT` `Golang`

## Proxy

A proxy is a server application that acts as an intermediary between a client requesting a resource and the server providing that resource. This section about forward (i.e. outgoing) proxies. For reverse proxies, see the Web Server section.

Related: Web Servers

- [Traefik](https://github.com/traefik/traefik) - The Cloud Native Application Proxy.
  [🔗 Files](traefik/docker-compose.yml) `MIT` `Golang`
