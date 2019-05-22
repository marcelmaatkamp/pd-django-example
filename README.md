# Practical docker tips
*Software does not live alone it is always a complex orchestration to get all the individual parts talk together. Luckily we have docker nowadays and in these talks I give examples on how to implement and secure a software stack with components like logging, monitoring, security, fault detection and more. See my [YouTube Channel with all episodes](https://www.youtube.com/channel/UCxp65f-xyu4z1PvmZBKqZGQ) for more information.*

This project will be one of the main example applications, a Django application which will log to graylog, is secured by openxpki and traefik. There will be a java and nodejs compagnion app in the future.

The rationale of why and how I made this framework is further explained in the https://github.com/marcelmaatkamp/pdt-django-example/wiki

# TL;DR
If `docker` and `docker-compose` are installed:
```
$ git clone https://github.com/marcelmaatkamp/pdt-django-example.git &&\
  cd pdt-django-example &&\
  ./bin/dc up -d
```
Install a socks5 proxy switcher app in your browser like https://github.com/FelisCatus/SwitchyOmega and use the following path to enable the internal socks5 proxy for this project

| Name  |  URL |
| - | -- |
| socks5 proxy | localhost:1080 | 

Now all the containers are resolvable via their internal container name:

| Name  |  URL |
| - | -- |
| django | http://django |
| keycloak | http://keycloak |
| graylog | http://graylog |
| sentry | http://sentry |
| openxpki | http://openxpki-client/openxpki |

# django example
<a href="https://www.djangoproject.com/"><img src="http://big.info/wp-content/uploads/2016/07/django.png" width="400"></a>

https://www.djangoproject.com/

*Django is a high-level Python Web framework that encourages rapid development and clean, pragmatic design. Built by experienced developers, it takes care of much of the hassle of Web development, so you can focus on writing your app without needing to reinvent the wheel. It’s free and open source.*

This will be the core software program in this example, a simple web applicaton in django to demonstrate how to secure, monitor, log and visualise data in this application. 

# dependencies
These are the dependencies of this project 

## openxpki
<a href="https://www.openxpki.org/"><img src="https://upload.wikimedia.org/wikipedia/commons/7/7b/OpenXPKI_logo.png" width="400"></a>

https://www.openxpki.org/

*OpenXPKI is an enterprise-grade PKI/Trustcenter software. It implements the necessary features to operate a PKI in professional environments. While primarily designed to run as an online RA/CA for managing X509v3 certificates, its flexibility allow for a wide range of possible use cases with regard to cryptographic key management.*

https://github.com/marcelmaatkamp/pdt-openxpki

PKI 

## keycloak 
<a href="https://www.keycloak.org/"><img src="https://www.keycloak.org/resources/images/keycloak_logo_480x108.png" width="400" /></a>

https://www.keycloak.org/

*Keycloak is an open source Identity and Access Management solution aimed at modern applications and services. It makes it easy to secure applications and services with little to no code.*

https://github.com/marcelmaatkamp/pdt-keycloak

Federated login for our applications

## dns
<img src="https://aidanfinn.com/wp-content/uploads/2017/12/Azure-DNS.png" width="400">
Each public facing container will get a unique hostname. This container will do the wildcard dns name resolution.

## traefik
<a href=""><img src="https://cdn-images-1.medium.com/max/1200/1*0Gu7W6KCr373QH4be5ShWQ.png" width="400"></a>

https://docs.traefik.io/

*A reverse proxy / load balancer that's easy, dynamic, automatic, fast, full-featured, open source, production proven, provides metrics, and integrates with every major cluster technology. Traefik is a modern HTTP reverse proxy and load balancer that makes deploying microservices easy. Traefik integrates with your existing infrastructure components (Docker, Swarm mode, Kubernetes, Marathon, Consul, Etcd, Rancher, Amazon ECS, ...) and configures itself automatically and dynamically. Pointing Traefik at your orchestrator should be the only configuration step you need.*

Each public facing container will get a unique hostname and together with Traefik and LetsEncrypt also a unique SSL certificate.

## ouroboros

<a href="https://github.com/pyouroboros/ouroboros"  width="400"><img src="https://res.cloudinary.com/teepublic/image/private/s--MkVDG5Bs--/t_Preview/b_rgb:ffffff,c_limit,f_jpg,h_630,q_90,w_630/v1546054510/production/designs/3842483_0.jpg" width="400" /></a>

https://github.com/pyouroboros/ouroboros

*Ouroboros will monitor (all or specified) running docker containers and update them to the (latest or tagged) available image in the remote registry. The updated container uses the same tag and parameters that were used when the container was first created such as volume/bind mounts, docker network connections, environment variables, restart policies, entrypoints, commands, etc.*

Automatic update of our containers

## graylog 
<a href="https://www.graylog.org/products/open-source"><img src="https://s24255.pcdn.co/wp-content/uploads/2017/06/graylog.png" width="400"></a>

https://www.graylog.org/products/open-source

*Graylog is purpose-built and designed to deliver the best log collection, storage, enrichment, and analysis experience.The simplicity in searching, exploring, and visualizing data means no expensive training or tool experts are required. Graylog has considerably faster analysis speeds, provides a more robust and easier-to-use analysis platform,*

Logging container

## logspout
<a href="https://github.com/gliderlabs/logspout"><img src="https://avatars0.githubusercontent.com/u/8484931?s=400&v=4" /></a>

https://github.com/gliderlabs/logspout

*Logspout is a log router for Docker containers that runs inside Docker. It attaches to all containers on a host, then routes their logs wherever you want. It also has an extensible module system. t's a mostly stateless log appliance. It's not meant for managing log files or looking at history. It is just a means to get your logs out to live somewhere else, where they belong.*

Automatic logging to graylog for all running containers without any extra configuration

## sentry
<img src="https://raw.githubusercontent.com/docker-library/docs/7d1c6fff37893bcefc186de7b978f5bdb2f801f6/sentry/logo.png" width="400">

https://sentry.io/

*<em>Your code is bad, but that’s fine</em>
Sentry is open-source error tracking that provides visibility across your entire stack, giving you the details you need to fix your bugs. Even the most bumbling, typo-prone developer can use our service to resolve problems, well before your users encounter them.*

Error tracking

# About
In these talks I will give practical tips and tricks on how to effectively use Docker as a valuable tool to solve various problems or just use it for fun projects with all kinds of hardware and software! See my [YouTube Channel with all episodes](https://www.youtube.com/channel/UCxp65f-xyu4z1PvmZBKqZGQ) for more information.
* [YouTube Channel with all episodes](https://www.youtube.com/channel/UCxp65f-xyu4z1PvmZBKqZGQ)


