### Documentation

#### Base Operating System
At it's current state, vOS supports both CentOS 6 and CentOS 7.

#### Default user
Default user is voyagerse. From this account, one can use sudo to gain super user privileges.

#### SSH Authorized Keys location
Local ssh authorized keys file is located in /etc/ssh/keys/%u, where %u is the username. This file is owned by the super user and can not be modified other than the same.

#### Hardening
Hardening is based on the PCI DSS (which version?) standards and applied through [puppet manifests](https://github.com/VoyagerInnovations/puppet-cis-module)

#### Application Logs
Log files under the directory **/var/log/apps** will be rotated automatically through the configuration at **/etc/logrotate.d/apps**.

Todo: Add more details like frequency, etc.

#### NTP Syncronization
The default time syncronization app is chrony which can be configured through **/etc/chrony.conf**

ntpd is still available through the default repository.

#### Syslog Daemon
Todo: Identify default logging server.

#### Anti-Malware
ClamAV is included!

Todo: Discuss details

#### OSSEC HIDS
Todo: Discuss details

#### Packages
The list of packages is available [publicly](https://github.com/VoyagerInnovations/hardened1-packages). Feel free to submit a merge request if you want to add your own package.
