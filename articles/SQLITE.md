# SQLITE

## Acessando um Banco de Dados

Após utilizar esse comando o banco de dados "exemplo.db" será criado (se já não existe) e você estará dentro do CLI (Command Line Interface) do SQLite3 para personaliza-lo.

```bash
sqlite3 exemplo.db
```

##  Criando uma Tabela

No sqlite3 CLI:

```sqlite
CREATE TABLE COMPANY(
   ID INT PRIMARY KEY     NOT NULL,
   NAME           TEXT    NOT NULL,
   AGE            INT     NOT NULL,
   ADDRESS        CHAR(50),
   SALARY         REAL
);
```

## Deletando uma Tabela

No sqlite3 CLI:

```sqlite
DROP TABLE COMPANY;
```

## Lendo dados de um Banco de Dados

Abra o banco de dados "database.sqlite":

```
sqlite3 database.sqlite
```

Agora dentro do CLI para descobrir todas as tabelas do banco:

```sqlite
sqlite> .tables
```

Retorna:

```
User
```

E para conseguir mais uma informação sobre alguma dessas tables:

```sqlite
.schema User
```

Retorna:

```sqlite
CREATE TABLE `User` (
	`UserId`	INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT UNIQUE,
	`FirstName`	TEXT NOT NULL,
	`LastName`	INTEGER NOT NULL,
	`Age`	INTEGER NOT NULL
);
```

