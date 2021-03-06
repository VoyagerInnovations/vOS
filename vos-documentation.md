### Documentation

#### Base Operating System
At it's current state, vOS supports both CentOS 6 and CentOS 7.

#### Default user
Default user is _voyagerse_. From this account, one can use sudo to gain super user privileges.

#### SSH Authorized Keys location
Local ssh authorized keys file is located in /etc/ssh/keys/%u, where %u is the username. This file is owned by the super user and can not be modified other than the same.

#### Hardening
Hardening is based on the PCI DSS (which version?) standards and applied through [puppet manifests](https://github.com/VoyagerInnovations/puppet-cis-module)

#### Application Logs
Log files under the directory _/var/log/apps_ will be rotated automatically through the configuration at _/etc/logrotate.d/apps_.

It it recommended that all application logs go to this directory.

Todo: Add more details like frequency, etc.

#### NTP Syncronization
The default time syncronization app is _chrony_ (not ntpd) which can be configured through _/etc/chrony.conf_.

ntpd is still available through the default repository.

#### Syslog Daemon
Default syslog daemon is rsyslogd.

Configuration files:
  - /etc/rsyslog.conf
  - /etc/rsyslog.d/*

#### Anti-Malware
ClamAV is included!

Todo: Discuss details

#### OSSEC HIDS / FIM
Todo: Discuss details

#### Pre-downloaded Agents
Some pre-downloaded packages are available at _/installers_ to minimize the time it takes to make a first boot. The packages are available but not yet installed. Install the package using your own preferred method.

The following are available:
  - Splunk Forwarder
  - Qualys Agent
  - osquery
  - filebeat
    
  
#### AWS Tagging
There is no need for an external system for tagging. The instance itself can tag its own provided that the instance is launched with an instance role with the following policy:

```
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Effect": "Allow",
			"Action": "ec2:CreateTags",
			"Resource": "arn:aws:ec2:*:*:instance/*"
		}
	]
}
```
#### Monitoring
osquery is installed by default.

Todo: Add more details

#### Packages
The list of packages is available [publicly](https://github.com/VoyagerInnovations/hardened1-packages). Feel free to submit a merge request if you want to add your own package.
