<div align="justify">

# MoSCoW

<img width="1206" height="701" alt="image" src="https://github.com/user-attachments/assets/6aff4f99-c233-4a0f-9592-973a0c599563" />

## Must Have ( Deve Ter)

Elementos que decidimos ser obrigatórios em nosso sistema e que não devem faltar em hipótese alguma.

| Prioridades | Explicação |
| :--- | :--- |
| **Compra e Venda de Passagens** | O coração do sistema. Sem isso, o aplicativo não cumpre seu propósito primário de monetização e garantia de vagas, tanto para o passageiro (que precisa de segurança) quanto para o proprietário (que precisa evitar calotes e controlar a lotação). |
| **Perfil das Embarcações** | Fundamental para a decisão de compra. Em um mercado informal, a "prova visual" (fotos, descrição de segurança e acomodações) é um requisito obrigatório para gerar a confiança necessária para que o usuário realize o pagamento antecipado. |
| **Chatbot** | Essencial para a escalabilidade do suporte. Como muitos usuários terão dúvidas básicas (local de embarque, horários), o sistema não funcionará de forma eficiente se depender apenas de atendimento humano. O Chatbot é obrigatório para triagem e respostas imediatas (FAQ automatizado). |
| **Filtros (Tipos, Acessibilidade, etc.)** | Crítico para a funcionalidade da busca. Como o app atende públicos com necessidades excludentes (ex: carga vs. passageiro; acessibilidade vs. comum), a ausência de filtros tornaria a busca inútil para personas chave como Ana Julia (Cargas) e Beatirz (PNE), impedindo a conversão. |

## Should Have ( Deveria Ter)

Elementos que acreditamos ser muito importantes para o aplicativo, essenciais, porém não tão cruciais quanto os do Must Have.

| Prioridades | Explicação |
| :--- | :--- |
| **Reserva de Passagens** | Embora vital a longo prazo, o sistema poderia ser lançado inicialmente apenas como um "Guia de Horários e Preços", direcionando o usuário para a compra no porto. A funcionalidade de reserva digital integrada seria o próximo passo lógico para fechar o ciclo de valor. |
| **Transporte de Encomendas** | Funcionalidade essencial para a persona Ana Julia e para a diversificação de receita. No entanto, o aplicativo pode focar primeiro em consolidar o mercado de passageiros (B2C), que possui maior volume, antes de introduzir a complexidade logística de cargas. |
| **Talkback** | Requisito fundamental para a inclusão da persona Beatriz. Classificá-lo aqui implica uma decisão de projeto arriscada: lançar o app funcional visualmente para a maioria, comprometendo-se a entregar a compatibilidade total com leitores de tela na primeira grande atualização subsequente. |
| **Contato com Proprietários** | Um canal direto (chat/telefone) aumenta a confiança de personas inseguras como Lucas. Porém, se as informações estáticas do barco forem boas o suficiente, o sistema pode operar sem esse canal direto no início, evitando sobrecarregar os donos de barco com suporte. |

## Could Have (Poderia Ter)

Elementos que não estão nos planos iniciais, mas que ainda assim são desejáveis, podendo ser incluídos em futuras atualizações.

| Prioridades | Explicação |
| :--- | :--- |
| **Sistema de Avaliação e Comentários** | Mecanismo de "prova social" onde usuários dão notas (estrelas) e depoimentos sobre a viagem. Embora útil para gerar confiança em personas inseguras como Lucas, o sistema pode ser lançado inicialmente apenas com as informações oficiais da embarcação. A avaliação comunitária exige uma base de usuários ativa para funcionar bem. |
| **Planos por Assinatura** | Modelo de fidelidade (ex: "Clube Fluvial") oferecendo descontos em passagens ou frete grátis para uma mensalidade fixa. É um recurso excelente para rentabilizar usuários frequentes, mas adiciona complexidade de gestão financeira que não é necessária na primeira versão do app. |
| **Geolocalização** | Refere-se aqui à visualização avançada em mapa (tipo Uber, vendo o barquinho se mexer). Embora o *status* da viagem (atrasado/no horário) seja vital, a visualização gráfica em tempo real consome muitos dados e bateria. Pode ser deixada para depois, focando apenas em notificações de texto precisas no início. |
| **Viagens para o Interior do Interior** | Expansão da cobertura para comunidades ribeirinhas muito remotas e de difícil acesso (o "beiradão"). O foco inicial deve ser as rotas de alto fluxo (ex: Manaus-Parintins). Atender o interior profundo envolve desafios de conectividade de internet que o app ainda não consegue resolver no lançamento. |

## Won't Have ( Não Vai Ter)


Elementos que não estarão presentes no sistema, embora possa haver alterações futuras para incluí-los.

| Prioridades | Explicação |
| :--- | :--- |
| **Suporte para iPhone (iOS)** | Dado o perfil demográfico da região e do público-alvo (ribeirinhos e comerciantes locais), a vasta maioria utiliza Android. Desenvolver para iOS agora dobraria o custo e tempo de desenvolvimento para atingir uma parcela mínima de usuários. Ficará para uma fase futura de expansão. |
| **Busca de Encomendas** | O sistema não gerenciará a logística de "última milha" (coleta na casa/loja do cliente ou entrega no endereço final). O escopo do serviço é estritamente porto-a-porto: o cliente é responsável por levar a encomenda até o barco e o destinatário deve retirá-la diretamente na embarcação. |
| **Acessibilidade Física** | O aplicativo é um software e não tem controle sobre o mundo físico. Embora possamos *informar* sobre acessibilidade (filtros), o sistema não pode *garantir* ou *construir* rampas e infraestrutura nos barcos, pois isso depende exclusivamente dos proprietários e dos portos públicos. |
| **Transporte até a Embarcação** | O escopo do sistema começa e termina na viagem fluvial. Oferecer serviços de translado terrestre (tipo Uber/Táxi) ou vans até o porto adicionaria uma camada operacional logística que a startup não consegue gerenciar no momento. É responsabilidade do passageiro chegar ao local de embarque. |


