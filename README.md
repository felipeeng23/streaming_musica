# 🎵 Sistema de Streaming de Música - Banco de Dados (SQL)

## 📌 Sobre o Projeto

Este repositório contém um **modelo de banco de dados relacional** para um sistema de **streaming de música**, projetado em **SQL**. O banco de dados gerencia usuários, artistas, álbuns, músicas e playlists, permitindo um funcionamento estruturado e escalável para plataformas musicais.

## 🗄️ Estrutura do Banco de Dados

Abaixo está um resumo das principais tabelas e seus relacionamentos:

### **1️⃣ Usuários (`usuarios`)

- `id` (INT, PRIMARY KEY, AUTO_INCREMENT) → Identificador único.
- `nome` (VARCHAR) → Nome do usuário.
- `email` (VARCHAR, UNIQUE) → E-mail único do usuário.
- `senha` (VARCHAR) → Senha protegida.

### **2️⃣ Artistas (`artistas`)

- `id` (INT, PRIMARY KEY, AUTO_INCREMENT) → Identificador do artista.
- `nome` (VARCHAR) → Nome do artista ou banda.
- `genero` (VARCHAR) → Gênero musical.

### **3️⃣ Álbuns (`albuns`)

- `id` (INT, PRIMARY KEY, AUTO_INCREMENT) → Identificador do álbum.
- `nome` (VARCHAR) → Nome do álbum.
- `artista_id` (FOREIGN KEY) → Referência à tabela `artistas`.
- `ano_lancamento` (YEAR) → Ano de lançamento do álbum.

### **4️⃣ Músicas (`musicas`)

- `id` (INT, PRIMARY KEY, AUTO_INCREMENT) → Identificador da música.
- `nome` (VARCHAR) → Nome da música.
- `album_id` (FOREIGN KEY) → Referência ao álbum correspondente.
- `duracao` (TIME) → Duração da faixa.

### **5️⃣ Playlists (`playlists`)

- `id` (INT, PRIMARY KEY, AUTO_INCREMENT) → Identificador da playlist.
- `usuario_id` (FOREIGN KEY) → Criador da playlist.
- `nome` (VARCHAR) → Nome da playlist.

### **6️⃣ Relacionamento entre Playlists e Músicas (`playlist_musicas`)

- `id` (INT, PRIMARY KEY, AUTO_INCREMENT) → Identificador do relacionamento.
- `playlist_id` (FOREIGN KEY) → Referência à playlist.
- `musica_id` (FOREIGN KEY) → Música adicionada à playlist.

## 🔗 Modelo Entidade-Relacionamento (MER)



## 🚀 Como Utilizar

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/seu-repositorio.git
   ```
2. Execute o script SQL em um banco de dados MySQL ou PostgreSQL.
3. Conecte sua aplicação ao banco e comece a testar consultas!

## ☁️ Implantação no Google Cloud Platform (GCP)

### Criando uma instância MySQL no GCP
1. Acesse o Google Cloud Console: [https://console.cloud.google.com](https://console.cloud.google.com)
2. No menu **SQL**, clique em **Criar Instância** e selecione **MySQL**.
3. Configure os detalhes da instância:
   - Nome da instância: `streaming-db`
   - Versão: MySQL 8.0
   - Defina um usuário e senha para acessar o banco.
4. Clique em **Criar** e aguarde a implantação.

### Conectando o Google Colab ao MySQL no GCP
1. No seu notebook do **Google Colab**, instale e importe o conector do MySQL:
   ```python
   !pip install mysql-connector-python
   import mysql.connector
   ```
2. Conecte-se ao banco de dados da instância do GCP:
   ```python
   connection = mysql.connector.connect(
       host='IP_DA_INSTANCIA',
       user='USUARIO',
       password='SENHA',
       database='streaming_db'
   )
   cursor = connection.cursor()
   ```
3. Execute uma consulta SQL de teste:
   ```python
   cursor.execute("SHOW TABLES;")
   for table in cursor:
       print(table)
   ```
4. Feche a conexão quando terminar:
   ```python
   cursor.close()
   connection.close()
   ```

## 📌 Tecnologias Utilizadas

- **MySQL** / **PostgreSQL** (compatível com ambos)
- **Google Cloud SQL** para armazenamento no GCP
- **Google Colab** para conexão remota
- **Diagramas ER** para modelagem
- **SQL Structured Query Language**

## 📝 Contribuições

Sinta-se à vontade para **abrir issues**, **sugerir melhorias** e **contribuir** para aprimorar esse banco de dados. Toda ajuda é bem-vinda! 😊

## 📩 Contato

📧 E-mail: felipedoliveira09@hotmail.com]
🔗 LinkedIn: [seu-linkedin](https://www.linkedin.com/in/felipe-souza-de-oliveira/)

---
🛠️ **Desenvolvido por [Felipe Oliveira]** 🚀

