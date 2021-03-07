# Windows SSH AMIs

## Description

Packer builds for OpenSSH enabled Windows 2019/2016/2012R2 images.


## Purpose

The primary driver for this repository was to use OpenSSH to simplify/eliminate setup required for launched instances to be managed by Ansible.

The use of OpenSSH and a preloaded public key allows for an Ansible configuration (almost) identical to that of a Linux client.


## Usage

Open `ansible/openssh.yml` and update the `ssh_public_key` variable with a local path to the public key of the key pair you will use to connect to the machines launched from the resultant AMI.

Open `packer/windows201{9,6,2r2}.json` and update `.builders.region` as required (optional).

Build image:

~~~bash
cd packer
packer build windows2019.json
~~~~


## Credit where credit's due

Inspiration (and code snippets) drawn from [this article](https://www.2ndwatch.com/blog/automating-windows-server-2016-builds-with-packer/) and [this repository](https://github.com/comerford/windows-ssh-base-ami.git).
