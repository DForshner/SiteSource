---
title: DevOps - Amazingly Awesome Ansible Meetup
date: 2016-04-21 00:00:00
tags:
- DevOps
- Meetup
---
Another great workshop with the people at [Boltmade](www.boltmade.com).  This time around, it was series of exercises to refactor the deployment of a cloud app using [Ansible](https://www.ansible.com/).

At its most basic Ansible is a way of replacing your app's initialization shell scripts or manual deployment steps.

Deployments will become complex over time.  Shell scripts hit a complexity wall where you have to give up and start over with a config management system.  Ansible is simple to start with and can evolve as complexity grows over time.  Extremely useful if you are deploying unusual combinations of software.

Puppet & Chef require a remote deploy server, so there is a centralized point of failure.  With Ansible, you just ssh in and start doing stuff so it can also provision a local server.

Deployments are not static.  Ansible allows you to tie your deployment requirements to your source making deployment repeatable and easy.  By looking at your source history, you can see how your server requirements have changed over time.  You can look at old versions of your application and see what the infrastructure was like back then.  It also captures any workarounds required to deploy combinations of software and infrastructure versions.

Ansible is a structured way of accomplishing a deployment.  It gives you a common language for how things are configured/deployed at your company.  The release engineers who follow you can understand your deployment process (playbook) because it has standard *style*.  Removes the need to have separate documents for how things should be setup.

It's possible to configure Ansible to do idempotent deployments so you can deploy again and again and get same results.  Ansible can be made smart enough to skip steps that aren't needed.  You won't need to comment out sections (like you have to with bash scripts) while doing iterative development.

A potential downside of ansibles simplicity is that if you can forget about temporary fixes while getting things working that come back and haunt you later (ex: hardcoded/default passwords).

Random Notes:
* <u>Galaxy Roles</u> - Community built roles you can use but they can be overkill (for large server farms) and have poor practices.
* Ansible + Vagrant = Can deploy both a real server and setup a development environment using the same scripts.  You may have to do some extra work to make vagrant behave like a remove box.
* <u>Ansible Vault</u> will encrypt data so it can be stored with the rest of the application code in source control.  It will only be decrypted when Ansible is provisioning a box.
* Could install Ansible on the load balancer which will have access to inner boxes.

[My progress through the workshop](https://github.com/DForshner/ansible-workshop-deploy)
[Meetup event](http://www.meetup.com/boltmade-sessions/events/230344829/?rv=cr1&_af=event&_af_eid=230344829&https=off)