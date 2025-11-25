# MOLIC

MOLIC é a sigla para Modelling Language for Interaction as Conversation (Linguagem de Modelagem para Interação como Conversa).

Ela é uma linguagem de modelagem utilizada na área de Interação Humano-Computador (IHC) e design de interfaces. Diferente de diagramas técnicos focados em código (como UML), o MOLIC foca no fluxo de comunicação e na experiência do usuário.

A base teórica do MOLIC é a Engenharia Semiótica. Nesta visão, toda interface é uma mensagem enviada do designer para o usuário.

O Metamodelo: O designer projeta o sistema para ser um interlocutor.

A Prática: Quando um usuário interage com um software (clicando em botões, preenchendo campos), ele está "conversando" com o designer através do sistema.

O MOLIC serve para mapear essa conversa antes de o sistema ser construído, garantindo que o "diálogo" seja coerente e ajude o usuário a atingir seus objetivos.

<p align="center">
  <img src="https://github.com/user-attachments/assets/1db18bb4-83b2-4c1a-8f2c-20afa8e2cefb" alt="sup" width="900"">
</p>


## Cadastro

<p align="center">
  <img src="https://github.com/user-attachments/assets/1f534b7c-6b71-495f-9aa9-8a2158e1d493" alt="sup" width="700"">
</p>



1. Início e Acessibilidade
- Ação Inicial: O usuário entra no aplicativo (u: entrar no aplicativo).

- Cena de Acessibilidade: O sistema inicia perguntando se há necessidade de recursos de acessibilidade.

- Há uma escolha exclusiva (XOR): O usuário define "Sim" ou "Não".

- Observação: É interessante notar que este sistema prioriza a configuração de acessibilidade antes mesmo do cadastro.

2. Escolha do Perfil (Ramificação)
Após prosseguir, o sistema apresenta a tela de cadastro e oferece opções (d: opções disponíveis). Aqui ocorre uma decisão crítica que divide o fluxo:

- O usuário deve escolher (XOR) entre:

- "Quero me cadastrar como Usuário."

- "Quero me cadastrar como Proprietário."

3. Preenchimento de Dados (Caminhos Diferentes)
Dependendo da escolha anterior, o sistema pede dados diferentes (indicado pela tag SEQ, que significa sequência de preenchimento):

Caminho do Usuário:

- Pede: Nome, Email, CPF e Senha.

- Caminho do Proprietário:

- Pede: Nome, Email, CNPJ e Senha.

- Diferença Chave: O diagrama modela que a principal diferença na interação entre os dois perfis é o documento exigido (CPF para pessoa física, CNPJ para proprietário/empresa).

4. Validação e Tratamento de Erro (Ruptura)
- Ambos os caminhos levam à ação u: confirmar dados, que entra em uma "caixa preta" (o quadrado preto), representando o processamento do sistema. Daqui saem duas possibilidades:

- Dados Inválidos (Linha tracejada): Se houver erro, o sistema devolve o usuário para a cena de preenchimento de dados para corrigir (o loop de retorno).

- Dados Validados (Linha contínua): Se tudo estiver certo, o fluxo segue adiante.

5. Finalização
- Cena Final: O sistema informa que um email foi enviado para confirmação (d: email enviado...).

- Encerramento: O objetivo é concluído com a confirmação do registro.

## Login

<p align="center">
  <img src="https://github.com/user-attachments/assets/71cf8dfa-83ff-4c34-9e20-31420c09eb6a" alt="sup" width="700"">
</p>


1. Abertura e Tela Inicial (Landing)
- Início: O usuário abre o aplicativo (u: Abrir Aplicativo).

- Estado Inicial (Caixa Cinza Superior): O usuário chega a uma tela inicial (provavelmente a "Home" deslogada).

- Aqui ele tem duas opções: sair do sistema imediatamente ou, o que nos interessa, iniciar a ação de u: Realizar Login.

2. Escolha de Perfil (Bifurcação)
- Assim como no cadastro, o sistema não pede o login direto. Ele primeiro leva à cena "Escolha de Login", onde o usuário deve selecionar (XOR) quem ele é:

- Opção A: Usuário Comum.

- Opção B: Proprietário.

- Detalhe Importante de Usabilidade: Note a seta tracejada u: Voltar a Tela Anterior. O diagrama prevê que o usuário pode ter clicado em "Login" por engano e querer voltar para a tela inicial. O MOLIC torna explícita essa "liberdade" do usuário.

3. Preenchimento das Credenciais
- Dependendo da escolha, o usuário vai para cenas diferentes com exigências diferentes:

- Login como Usuário: O sistema pede CPF e Senha.

- Login como Proprietário: O sistema pede CNPJ e Senha.

- Navegação: Em ambas as telas de preenchimento, existe a opção u: Voltar Ação. Isso permite que, se o usuário clicou em "Proprietário" sem querer, ele possa voltar e escolher "Usuário" sem ter que fechar o app.

4. Processamento e Erros (O "Loop")
- Após inserir os dados, a informação vai para o sistema (o quadrado preto).

- Caminho de Erro (Linhas tracejadas): Se os dados forem inválidos ou incorretos, o sistema devolve o usuário para a mesma tela de preenchimento para tentar novamente.

- Caminho de Sucesso: Se o login for concluído (d: login concluído), o usuário avança.

5. Convergência e Acesso
- Independentemente de ser Usuário ou Proprietário, após o sucesso, ambos são direcionados para a Caixa Cinza Inferior.

- Isso representa a Área Logada (o dashboard ou a tela principal do app).

- O fluxo termina com a opção final de u: sair do aplicativo.

## Criar Perfil de Embarcações

<p align="center">
  <img src="https://github.com/user-attachments/assets/d0ce6f3a-77cf-44db-8701-5f1001cf5129" alt="sup" width="700"">
</p>



1. Acesso à Funcionalidade
- O Ponto de Partida: O usuário está na área logada (caixa cinza) e seleciona a opção u: perfis de embarcações.

- Listagem: Ele entra numa tela que provavelmente lista os barcos existentes, mas decide seguir o caminho de u: prosseguir para criar um novo.

2. O "Hub" de Criação (Nó Central)
- O usuário chega à cena "criar perfil da embarcação". Diferente de um formulário único e longo, o diagrama divide o trabalho em duas grandes tarefas (ramificações) que podem ser acessadas e retornadas:

- Lado Esquerdo (Informações Técnicas):

- O usuário entra em adicionar descrição.

- Aqui ele insere: Nome, Tipo da embarcação, Cronograma de viagens (horários) e Informações essenciais (capacidade de carga/passageiros, vagas disponíveis e se aceita encomendas).

- Observação: Note a riqueza de dados logísticos aqui, essenciais para o funcionamento do app.

#### Lado Direito (Visual):

- O usuário entra em adicionar fotos da embarcação.

- Foca exclusivamente no upload de imagens.

3. Flexibilidade de Navegação (Ir e Voltar)
- O diagrama mostra setas tracejadas (u: retornar ao criar perfil...) saindo de ambas as sub-tarefas.

- Isso significa que o usuário pode entrar na tela de fotos, desistir ou mudar de ideia, e voltar para o menu principal de criação sem necessariamente salvar ou bloquear o app.

4. Confirmação e Salvamento
Quando o usuário preenche as informações (seja descrição ou fotos) e clica em u: prosseguir (setas sólidas para baixo):

- A ação vai para o Processamento (Quadrado Preto).

- O sistema confirma que as descrições/fotos foram adicionadas corretamente.

- O fluxo termina na cena finalizar perfil, onde o proprietário conclui a criação.

5. O "Botão de Pânico" (Cancelar Tudo)
- Existe uma linha tracejada longa à direita: u: cancelar toda a ação.

- Ela sai lá do final (finalizar perfil) e volta direto para o início da listagem (entrar em perfis de embarcações).

- Isso indica que, mesmo no último passo, o usuário tem a liberdade de descartar todo o processo de criação e voltar para a lista de barcos.

## Criação de Viagem

<p align="center">
  <img src="https://github.com/user-attachments/assets/8ffb173f-5a4a-4d9f-8f5a-dbe8b4a70ba8" alt="sup" width="700"">
</p>


1. Seleção do Transporte
- O Passo Inicial: Saindo da Home (caixa cinza), o usuário entra em Definir embarcação.

- Validação: Ele escolhe o barco. O sistema verifica (quadrado preto) se a embarcação é válida.

- Erro: Se houver problema com o barco escolhido, o sistema avisa (d: embarcação inválida) e pede para selecionar de novo.

2. Definição da Logística (O "Onde" e "Quando")
- Se o barco for válido, o usuário avança para Definir viagem. Aqui ele preenche os dados cruciais de navegação:

- Tipo de Viagem (XOR): Escolha exclusiva entre "Ida" ou "Ida e volta".

- Rota e Data: Origem, Destino e Data.

- Pontos Específicos: Local exato de Embarque e Desembarque (muito importante na região amazônica, onde nem sempre é um porto oficial).

- Validação: O sistema checa se todos os campos obrigatórios foram preenchidos (d: dados não preenchidos).

3. Precificação (O "Quanto")
- Na etapa Definir valores, o proprietário configura a tabela de preços para essa viagem específica. O diagrama mostra uma segmentação bem detalhada:

- Passageiros: Preço Integral, Idoso e Pet.

- Cargas: Preço para Veículos e Encomendas.

- Navegação Importante: Note a seta u: Voltar a Tela Anterior. O usuário pode perceber que errou a data na etapa anterior e voltar sem perder tudo.

4. Revisão e Confirmação
- Antes de publicar a viagem, o sistema leva para a cena Confirmação da viagem.

- O sistema exibe um resumo de tudo (Verificar dados e Verificar valores).

- Se o usuário notar um erro, existe a seta u: alterar informações que retorna para a edição de valores (e de lá pode voltar para dados da viagem).

- Se estiver tudo certo, ele confirma.

5. Finalização
- O sistema processa (d: viagem marcada).

- Exibe a mensagem de sucesso na cena Viagem concluída.

- O fluxo encerra retornando o usuário para a Tela Inicial (Home).

## Compra de Passagens

<p align="center">
  <img src="https://github.com/user-attachments/assets/402ea532-6194-40d7-852b-177e95059174" alt="sup" width="700"">
</p>

1. Início e Coleta de Dados do Passageiro
- Seleção: O usuário começa selecionando uma viagem específica na listagem (u: Selecionar viagem).

- Identificação: A primeira grande interação é informar quem vai viajar (Informações do passageiro).

- O sistema pede: Quantidade de passagens, Nome completo, Telefone, Documento (RG/CPF) e Data de nascimento.

- Validação: Se o usuário tentar avançar sem preencher tudo, o sistema barra e devolve para a mesma tela (d: dados não preenchidos).

2. O Checkout (Pagamento)
- Após inserir os dados do passageiro, o usuário vai para a tela de Formas de pagamento. Esta cena tem três funções importantes:

- Confirmação do Comprador: O sistema exibe os dados de quem está comprando (Nome, CPF, Email/Gmail e Contato) para garantir que o recibo vá para a pessoa certa.

- Escolha do Método (XOR): O usuário deve escolher entre:

- Pix: O sistema gera o QR Code e a chave Pix.

- Crédito/Débito: O sistema abre os campos para dados do cartão (Número, Validade, CVV).

- Correção de Dados (Navegação): Note a seta longa à esquerda (d: Alterar informações). Se, ao chegar no pagamento, o usuário perceber que digitou o nome do passageiro errado, ele pode voltar para a tela anterior sem cancelar a compra.

3. Validação Financeira
- Ao clicar em u: Prosseguir, o sistema verifica se uma forma de pagamento foi selecionada e processada.

- Se o usuário esquecer de selecionar, o sistema avisa (d: Pagamento não selecionado) e mantém ele na tela.

4. O Comprovante (Visualizar Passagem)
- Se o pagamento for aprovado (d: Valor pago), o usuário chega à cena final: Visualizar Passagem.

- Esta tela funciona como um Voucher/Bilhete Virtual, exibindo:

- Resumo da Compra.

- Dados do Passageiro.

- Confirmação do Pagamento.

- Feedback Final: O sistema informa explicitamente que uma cópia foi enviada para o email cadastrado (d: Será enviado uma mensagem...).

## Notificação do Dono da Embarcação

<p align="center">
  <img src="https://github.com/user-attachments/assets/2d1c44c8-0e6c-4ae0-8910-d3bc80206d8b" alt="sup" width="700"">
</p>


1. Início e Vínculo com a Viagem
- Ação: O proprietário decide u: criar nova notificação a partir da tela inicial.

- Contextualização: O sistema não deixa criar uma mensagem solta. Primeiro, é necessário selecionar a Viagem a ser Notificada.

- Isso garante que a mensagem chegue apenas para os passageiros daquele barco e horário específicos.

- Validação: Se o proprietário tentar avançar sem escolher, o sistema barra (d: selecione pelo menos uma viagem).

2. Redação da Mensagem
- Uma vez definida a viagem, o sistema abre a cena "Conteúdo da Notificação". Aqui a conversa se aprofunda:

- Preenchimento (SEQ): O usuário deve informar:

- A mensagem em si.

- O Motivo (ex: "Mau tempo", "Manutenção").

- A Descrição detalhada.

- Validação: O diagrama mostra um loop de retorno (u: preencher todas as informações) saindo da caixa preta. Isso indica que o sistema checa se os campos estão vazios antes de deixar prosseguir.

3. Revisão (Safety Check)
- Antes de disparar a notificação para os celulares dos clientes, o sistema leva para a cena "Confirmar conteúdo da mensagem".

- Visualização: O sistema exibe o motivo e a descrição para leitura.

- Correção: Existe uma seta tracejada à direita (u: alterar conteúdo da mensagem) que permite voltar para a tela anterior. Isso é essencial para evitar o envio de mensagens com erros de digitação ou informações confusas.

4. Disparo e Retorno
- Ação Final: O usuário confirma (u: notificação confirmada).

- Feedback: O sistema processa e exibe a confirmação (d: notificação criada com sucesso).

- Ciclo: A seta tracejada longa à esquerda leva o usuário de volta para a Caixa Cinza (Home), permitindo que ele continue usando o app para outras tarefas.

## Envio de Encomendas

<p align="center">
  <img src="https://github.com/user-attachments/assets/a73dd8f1-81d9-4dee-b47d-a6a42c533745" alt="sup" width="700"">
</p>

1. Definição da Rota (Logística)
- Início: O usuário seleciona u: Selecionar envio de encomenda na Home.

- Destino: A primeira preocupação do sistema é saber para onde vai (local de envio) e como vai (modalidade).

- Validação de Disponibilidade: O sistema checa se existe rota disponível para aquele local (o quadrado preto saindo com d: disponibilidade para a escolha). Se o usuário não preencher tudo, o sistema cobra (d: seleciona todas as opções...).

2. Identificação do Recebedor (Segurança)
- Cena: Informações do destinatário.

- Dados: O sistema exige Nome, CPF e Telefone de quem vai receber a encomenda no destino.

- Validação Específica: Note a regra de negócio explícita na linha tracejada: d: insira um CPF válido. O sistema provavelmente consulta se o CPF existe para evitar fraudes ou problemas na entrega.

3. Caracterização da Carga
- Cena: Tipo de Encomenda.

- Categorização: O usuário deve informar o que está enviando. O diagrama lista categorias vitais para o transporte fluvial: Eletrodomésticos, Móveis, Hortifruti (perecíveis), Materiais de construção, Veículos, etc.

- Detalhes: O usuário precisa especificar os detalhes.

- Navegação: Existe uma opção de voltar (u: retornar caso perceba algum erro) que leva de volta para a tela do destinatário.

4. Pagamento (Checkout)
- Transição: Há uma caixa cinza pequena que serve como um ponto de confirmação (u: prosseguir para pagamento).

- Cena: Métodos de Pagamento.

- Consistência: O fluxo é idêntico ao da compra de passagens: escolha entre Pix (QR Code) ou Cartão de Crédito (dados do cartão).

- Correção: Se o usuário chegar aqui e lembrar que descreveu o produto errado, ele pode voltar (u: alterar descrição da encomenda).

5. Finalização e Comprovante
- Sucesso: Após o pagamento ser processado (d: pagamento confirmado), o usuário vai para a cena Comprovantes.

- Feedback Duplo: O sistema mostra o comprovante na tela E envia por e-mail. Isso é crucial para encomendas, pois o remetente precisa enviar esse comprovante para o destinatário retirar a mercadoria.

- Fim: O fluxo retorna para a Home (d: retorno a home).

## Compra de Passagens e Envio de Encomendas

<p align="center">
  <img src="https://github.com/user-attachments/assets/0ae3b99b-8799-4bac-b0a2-ac2ffcdb0bab" alt="sup" width="700"">
</p>

1. A Iniciativa da Busca
- Início: O usuário abre o aplicativo e, na tela inicial (caixa cinza), decide u: Realizar Busca de Viagens.

- Cena Principal: Ele chega à cena "Navegar na Barra de Pesquisa".

- Parâmetros Básicos: Aqui ele define o essencial da viagem:

- Tipo (XOR): Ida OU Ida e Volta.

- Rota: Origem e Destino.

- Quando: Data.

2. O Poder dos Filtros (Refinamento)
- Esta é a parte mais rica do diagrama. O usuário pode decidir não apenas pesquisar por data, mas refinar a busca (u: Entra nos filtros).

- Cena de Filtros: O sistema exibe opções específicas (Navegar pelos Filtros).

- Critérios de Escolha (OR): O diagrama usa OR (ou), o que significa que o usuário pode marcar várias opções ao mesmo tempo. Os filtros mostram que o app está preparado para necessidades reais da região:

- Tipo de Embarcação: (Lancha rápida, Barco recreio, Balsa).

- Possuem Alimentação: (Importante para viagens longas).

- Transporte de Veículos: (Para quem precisa levar moto/carro).

- Acessibilidade: (Crucial para idosos ou PCDs).

- Acomodações: (Rede ou Camarote).

- Transporte de Pets: (Permite viajar com animais).

- Retorno: Após escolher, o usuário volta (u: Filtros Escolhidos) para a tela de resultados.

3. Seleção do Resultado
- Cena: Seleciona Destino (aqui o nome da caixa talvez fosse melhor como "Selecionar Viagem/Embarcação", mas o sentido é claro).

- Ação: O usuário vê as opções que sobraram após a filtragem e escolhe a que deseja (Usuario seleciona Destino e Embarcação).

4. Navegação e Desistência
- O diagrama prevê várias rotas de fuga (linhas tracejadas):

- Retornar: O usuário pode u: Volta a tela anterior tanto da tela de filtros quanto da tela de seleção.

- Cancelar: Da tela de pesquisa inicial ou da seleção final, ele pode u: Usuário Cancela Operação, voltando para a Home do app.
