# Tablespace

Tablespace permite que se defina locais no sistema de arquivos para representar os objetos do banco de dados
(banco de dados, tabelas ...). Ou seja, você armazena seus objetos em outros locais diferentes do cluster.
No entando aquele objeto ainda fará parte do cluster, de forma que metadados serão usados.
Isso serve caso algum servidor de banco fique sem espaço e não seja possível estender seu tamanho. Dessa forma 
pode-se criar um no spacetable até mesmo em outro disco diferente.

 
#### exemplo de uso

```
CREATE TABLESPACE fastspace LOCATION '/ssd1/postgresql/data';
```

O tablespace acima é criado em `/ssd1/postgresql/data`.
> O subdiretório /ssd1/postgresql/data já deve ter sido criado antes no sistema de arquivos




