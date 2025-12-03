<div align="justify">

# Desing Final

&ensp; O design final do protótipo do Porto Certo foi concebido com o objetivo central de modernizar e simplificar a aquisição de passagens fluviais, focando na eficiência da experiência do usuário (UX) para reduzir filas e burocracia. A interface prioriza uma navegação intuitiva e limpa, facilitando o acesso rápido a horários, destinos e seleção de assentos, garantindo que usuários de diferentes níveis de familiaridade tecnológica possam concluir a compra com segurança e agilidade. Visualmente, o protótipo adota uma identidade que transmite confiança e conexão com o transporte regional, consolidando o aplicativo não apenas como uma ferramenta de vendas, mas como uma solução essencial de mobilidade para os usuários do transporte hidroviário.

# 1. Protótipo

Link para o Protótipo: 
- https://www.figma.com/design/kPXD5lXJNX8wmHI1iN726y/prot%C3%B3tipo---Porto-Certo?node-id=0-1&t=lPiGmtmcyNWOdQTL-1

# 2. Telas

## 2.1 Escolha de Cadastro/Login


<img width="502" height="475" alt="Escolha de Login" src="https://github.com/user-attachments/assets/fc62820a-bd02-4d39-af20-03050691cf19" />

- Ambas as telas apresentam um fundo com gradiente suave (azul no topo desvanecendo para branco na parte inferior), transmitindo uma sensação de limpeza e modernidade.

- No topo, centralizado, encontra-se o logotipo do aplicativo: um ícone circular representando uma onda, seguido pelo nome "PORTO CERTO" em destaque e "VIAGENS" logo abaixo em fonte menor.

### 2.1.1 Tela 1: Seleção de Cadastro (Esquerda)
- Cadastro como Usuário: Botão azul sólido destinado ao público geral (passageiros).
- Cadastro com Conta Empresarial: Botão azul sólido destinado a parceiros, donos de embarcações ou empresas (o perfil "Proprietário").
- Na parte inferior, há um link de texto sublinhado "Já possui conta? Faça Login", permitindo que o usuário que entrou na tela errada alterne rapidamente para a tela de login.

### 2.1.2 Tela 2: Seleção de Login (Direita)
- Login como Usuário: Botão para acesso de passageiros.
- Login com Conta Empresarial: Botão para acesso administrativo/empresarial.
- Na parte inferior, o link de texto sublinhado "Não Possui Conta? Cadastre-se" direciona novos visitantes para a tela de criação de conta.

O design propõe uma bifurcação clara logo no início da experiência. Ele obriga o usuário a definir seu papel (Cliente ou Empresa) antes de preencher formulários, o que ajuda a simplificar os passos seguintes, garantindo que o usuário veja apenas os campos relevantes para o seu tipo de perfil.

## 2.2 Cadastro/Login

<img width="1064" height="475" alt="Cadastro e Login" src="https://github.com/user-attachments/assets/dddd1911-886c-4aa4-9695-1e342f947f60" />

- Todas as quatro telas mantêm o fundo com gradiente azul e o logotipo "Porto Certo Viagens" no topo, garantindo consistência visual com a etapa anterior.
- Diferente da tela de seleção, os formulários aqui são apresentados dentro de um card branco com bordas arredondadas. Isso cria um foco visual centralizado e separa claramente os campos de entrada do fundo.
- Todas as telas possuem uma seta de "voltar" no canto superior esquerdo, permitindo que o usuário retorne à tela de escolha de perfil caso tenha clicado na opção errada.

### 2.2.1 Telas de Cadastro (Duas primeiras à esquerda):

Estas telas aparecem quando o usuário opta por criar uma conta nova.
- Cadastro de Usuário (Pessoa Física):
  - Exige os campos: Nome completo, Email, CPF e Senha.
  - O botão de ação final é "Cadastre-se", localizado na parte inferior do card.
- Cadastro Empresarial (Pessoa Jurídica/Proprietário):
  - Mantém a estrutura visual, mas substitui o campo de identificação pessoal pelo CNPJ, adequando-se ao perfil comercial.

### 2.2.1 Telas de Login (Duas últimas à direita):

Estas telas são destinadas a quem já possui registro.
- Login de Usuário:
  - O acesso é feito via CPF e Senha.
  - Inclui funcionalidades de conforto: caixa de seleção "Lembrar de mim" e link para recuperação de conta "Esqueceu a Senha?".
  - Possui um ícone do Google na parte inferior, indicando a opção de Login Social (entrar com a conta Google) para facilitar o acesso rápido de passageiros.
- Login Empresarial:
  - O acesso é solicitado via CNPJ e Senha.
  - Mantém as opções de "Lembrar de mim" e recuperação de senha, mas, diferentemente da versão de usuário comum, não apresenta a opção de login via Google nesta visualização, focando no acesso corporativo padrão.

O design utiliza campos específicos (CPF vs. CNPJ) para validar o tipo de usuário logo na entrada. A interface é limpa, com botões de ação (azul sólido) chamativos e links secundários ("Não tem conta? Cadastre-se") posicionados para garantir que o usuário nunca fique "preso" em uma tela sem saída.

## 2.3 Home - Usuário

<img width="502" height="475" alt="Home - Usuario" src="https://github.com/user-attachments/assets/75559249-85d4-4099-8dd7-b752420df4c8" />

### 2.3.1 Ferramenta de Busca Principal

O coração desta tela é o card de pesquisa flutuante, posicionado estrategicamente no centro para ser a primeira ação do usuário. Ele é dinâmico e se adapta à necessidade da viagem:
- No topo do card, há botões de alternância claros para "Somente Ida" ou "Ida e Volta".
- Há espaços dedicados para inserir a Cidade de origem e a Cidade de destino, essenciais para filtrar as rotas disponíveis.
- Um botão largo e azul "Buscar" finaliza o card, convidando o usuário a iniciar a pesquisa.

### 2.3.2 Menu de Navegação Inferior (Barra de Tarefas)

- Início (Ícone de Casa): A tela atual, que serve como hub de ofertas e busca rápida. Está destacada em azul para indicar a localização do usuário.
- Busca (Ícone de Lupa): Destinada a Tela de Busca de Viagens.
- Viagens (Ícone de Mala): Área reservada para o gerenciamento das passagens compradas, Viagens em Andamento e histórico de viagens do usuário.
- Config (Ícone de Engrenagem): Acesso às configurações, com as configurações do sistema, do perfil e de acessibilidade.

### 2.3.3 Acesso ao Perfil

- No canto superior direito, há um ícone de perfil de usuário (silhueta em círculo). Este posicionamento padrão permite que o usuário acesse rapidamente seus dados pessoais, edite informações da conta ou faça logout sem obstruir a navegação principal.

### 2.3.4 Conteúdos Promocionais (Meio da Tela)

- Uma lista de cards horizontais que destacam destinos populares (ex: Itacoatiara, Maués, Parintins).
- Cada item exibe uma foto do local, o nome do destino, o local de embarque (ex: "Embarque em Manaus") e um botão "Conferir Oferta", incentivando a compra por impulso ou oportunidade.

Esta tela foi desenhada para reduzir o esforço cognitivo: o usuário pode pesquisar imediatamente sua passagem ou, se estiver indeciso, ser inspirado pelas promoções visuais logo abaixo. A barra inferior garante que ele nunca se perca, mantendo as funções vitais (como acessar seus bilhetes em "Viagens") sempre a um toque de distância.

## 2.4 Busca de Viagens

<img width="863" height="475" alt="Busca de Viagens" src="https://github.com/user-attachments/assets/8f6fcc50-36fb-4c6f-963d-b1a2113a2c8a" />

### 2.4.1 Tela de Filtros Avançados (Esquerda)
- O topo exibe o título "Busca de Viagens" e uma barra de pesquisa textual ("Insira Destino de Viagem") para mudanças rápidas de rota.
- Abaixo, uma lista extensa de critérios permite personalizar a experiência.
- Campos para escolher entre barcos, lanchas ou ferry boats, e tipos de conforto (redes, suítes, camarotes).
- Filtros específicos para necessidades especiais ("Acessibilidade") e serviços a bordo, como Transporte de Veículos, Transporte de Pets e disponibilidade de Alimentação.
- Um seletor para ajustar o orçamento da viagem.
- Um botão "Buscar" azul sólido no rodapé aplica todos esses critérios.

### 2.4.2 Tela de Resultados / Escolha de Viagem (Centro)

Aqui são apresentadas as opções disponíveis baseadas nos filtros aplicados.

- Cada viagem é exibida em um card individual para facilitar a comparação.
- O card destaca o trajeto (ex: "Parintins -> Manaus"), o nome e tipo da embarcação (ex: "El Condor Pasa VI - Barco", "Sergio August's - Lancha") e, mais importante, a Data e Hora de saída.
- O uso de imagens da embarcação ajuda na identificação visual rápida, enquanto o fundo branco do card contrasta com o azul do app para destacar a informação.

### 2.4.3 Tela de Detalhes da Viagem (Direita)
- Uma imagem maior da embarcação selecionada domina o topo, confirmando a escolha do usuário.
- Abaixo da imagem, são listados os detalhes finais: Origem e Destino, data exata de Embarque e Desembarque, além de informações de lotação, criando um senso de urgência ou disponibilidade.
- O botão "Confirmar Embarcação" é grande e destacado, servindo como o "call-to-action" final para proceder ao pagamento.

O design guia o usuário de forma lógica: primeiro Refinar (filtros técnicos e de conforto), depois Comparar (lista visual de opções) e finalmente Validar (revisão de detalhes e datas). Isso minimiza erros na compra, garantindo que o passageiro saiba exatamente o tipo de barco e serviços que está contratando.

## 2.5 Compra de Passagens

<img width="788" height="475" alt="Compra de Passagens" src="https://github.com/user-attachments/assets/ca2c2961-625e-4db3-a36b-44290d7d6345" />

- No topo de todas as telas, há um indicador numérico circular (1, 2, 3) que orienta visualmente o usuário sobre em qual fase do processo de compra ele está, reduzindo a ansiedade durante o checkout.
- O fundo azul gradiente e o cabeçalho com a seta de retorno e o ícone de perfil se mantêm, preservando a identidade do app.

### 2.5.1 Tela de Informações do Passageiro (Etapa 1)

Esta tela foca na coleta de dados obrigatórios para a emissão do bilhete.

- As informações são agrupadas em um card branco bem definido.
- Existe um interruptor (toggle) no topo do card rotulado como "Comprador". Isso sugere uma função inteligente de preenchimento automático: se ativado, o app provavelmente copia os dados do usuário logado para os campos abaixo, economizando tempo.
- formulário solicita Nome completo, Telefone, Data de nascimento e Documento.
- O botão "Continuar" no rodapé avança para o pagamento.

### 2.5.2 Tela de Pagamento (Etapa 2)

Aqui o usuário define quem está pagando e como.

- Um card superior exibe os dados do responsável financeiro: Nome completo, Email, Telefone e CPF. Isso é crucial para a nota fiscal e confirmação por e-mail.
- parte inferior apresenta a seção "Selecione a forma de pagamento" com dois botões grandes e amigáveis ao toque.

### 2.5.3 Tela de Confirmação (Etapa 3)

A tela de "Sucesso" que finaliza a jornada.

- O título "Compra realizada" no topo do card confirma o sucesso da transação.
- O card lista os detalhes finais para conferência: Nome, Email, CPF, Telefone, quantidade de Passagens, Valor pago e Modo de pagamento.
- A funcionalidade mais importante aqui é a seção "Baixar bilhete", que oferece duas opções: PDF ou Imagem

O processo de checkout foi desenhado para ser linear e sem distrações. A divisão em três passos claros (Quem vai? -> Quem paga? -> Bilhete na mão) evita sobrecarregar o usuário com um formulário único e longo. A inclusão de opções de download (PDF/Imagem) no final demonstra preocupação com o cenário de uso real (embarque em portos onde a internet pode ser instável).

## 2.6 Tela de Viagens Gerais

<img width="219" height="475" alt="1600 96 % Seja bem vindo ! Cadastro como Usuário Cadastro com Conta Empresarial Já possui conta Faça Login (1)" src="https://github.com/user-attachments/assets/5e403c15-9eb0-41fe-b161-3d220a75016d" />

- A tela é dividida verticalmente em três seções distintas, separadas por títulos em negrito ("Viagens em Andamento", "Viagens Programadas", "Viagens Realizadas"), permitindo que o usuário localize rapidamente a informação que precisa com base no status da viagem.
- Cada viagem é representada por um card com um cabeçalho azul escuro que destaca a rota (Origem $\rightarrow$ Destino). O corpo do card é branco, contendo uma foto da embarcação à esquerda e os detalhes técnicos à direita, mantendo a consistência visual com as telas de busca anteriores.

Esta tela fecha o ciclo de experiência do usuário. O design adapta inteligentemente as informações exibidas conforme o contexto temporal da viagem: Previsão para quem está viajando, Agenda para quem vai viajar, e Preço para quem já viajou.

### 2.7 Home - Proprietário

<img width="220" height="475" alt="1600 96 % Seja bem vindo ! Cadastro como Usuário Cadastro com Conta Empresarial Já possui conta Faça Login" src="https://github.com/user-attachments/assets/0ef4741f-3cc5-4cd7-9ad5-5de1251b9da8" />

### 2.7.1 Painel de Plano de Viagens

Diferente da versão do passageiro (que foca em busca e promoções), a tela inicial do proprietário é um painel administrativo e de comunicação.

A tela mantém o fundo gradiente azul e o cabeçalho limpo, garantindo que, mesmo sendo uma área administrativa, a experiência seja visualmente agradável e consistente com o que o cliente final vê, reforçando a marca "Porto Certo" em todas as pontas.

- As viagens são listadas em cards claros (ex: "Parintins $\rightarrow$ Manaus", "Manaus $\leftrightarrow$ Santarém"), mostrando a embarcação, data e hora agendadas.
- O diferencial crítico de usabilidade é o botão circular azul com um "+" branco, anexado à parte inferior de cada card. Sua função específica é permitir que o proprietário emita comunicados e avisos sobre aquela viagem diretamente para os passageiros (como informar atrasos, mudanças de horário ou instruções de embarque), garantindo uma comunicação ágil e direta.

### 2.7.2 Menu de Navegação Inferior

- Início (Casa): O painel de visão geral atual.
- Perfil (Ícone de Barco): Aqui reside a principal mudança. O ícone de lupa (Busca) do usuário comum foi substituído por um ícone de Frente de Barco, rotulado como "Perfil". Isso indica que esta aba é dedicada ao gerenciamento da identidade da empresa ou da frota (cadastro de barcos, fotos, descrições).
- Viagens (Mala): Tela aonde o Proprietário pode criar viagens, utilizando por exemplo, as embarcações cadastradas na aba de Perfil.
- Config (Engrenagem): Ajustes da conta empresarial.

Esta interface transforma o aplicativo em uma ferramenta de gestão e comunicação. O proprietário não apenas visualiza seu cronograma logístico, mas possui um canal direto (através do botão "+") para manter seus clientes informados sobre qualquer eventualidade na viagem, reduzindo ruídos de comunicação e aumentando a confiança no serviço.

## 2.8 Notificar Avisos

<img width="786" height="461" alt="Notificar Viagens" src="https://github.com/user-attachments/assets/d64f059b-0a52-4222-bcb1-9f42e4cc4270" />

O design adota uma abordagem séria e direta. O foco não é vender, mas sim informar. A interface limpa evita distrações, permitindo que o proprietário se concentre na mensagem crítica que precisa ser enviada.

### 2.8.1 Tela de Detalhes da Viagem (Esquerda)

Esta tela serve como um painel de impacto antes do envio da mensagem.

- O topo exibe a foto da embarcação, a rota e as datas, garantindo que o proprietário saiba exatamente qual viagem está manipulando.
- O campo "Vendidas: 350" informa ao gestor o tamanho do público que será afetado pelo aviso, dando uma dimensão real da responsabilidade da comunicação.
- O botão "Notificar Viagem" é largo e azul, servindo como o gatilho para abrir a ferramenta de composição de mensagem.

### 2.8.2 Tela de Criação de Aviso (Direita)

Aqui ocorre a redação do comunicado.

- O primeiro campo é um menu suspenso chamado "Motivo". Na imagem, ele está selecionado como "Atraso", aonde o sistema já pré-classifica os avisos.
- Título da Mensagem, para um resumo curto.
- Descrição, uma área de texto maior para explicar detalhes, instruções de espera ou pedidos de desculpas.
- Um recurso muito importante é o interruptor (toggle) "Enviar para o email". Isso permite que o aviso chegue não apenas como notificação push no app, mas também na caixa de entrada do passageiro, aumentando a garantia de leitura.

Este fluxo fecha o ciclo de responsabilidade do proprietário. Ele transforma dados operacionais (uma viagem vendida) em ação de comunicação (um aviso de atraso). A interface é projetada para ser rápida e eficiente, permitindo que, em poucos toques, 350 passageiros sejam avisados simultaneamente sobre uma mudança de itinerário, minimizando o caos no porto.

## 2.9 Perfis de Embarcação

<img width="787" height="475" alt="Perfis de Embarcação" src="https://github.com/user-attachments/assets/5c7839c2-b9ca-4e66-bbea-ca02575fe3b2" />

### 2.9.1 Tela de Listagem de Frota (Esquerda)

- As embarcações cadastradas são exibidas em uma lista de cards verticais. Cada card contém uma miniatura da foto, o nome (ex: "El Condor Pasa VI") e o tipo da embarcação (ex: "Barco", "Ferry Boat", "Lancha"), permitindo rápida identificação.
- Um botão grande e claro "Adicionar Embarcação" com um ícone de "+" azul ocupa a parte inferior da lista, incentivando o crescimento da frota cadastrada.

### 2.9.2 Tela de Cadastro - Vazia (Centro)

Ao clicar em adicionar, o proprietário é levado a este formulário estruturado.

- O topo da tela é dominado por uma área grande para "Adicionar Foto", reconhecendo que a imagem é o principal fator de venda para o passageiro.
- O formulário solicita informações cruciais para a venda: Descrição, Acomodações, Capacidade, Rotas e Acessibilidade.
- Note a presença de pequenos ícones de interrogação (?) ao lado de cada título de campo. Isso sugere a existência de tooltips ou ajudas contextuais para orientar o proprietário sobre o que escrever em cada seção.

### 2.9.3 Tela de Cadastro - Preenchida (Direita)

Esta tela mostra como os dados ficam organizados após a inserção.

- O sistema formata as entradas com ícones visuais (ex: ícone de rede para "rede", ícone de cama para "suite"), tornando a leitura mais agradável.
- importante notar que todas as informações preenchidas aqui (foto, lotação, serviços) são exatamente o que alimentará a "Tela de Detalhes da Viagem" que o passageiro vê durante a busca (analisada anteriormente).

Este fluxo empodera o proprietário a gerenciar a apresentação do seu produto. A interface guia o usuário desde a visão macro (lista de frota) até a micro (detalhes técnicos), garantindo que informações essenciais como capacidade e acessibilidade não sejam esquecidas, padronizando a qualidade das informações disponíveis no aplicativo.

## 2.10 Criar Viagens

<img width="1640" height="475" alt="Criar Viagens" src="https://github.com/user-attachments/assets/beb1e966-006c-4d16-925e-2e04512bac7c" />

### 2.10.1 Seleção da Embarcação (Etapa Inicial)

O processo começa com a definição do ativo que fará a rota.

- A tela "Selecione o transporte" apresenta as embarcações cadastradas em cartões grandes e claros (ex: "El Condor Pasa VI", "Teto II"), com fotos e tipo de embarcação, permitindo que o proprietário escolha facilmente qual barco será alocado para a viagem.

### 2.10.2 Definição Logística (Dados da Rota)

Uma vez selecionado o barco, o sistema pede os dados operacionais no formulário "Definir viagem".

- O topo da tela exibe um card de confirmação com a foto e nome da embarcação escolhida, garantindo que o usuário saiba para qual barco está criando a agenda.
- O formulário solicita os detalhes técnicos do trajeto.

### 2.10.3 Definição de Valores (Precificação)

A tela seguinte foca na monetização da viagem, sob a seção "Definir valores".

- O sistema permite uma precificação granular, essencial para maximizar a receita.
- "Integral" (preço cheio) e "Idoso" (meia ou diferenciada).
- Campos dedicados para "Pet", "Cargas", "Veículos" e "Encomendas", demonstrando que o sistema suporta a complexidade real do transporte fluvial, que vai além de apenas levar pessoas.

### 2.10.4 Confirmação

A última tela apresentada, "Plano de viagens", serve como revisão.

- Exibe todos os dados inseridos (embarcação, rota, horários e locais) em um formato de leitura (não editável), permitindo que o proprietário valide as informações antes de publicar a viagem para venda.

Este fluxo de criação é robusto e especializado. Ele não trata a viagem apenas como "Origem x Destino", mas cobre todas as nuances do negócio fluvial: qual barco vai (seleção visual), de onde sai exatamente (pontos de embarque) e quanto custa cada tipo de carga (precificação segmentada). Isso dá ao proprietário controle total sobre a operação comercial de cada trecho.



## 2.11 Tela de Configurações - Usuário e Proprietário

<img width="788" height="475" alt="Config - Usu" src="https://github.com/user-attachments/assets/03862b0d-730b-4792-a21f-0db612f45c19" />

<img width="786" height="475" alt="Config - Prop" src="https://github.com/user-attachments/assets/2a9d0ac1-2a96-4d75-9fd4-bac4a735e440" />

Ambos os perfis utilizam a mesma linguagem visual: fundo com gradiente azul, cabeçalho limpo com seta de retorno e botões grandes em estilo de cartão com ícones pretos destacados. Isso facilita a manutenção do aplicativo e cria uma experiência de marca coesa.

Navegação Inferior: A distinção mais imediata está na barra de tarefas.

### 2.11.1 Menu Principal (Esquerda - Ambos)

A tela de entrada das configurações serve como uma central de distribuição.

- Ambos os perfis têm acesso aos mesmos três pilares macro: "Opções do Sistema" (técnico), "Opções de Perfil" (dados cadastrais) e "Opções de Acessibilidade" (inclusão). Isso demonstra que a arquitetura do app trata ambos os usuários com o mesmo nível de importância.

### 2.11.2 Opções de Perfil (Centro)

Ao entrar na gestão de dados, o aplicativo bifurca a experiência para atender às necessidades legais de cada pessoa.

- Ambos possuem "Dados Pessoais" e "Métodos de Pagamento".
- O botão exibe "Documentos do Proprietário". Isso implica a gestão de documentos jurídicos, licenças de navegação (CHA), CNPJ e permissões da frota.
- O botão exibe "Documentos do Usuário". Focado em documentos pessoais de identificação (RG, CPF) necessários para a emissão de bilhetes e seguros de viagem.

### 2.11.2 Acessibilidade (Direita - Universal)

O módulo de inclusão é idêntico para ambos, reforçando o compromisso do "Porto Certo" com o design universal.

- Tanto o passageiro quanto o empresário têm acesso a "Alto Contraste", "Textos Ampliados" e "Talkback". Isso reconhece que proprietários de barcos também podem ser idosos ou pessoas com deficiência, e precisam de uma interface acessível para trabalhar, assim como o passageiro precisa para comprar.

A área de configurações foi projetada com uma inteligência modular: a "casca" do design é a mesma para reduzir a curva de aprendizado, mas o "miolo" (especificamente a gestão documental) muda dinamicamente. O sistema protege a integridade da plataforma exigindo documentos específicos de cada lado (CPF para viajar, Licenças para navegar), mantendo a navegação fluida e intuitiva para todos.

## 2.12 Telas de Acessibilidade

<img width="504" height="475" alt="Acessibilidade" src="https://github.com/user-attachments/assets/b084616b-5044-49df-97b7-8cb5fa2442ac" />

O design das telas demonstra uma preocupação clara com a acessibilidade, tanto na estrutura de navegação quanto nos elementos visuais.

### 2.12.1 Modo Alto Contraste (Tela à Esquerda)

Esta tela demonstra a aplicação do modo de Alto Contraste, essencial para usuários com baixa visão ou sensibilidade à luz (fotofobia).

- O fundo gradiente azul/branco padrão foi substituído por um fundo preto sólido. Isso reduz drasticamente o brilho da tela e o cansaço visual.
- O título "Plano de viagens" aparece em amarelo vibrante, uma cor que oferece o maior contraste possível contra o fundo preto, garantindo legibilidade imediata.
- Os cards de viagem e a barra de navegação utilizam um tom de verde-azulado (teal), que se destaca claramente do fundo escuro sem causar o ofuscamento do branco puro.
- Os ícones da barra inferior (Início, Perfil, Viagens, Config) são renderizados em amarelo ou branco, facilitando a identificação rápida das formas.

### 2.12.2 Modo Textos Ampliados (Tela à Direita)

Esta tela ilustra a funcionalidade de Textos Ampliados (Fontes Grandes), vital para idosos (presbiopia) e pessoas com dificuldades de leitura.

- O layout preserva a estrutura original da "Busca de Viagens", mas todos os elementos textuais foram redimensionados significativamente.
- A palavra "Filtros" está em negrito e em tamanho muito maior, servindo como uma âncora visual clara.
- Os textos auxiliares como "Tipo de Embarcação" e "Acessibilidade" ocupam mais espaço vertical, tornando a leitura confortável sem necessidade de aproximar o dispositivo do rosto.
- Mesmo com o aumento da fonte, os campos de entrada e o botão de ação "Buscar" se ajustaram proporcionalmente, garantindo que o texto não fique cortado e que as áreas de toque (clique) sejam maiores e mais fáceis de acertar.

Essas telas confirmam que o Sistema não apenas possui um menu de acessibilidade, mas que o sistema foi construído para se adaptar elasticamente. O design não "quebra" quando submetido a mudanças drásticas de cor ou tamanho de fonte, mantendo a usabilidade intacta para todos os perfis de passageiros e proprietários.



