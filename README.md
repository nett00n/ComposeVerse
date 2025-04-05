# Compose Verse - a docker compose selfhosted awesome list

Here are located my attempts to deploy an kind of services.

- I use [Traefik](https://doc.traefik.io/traefik/) as a reverse proxy. Sample config is located [🔗 here](traefik/docker-compose.yml)
- I use [Cloudlare DNS](https://www.cloudflare.com/) and deploy it with [Terraform](https://www.terraform.io/)

  AFAIK [❔](https://www.wordnik.com/words/afaik) [Desec](https://desec.io/) and [IBM NS1](https://www.ibm.com/products/ns1-connect) can be conigured with terraform too: [\[Desec terraform module\]](https://registry.terraform.io/providers/Valodim/desec/latest/docs) [\[IBM NS1 terraform module\]](https://registry.terraform.io/providers/Valodim/desec/latest/docs)
- My docker stacks directory is mounted to `/Stacks`
- My data directory is mounted to `/Data`
- I use watchtower to update containers, which are safe to update
- At most cases environment must be conigured in `.env` file
- if anything except `docker-compose*.yml`, `.env` and `README.md` located in directory - you need them in your stack folder
- I use [dockge] on my development machine, so my compose files has this code, which renders URL to service dnamically in dockge WUI:

  ```yaml
  x-dockge:
    urls:
      - https://${SERVICE_NAME_OVERRIDE:-servicename}.${DOMAIN_NAME:-local}
  ```

## Automation

Automation software designed to reduce human intervention in processes.

Related: Internet of Things (IoT), Software Development - Continuous Integration & Deployment

- [headphones](https://github.com/rembo10/headphones) - Automated music downloader for NZB and Torrent, written in Python. It supports SABnzbd, NZBget, Transmission, µTorrent, Deluge and Blackhole.
  [🔗 Files](Stacks/headphones/docker-compose.yml)
  `GPL-3.0`
  `Python`

## DNS

DNS servers and management tools with advertisement blocking functionality, primarily aimed at home or small networks.

- [blocky](https://github.com/0xERR0R/blocky) - Fast and lightweight DNS proxy (like Pi-hole) as ad-blocker for local network with many features.
  [🔗 Files](Stacks/blocky/docker-compose.yml)
  `Apache-2.0`
  `Go/Docker`
- [DumbWhois](https://github.com/DumbWareio/DumbWhoIs) - A simple web application for looking up WHOIS, IP, and ASN information using free APIs. The application automatically detects the type of query and provides formatted results with a clean, modern UI that supports both light and dark modes.
  [🔗 Files](Stacks/dumbwhois/docker-compose.yml)
  `Apache-2.0`
  `Go/Docker`

## Docker Management

- [Dockge](https://github.com/louislam/dockge) - A fancy, easy-to-use and reactive self-hosted docker compose.yaml stack-oriented manager
  [🔗 Files](Stacks/dockge/docker-compose.yml)
  `MIT`
  `Golang, Typescript`
- [Dozzle](https://dozzle.dev/) - Simple Container Monitoring and Logging
  [🔗 Files](Stacks/dozzle/docker-compose.yml)
  `MIT`
  `Golang`

## File Transfer - Web-based File Managers

- [filebrowser](https://github.com/filebrowser/filebrowser) - Web File Browser with a Material Design web interface.
  [🔗 Files](Stacks/filebrowser/docker-compose.yml)
  `Apache-2.0`
  `Go`

### Miscellaneous

Software that does not fit in another section.

- [morphos](https://github.com/danvergara/morphos) - Self-hosted file converter server
  [🔗 Files](Stacks/morphos/docker-compose.yml)
  `MIT`
  `Golang`
- [noisedash](https://github.com/kaythomas0/noisedash) - Self-hostable web tool for generating ambient noises
  [🔗 Files](Stacks/noisedash/docker-compose.yml)
  `MIT`
  `Golang`

## Money, Budgeting & Management

Software and tools to help with resource and supply planning, including enterprise resource and supply planning (ERP).

Related: Money, Budgeting & Management, Inventory Management

- [ExpenseOwl](https://github.com/Tanq16/ExpenseOwl) - Extremely simple, self-hosted expense tracker with a beautiful UI.
  [🔗 Files](Stacks/expenseowl/docker-compose.yml)
  `MIT`
  `Golang`

## Monitoring

Software for monitoring systems, networks, applications and websites.

- [Beszel](https://github.com/henrygd/beszel) - Lightweight server monitoring hub with historical data, docker stats, and alerts.
  [🔗 Server Files](beszel-server/docker-compose.yml)
  [🔗 Agent Files](beszel-agent/docker-compose.yml)
  `MIT`
  `Golang, Typescript`
- [scrutiny](https://github.com/AnalogJ/scrutiny) - Hard Drive S.M.A.R.T Monitoring, Historical Trends & Real World Failure Thresholds
  [🔗 Files](Stacks/scrutiny/docker-compose.yml)
  `MIT`
  `Docker`
- [StatPing.ng](https://statping-ng.github.io/) - An easy to use Status Page for your websites and applications. Statping will automatically fetch the application and render a beautiful status page with tons of features for you to build an even better status page.
  [🔗 Files](Stacks/statping-ng/docker-compose.yml)
  `GPL-3.0`
  `Docker/Go`

### Note-taking & Editors

[Note taking](https://en.wikipedia.org/wiki/Note-taking) editors.

Related: Wikis

- [Joplin](https://joplinapp.org/) - Joplin is a note taking application with Markdown editor and encryption support for mobile and desktop platforms. Runs client-side and syncs through self hosted Nextcloud or similar (alternative to Evernote).
  [🔗 Files](Stacks/joplin-server/docker-compose.yml)
  `MIT`
  `Nodejs`

### Personal Dashboards

Dashboards for accessing information and applications.

- [ryot](https://github.com/ignisda/ryot) - Platform for tracking various facets of your life - media, fitness, etc. ([Demo](https://github.com/IgnisDa/ryot?tab=readme-ov-file#-demo))
  [🔗 Files](Stacks/ryot/docker-compose.yml)
  `GPL-3.0`
  `Docker`


## Proxy

A proxy is a server application that acts as an intermediary between a client requesting a resource and the server providing that resource. This section about forward (i.e. outgoing) proxies. For reverse proxies, see the Web Server section.

Related: Web Servers

- [Traefik](https://github.com/traefik/traefik) - The Cloud Native Application Proxy.
  [🔗 Files](Stacks/traefik/docker-compose.yml)
  `MIT`
  `Golang`

## Recipe Management

Software and tools for managing recipes.
- [Recipya](https://recipes.musicavis.ca) - A clean, simple and powerful recipe manager your whole family will enjoy. ([Demo](https://recipes.musicavis.ca/guide/login), [Source Code](https://github.com/reaper47/recipya))
  [🔗 Files](Stacks/recipya/docker-compose.yml)
  `GPL-3.0`
  `Docker/Go`
- [tandoor](https://tandoor.dev/) - The recipe manager that allows you to manage your ever growing collection of digital recipes.
  [🔗 Files](Stacks/tandoor/docker-compose.yml)
  `“Commons Clause” License Condition v1.0`
  `Python`

## Resource Planning

Software and tools to help with resource and supply planning, including enterprise resource and supply planning (ERP).

Related: Money, Budgeting & Management, Inventory Management

- [grocy](https://grocy.info/) - ERP beyond your fridge - grocy is a web-based self-hosted groceries & household management solution for your home. (Demo, Source Code)
  [🔗 Files](Stacks/grocy/docker-compose.yml)
  `MIT`
  `PHP`

## Software Development


Software development is the process of conceiving, specifying, designing, programming, documenting, testing, and bug fixing involved in creating and maintaining applications, frameworks, or other software components.

- [it-tools](https://github.com/CorentinTh/it-tools) - Collection of handy online tools for developers, with great UX.
  [🔗 Files](Stacks/it-tools/docker-compose.yml)
  `GPL-3.0`
  `Vue, Typescript`

## Software Development - Project Management

Tools and software for software project management.

Related: Ticketing, Task Management & To-do Lists

- [Gitea](https://about.gitea.com/) - Git with a cup of tea! Painless self-hosted all-in-one software development service, including Git hosting, code review, team collaboration, package registry and CI/CD. (Demo, Source Code)
  [🔗 Files](Stacks/gitea/docker-compose.yml)
  `MIT`
  `Golang`
