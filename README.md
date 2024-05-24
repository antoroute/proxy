# Activer le serveur HTTP
CONFIG proxy.config.http.enabled INT 1

# Activer le cache HTTP
CONFIG proxy.config.http.cache.http INT 1

# Configurer les ports d'écoute HTTP
CONFIG proxy.config.http.server_ports STRING 8080

# Configurer les logs
CONFIG proxy.config.log.logging_enabled INT 1
CONFIG proxy.config.log.squid_log_enabled INT 1

# Désactiver le reverse proxy
CONFIG proxy.config.reverse_proxy.enabled INT 0

# Autoriser le remap URL
CONFIG proxy.config.url_remap.remap_required INT 0

# Paramètres de cache
CONFIG proxy.config.cache.ram_cache.size INT 268435456
CONFIG proxy.config.cache.storage_size INT 1073741824

# Paramètres DNS
CONFIG proxy.config.dns.enabled INT 1
CONFIG proxy.config.dns.resolv_conf STRING /etc/resolv.conf

# Paramètres de sécurité
CONFIG proxy.config.url_remap.pristine_host_hdr INT 1
