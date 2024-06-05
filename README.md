[global]
    bind interfaces only = Yes
    dns proxy = No
    interfaces = 127.0.0.1/8 ens160
    log file = /var/log/samba/log.%m
    max log size = 50
    realm = EDISONCAMERA.LOCAL
    security = ADS
    server string = Samba Server
    workgroup = EDISONCAMERA
    usershare allow guests = Yes

    idmap config * : backend = tdb
    idmap config * : range = 3000-7999
    idmap config EDISONCAMERA : backend = rid
    idmap config EDISONCAMERA : range = 10000-999999

    winbind use default domain = yes
    winbind offline logon = false
    winbind nss info = rfc2307
    winbind enum users = yes
    winbind enum groups = yes

    template shell = /bin/bash
    template homedir = /home/%D/%U

[homes]
    browseable = No
    comment = Home Directories
    create mask = 0700
    directory mask = 0700

[public]
    path = /srv/samba/public
    browseable = yes
    read only = no
    guest ok = yes

[confidential]
    path = /srv/samba/confidential
    browseable = no
    read only = no
    guest ok = no
    valid users = @EDISONCAMERA\Domain Users
