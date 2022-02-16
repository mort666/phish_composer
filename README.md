# Phish-Composer

**NOTE: This repository updates the original Phish-Composer scripts to use the latest versions of Gophish and Evilginx2.This setup should never have the SMTP relay open to the Internet inbound as there is no restriction on it and will get your IP Blacklisted.**

Phish-Composer is a docker-compose project intended to spin up three docker images often used together for phishing. The individual components of this infra are Gophish, Evilginx2, and Postfix, as are [detailed in this blog post](http://lockboxx.blogspot.com/2018/12/gophish-evilginx2-for-phishing.html). The following are the docker containers used to wrap each of the individual projects:

  - [gophish/gophish](https://hub.docker.com/r/gophish/gophish/dockerfile/)
  - [warhorse/evilginx2](https://hub.docker.com/r/warhorse/evilginx2/dockerfile)
  - [mwader/postfix-relay](https://hub.docker.com/r/mwader/postfix-relay/dockerfile)


[Read more about this project here](https://lockboxx.blogspot.com/2020/01/gophish-evilginx2-auto-deployment-w.html), which explains some more of the theory behind this deployment as well as some key configuration files in the deployment.


Execution example:
```sh
sudo docker-compose up -d
sudo docker ps
# Attach to evilginx2
sudo docker attach `sudo docker ps | grep evilginx2 | cut -d ' ' -f1`

```
