# Cluster

### Criar e iniciar um cluster

O cluster pode ser criado através da ferramenta `initdb` em `/usr/lib/postgresql/13/bin/bin`.

```
/usr/lib/postgresql/13/bin/initdb -D /usr/local/pgsql/data
```

Também pode-se usar a ferramenta `pg_ctl`

```
pg_ctl -D clus1 initdb
```

Nos comandos acima, -D especifica o local onde o cluster será criado. Nos exemplos, o cluster de nome *data* será criado em `/usr/local/pgsql` e *clus1* será criado no diretório atual. Perceba que *data* e *clus1* são diretórios que contêm arquivos de configuração e dados.

> Os comandos acima devem ser executados pelo usuário postgres.
