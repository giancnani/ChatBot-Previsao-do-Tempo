# 🌤️ ClimaBot – ChatBot de Previsão do Tempo 
Assistente inteligente de previsão do tempo usando API Key da **IA (Gemini)** + **Open-Meteo** + **Google Colab** + **Streamlit**.

---

## 📌 Sobre o projeto
Este projeto foi desenvolvido como parte de um case técnico, com o objetivo de demonstrar:

✔ Integração de modelos de **IA Generativa** (Google Gemini)  
✔ Consumo de API externa de dados meteorológicos (Open-Meteo)  
✔ Construção de um **chatbot interativo**, com interface estilo aplicativo  
✔ Tratamento de linguagem natural (NLP) para interpretar intenções de usuário 
✔ Arquitetura modular e organizada  

## 📌 Descrição Geral
O ClimaBot – BV é um chatbot inteligente capaz de:

✔ Interpretar perguntas em linguagem natural sobre clima e previsão do tempo

✔ Identificar cidade, tipo de pergunta e dia solicitado

✔ Buscar dados meteorológicos reais via Open-Meteo

✔ Retornar respostas detalhadas, estruturadas e contextualizadas

✔ Interagir em interface estilo chat (frontend Streamlit)

✔ Exibir mensagens com horário e animação “digitando…”

✔ Ele foi projetado seguindo princípios de:

 --simplicidade,

--clareza,

--boa arquitetura,

--praticidade para auditoria (monitoramento, logs, explicações claras).

Além disso, o projeto prevê expansão futura com:

--LangChain/LangGraph

--desenvolvimento de métricas de desempenho do chatbot

-- melhoria do dataset de testes automatizados de verificação de desempenho



---------------------------------------------------------------------------------------------------------------------------------------

## 🧠 Tecnologias utilizadas

| Componente | Tecnologia |
|-----------|------------|
| **IA Generativa** | Google Gemini (/gemini-2.5-flash) |
| **APIs Externas** | Open-Meteo  |
| **Backend** | Python 3 (Google Colab) |
| **Interface** | Streamlit |
| **Estilo** | Tema personalizado inspirado no Banco BV |

| Tecnologia                | Descrição                                |
| ------------------------- | ---------------------------------------- |
| **API Gemini** | Interpretador de linguagem natural (NLU) |
| **Open-Meteo API**        | Geolocalização e previsão do tempo       |
| **Streamlit**             | Interface do chatbot                     |
| **Python 3.10+**          | Base do projeto                          |
| **pyngrok**               | Deploy da interface Streamlit no Colab   |
| **pytz**                  | Fuso horário para Brasil                 |


---------------------------------------------------------------------------------------------------------------------------------------

## 🏗 Arquitetura do projeto


O notebook é organizado em três partes:

1. **Imports de Bibliotecas + Configuração do Gemini via API local**  
2. **Funções do backend**  
   - análise de intenção da pergunta
   - integração com Open-Meteo para dados de clima
   - formatação de resposta final baseada em critérios pré-estabelecidos
3. **Interface estilo chat (Streamlit)**

## 🏗 Fluxo de Interação
→ Usuário  
→ Streamlit UI  
→ analise_gemini()      
→ Gemini LLM → interpretar intenção → extrair cidade + tipo + referência de data →            
→ gerar_resposta_clima()  
→ Open-Meteo (geocoding + forecast)  
→ interpretar weathercode  
→ compor resposta human-friendly  
→ Streamlit exibe resposta com bolhas de chat  

---------------------------------------------------------------------------------------------------------------------------------------

## 🔐 Configuração da chave de API (seguro)

Sua chave do Gemini **NÃO deve ser exposta no GitHub** ou em outros locais de compartilhamento do projeto, por isso criei uma célula isolada para rodar a chave previamente.
Para encontrar sua chave, basta ir em https://aistudio.google.com/api-keys e clicar em 'Criar chave de API'.
Após isso, é só copiar e colar a chave para o local indicado e rodar o código normalmente.

## ▶️ Como executar

1. Abra o notebook no Google Colab ou terminal de preferência.

2. Configure a chave API local e pessoa e o token ngrok

3. Execute as células na ordem.  

4. Digite suas perguntas no chat, como por exemplo:

Vai chover em Campinas amanhã?  
Previsão para São Paulo no dia 24/12? -- indicará limitação da API  
Qual o clima atual em Recife?  
Previsão para Curitiba daqui 3 dias?  
2+2=? -- indicará limitação de escopo do Bot  

**✨ Principais funcionalidades**  
Interpretação contextual com Gemini  
✔ entende perguntas como:  
--“Vai chover amanhã em Campinas?”  
--“Previsão para 24/12 em São Paulo”  
✔ corrige datas como 24/12, 01-01, etc.  
✔ identifica perguntas fora de escopo (“qual seu nome?”, etc.)  

Integração com Open-Meteo  
✔ busca coordenadas reais da cidade  
✔ obtém previsão diária (máx/min chuva e weathercode)  
✔ limita consulta a 4 dias (restrição da API)  

Respostas naturais e amigáveis  
✔ emojis ☀️ ⛈️ 🌧️  
✔ sensação térmica (frio, ameno, quente, muito quente)  
✔ recomendações práticas  
✔ aviso quando data solicitada ultrapassa limite da API  

Interface estilo chat  
✔ balões de mensagem  
✔ horário em cada mensagem  
✔ bot "digitando…”  
✔ Enter para enviar  
✔ botão “Nova conversa”   

**Backend**  
O backend está isolado no arquivo:  

backend.py  


Ele contém:  
✔ processamento semântica com Gemini  
✔ tratamento de datas  
✔ consulta Open-Meteo  
✔ formatação de respostas  
✔ fallback para fora de escopo    

Isso permite fácil reuso e evolução futura para:  
--LangChain  
--métricas  
--logs  
--agentes inteligentes  
-- estudos de caso (ex: comparação e diversificação de respostas maias vançadas)  



