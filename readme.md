###ansible-base
---

An extensible [Ansible](http://docs.ansible.com/) framework for deploying services and web applications.

Contains some basic plays, such as setup of basic security and installation of server monitoring.

Tested on Ubuntu 14.04.

Requires Ansible >= 1.8.1 and optionally Vagrant to use the included Vagrantfile.

Full contents of base playbook:
- Installs:
    - `bash`
    - `openssl`
    - `libssl`
    - `build-essential`
    - `ntp`
    - `htop`
    - `git`
    - `supervisor`
    - `newrelic-server`
    - `fail2ban`
    - `ufw`
    - `memcached`
    - `nginx`
- Uninstalls
    - `[landscape](https://landscape.canonical.com/)`
- Configures
    - All incoming TCP connections are blocked except on ports 22, 80, and 443
    - Fail2ban is configured to block failed SSH connections from unknown IPs for 10 minutes after 3 failures
    - A 512MB swapfile is created, enabled and placed at `/swapfile`
    - Memcached is installed and enabled on port `11211`

Based in part on [jcalazan/ansible-django-stack](https://github.com/jcalazan/ansible-django-stack) and [kamaln7/ansible-swapfile](https://github.com/kamaln7/ansible-swapfile).
