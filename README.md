gpenaud.k3s
===========

This role deploys a k3s cluster ready-to-work with on your local computer. It configures
your kubeconfig, local TLS CA and wildcards, and install traefik as an Helm chart.  

Requirements
------------

At minimum, you must have:
- ansible

For confortable use and testing purposes, you can install:
- molecule

Role Variables
--------------

**k3s_user** : The user account to install k3s cluster on.  
**k3s_user_path** : The home of the user (home/{{ k3s_user }} by default).  
**k3s_installation_path** : The path where we should store k3s useful files ({{ k3s_user_path }}/.k3s by default).  
**k3s_dockerconfig** : The docker configuration file for registry secrets ({{ k3s_user_path }}/.docker/config.json by default).  

Dependencies
------------

No dependencies for this role.

Example Playbook
----------------

To efficiently use this role, you can deploy it from a random playbook in this way:

    - hosts: developers
      roles:
        - role: gpenaud.k3s
          vars:
            k3s_installation_path: /var/k3s

License
-------

BSD

Author Information
------------------

Guillaume Penaud (gpenaud)  
Site Reliability Engineer  
gpenaud S.A
