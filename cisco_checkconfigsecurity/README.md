## check_mk Plugin: cisco_checkconfigsecurity

### Content
The idea of this plugin is to check a local directory containing Cisco configuration files.

'''python
CONFIGROOT = "/var/rancid/"
GROUPS = ['QB', 'NO']
CONFIGSUB = "/configs/"
'''

There are some validation routines which produce a warning if they fail.

'''python
def check_exectimeout(config):
'''

#### Idle Timeout
Warn if the idle timeout is not 10 minutes.

#### Local user accounts
Warn if there are local useraccounts configured (e.g. because it's only
permitted to use a central authentication instance)

### Installation
Just copy the file to the directory where the check_mk_agent is looking for
local plugins (e.g. /usr/lib/check_mk_agent/local)

