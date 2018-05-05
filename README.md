# Infopen Ansible styleguide

Our Ansible resources increasing, it's time to reference main rules to use.
It's can be useful to understand how roles are built or what are the planned
updates for legacy roles.


## Ansible roles

### Cookiecutter template

New roles are initialized using a [Cookicutter template](https://github.com/infOpen/cookiecutter-ansible-role).

This template manage:
* a common structure
* a variables management using OS family and distribution priority
* [Travis CI](https://travis-ci.org) and [Molecule](https://github.com/metacloud/molecule) testing
* Tests are run using an [ os_distributions * ansible_versions ] matrix
* [Pyup](https://pyup.io/) integration to manage Python requirements updates

New and recently updated roles use github repositories tags to reference the template version used (ex: *infopen-template-0-29-0*).
This will be useful to plan future upgrades.

### Dependencies management

To keep every the choice of their Ansible role, no mandatory dependencies are defined.

From 2018-05, conditional dependencies will be defined, and can be managed via:
* the role variable *<role_name>_use_ansible_galaxy_dependencies*
* for all Infopen roles once via the variable *infopen_use_ansible_galaxy_dependencies*

This will be rolled out gradually over existing roles.
