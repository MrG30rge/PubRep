# This example is using "admin" as the username and "pass1234" as the password (db2 as the encryption)

# Run this to get the output on screen:
docker run --rm -it alpine:latest sh -c "apk add --no-cache apache2-utils && htpasswd -nbB admin pass1234"

# Run this to generate the password and add it to your .env file:
echo "TRAEFIK_DASHBOARD_CREDENTIALS=$(docker run --rm -it alpine:latest sh -c "apk add --no-cache apache2-utils && htpasswd -nbB admin pass123" | tail -n 2 | head -n 1)" >> .env

