## Ldap

```bash
cn=admin,dc=example,dc=com
admin
```

## Add

```bash
docker run --rm --entrypoint \
    cat osixia/openldap:1.3.0 /container/service/slapd/assets/test/new-user.ldif > \
    resource/new-user.ldif

ldapadd -x -D "cn=admin,dc=example,dc=org" \
    -w admin \
    -f resource/new-user.ldif \
    -H ldap://localhost -ZZ

ldapadd -x -D "cn=admin,dc=example,dc=org" \
    -w admin \
    -f resource/new-user.ldif \
    -H ldap://localhost
```