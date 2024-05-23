# records.config - Apache Traffic Server Configuration

# Enable or disable Traffic Server
CONFIG proxy.config.http.enabled INT 1

# Set the HTTP listening port
CONFIG proxy.config.http.server_ports STRING 8080

# Set the cache directory and size
CONFIG proxy.config.cache.ram_cache.size INT 256M
CONFIG proxy.config.cache.ram_cache.compress INT 1
CONFIG proxy.config.cache.disk.storage_size INT 1G

# Logging configuration
CONFIG proxy.config.log.logging_enabled INT 1
CONFIG proxy.config.log.logfile_perm STRING 0644
CONFIG proxy.config.log2.logging_enabled INT 1
CONFIG proxy.config.log2.logfile_perm STRING 0644

# DNS settings
CONFIG proxy.config.dns.enabled INT 1
CONFIG proxy.config.dns.resolv_conf STRING /etc/resolv.conf
CONFIG proxy.config.dns.dedicated_thread INT 0
CONFIG proxy.config.dns.splitDNS.enabled INT 0

# Cache settings
CONFIG proxy.config.cache.http.enabled INT 1
CONFIG proxy.config.http.cache.required_headers INT 2
CONFIG proxy.config.http.cache.ignore_client_cc_max_age INT 1
CONFIG proxy.config.http.cache.ignore_server_no_cache INT 0
CONFIG proxy.config.http.cache.when_to_revalidate INT 1

# Timeouts
CONFIG proxy.config.http.transaction_no_activity_timeout_in INT 30
CONFIG proxy.config.http.keep_alive_no_activity_timeout_in INT 60
CONFIG proxy.config.http.keep_alive_no_activity_timeout_out INT 60
CONFIG proxy.config.http.transaction_active_timeout_in INT 900
CONFIG proxy.config.http.origin_max_connections INT 50

# Security settings
CONFIG proxy.config.url_remap.pristine_host_hdr INT 1
CONFIG proxy.config.ssl.client.cert.filename STRING NULL
CONFIG proxy.config.ssl.client.private_key.filename STRING NULL

# Proxy Protocol settings
CONFIG proxy.config.http.server_ports STRING 8080:tr-incoming=1
CONFIG proxy.config.net.connections_throttle INT 30000

# Network settings
CONFIG proxy.config.net.defer_accept INT 0
CONFIG proxy.config.net.connections_max INT 100000

# Forward Proxy settings
CONFIG proxy.config.url_remap.remap_required INT 0
CONFIG proxy.config.http.forward.proxy_auth_to_parent INT 0
