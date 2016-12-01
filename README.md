DSpace
=========

Install and manage a DSpace/StatSpace site.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

### Database connection

These define the name and ownership of the (Postgres) database used to
store DSpace data.

- dspace_db_name: dspace
- dspace_db_owner: dspace
- dspace_db_user: dspace
- dspace_db_password: dspace

### Directory locations
- dspace_src_dir: location of DSpace source directory (`/var/dspace-src`)
- dspace_install_dir: location of DSpace installation directory (`/dspace`)
- dspace_version: Git branch used to check out the source (`statspace`)
- dspace_user: owner of the source and install directory (`vagrant`)
- dspace_group: group of the source directory *only* (`vagrant`); the
  group of the install directory is `tomcat`

### Site customizations
- dspace_admins: pre-loaded site administrators (`[]`)
- dspace_site_registries: custom metadata schema definitions that
  should be installed (`[]`)
- dspace_use_proxy: whether the role should install an Nginx proxy (`yes`)
- dspace_ssl_self_signed: whether the proxy should use a self-signed
  SSL certificate (`true`)


Dependencies
------------

- `geerlingguy.repo-epel` for subscribing to the EPEL repository
- `jdauphant.ssl-certs` for creating self-signed SSL certificates
- `jdauphant.nginx` for managing the Nginx proxy

License
-------

BSD

Author Information
------------------

Davor Cubranic, (c) 2016 University of British Columbia
