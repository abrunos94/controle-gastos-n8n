🤖 Jarvis Intelligence - Gestão Financeira via Telegram <br>
O Jarvis Intelligence é uma solução de automação para finanças pessoais que permite registrar ganhos e gastos em tempo real através do Telegram, eliminando a necessidade de abrir planilhas manualmente no dia a dia.

📑 Visão Geral do Projeto <br>
Este projeto integra o Telegram como interface de usuário (UI), o n8n como motor de orquestração e o Google Sheets como banco de dados (DB).

🛠️ Tecnologias Utilizadas <br>
- Orquestrador: n8n (Workflow Automation).

- Interface (Bot): Telegram Bot API.

- Banco de Dados: Google Sheets API.

- Lógica de Negócio: JavaScript (Node.js) para processamento de dados e agregação aritmética.

🚀 Como Funciona? <br>
1. Registro de Dados
O usuário envia comandos simples no chat para registrar transações:

/receita [valor] - Registra entrada de dinheiro.

/gastofixo [categoria] [valor] - Registra despesas recorrentes (Aluguel, Internet, etc).

/gasto [descrição] [valor] [categoria] - Registra despesas do dia a dia.

2. Processamento e Lógica <br>
O sistema utiliza um nó de código JavaScript personalizado para filtrar os dados por mês, agrupar categorias e calcular o saldo final. Para garantir a integridade dos cálculos, o fluxo foi projetado de forma linear e com a configuração Execute Once em nós críticos, evitando a duplicidade de informações.

3. Visualização do Fluxo <br>
Abaixo, o diagrama UML que ilustra a comunicação entre os sistemas:
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/b9812fe7-8260-47c6-aed3-b59b9d55d09c" />
4. Visualização do Fluxo na tela do n8n<br>
<img width="815" height="633" alt="image" src="https://github.com/user-attachments/assets/f9daaae0-6768-402d-a72d-a72a4934fb61" />
📊 Resultados e Demonstração <br>
Relatórios Automáticos <br>
O Jarvis gera relatórios detalhados com listas verticais de gastos e cálculo de saldo residual.

Demonstração em Vídeo <br>
Confira o Jarvis Intelligence em ação registrando uma receita e gerando um relatório:


https://github.com/user-attachments/assets/20d9d8b8-a8ab-4bce-8f60-36f5ac4b967c

⚙️ Como Testar o Projeto <br>
Para replicar este projeto, siga os passos abaixo:

Clone o Repositório:

Bash
git clone https://github.com/seu-usuario/jarvis-intelligence.git
Importe o Fluxo no n8n:

No seu n8n, clique em "Workflows" -> "Import from File".

Selecione o arquivo Simple Monthly Expense Tracker (27).json da pasta /workflow.

Configuração de Credenciais:

Crie um bot no Telegram via @BotFather e insira o Token no nó Telegram Trigger.

Configure as credenciais do Google Sheets e aponte os IDs das planilhas nos nós de leitura e escrita.

🗄️ Banco de Dados (Sheets): <br>

Crie uma planilha com as abas Renda, Fixed_Expenses e Daily_Expenses, seguindo o cabeçalho: user | category | value | month | chat_id.

Ative o Workflow:

Mude a chave no canto superior direito do n8n para Active.

