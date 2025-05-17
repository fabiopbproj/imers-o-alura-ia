# Guia Desengasgo Bebê IA: Seu Assistente de Suporte Básico de Vida em Casa

![image](https://github.com/user-attachments/assets/cbffa871-c8dc-433f-94c9-1f9f738260b2)


## Sobre o Projeto

Como especialista em Primeiros Socorros com foco em Suporte Básico de Vida (SBV) para leigos, especialmente em situações pediátricas críticas, sempre fui motivado pela necessidade de capacitar as pessoas para agirem corretamente em momentos de emergência. Uma das situações mais aterrorizantes e que exigem ação rápida é o engasgo em bebês ou a perda de consciência, que podem ocorrer a qualquer momento em casa. Nesses instantes de pânico, o tempo é crucial e ter acesso a orientações claras e calmas pode salvar uma vida.

Motivado por essa necessidade e pela minha recente imersão em Inteligência Artificial Generativa na Alura, concebi o **"Guia Seguro Bebê IA"**. Este projeto visa criar um Agente de IA (chatbot avançado) capaz de guiar um cuidador leigo, que esteja sozinho e sob extremo estresse, através dos procedimentos emergenciais de SBV para bebês (< 1 ano), no padrão da American Heart Association (AHA), até a chegada do socorro profissional.

## O Problema que Resolvemos

Em uma emergência como o engasgo de um bebê ou uma parada cardiorrespiratória súbita em casa, o pânico é imediato. Cuidadores sem treinamento prévio (ou cujo treinamento foi há muito tempo) podem não lembrar os passos corretos do SBV, ou a ansiedade pode impedi-los de executar as manobras de forma eficaz. Um Agente de IA acessível pode fornecer instruções passo a passo, mantendo a calma e focando nas ações críticas.

## Funcionalidades Principais do Agente IA

* **Orientação Calma e Clara:** Comunica-se de forma simples, direta e tranquilizadora, essencial em momentos de alto estresse.
* **Guiamento Passo a Passo (SBV Pediátrico - AHA):** Fornece instruções procedurais para:
    * Identificação da emergência (engasgo vs. inconsciência).
    * Manobras de desengasgo em bebês conscientes (golpes nas costas e compressões peitorais).
    * Transição para RCP se o bebê ficar inconsciente.
    * Procedimentos básicos de RCP em bebês (compressões e ventilações - padrão leigo).
* **Priorização da Chamada de Emergência:** A primeira instrução após a identificação da emergência é sempre "LIGUE PARA 192 ou 193 AGORA!". O Agente incentiva o uso do viva-voz para continuar o guiamento.
* **Recursos Complementares (Futuro/Referência):** Capacidade de referenciar ou descrever recursos visuais (como links para vídeos curtos de demonstração) no momento apropriado do procedimento.

## Como Funciona (Visão Técnica)

O "Guia Seguro Bebê IA" é construído utilizando:

* **Python:** Linguagem de programação principal para orquestrar a interação.
* **Google Colab:** Ambiente de desenvolvimento e execução inicial (para este projeto).
* **Google AI Studio / Gemini API:** O coração inteligente do Agente. O modelo **Gemini 1.5 Flash (latest)** é utilizado para processar as entradas do usuário, manter o contexto da conversa e gerar as respostas do Agente com base nas instruções e na persona definida.
* **System Instruction:** Uma configuração crucial no Gemini API (ou no prompt inicial) que define o papel do Agente como especialista em SBV, garantindo o tom, a prioridade da chamada de emergência e a aderência aos protocolos AHA.

O script Python atua como a interface: recebe a entrada do usuário (simulada via texto no Colab), envia para o Gemini API, recebe a resposta gerada pela IA e a exibe para o usuário, guiando a conversa e, no futuro, gerenciando a sequência dos passos do SBV de forma mais robusta.

## Estrutura do Projeto

* `README.md`: Este arquivo, descrevendo o projeto.
* `guia_seguro_bebe.ipynb` (ou `.py`): O arquivo principal em Python contendo o código para interagir com a Gemini API, definir a persona e gerenciar o fluxo básico da conversa e do SBV.

## Como Rodar o Projeto

1.  **Pré-requisitos:**
    * Conta Google.
    * Acesso ao Google Colab.
    * Obter uma API Key do Google AI Studio (ou Google Cloud).
2.  **Obtenha o Código:**
    * Clone este repositório: `git clone <URL_DO_SEU_REPOSITORIO>`
    * Navegue até a pasta do projeto.
3.  **Configure a API Key no Google Colab:**
    * Abra o notebook `guia_seguro_bebe.ipynb` no Google Colab.
    * No menu lateral esquerdo, clique no ícone da chave (🔑) para abrir "Segredos".
    * Clique em "Gerenciar segredos".
    * Clique em "Adicionar novo Segredo".
    * No campo "Nome", digite **`GOOGLE_API_KEY`**.
    * No campo "Valor", cole a sua API Key obtida no Google AI Studio.
    * Marque a caixa "Acesso ao notebook".
    * Feche a janela de segredos.
4.  **Execute as Células no Colab:**
    * Execute a primeira célula para instalar a biblioteca.
    * Execute a segunda célula para importar a biblioteca e configurar a API Key (ela deve acessar o segredo que você configurou).
    * Execute a terceira célula para definir o modelo e a instrução do sistema.
    * Execute a quarta célula para iniciar o chat e ver a resposta inicial do Agente.
    * Execute a quinta célula para entrar no loop de interação e simular a conversa passo a passo. Digite `fim` para sair.

## Exemplo de Uso (Simulado)
