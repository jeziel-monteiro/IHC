<div align="justify">

# HTA (hierarchical task analysis)

&ensp; Análise hierárquica de tarefas (HTA) é uma abordagem que os designers usam para organizar as tarefas do usuário em metas, submetas e etapas, formando uma hierarquia de tarefas clara. Designers de UX (experiência do usuário) usam HTA para mapear o comportamento do usuário, descobrir gargalos e otimizar fluxos, tornando as interfaces intuitivas e eficientes desde o início.

# 1. Realizar Cadastro

&ensp; O diagrama ilustra o fluxo de registro no aplicativo, que se inicia com a abertura da interface e conduz o usuário a uma etapa de decisão de perfil, onde ele deve optar entre "Usuário" (passageiro), preenchendo dados pessoais como CPF, ou "Proprietário" (dono da embarcação), fornecendo dados empresariais como CNPJ; essa bifurcação define a coleta específica de dados, mas ambos os caminhos convergem para a mesma etapa final de segurança, que é a validação do processo através de uma confirmação enviada por e-mail.

<img width="484" height="108" alt="image" src="https://github.com/user-attachments/assets/26413bee-f73c-4419-b052-b52ef32deef0" />

<img width="5472" height="4192" alt="Cadastro drawio (1)" src="https://github.com/user-attachments/assets/798eed73-345b-4a5d-9611-d7448fac8d6a" />

# 2. Realizar Login

&ensp; O diagrama descreve o procedimento de acesso ao sistema, iniciando-se com a abertura do aplicativo e seguindo para uma etapa de seleção de perfil, onde o fluxo se divide entre o login de "Usuário" (validado via CPF e senha) e o de "Proprietário" (validado via CNPJ e senha), culminando na conclusão da autenticação que libera o acesso à plataforma.

<img width="450" height="97" alt="image" src="https://github.com/user-attachments/assets/102b0d41-9d78-43b0-b4f8-cf503e34ab9b" />

<img width="5472" height="4184" alt="Login drawio (1)" src="https://github.com/user-attachments/assets/854b3802-02f8-4c0a-88d0-802e541f29c3" />

# 3. Realizar Busca de Viagens

&ensp; O diagrama ilustra o processo de busca de viagens dentro do aplicativo, partindo da abertura da interface e concentrando-se na interação com a ferramenta de pesquisa, onde o usuário pode refinar sua escolha através de um conjunto robusto de filtros — incluindo tipo de embarcação, disponibilidade de alimentação, transporte de veículos, acessibilidade, acomodações e transporte de animais — para, em seguida (ou em conjunto), definir o destino final da viagem.

<img width="454" height="82" alt="image" src="https://github.com/user-attachments/assets/345da6ce-4015-443a-96bd-7492c912fa7f" />

<img width="8148" height="3878" alt="RealizarBusca drawio" src="https://github.com/user-attachments/assets/3189b630-4510-46d2-8d7e-3ad5bd8e250d" />

# 4. Realizar Compra de Passagens

&ensp; O diagrama mapeia a jornada completa de aquisição do bilhete, começando pela seleção da viagem específica e avançando para a identificação dos passageiros, com um diferencial importante na etapa de "Dados Opcionais", onde o usuário pode incluir serviços extras como transporte de veículos, pets e cargas (o que se conecta diretamente com os tipos de encomenda que discutimos); o fluxo segue para a escolha do pagamento (bifurcando entre Pix e Cartão) e culmina na dupla confirmação: a financeira (comprovante) e a operacional (emissão da guia de embarque).

<img width="453" height="85" alt="image" src="https://github.com/user-attachments/assets/3084bdef-0a23-48da-8a8e-14f407f9d9fb" />

<img width="9940" height="3941" alt="CompraPassagens drawio" src="https://github.com/user-attachments/assets/114925de-2afe-45f6-8bc3-11434cc543c5" />

# 5. Realizar Envio de Encomendas

&ensp; O diagrama mapeia o processo logístico de despacho de mercadorias, começando pela definição do destino e identificação do destinatário, e avançando para a etapa central de classificação da carga, onde o sistema oferece categorias específicas alinhadas à realidade regional (Eletrodomésticos, Móveis, Hortifruti, Materiais de Construção e Veículos); o fluxo segue para o pagamento (via Pix ou Cartão) e encerra-se com a emissão dupla de documentos: o comprovante financeiro e o guia oficial de envio da encomenda.

<img width="455" height="86" alt="image" src="https://github.com/user-attachments/assets/acdaba97-f3eb-41fe-b74e-3186e59fce54" />

<img width="12215" height="4970" alt="Encomendas drawio" src="https://github.com/user-attachments/assets/0ee8afd5-b8bd-4563-921f-0ff59606860e" />

# 6. Criar Viagens

&ensp; O diagrama estrutura a rotina administrativa de criação de uma nova viagem (fluxo do Proprietário), partindo da seleção da embarcação e da definição dos dados logísticos (origem, destino e horários), e aprofundando-se na configuração financeira, onde o sistema exige a definição separada de tarifas para passageiros (incluindo inteira, meia e taxas para animais) e tarifas para transporte de cargas (veículos e encomendas), finalizando o fluxo com a revisão completa das informações antes da publicação da viagem na plataforma.

<img width="453" height="95" alt="image" src="https://github.com/user-attachments/assets/93914a09-fa3b-42b6-aff7-2154f718c28a" />

<img width="6258" height="4991" alt="CriarViagens drawio" src="https://github.com/user-attachments/assets/de4944a6-9f89-4bc6-b0bb-8091690d6890" />

# 7. Criar Perfil da Embarcação

&ensp; O diagrama descreve o processo de cadastro da frota pelo proprietário, iniciando com o acesso à gestão de perfis e focando na construção da identidade digital da embarcação, tarefa que se divide entre a inserção de prova visual (upload de fotos) e o preenchimento de um formulário técnico detalhado — que abrange desde dados básicos (nome e tipo) e logísticos (cronograma) até definições operacionais críticas (capacidade de carga/passageiros) e comodidades extras (como Wi-Fi e alimentação) —, encerrando-se com a validação final desse perfil no sistema.

<img width="454" height="95" alt="image" src="https://github.com/user-attachments/assets/b449dcab-5842-4dd8-bd17-1f851164c398" />

<img width="5705" height="4011" alt="CriarEmbarcacao drawio" src="https://github.com/user-attachments/assets/926e2daa-3d78-4568-9f34-861fa03a7d04" />

# 8. Notificar Avisos

&ensp; O diagrama mapeia o fluxo de comunicação ativa entre o operador (provavelmente o proprietário ou tripulação) e os passageiros, iniciando-se com a seleção da funcionalidade de notificação e o vínculo imediato a uma viagem específica (garantindo que o aviso chegue apenas a quem interessa); a partir desse contexto, o usuário constrói o alerta em três passos detalhados — criação do título, categorização do motivo (como atrasos ou cancelamentos) e inserção da descrição completa —, finalizando o processo com a confirmação de envio da mensagem.

<img width="449" height="84" alt="image" src="https://github.com/user-attachments/assets/b0291723-88c3-45a7-a96a-3ae8eb016167" />

<img width="4228" height="3381" alt="Notifica drawio" src="https://github.com/user-attachments/assets/bfada8ab-b3fd-4a5f-ab4a-e9a4d760d005" />
