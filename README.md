# 📚 Aula Prática: Conexão com Banco de Dados usando JDBC

Este repositório contém um exemplo simples feito como parte de uma aula de JDBC em Java, com foco em como estabelecer uma conexão com um banco de dados MySQL utilizando boas práticas e tratamento de exceções.

## 🎯 Objetivo
Demonstrar como se conectar a um banco de dados MySQL via JDBC

Separar as configurações sensíveis em um arquivo .properties

Aplicar o tratamento de exceções com uma classe personalizada

Aprender a configurar o driver do MySQL Connector no IntelliJ IDEA


## 🧱 Estrutura do Projeto

ProjetoCrudCurso/

├── src/

│   ├── application

│   │   └── Program.java           → Classe principal que testa a conexão

│   └── db/

│       ├── DB.java                → Classe utilitária para gerenciar a conexão

│       └── dbException.java       → Classe personalizada para tratar exceções de banco

├── db.properties                 → Arquivo de configuração do banco (usuário, senha, URL)

└── java-libs/
    └── java-connectors/          → Pasta contendo o driver MySQL Connector (JAR)



## ⚠️ Tratamento de Exceções
O projeto faz uso de uma classe personalizada de exceção chamada dbException, que estende RuntimeException.

**🔹 Para que serve?**

Ela encapsula as exceções do tipo SQLException e IOException, que podem ocorrer ao:

Carregar o arquivo de propriedades (db.properties)

Estabelecer ou fechar a conexão com o banco de dados

Dessa forma, o código fica mais limpo, e o tratamento de erro é centralizado e mais descritivo.

## 🛠 Configuração do Ambiente

**🔹 1. Instalação do MySQL**

Foi instalado o MySQL localmente

Durante a instalação, foi definido:

**Usuário: root** 
**Senha: #####**

Foi criado o banco de dados coursejdbc via MySQL Workbench ou terminal

**🔹 2. Arquivo de Configuração (db.properties)**

**user=root**

**password=#####**

dburl=jdbc:mysql://localhost:3306/coursejdbc

useSSL=false

**🔹 3. Instalação do Driver JDBC (MySQL Connector/J)**

Foi feito o download da versão ZIP do MySQL Connector/J

O arquivo .jar (ex: mysql-connector-java-8.x.x.jar) foi extraído e movido para:

java-libs/java-connectors/

**🔹 4. Configuração no IntelliJ IDEA**

Para que o IntelliJ reconheça o driver JDBC:

Vá em File > Project Structure > Modules

Aba Dependencies

Clique em + > JARs or directories

Adicione a pasta: java-libs/java-connectors/

Aplique e feche

## 🚀 Execução

Para testar a conexão:

Compile e execute a classe Program.java

Se tudo estiver correto, a seguinte mensagem será exibida:

![image](https://github.com/user-attachments/assets/e057d4a9-ed4a-4084-bc11-fe3223261143)


## 📌 Requisitos

Java 21

IntelliJ IDEA

MySQL instalado localmente

Driver JDBC (MySQL Connector/J)
