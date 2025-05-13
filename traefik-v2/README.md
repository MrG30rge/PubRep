This is a traefik configuration with authentik as an authentication middleware (config.yml - 'forwardAuth')
Replacing traefik default Web certs with a domain/internal own cert (config.yml - 'tls').

To make use of authentik via traefik, a new traefik label must be added to any new pod/app:
"traefik.http.routers.${SERVICE_NAME}-secure.middlewares=authentik@file"

Also, a new (proxy forward-auth) application must be configured in authentik.
