# 🌤️ ClimaBot – ChatBot de Previsão do Tempo 
Assistente inteligente de previsão do tempo usando API Key da **IA (Gemini)** + **Open-Meteo** + **Google Colab** + **ipywidgets**.

---

## 📌 Sobre o projeto
Este projeto foi desenvolvido como parte de um case técnico, com o objetivo de demonstrar:

✔ Integração de modelos de **IA Generativa** (Google Gemini)  
✔ Consumo de API externa de dados meteorológicos (Open-Meteo)  
✔ Construção de um **chatbot interativo**, com interface estilo aplicativo  
✔ Tratamento de linguagem natural (NLP) para interpretar intenções de usuário 
✔ Arquitetura modular e organizada  

O bot é capaz de interpretar perguntas sobre clima e previsão do tempo em linguagem natural, diferenciando de perguntas sobre outros temas, extraindo:

- Cidade  
- Tipo de pergunta  
- Dia de referência  

E retornar previsões reais usando a API **Open-Meteo** que traz dados de geolocalização e clima.

---------------------------------------------------------------------------------------------------------------------------------------

## 🧠 Tecnologias utilizadas

| Componente | Tecnologia |
|-----------|------------|
| **IA Generativa** | Google Gemini (/gemini-2.5-flash) |
| **APIs Externas** | Open-Meteo  |
| **Backend** | Python 3 (Google Colab) |
| **Interface** | ipywidgets + HTML/CSS |
| **Estilo** | Tema personalizado inspirado no Banco BV |

---------------------------------------------------------------------------------------------------------------------------------------

## 🏗 Arquitetura do projeto


O notebook é organizado em três partes:

1. **Imports de Bibliotecas + Configuração do Gemini via API local**  
2. **Funções do backend**  
   - análise de intenção da pergunta
   - integração com Open-Meteo para dados de clima
   - formatação de resposta final baseada em critérios pré-estabelecidos
3. **Interface estilo chat (HTML + ipywidgets)**  

---------------------------------------------------------------------------------------------------------------------------------------

## 🔐 Configuração da chave de API (seguro)

Sua chave do Gemini **NÃO deve ser exposta no GitHub** ou em outros locais de compartilhamento do projeto, por isso criei uma célula isolada para rodar a chave previamente.
Para encontrar sua chave, basta ir em https://aistudio.google.com/api-keys e clicar em 'Criar chave de API'.
Após isso, é só copiar e colar a chave para o local indicado e rodar o código normalmente.

## ▶️ Como executar

1. Abra o notebook no Google Colab ou terminal de preferência.

2. Execute as células na ordem:

3. Configure a chave API local e pessoal.

4. Digite suas perguntas no chat, como por exemplo:

Vai chover em Campinas amanhã?  
Previsão para São Paulo no dia 24/12? -- indicará limitação da API  
Qual o clima atual em Recife?  
Previsão para Curitiba daqui 3 dias?  
2+2=? -- indicará limitação de escopo do Bot  

**✨ Recursos visuais do chatbot**


✔ Tema personalizado  
✔ Cabeçalho fixo azul  
✔ Balões de conversa arredondados (usuário/bot)  
✔ Ícones 🙂 / 🤖 abaixo das mensagens representando usuário/bot  
✔ Botão Nova conversa para reiniciar a interação   
✔ Enviar com Enter  
✔ Animação de “digitando…” antes da resposta do bot  



