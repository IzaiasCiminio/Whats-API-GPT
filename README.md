# Whats-API-GPT
Projeto criando com um curso de automação Python

Esta automação implementada em Python utiliza a biblioteca Selenium para interagir com o WhatsApp Web e a API do OpenAI para processar e responder mensagens automaticamente. Abaixo está uma breve descrição das etapas e funcionalidades do código:

1. **Configuração Inicial**:
   - Importa as bibliotecas necessárias, incluindo `selenium` para automação do navegador e `openai` para integração com a API do OpenAI.
   - Configura o agente de usuário e faz uma requisição HTTP para obter informações de configuração específicas (classes de HTML) de uma API externa.

2. **Configuração do Navegador**:
   - Obtém o diretório atual e configura as opções do Chrome para usar um perfil de usuário específico, permitindo a preservação de sessões e cookies.
   - Inicializa o WebDriver do Chrome apontando para o caminho específico do `chromedriver.exe`.
   - Abre o WhatsApp Web e espera 10 segundos para garantir que a página esteja completamente carregada.

3. **Função Principal (bot)**:
   - Inicia um loop infinito que aguarda novas mensagens no WhatsApp.
   - Procura por notificações de novas mensagens (indicadas por uma "bolinha" no WhatsApp Web).
   - Se uma nova mensagem for detectada, clica na notificação para abrir a conversa.

4. **Processamento da Mensagem**:
   - Captura a última mensagem recebida do cliente.
   - Envia a mensagem para a API do OpenAI, que usa o modelo `gpt-3.5-turbo` para gerar uma resposta baseada no conteúdo da mensagem do cliente.

5. **Resposta Automática**:
   - Envia a resposta gerada pela API do OpenAI de volta para o campo de texto do WhatsApp e envia a mensagem.

6. **Tratamento de Erros**:
   - Inclui tratamento de exceções para capturar e imprimir erros relacionados à interação com o Selenium e à API do OpenAI, garantindo que o script não seja interrompido por falhas.

7. **Loop Infinito**:
   - Após responder a mensagem, o script aguarda 10 segundos antes de verificar novamente por novas mensagens, criando um loop contínuo de monitoramento e resposta.
