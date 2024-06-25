# LDAP

# URL du serveur (SSL est automatiquement activé avec le protocole ldaps)
auth.ldap.server.url = ldap://votre_serveur_ldap:389

# Base de recherche pour les utilisateurs
auth.ldap.user.base = ou=users,dc=example,dc=com

# Base de recherche pour les groupes
auth.ldap.group.base = ou=groups,dc=example,dc=com

# Modèle pour rechercher les utilisateurs par identifiant
auth.ldap.user.filter = (uid={0})

# Attribut identifiant de l'utilisateur : uid / cn
auth.ldap.user.id-attribute = uid

# Modèle pour rechercher les groupes par identifiant d'utilisateur
auth.ldap.group.filter = (uniqueMember=uid={0},ou=users,dc=example,dc=com)

# Utilisateur système pour l'authentification LDAP
auth.ldap.server.auth.user = uid=admin,ou=system
# Mot de passe système
auth.ldap.server.auth.password = secret

# Type d'authentification SASL : simple (par défaut) / CRAM-MD5 / DIGEST-MD5 / EXTERNAL / GSSAPI
auth.ldap.server.auth.type = simple

# Utiliser StartTLS (par défaut : false)
auth.ldap.server.starttls = true

# Configurations SSL et startTLS (si nécessaire)
# Truststore
auth.ldap.server.ssl.trust-store.path =
auth.ldap.server.ssl.trust-store.password =
auth.ldap.server.ssl.trust-store.type =
auth.ldap.server.ssl.trust-store.aliases =

# Keystore
auth.ldap.server.ssl.key-store.path =
auth.ldap.server.ssl.key-store.password =
auth.ldap.server.ssl.key-store.type =
auth.ldap.server.ssl.key-store.aliases =

# Certificats de confiance
auth.ldap.server.ssl.cert.trust-path =
# Certificat d'authentification
auth.ldap.server.ssl.cert.auth-path =
# Clé d'authentification
auth.ldap.server.ssl.cert.key-path =

# Délais (timeouts)
# Temps que les connexions bloqueront en secondes
auth.ldap.server.connect-timeout = 10
# Temps d'attente des réponses en secondes
auth.ldap.server.response-timeout = 10
