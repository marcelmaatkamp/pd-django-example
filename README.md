# Practical docker tips
Software does not live alone it is always a complex orchestration to get all the individual parts talk together. Luckily we have docker nowadays and in these talks I give examples on how to implement and secure a software stack with components like logging, monitoring, security, fault detection and more. 

See my [YouTube Channel with all episodes](https://www.youtube.com/channel/UCxp65f-xyu4z1PvmZBKqZGQ) for more information.
* [YouTube Channel with all episodes](https://www.youtube.com/channel/UCxp65f-xyu4z1PvmZBKqZGQ)

# django example
<a href="https://www.djangoproject.com/"><img src="http://big.info/wp-content/uploads/2016/07/django.png"></a>

https://www.djangoproject.com/

This will be the core software program in this example, a simple web applicaton in django to demonstrate how to secure, monitor, log and visualise data in this application. 

# dependencies
These are the dependencies of this project 

## openxpki
<a href="https://www.openxpki.org/"><img src="https://upload.wikimedia.org/wikipedia/commons/7/7b/OpenXPKI_logo.png" width="400"></a>

https://www.openxpki.org/

*OpenXPKI is an enterprise-grade PKI/Trustcenter software. It implements the necessary features to operate a PKI in professional environments. While primarily designed to run as an online RA/CA for managing X509v3 certificates, its flexibility allow for a wide range of possible use cases with regard to cryptographic key management.*

## dns
<img src="https://aidanfinn.com/wp-content/uploads/2017/12/Azure-DNS.png" width="400">
Each public facing container will get a unique hostname. This container will do the wildcard dns name resolution.

## traefik
<a href=""><img src="https://cdn-images-1.medium.com/max/1200/1*0Gu7W6KCr373QH4be5ShWQ.png" width="400"></a>

https://docs.traefik.io/

*A reverse proxy / load balancer that's easy, dynamic, automatic, fast, full-featured, open source, production proven, provides metrics, and integrates with every major cluster technology. Traefik is a modern HTTP reverse proxy and load balancer that makes deploying microservices easy. Traefik integrates with your existing infrastructure components (Docker, Swarm mode, Kubernetes, Marathon, Consul, Etcd, Rancher, Amazon ECS, ...) and configures itself automatically and dynamically. Pointing Traefik at your orchestrator should be the only configuration step you need.*

Each public facing container will get a unique hostname and together with Traefik and LetsEncrypt also a unique SSL certificate.Letsencrypt ssl and wildcard dns mapping for internal and external facing containers
 
## graylog 
<a href="https://www.graylog.org/products/open-source"><img src="https://s24255.pcdn.co/wp-content/uploads/2017/06/graylog.png" width="400"></a>

https://www.graylog.org/products/open-source


Logging

## sentry
<img src="https://raw.githubusercontent.com/docker-library/docs/7d1c6fff37893bcefc186de7b978f5bdb2f801f6/sentry/logo.png" width="400">

Error tracking

# About
In these talks I will give practical tips and tricks on how to effectively use Docker as a valuable tool to solve various problems or just use it for fun projects with all kinds of hardware and software! See my [YouTube Channel with all episodes](https://www.youtube.com/channel/UCxp65f-xyu4z1PvmZBKqZGQ) for more information.
* [YouTube Channel with all episodes](https://www.youtube.com/channel/UCxp65f-xyu4z1PvmZBKqZGQ)


