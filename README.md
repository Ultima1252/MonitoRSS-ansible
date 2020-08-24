# MonitoRSS-ansible
Ansible playbook for MonitoRSS

Only currently support Debian and only tested on buster.

Edit vars in monitorss.yml, I suggest adding the secret ones to a vault file.

playbook can be tested locally using ```vagrant up```

Systemd units:

monitorss.service = bot

monitorss-web.service = web



TODO:
* Improve README
* Add support for more OS's
* Add better support for SSL/TLS
* Add integrated testing
