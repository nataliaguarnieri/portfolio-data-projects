# 📊 Análise e Otimização para E-commerce: Um Estudo de Caso com Teste A/B

Este projeto tem como objetivo principal demonstrar habilidades em **análise de dados**, **testes estatísticos (Teste A/B)** e **visualização de dados**, utilizando um conjunto de dados sintético que simula a jornada de compra em um e-commerce. O projeto é um exemplo prático de como dados podem ser usados para tomar decisões de produto e marketing.

---

### **Contexto do Problema**

O setor de e-commerce é altamente competitivo, e a otimização da experiência do usuário é crucial para o sucesso. Neste estudo de caso, simulamos uma empresa que implementou uma nova versão de sua página de produto e precisa avaliar se a mudança teve um impacto significativo na taxa de conversão.

A questão de negócio a ser respondida é: **o novo design da página de produto leva a um aumento estatisticamente significativo na taxa de conversão do funil de vendas?**

---

### **Objetivo do Projeto**

O projeto é dividido em etapas claras, cada uma focada em uma habilidade específica:

1.  **Geração e Estrutura de Dados:** Criar um conjunto de dados único e robusto que combine informações de usuários, sessões, produtos e eventos de navegação.
2.  **Análise e Teste A/B:** Analisar o funil de vendas dos grupos de controle e teste, utilizando análise estatística para validar a hipótese do teste A/B.
3.  **Visualização e Insights:** Construir um dashboard com as principais métricas e resultados do experimento, tornando a informação acessível e fácil de ser interpretada por times de negócio.

---

### **Estrutura de Dados**

Para esta análise, utilizamos uma tabela única que consolida todos os eventos de interação do usuário com o site. Essa estrutura foi projetada para otimizar a análise do funil e do teste A/B, garantindo que todas as informações necessárias estejam em um só lugar.

| Campo | Tipo de Dado | Descrição |
| :--- | :--- | :--- |
| `event_id` | `STRING` | ID único de cada ação. |
| `user_id` | `INT` | Identificador do usuário. |
| `group` | `STRING` | Grupo do teste A/B (`control` ou `test`). |
| `timestamp` | `TIMESTAMP` | Data e hora em que a ação ocorreu. |
| `event_type` | `STRING` | Tipo de evento (`view_page`, `add_to_cart`, `purchase`, etc.). |
| `session_id` | `INT` | Identificador da sessão de navegação. |
| `product_id` | `INT` | ID do produto. |
| `product_category`| `STRING` | Categoria do produto. |
| `product_price` | `FLOAT` | Preço do produto. |
| `quantity` | `INT` | Quantidade de um item. |
| `order_id` | `INT` | ID da compra (para o evento `purchase`). |
| `total_value` | `FLOAT` | Valor total da compra (para o evento `purchase`). |
| `device_type` | `STRING` | Tipo de dispositivo do usuário. |
| `traffic_source` | `STRING` | Fonte de tráfego. |

---

### **Metodologia de Geração de Dados**

Os dados foram gerados em Python de forma controlada para simular um cenário realista de teste A/B. As principais características da metodologia incluem:

* **Taxas de Conversão Aleatórias:** As probabilidades de conversão do funil para o grupo de teste foram geradas com uma pequena variação aleatória. Isso garante que o resultado da análise seja uma **descoberta genuína** e não uma conclusão pré-determinada.
* **Funil Sequencial:** A simulação segue a jornada de compra, onde um evento de compra só pode ocorrer após a adição ao carrinho, que só ocorre após a visualização da página.
* **Estrutura de Tabela Única:** Todos os eventos foram consolidados em uma única tabela para simplificar a análise, sem a necessidade de joins complexos, mantendo o foco no objetivo do projeto.

---

### **Tecnologias Utilizadas**

* **Linguagem de Programação:** `Python`
* **Manipulação de Dados:** `Pandas` e `NumPy`
* **Análise Estatística:** `SciPy` (a ser utilizado)
* **Visualização (dashboard):** `Power BI` (a ser utilizado)