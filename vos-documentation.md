### Documentation

#### Base Operating System
At it's current state, vOS supports both CentOS 6 and CentOS 7.

#### Default user
Default user is _*voyagerse*_. From this account, one can use sudo to gain super user privileges.

#### SSH Authorized Keys location
Local ssh authorized keys file is located in /etc/ssh/keys/%u, where %u is the username. This file is owned by the super user and can not be modified other than the same.

#### Hardening
Hardening is based on the PCI DSS (which version?) standards and applied through [puppet manifests](https://github.com/VoyagerInnovations/puppet-cis-module)

#### Application Logs
Log files under the directory _**/var/log/apps**_ will be rotated automatically through the configuration at _**/etc/logrotate.d/apps**_.

It it recommended that all application logs go to this directory.

Todo: Add more details like frequency, etc.

#### NTP Syncronization
The default time syncronization app is chrony which can be configured through _**/etc/chrony.conf**_.

ntpd is still available through the default repository.

#### Syslog Daemon
Todo: Identify default logging server.

#### Anti-Malware
ClamAV is included!

Todo: Discuss details

#### OSSEC HIDS
Todo: Discuss details

#### Pre-downloaded Agents
Some pre-downloaded are available at _**/installers**_ to minimize the time it takes to make a first book. The packages are available but not yet installed. Install the package using your own method.

The following are available:
  - Splunk Forwarder
  - Qualys Agent
  - 

#### Packages
The list of packages is available [publicly](https://github.com/VoyagerInnovations/hardened1-packages). Feel free to submit a merge request if you want to add your own package.
