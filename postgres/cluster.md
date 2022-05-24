# Cluster

### Criando um cluster

O cluster pode ser criado através da ferramenta `initdb` em `/usr/lib/postgresql/13/bin/bin`.

```
/usr/lib/postgresql/13/bin/initdb -D /usr/local/pgsql/data
```

Também pode-se usar a ferramenta `pg_ctl`

```
pg_ctl -D clus1 initdb
```

Nos comandos acima, a opção `-D` especifica o local onde o cluster será criado. Nos exemplos, o cluster de nome *data* será criado em `/usr/local/pgsql` e *clus1* será criado no diretório atual. Perceba que *data* e *clus1* são diretórios que contêm arquivos de configuração e dados.

> Os comandos acima devem ser executados pelo usuário postgres.

### Iniciando um cluster

O cluster pode ser iniciado por meio da ferramenta `pg_ctl` dentro de `/usr/lib/postgresql/13/bin/bin`.

```
/usr/lib/postgresql/13/bin/pg_ctl -D /usr/local/pgsql/data2 -l /tmp/postgres.log start
```
> o arquivo de log pode ser criado com o parâmetro `-l` em qualquer local.

### Backup

Existem três tipos de backups no postgres

- SQL dump
- Backup a Nível de Sistema de arquivo
- Arquivamento Contínuo

### SQL dump

### Backup a Nível de Sistema de Arquivos
Uma cópia do dos dados que pode ser feita utilizando qualquer ferramenta.
ex.: tar -cf backup.tar /usr/local/pgsql/data
O servidor de banco de dados deve está parado
Não basta bloquear as próximas conexões, pois o buffers pode conter dados.
Pode usar o rsync. 
Primeiro faz rsync com o banco ativado.
Após, faz rxync –checksum com o banco parado. O segundo rxync levará menos tempo, pois praticamente todos irão para lá com o primeiro sync. O checksum serve para o rsync fazer uma verificação cada vez que os arquivos tiverem o mesmo tamanho.
 
         
### Arquivamento Contínuo


