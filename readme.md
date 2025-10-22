# FinanSync: Seu Dashboard Financeiro Inteligente

FinanSync é uma aplicação web completa (full-stack) projetada para oferecer uma visão clara e detalhada sobre suas finanças pessoais. Com uma interface intuitiva e gráficos interativos, a plataforma permite que os usuários gerenciem suas transações, identifiquem padrões de gastos e tomem decisões financeiras mais inteligentes.

## ⚙️ Funcionalidades Principais

-   **Autenticação Segura:** Sistema completo de registro e login de usuários com autenticação baseada em JSON Web Tokens (JWT).
-   **Dashboard Interativo:** Uma visão centralizada com todas as suas transações financeiras.
-   **Gerenciamento de Transações (CRUD):** Adicione, visualize, edite e exclua suas receitas e despesas facilmente.
-   **Filtragem Avançada:** Filtre suas transações por descrição e intervalo de datas para encontrar exatamente o que você procura.
-   **Visualização de Dados:** Um conjunto de gráficos dinâmicos que se atualizam com base nos seus filtros, oferecendo insights valiosos:
    -   **Gráfico de Barras:** Comparativo total de Receitas vs. Despesas.
    -   **Gráfico de Pizza (Setor):** Distribuição percentual das suas despesas por categoria.
    -   **Gráfico de Bolhas:** Análise multidimensional que cruza o valor gasto, a quantidade de transações e a categoria de despesa.
    -   **Mapa de Calor (Heatmap):** Calendário anual que destaca os dias com maior volume de gastos.
-   **Importação Automática (Em Desenvolvimento):** Funcionalidade para sincronizar com sua conta do Gmail e importar transações de extratos bancários enviados por e-mail, automatizando a entrada de dados.

## 🚀 Tecnologias Utilizadas

Este projeto foi construído com uma arquitetura moderna, separando claramente as responsabilidades entre o frontend e o backend.

### Backend

-   **Linguagem:** Java 17+
-   **Framework:** Spring Boot 3
    -   **Spring Security:** Para gerenciamento de autenticação e autorização com JWT.
    -   **Spring Data JPA:** Para persistência de dados e comunicação com o banco de dados.
    -   **Spring Web:** Para a criação da API RESTful.
-   **Banco de Dados:** PostgreSQL (ou qualquer banco relacional compatível com JPA).
-   **APIs Externas:** Integração com a API do Gmail via OAuth 2.0.

### Frontend

-   **Framework:** React 18+ (utilizando Vite para o ambiente de desenvolvimento).
-   **Gerenciamento de Estado:** React Context API para o estado de autenticação.
-   **Roteamento:** React Router DOM para a navegação entre páginas.
-   **Comunicação com API:** Axios, com interceptors para tratamento automático de tokens expirados.
-   **Visualização de Dados:**
    -   `react-chartjs-2`: Para os gráficos de Barra, Pizza e Bolhas.
    -   `react-calendar-heatmap`: Para o mapa de calor de calendário.
-   **Estilização:** Tailwind CSS para uma estilização moderna e responsiva.
-   **Notificações:** `react-toastify` para feedback visual das operações do usuário.

## ⚙️ Como Executar o Projeto

Para executar este projeto localmente, você precisará ter o **Java (JDK)**, o **Node.js** e um **banco de dados PostgreSQL** instalados.

### Backend

1.  Clone o repositório do backend.
2.  Configure as credenciais do seu banco de dados no arquivo `src/main/resources/application.properties`.
3.  Configure as credenciais do OAuth 2.0 para a API do Gmail, se desejar usar a funcionalidade de importação.
4.  Execute a aplicação a partir da sua IDE ou via linha de comando com o Maven/Gradle.
    ```
    ./mvnw spring-boot:run
    ```
5.  O servidor backend estará rodando em `http://localhost:8080`.

### Frontend

1.  Clone o repositório do frontend.
2.  Instale as dependências do projeto.
    ```
    npm install
    ```
3.  Inicie o servidor de desenvolvimento.
    ```
    npm run dev
    ```
4.  A aplicação estará acessível em `http://localhost:5173` (ou a porta indicada pelo Vite).
