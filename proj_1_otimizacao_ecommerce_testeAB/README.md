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

### **Metodologia para a Análise dos Dados**

#### **Análise Primária: Teste Qui-Quadrado**

O **Teste Qui-Quadrado ($\chi^2$)** foi utilizado para validar as diferenças nas taxas de conversão (comparação de proporções). Este teste é o **padrão da indústria** para essa finalidade e confirmou a significância estatística do resultado.

#### **Análise de Segmentação: Regressão Logística**

Para isolar o efeito do teste A/B e verificar o impacto de variáveis de segmento, foi utilizada a **Regressão Logística**. Este modelo avançado permitiu quantificar a Razão de Chances (*Odds Ratio*) de conversão, controlando simultaneamente o efeito de Dispositivo, Categoria e Fonte de Tráfego.

---

### **Resultados Chave do Teste A/B**

O Teste A/B demonstrou uma clara e robusta vitória do grupo de Teste (novo design de página de produto):

| Etapa do Funil | Taxa de Conversão do Controle | Taxa de Conversão do Teste | Lift (%) | Conclusão Estatística |
| :--- | :--- | :--- | :--- | :--- |
| **View $\rightarrow$ Add to Cart** | $10.38\%$ | $14.29\%$ | **+37.65%** | **Significativo** ($p \ll 0.05$) |
| **Add to Cart $\rightarrow$ Purchase** | $25.08\%$ | $29.59\%$ | **+17.96%** | **Significativo** ($p \ll 0.05$) |

#### **Insights da Regressão Logística:**

O modelo de Regressão Logística reforçou a conclusão primária e forneceu o principal *insight* de segmentação:

1.  **Vitória Isolada:** Um usuário no grupo de Teste teve **65.15% mais chance de converter** (*Odds Ratio = 1.65*) em comparação com o grupo de Controle, provando que o novo design é o principal *driver* do aumento.
2.  **Consistência:** Nenhuma das variáveis de segmento (dispositivo, tráfego ou localização) teve um impacto estatisticamente significativo na conversão final.
    * **Conclusão de Negócio:** O novo design funciona de maneira **consistente** em todos os segmentos, simplificando a implementação e eliminando a necessidade de otimizações segmentadas imediatas.

---

### **Visualização e Design (Power BI + UX)**

O dashboard foi construído com foco em Hierarquia Visual e Design Clean & Modern (UX), utilizando um template customizado no Power BI.

* **Página 1 (Performance):** Focada em provas (KPIs e Funil) e robustez (segmentação por dispositivo e tráfego).

* **Página 2 (Conclusão):** Dedicada exclusivamente às Recomendações Estratégicas e ao resumo do impacto financeiro do Teste.

**Destaque: O Verde (Teste) e o Cinza (Controle) são usados consistentemente para guiar o olhar e comunicar a vitória do novo design de forma instantânea.**

---

### **Tecnologias Utilizadas**

* **Linguagem de Programação:** `Python`
* **Manipulação de Dados:** `Pandas` e `NumPy`
* **Análise Estatística:** `SciPy` (Teste Qui-Quadrado) e `Statsmodels` (Regressão Logística)
* **Visualização (dashboard):** `Power BI`
---

### **Plano de Ação: 5 Recomendações Estratégicas**

Com base na significância estatística e no impacto financeiro, o projeto conclui com um plano de ação imediato para a equipe de Produto e Liderança:

1. **🚀 Implementação Imediata:** Aprovar e lançar o novo design para **100% da base** de usuários o mais rápido possível, interrompendo o Teste A/B.

* **Motivo:** O Lift é estatisticamente provado e garante que mais vendas estão sendo perdidas a cada dia em que o design antigo permanece ativo.

2. **💰 Foco no Ganho Financeiro:** Comunicar o **Ganho de Receita de R$ 143 Mil** à liderança.

* **Motivo:** O projeto é um driver financeiro primário e justificou o investimento em otimização de UX/Produto.

3. **✅ Robustez da Solução:** Manter o design como uma **solução única** (sem segmentação por dispositivo ou tráfego).

* **Motivo:** A Regressão Logística provou que o benefício do design é **consistente** em todos os segmentos, simplificando a implementação.

4. **📉 Otimização de Marketing:** O time de Marketing deve revisar o **Custo por Aquisição (CPA)**.

* **Motivo:** A taxa de conversão mais alta da página de produto torna o gasto com tráfego mais **eficiente**.

5. **🎯 Próximo Foco:** Mudar o foco da otimização para a **etapa de Checkout/Pagamento**.

* **Motivo:** O Funil indica que, após o novo design, a maior taxa de abandono ocorre agora entre *Cart* e *Purchase*, sendo a próxima área de maior potencial de retorno.