# Sprint_IA

# GoodWe EV Chatbot — EV Challenge 2026

> Chatbot com IA baseado em RAG para suporte operacional de eletropostos e gestão de recarga em condomínios.
> O Chatbot está no final do readme
---

##Integrantes

- Mauricio Bertuci Saletti - RM571229
- Mateus Eduardo da Cruz Rocha - RM570736
- Lucas Caram Bueno - RM570158
- ⁠Rhuan Pacheco Carreri - RM570129
- Leonardo Fortini Marcelo - RM572566
- ⁠Nicolas Andrade Rodrigues - 572782


---

## Problema Abordado

A GoodWe identificou dois gaps críticos no ecossistema de mobilidade elétrica urbana:

**1. ChargeGrid Intelligence (operadores comerciais)**
Eletropostos públicos e comerciais carecem de mecanismos integrados para orquestrar potência entre múltiplos carregadores, registrar ciclos de uso, emitir cobranças automáticas e comunicar status em tempo real. Isso resulta em perda de receita, manutenção reativa e experiência ruim para o usuário final.

**2. EV ChargeOps (condomínios)**
Em condomínios, a ausência de um sistema de gestão de uso compartilhado das tomadas gera conflitos entre moradores, sobrecarga da rede elétrica do edifício e impossibilidade de rateio justo de custos.

---

## Proposta do Chatbot

O GoodWe EV Chatbot é uma ferramenta operacional voltada para operadores comerciais de eletropostos, respondendo dúvidas sobre:

- Configuração e monitoramento de carregadores GoodWe
- Orquestração de potência e gerenciamento de carga
- Registro de sessões e faturamento automático
- Diagnóstico de falhas e manutenção preventiva
- Integração com sistemas de back-office

### Por que o contexto comercial?

O operador comercial é a persona com maior volume de interações repetitivas e técnicas, tornando o chatbot mais impactante nesse contexto. Dúvidas sobre configuração, faturamento e diagnóstico consomem tempo de suporte especializado que pode ser automatizado com RAG.

---

##  Tecnologias Selecionadas

Modelo de linguagem LLAMA e o editor Google Colab

---

##  Fluxo de Funcionamento

```
Usuário digita pergunta
        ↓
Busca semântica no vector store
Retorna top-4 trechos relevantes dos PDFs
        ↓
Monta prompt: system prompt + contexto + pergunta
LLaMA gera a resposta
        ↓
Resposta exibida ao usuário + documentos-fonte retornados
```

---

## System Prompt (Contexto-Base)

```
Você é um assistente técnico especializado em produtos GoodWe para 
mobilidade elétrica, com foco em eletropostos comerciais e sistemas 
de recarga.

Seu papel é apoiar operadores comerciais de eletropostos com dúvidas 
sobre: configuração de equipamentos, orquestração de potência, 
registro de sessões de recarga, faturamento, diagnóstico de falhas 
e manutenção.

Regras:
- Responda SEMPRE em português
- Use apenas as informações presentes nos documentos fornecidos
- Se não encontrar a informação, responda: "Não encontrei essa 
  informação na documentação disponível. Consulte o suporte GoodWe."
- Seja objetivo e técnico
- Cite a seção ou página do documento quando possível
```

---

##  Modelo de Teste

Pergunta, Resposta Esperada

 1  O que é o ChargeGrid Intelligence e qual problema ele resolve? | Sistema da GoodWe que integra orquestração de potência, registro de ciclos, faturamento e comunicação dos eletropostos em uma única plataforma, resolvendo a fragmentação de gestão em postos comerciais. 

 2  Como funciona o gerenciamento de potência entre múltiplos carregadores? | O sistema distribui dinamicamente a potência disponível entre os carregadores ativos, priorizando sessões conforme regras configuradas pelo operador, evitando sobrecarga da rede. 

 3  Como é feito o registro e faturamento de uma sessão de recarga? | Cada sessão é registrada automaticamente com dados de início, fim, energia consumida (kWh) e identificação do usuário, gerando cobrança automática via plataforma integrada.
 
 4  Quais alertas o sistema emite em caso de falha no carregador? | O sistema notifica o operador em tempo real via painel e e-mail com código de erro, carregador afetado e sugestão de ação corretiva, permitindo manutenção proativa. 

 5  Como configurar o limite de potência por ponto de recarga? | Acesse o painel de gestão GoodWe, selecione o carregador desejado, vá em Configurações > Potência e defina o limite máximo em kW. A alteração é aplicada imediatamente. 

---

---

##  Links

- HuggingFace — LLaMA 3.2-1B-Instruct (https://huggingface.co/meta-llama/Llama-3.2-1B-Instruct)
- LangChain Docs (https://python.langchain.com)
- GoodWe EV Challenge 2026 — FIAP

***https://colab.research.google.com/drive/133L6kvWXE4glEdPkMe-0JvoTpszbRu_T?usp=sharing#scrollTo=efb4aa7c***
