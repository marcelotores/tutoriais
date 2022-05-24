# Cluster

### Criar e iniciar um cluster

O cluster pode ser criado através da ferramenta `initdb` em `/usr/lib/postgresql/13/bin/bin`.

```
/usr/lib/postgresql/13/bin/initdb -D /usr/local/pgsql/data
```

ou 

```
pg_ctl -D clus1 initdb
```

> Os comandos acima devem ser executados pelo usuário postgres.
