
# <p align="center"> Heurísticas presentes na aplicação
</p>

Este documento apresenta uma análise de usabilidade aplicada ao protótipo do projeto Porto Certo.

A concepção da interface, desenvolvida no Figma, foi fundamentada nas Heurísticas de Usabilidade de Jakob Nielsen. O objetivo desta etapa de design foi estruturar os fluxos de interação e garantir uma experiência de usuário (UX) sólida 
e intuitiva antes do início do desenvolvimento técnico.

As decisões visuais e de navegação documentadas a seguir visam reduzir a carga cognitiva e alinhar o sistema ao modelo mental dos usuários de transporte fluvial da região amazônica. Abaixo, detalhamos como os princípios de Interação 
Humano-Computador (IHC) foram integrados aos mockups e componentes do protótipo.

## Compatibilidade entre o sistema e o mundo real
<br>

<p align="center">
  <img src="https://github.com/user-attachments/assets/d3e527a1-f80d-4a64-8bed-d045ba31bb3c" alt="sup" width="400"">
</p>

<p align="center"> <i>Figura 1:</i> Tela demonstrativa da heurística compatibilidade entre o sistema e o mundo real
</p>

<br>

### 1. Linguagem Natural e Terminologia Familiar

O sistema utiliza palavras e frases que fazem parte do vocabulário cotidiano de quem viaja, evitando termos técnicos de sistemas (como "input de dados" ou "query de busca").

<br>
<br>
  - "Origem" e "Destino": São termos universais de transporte. O usuário entende imediatamente que precisa dizer de onde sai e para onde vai.
  - "Somente Ida" e "Ida e Volta": Refletem exatamente as opções de compra de passagens em um guichê físico de porto ou rodoviária.
  - "Embarque em...": O uso da palavra "Embarque" (ao invés de "Início" ou "Partida") conecta-se diretamente ao contexto náutico/viagem.
<br>

### 2. Metáforas Visuais (Iconografia)

Os ícones utilizados funcionam como "atalhos mentais" porque imitam objetos do mundo físico. Isso reduz a carga cognitiva, pois o usuário não precisa "aprender" o significado do ícone; ele já o conhece.
<br>
<br>
  - Ícone de Calendário (campo "Ida"): Representa a data. No mundo real, olhamos um calendário para planejar viagens.
  - Ícones de Pin de Mapa (nos campos de local): O "pin" tornou-se um padrão global (graças ao Google Maps) para representar um ponto físico no mundo real.
  - Ícone de Lupa (botão "Buscar"): Remete à ação de investigar ou procurar algo, uma metáfora clássica de investigação no mundo físico.
  - Ícone de Mala (Menu "Viagens"): A mala é o objeto físico mais associado ao ato de viajar. O usuário entende que ali estarão seus bilhetes ou histórico.
<br>

## Design estético e minimalista
<br>

<div align="center">
<p float="left">
  <img src="https://github.com/user-attachments/assets/1e9c647c-8119-464e-b8b6-bc61ecd75900" width="39%" />
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://github.com/user-attachments/assets/f48025c5-3002-41ad-9c8d-c6add28aa1b9" width="36.5%" /> 
</p>
</div>

<p align="center"><i>Figura 2:</i> Representação da heurística design estético e minimalista</p>

<br>

### 1. O Conceito Central: "Divulgação Progressiva"

A Heurística 8 não diz apenas para deixar a tela "bonita"; ela diz que "cada unidade extra de informação compete com as unidades de informação relevantes".

<br>

  - Tela 1 (A Lista): Se fosse colocado todas as informações (Passagens, Vendidas, Embarque/Desembarque detalhado) diretamente na lista principal, a tela ficaria poluída, difícil de ler (scannable) e o usuário ficaria sobrecarregado cognitivamente.
  - A Solução: O design mantém a lista minimalista, mostrando apenas o essencial para a decisão imediata (Barco, Rota e Data principal).
  - Tela 2 (O Modal): Os detalhes secundários (quantidade de passagens, datas específicas de desembarque) são exibidos apenas sob demanda. Isso é chamado de Divulgação Progressiva.
<br>

## Liberdade e controle do usuário
<br>

<div align="center">
<p float="left">
  <img src="https://github.com/user-attachments/assets/e400748f-83ff-47bc-9dec-f6d59faeebae" width="38%" />
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://github.com/user-attachments/assets/a6a19fd1-9b9f-4b40-8e69-d05183cb2311" width="38.11%" /> 
</p>
</div>
<p align="center"><i>Figura 3:</i> Opções de acessibilidade disponíveis ao usuário</p>

<br>

### 1. A Liberdade de Escolha (Configuração do Estado)
O sistema não impõe uma única forma de visualização. Ao oferecer a tela de "Opções de Acessibilidade", você está entregando o controle nas mãos do usuário.
<br>

  - O Cenário: O usuário pode estar em um ambiente com muito sol, ou ter baixa visão, ou simplesmente preferir interfaces escuras para não cansar a vista.
  - O Controle: Ele tem a liberdade de ativar o "Alto Contraste" (mudando da tela branca para a preta) ou "Textos Ampliados". Ele não é refém do design padrão definido pelo programador.
<br>

### 2. A Capacidade de Reversão (Undo/Redo)
Um dos pilares dessa heurística é a "saída de emergência" e a capacidade de desfazer ações.
<br>

  - Note que os botões na tela de acessibilidade (Alto Contraste, Textos Ampliados) funcionam como interruptores (toggles).
  - Isso implica que o usuário tem a liberdade de testar: "Deixa eu ver como fica no modo escuro... ah, não gostei", e imediatamente desligar a opção, voltando ao estado original. Essa reversibilidade sem punição é a essência do "Controle do Usuário".
<br>

### 3. A "Saída de Emergência" (Navegação)
Além da troca de cores, há um elemento clássico dessa heurística presente em todas as telas (canto superior esquerdo): a Seta de Voltar (←).
<br>

  - Se o usuário entrou na tela de "Opções de Acessibilidade" por engano, ele tem uma "saída de emergência" clara e marcada para voltar à tela anterior (o Dashboard ou Configurações) sem ter que fechar o aplicativo ou completar uma tarefa indesejada.
<br>

## Prevenção de erros
<br>

<p align="center">
  <img src="https://github.com/user-attachments/assets/73193e9e-8f22-4fc2-85a6-af4bfc6a7ed2" alt="sup" width="400"">
</p>
<p align="center"><i>Figura 4:</i> Usuário não precisa digitar o nome da cidade e correr o risco de errar</p>
<br>

### 1. Eliminação de Erros de Digitação ("Slips")
Se este campo fosse uma caixa de texto livre onde o usuário tivesse que digitar "Itacoatiara", poderiam ocorrer inúmeros erros:
<br>

  - Erros de digitação: "Itacotiara", "Itacoatira".
  - Variações de acentuação: "Belem" vs "Belém".
  - Case sensitive: "manaus" vs "Manaus".
  - Ao forçar a escolha em uma lista, o sistema impossibilita que o usuário cometa esses erros mecânicos. O dado que entra no sistema é sempre limpo e exato (100% validado).
<br>

### 2. Restrição ao Conjunto Válido ("Constraints")
A heurística de prevenção de erros sugere o uso de restrições.
<br>

  - Imagine que o usuário digite "São Paulo". Esse seria um erro conceitual, pois não há rota de barco saindo de São Paulo para o Amazonas.
  - Ao apresentar apenas a lista de cidades onde a empresa opera (Alenquer, Almerim, Alvarães, etc.), você impede que o usuário tente buscar uma rota inexistente. Você evita a frustração de ele clicar em "Buscar" e receber uma mensagem de erro dizendo "Cidade não encontrada".
<br>

### 3. Redução da Carga de Memória (Heurística Bônus #6)
Embora o foco seja prevenção de erros, essa tela também toca na Heurística #6 (Reconhecer em vez de relembrar).
<br>

  - O usuário não precisa lembrar se a cidade se escreve com "s" ou "z", ou qual é a sigla do estado (AM ou PA). Ele apenas precisa reconhecer o nome correto na lista.
<br>

## Ajuda e documentação
<br>

<div align="center">
<p float="left">
  <img src="https://github.com/user-attachments/assets/359d5cf5-7e03-4401-b75a-785430677143" width="38%" />
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
  <img src="https://github.com/user-attachments/assets/ea9d46cb-925a-4410-b72c-e6f796f33d37" width="38.12%" />
</p>
</div>
<br> 

### 1. Embora seja melhor que o sistema não precise de explicações, pode ser necessário fornecer ajuda contextual.
<br>

  - O que está acontecendo na tela: O ícone de interrogação (?) funciona como um pedido de socorro pontual. O usuário pensa: "O que eu devo escrever aqui?".
  - A resposta do sistema: O balão "Informar local de saída do transporte" é uma mini-documentação. Ele não diz como o sistema está (status), ele ensina o usuário como usar o campo.
<br>



