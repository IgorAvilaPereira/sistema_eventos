# Sistema de Eventos — 2025/2  

Projeto desenvolvido durante a disciplina **Implementação em Banco de Dados**, ministrada pelo **Prof. Igor** em 2025/2, com participação da turma.  

Este repositório contém uma aplicação web construída com **Java**, **Javalin**, **Mustache**, **PostgreSQL**, **HTML/CSS (Bootstrap)**, além de suportar **upload de arquivos**, **busca assíncrona** e **controle de acesso via login**. O sistema implementa o **padrão DAO** para persistência.

---

## 🧩 Tecnologias Utilizadas

- **Java 17+**
- **Javalin**
- **Mustache**
- **PostgreSQL**
- **JDBC / DAO Pattern**
- **HTML5 & CSS3**
- **Bootstrap 5**
- **JavaScript (Vanilla)** — para requisições assíncronas  
- **Upload de Arquivos**
- **Autenticação & Autorização**

---

## 📌 Funcionalidades Principais

- Cadastro, edição e remoção de eventos  
- **Busca assíncrona** de eventos usando JavaScript vanilla (fetch API)  
- Visualização detalhada de eventos  
- Upload de imagens/arquivos relacionados  
- Sistema de login com permissões/restrições  
- Renderização dinâmica com Mustache  
- Persistência em PostgreSQL via DAO  
- Organização em camadas (MVC simplificado)

---

## 📁 Estrutura do Projeto

```
/src
 └── main
     ├── java
     │    └── ... (controllers, models, DAOs, serviços)
     ├── resources
     │    ├── templates/          (arquivos .mustache)
     │    └── public/             (CSS, JS, imagens)
     └── database
          └── dump.sql            (backup e estrutura do banco)
```

---

## 🗄️ Banco de Dados

- Sistema utiliza PostgreSQL  
- O arquivo de criação/backup do banco está localizado em:  
  **`/database/dump.sql`**  
- Configurações de conexão devem ser feitas via variáveis de ambiente ou arquivo próprio

---

## ▶️ Como Executar

1. **Clonar o repositório**
   ```bash
   git clone <url-do-repositorio>
   ```

2. **Configurar o banco de dados PostgreSQL**
   - Criar um banco  
   - Importar o arquivo `dump.sql`  

3. **Configurar variáveis de ambiente**
   ```
   DB_URL=jdbc:postgresql://localhost:5432/eventos
   DB_USER=postgres
   DB_PASSWORD=******
   ```

4. **Executar o projeto**
   ```bash
   ./mvnw clean package
   java -jar target/eventos.jar
   ```

5. Acessar no navegador:  
   **http://localhost:7000**

---

## 🔎 Busca Assíncrona (JavaScript Vanilla)

A busca de eventos funciona através de requisições assíncronas usando **fetch()**, retornando JSON e atualizando a página sem recarregar.  
Fluxo básico:

- Usuário digita na barra de pesquisa  
- JavaScript dispara requisição async  
- A API retorna os resultados filtrados  
- A página atualiza apenas a lista de eventos (DOM update)

---

## 🔒 Autenticação

Inclui:
- Login por usuário e senha  
- Sessão autenticada  
- Proteção de rotas administrativas  

---

## 📤 Upload de Arquivos

- Upload de imagens ou documentos relacionados ao evento  
- Armazenamento local configurável  
- Caminho persistido no banco de dados  


