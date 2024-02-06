# c-_sql
## repositorio experimental
MySQL Connector/C++: Esta é a biblioteca oficial fornecida pela Oracle para se conectar ao MySQL usando C++. Ela fornece uma API orientada a 
objetos para trabalhar com MySQL.

SQLiteCpp: Esta é uma biblioteca C++ que oferece uma API simples e fácil de usar para trabalhar com o SQLite, um banco de dados SQL embutido.

cppdb: cppdb é uma biblioteca C++ que oferece uma API de alto nível para trabalhar com bancos de dados SQL. Ele suporta vários backends de banco
de dados, incluindo SQLite, PostgreSQL, MySQL e outros.

SOCI: SOCI é uma biblioteca C++ que fornece uma camada de abstração sobre diferentes bibliotecas de acesso a banco de dados. Ele suporta uma vari
edade de backends de banco de dados, incluindo SQLite, PostgreSQL, MySQL, Oracle, entre outros.

ODBC: ODBC (Open Database Connectivity) não é exatamente uma biblioteca C++, mas é uma API padrão para acessar bancos de dados SQL. Existem várias
bibliotecas C++ que fornecem suporte para ODBC, permitindo que você se conecte a uma variedade de fontes de dados usando ODBC.

dockerfile
```shell
# Use a imagem base com suporte para C++ e compilador
FROM gcc:latest

# Copie os arquivos do código fonte do aplicativo para o contêiner
COPY . /app

# Defina o diretório de trabalho como o diretório do aplicativo
WORKDIR /app
# Instale as dependências do MySQL e do cliente MySQL C++
RUN apt-get update && apt-get install -y \
    libmysqlclient-dev \
    && rm -rf /var/lib/apt/lists/*

# Compile o aplicativo C++
RUN g++ -o myapp main.cpp -lmysqlclient

# Comando padrão para executar o aplicativo
CMD ["./myapp"]

```
