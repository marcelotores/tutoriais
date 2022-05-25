# Backup

Existem três tipos de backups no postgres

- SQL dump
- Backup a Nível de Sistema de arquivo
- Arquivamento Contínuo

## SQL dump

**dump**

```
pg_dump dbname > dumpfile 
```
> O pg_dump faz backup apenas de banco, esquemas ou tabelas individuais. Para todo o cluster, use o pg_dumpall.

**Restore**

```
createdb -T template0 dbname
psql dbname < dumpfile 
```

> Antes de restaurar um dump SQL, todos os usuários que possuem objetos ou receberam permissões em objetos no banco de dados despejado já devem existir. Caso contrário, a restauração falhará ao recriar os objetos com a propriedade e/ou permissões originais. 
> Perceba que o banco _dbname_ não é criado automaticamente, então voce deve criá-lo antes, assim como todos os bancos de dados dos quais fizer o dump.

**dumpall**

O pg_dumpall fará backup de todo o cluster. No entanto você deve criar manualmente cada banco de dados que faz parte do cluster. Outros objetos como usuários serão criado automaticamente.

```
pg_dumpall > dumpfile
```

**restore**

```
psql -f dumpfile postgres
```

> É sempre necessário ter acesso de superusuário ao banco de dados ao restaurar um dump pg_dumpall

## Backup a Nível de Sistema de Arquivos

Uma cópia do dos dados que pode ser feita utilizando qualquer ferramenta.

```
tar -cf backup.tar /usr/local/pgsql/data
```

O servidor de banco de dados deve está parado. Não basta bloquear as próximas conexões, pois o buffers pode conter dados.

### Utilizando o rsync. 

1. Primeiro faz `rsync` com o banco ativado.
2. Após, faz `rxync –checksum` com o banco parado. O segundo `rxync` levará menos tempo, pois praticamente todos irão para lá com o primeiro `sync`. O checksum serve para o `rsync` fazer uma verificação cada vez que os arquivos tiverem o mesmo tamanho.
 
         
## Arquivamento Contínuo

<!-- Escreva aqui -->
