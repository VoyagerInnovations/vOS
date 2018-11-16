### Documentation

#### Base Operating System
At it's current state, vOS supports both CentOS 6 and CentOS 7.

#### Default user
Default super user is voyagerse.

#### SSH Authorized Keys location
Local ssh authorized keys file is located in /etc/ssh/keys/%u, where %u is the username. This file is owned by the super user and can not be modified other than the same.

#### Hardening
Hardening is based on the PCI DSS (which version?) standards and applied through the scripts at https://github.com/VoyagerInnovations/puppet-cis-module

#### Packages
The list of packages is available at https://github.com/VoyagerInnovations/hardened1-packages. Feel free to submit a merge request if you want to add your own package.
