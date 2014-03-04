An attempt at provisioning an Ubuntu 12.04 instance with PostgreSQL using Chef, following Ch 11.1 - 'PostgreSQL' 
in Ben Dixon's Leanpub __Reliably Deploying Rails Applications__ ([find here](https://leanpub.com/deploying_rails_applications)).
### Dependencies

* ruby (2.0)
* knife-solo (0.4)
* berkshelf (2.0)

### Commands

1. berks install
2. knife solo prepare root@<yourserverhere>
3. knife solo cook root@<yourserverhere>

### Result
The foregoing got me PostgreSQL on my server (and use and installation was as Ben's chapter promised), however
I was unable to add the Monit server:
```
Chef Client failed. 1 resources updated in 1.738820267 seconds
[2014-03-04T14:36:06-05:00] ERROR: template[/etc/monit/conf.d/postgres.conf] (monit_configs-tlq::postgres line 1) had an error: Chef::Exceptions::EnclosingDirectoryDoesNotExist: Parent directory /etc/monit/conf.d does not exist.
[2014-03-04T14:36:06-05:00] FATAL: Chef::Exceptions::ChildConvergeError: Chef run process exited unsuccessfully (exit code 1)
ERROR: RuntimeError: chef-solo failed. See output above.
```
