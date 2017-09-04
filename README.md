This Role checks every day new random comics from http://pbfcomics.com/ and sends it to your slack channel.

Requirements
------------
You must define in vars/main.yml
1. "hooks" variable to your slack account
2. "channel" variable to your slack channel where comics will be displayed

Role Variables
--------------

```yaml
# vars/main.yml

# vars file for ansible-role-pbfcomics

#Destination path
dest_path: /usr/local/bin

#Crontab settings
#Minute when the job should run ( 0-59, *, */2, etc )
minute: "0"
#Hour when the job should run ( 0-23, *, */2, etc )
hour: "7"
#Day of the month the job should run ( 1-31, *, */2, etc )
day: "*"
#Month of the year the job should run ( 1-12, *, */2, etc )
month: "*"
#Day of the week that the job should run ( 0-6 for Sunday-Saturday, *, etc )
weekday: "*"

# http://pbfcomics.com
pbfcomics_link: http://pbfcomics.com
pbfcomics_src: pbfcomics.com

# Slack channel settings
channel: comics
username: podgrzybek
hooks: https://hooks.slack.com/services/yourslackhash
# Attachments for channel settings
pretext: Found a new free eBook
author_name: https://github.com/Grzyboll
```

Dependencies
------------


Example Playbook
----------------

```yaml
    - hosts: local
      roles:
         - ansible-role-pbfcomics
```

License
-------

MIT

Author Information
------------------
Grzyboll: pokiegogrzyba @gmail.com
