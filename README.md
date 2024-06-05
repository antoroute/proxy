# Squid configuration file

# Access Control Lists (ACLs)
acl SI_Administratif src 10.130.0.0/16
acl SI_Usuel src 10.126.0.0/16
acl SSL_ports port 443
acl Safe_ports port 80		# http
acl Safe_ports port 21		# ftp
acl Safe_ports port 443		# https
acl Safe_ports port 70		# gopher
acl Safe_ports port 210		# wais
acl Safe_ports port 1025-65535	# unregistered ports
acl Safe_ports port 280		# http-mgmt
acl Safe_ports port 488		# gss-http
acl Safe_ports port 591		# filemaker
acl Safe_ports port 777		# multiling http
acl CONNECT method CONNECT

# Access permissions
http_access deny !Safe_ports
http_access deny CONNECT !SSL_ports
http_access allow SI_Administratif
http_access allow SI_Usuel
http_access deny all

# Ports configuration
http_port 3128 ssl-bump cert=/etc/squid/certs/squid-ca-cert-key.pem generate-host-certificates=on dynamic_cert_mem_cache_size=16MB
https_port 3129 intercept ssl-bump cert=/etc/squid/certs/squid-ca-cert-key.pem generate-host-certificates=on dynamic_cert_mem_cache_size=16MB

# SSL bumping configuration
sslcrtd_program /usr/lib64/squid/ssl_crtd -s /var/lib/ssl_db -M 16MB
acl step1 at_step SslBump1
ssl_bump peek step1
ssl_bump bump all
ssl_bump splice all

# Miscellaneous configurations
coredump_dir /var/spool/squid
refresh_pattern ^ftp:		1440	20%	10080
refresh_pattern ^gopher:	1440	0%	1440
refresh_pattern -i (/cgi-bin/|\?) 0	0%	0
refresh_pattern .		0	20%	4320
