selinux-nginx
=============

SELinux Nginx policy for Debian.

Modified from http://sourceforge.net/projects/selinuxnginx/

This policy has **not** been thoroughly tested or peer reviewed. Use at your own risk.
However, it should be substantially better than running Nginx without any policy.


## Install

```bash
apt-get install selinux-policy-dev
git clone https://github.com/simple10/selinux-nginx.git
cd selinux-nginx/nginx
make
semodule -i nginx.pp

# Relabel the filesystem
touch /.autorelabel
reboot

# Make sure nginx is running as nginx_exec_t
ls -Z /usr/sbin/nginx
# system_u:object_r:nginx_exec_t:SystemLow /usr/sbin/nginx

# Check the audit logs to see if nginx is being denied
audit2why -al
# No output is good. If there are denials, modify the policy as necessary.
```
