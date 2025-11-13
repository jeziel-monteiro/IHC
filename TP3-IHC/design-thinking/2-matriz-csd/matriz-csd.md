<div align="justify">

# <p align="center">Matriz CSD</p>

A Matriz de Certezas, Suposições e Dúvidas (CSD) a seguir detalha o panorama atual do projeto de desenvolvimento do aplicativo de transporte fluvial, focado na compra de passagens e envio de encomendas.

<img width="4388" height="2034" alt="Matriz CSD (Community) (1)" src="https://github.com/user-attachments/assets/922d4dc9-6298-42ee-ab2b-390c093bb2e3" />

## Análise da Matriz

### Certezas:
A seguir estão detalhados os requisitos fundamentais do projeto, agrupados por afinidade. Cada grupo define uma área central do produto, suas implicações e os próximos passos para o design e desenvolvimento.

<p align="center">
  <img src="https://github.com/user-attachments/assets/fd5b9e5d-6795-4005-8376-bc8da7ff3c9b" alt="sup" width="600"">
</p>

As Certezas definem o escopo central e inegociável do aplicativo. Elas garantem a funcionalidade principal, como o fluxo de compra de passagens, envio de encomendas e o cadastro de usuários (PF/PJ). Cobrem também a transparência total das informações, incluindo perfis detalhados de embarcações, filtros de busca (pets, veículos), informações de alimentação e o trajeto completo. Por fim, estabelecem as políticas de negócio (meia-passagem, estornos) e os requisitos fundamentais de acessibilidade (talkback) e suporte (chatbot), que avançarão diretamente para o design.

| Grupo Temático | Certezas Principais | Implicação-Chave | Ação Imediata |
| :--- | :--- | :--- | :--- |
| **1. Fluxo Principal** | Compra (passagem/encomenda), Reserva de passagem, Cadastro (PF/PJ). | O app precisa de 3 fluxos centrais claros (cadastro, compra, reserva) com regras de negócio definidas. | Mapear os *user flows* (mapas de tela) e criar as *User Stories* prioritárias. |
| **2. Descoberta e Informação** | Perfis de barcos, filtros (pets, veículos), detalhes de trajeto e alimentação. | Transparência é vital. O sucesso da conversão depende de uma busca e filtros eficientes. | Projetar os *wireframes* das telas de "Busca/Resultados" e "Detalhes da Viagem". |
| **3. Regras de Negócio** | Meia-passagem (idoso/criança), estorno por imprevistos, comprovante (app/email). | O *backend* necessita de lógica de preço flexível e integração com sistemas financeiros e de e-mail. | Detalhar as regras de negócio (critérios de estorno, validação de idade) e documentar as APIs. |
| **4. Acessibilidade e Suporte** | Função *Talkback* (baixa visão) e suporte via *chatbot*. | Acessibilidade é um requisito-base de design e código. O *chatbot* será a 1ª linha de suporte. | Incluir Requisitos de Acessibilidade (WCAG) no design e definir o escopo do *chatbot* (FAQ ou consulta). |

### Suposições: 

As Suposições representam as hipóteses que temos sobre o aplicativo e seu ecossistema. Embora baseadas em algum conhecimento, elas ainda não foram validadas e carregam um certo risco. Abordam funcionalidades que, se confirmadas, podem agregar grande valor, como a rastreabilidade das embarcações, promoções e a expansão para outras plataformas, mas que demandam investigação.

<p align="center">
  <img src="https://github.com/user-attachments/assets/5d713780-12a1-48da-a320-33c2f2530dc0" alt="sup" width="600"">
</p>

#### Plano de Validação das Suposições
Para transformar essas suposições em certezas (ou descartá-las), é crucial um plano de validação. Isso envolve pesquisa de mercado, entrevistas com usuários e análise de viabilidade técnica. Cada suposição será investigada para entender seu real impacto no valor do produto e nos recursos necessários para sua implementação, direcionando os próximos passos de pesquisa e desenvolvimento.

| Grupo Temático | Suposições Principais | Implicação-Chave / Valor Potencial | Ação Imediata (Validação) |
| :--- | :--- | :--- | :--- |
| **1. Rastreabilidade e Engajamento** | Geolocalização da embarcação; Notificações de localização. | Aumento da segurança e confiança do usuário. Potencial para engajamento contínuo durante a viagem. | **Pesquisa Técnica:** Viabilidade e custo de GPS/sinal nas rotas. **Pesquisa UX:** Entendimento do valor percebido pelo usuário. |
| **2. Estratégia de Preços e Promoções** | Alimentação e passagem com valor único; Todas as embarcações terão promoção. | Simplificação da oferta e atratividade. Impacto direto na estratégia de monetização e competitividade. | **Análise de Mercado:** Benchmarking de preços e promoções no setor. **Análise de Viabilidade:** Impacto financeiro para as embarcações. |
| **3. Expansão e Fidelização** | Versão Web; Tradução para outros idiomas; Sistema de acúmulo de pontos. | Potencial para maior alcance de usuários, conveniência e retenção. | **Pesquisa de Mercado:** Demanda por versão Web/idiomas. **Pesquisa UX:** Desejo e preferência por programas de fidelidade. |
| **4. Benefícios Agregados** | Preço único para passagem e Wi-Fi. | Aumenta o valor percebido do serviço, melhora a experiência do passageiro. | **Análise de Custos:** Viabilidade de inclusão do Wi-Fi no preço. **Pesquisa UX:** Qual a preferência do usuário por pacotes ou serviços separados. |

### Dúvidas:

As Dúvidas representam as lacunas de conhecimento mais críticas do projeto. Elas não são apenas hipóteses, mas sim questões em aberto que podem alterar fundamentalmente o modelo de negócio, o escopo operacional e a estratégia de plataforma. São os pontos que carregam maior risco e, portanto, exigem investigação imediata antes que decisões estratégicas de longo prazo sejam tomadas.

<p align="center">
  <img src="https://github.com/user-attachments/assets/24ae84b2-5e22-4030-9c90-8b66457f792f" alt="sup" width="600"">
</p>

#### Plano de Investigação das Dúvidas

O plano para endereçar essas dúvidas é focado em pesquisa estratégica e de viabilidade. Questões sobre novos fluxos de receita (assinaturas, hotéis) e expansão logística (transporte ponta-a-ponta) exigem uma análise de mercado aprofundada e um estudo de custo-benefício. A dúvida sobre a plataforma (iPhone) impacta diretamente o roadmap técnico. As respostas definirão os limites e a direção futura do produto.

### Resumo das Dúvidas do Projeto

| Grupo Temático | Dúvidas Principais | Implicação-Chave / Risco | Ação Imediata (Investigação) |
| :--- | :--- | :--- | :--- |
| **1. Modelo de Negócio** | O app terá plano por assinatura? Venderá passagens com reserva de hotéis/pousadas? | Define novos fluxos de receita versus o risco de complexidade e perda de foco no produto principal. | **Pesquisa de Mercado:** Análise de concorrência e modelos de negócio similares. **Definição Estratégica:** Alinhamento com a visão de longo prazo do produto. |
| **2. Expansão Logística** | Suporte logístico (passageiro/encomenda) até o barco? Regras para encomendas de alimentos? | Transforma o app de um *marketplace* para um operador logístico. Risco operacional e de custo altíssimo. | **Estudo de Viabilidade:** Análise de custos vs. benefício. **Pesquisa UX:** Entrevistas para medir a demanda real por serviços "ponta-a-ponta". |
| **3. Plataforma Técnica** | O aplicativo contará com suporte para iPhone (iOS)? | Impacto direto no custo, tempo de desenvolvimento e no tamanho do mercado alcançável (market share). | **Análise de Mercado:** Pesquisar o *market share* de dispositivos (Android vs. iOS) na região alvo. **Decisão Técnica:** Definir *roadmap* (nativo, híbrido, PWA). |


### Evidência da Matriz

![WhatsApp Image 2025-11-12 at 21 26 03](https://github.com/user-attachments/assets/d9647c98-98c1-465d-8cee-c3eec30f88f0)

