<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:6C63FF,100:48CAE4&height=200&section=header&text=André%20Quintela&fontSize=50&fontColor=ffffff&fontAlignY=38&desc=AI%20Engineer%20em%20formação%20%7C%20LLMs%20•%20RAG%20•%20ML%20•%20.NET&descAlignY=58&descSize=18" width="100%"/>

### Levo IA do notebook à produção.

[![Portfólio](https://img.shields.io/badge/Portfólio-andre--quintela.github.io-6C63FF?style=for-the-badge&logo=googlechrome&logoColor=white)](https://andre-quintela.github.io)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-André%20Quintela-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/andre-quintela/)
[![Gmail](https://img.shields.io/badge/E--mail-andre.lsquintela%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:andre.lsquintela@gmail.com)

</div>

---

## Em 30 segundos

- **Coloquei um produto com LLM em produção.** O [Letters](https://github.com/Andre-Quintela/Letters) corrige redações com Azure OpenAI e está no ar, com [demo](https://letterspi.azurewebsites.net/) e [vídeo](https://youtu.be/RH9m-NrcWZk).
- **Construí um RAG distribuído que não cai junto com o LLM.** São 3 microsserviços com Redis Streams, circuit breaker, retry e timeout, cobertos por 15 testes automatizados.
- **Treino e avalio modelos** de visão computacional (ResNet-50, CNN), NLP (BERT) e sistemas de recomendação (SVD).
- **Tenho base sólida de engenharia de software:** trabalho com C#, .NET e Angular em Clean Architecture. Por isso penso em IA como *sistema* — confiável, testável e útil para quem usa.

---

## Destaque: RAG distribuído que continua de pé quando o LLM cai

> [`C2-Howard`](https://github.com/Andre-Quintela/C2-Howard) · Python · FastAPI · Redis Streams · Docker · pytest

```mermaid
flowchart LR
    C([Cliente]) --> G[Geração]
    D([Documentos]) -- fila --> I[Ingestão<br/>trechos + embeddings]
    G -- REST --> R[Recuperação<br/>cosseno + reranking]
    R -- REST --> I
    G --> CB{{retry · circuit breaker · timeout}}
    CB --> L[(LLM)]
```

| Problema | Decisão |
|---|---|
| O LLM é lento e instável | Fila também nas perguntas: workers assíncronos que escalam horizontalmente |
| Mensagem pode se perder numa falha | Sem `ACK` em falha: a mensagem volta para a fila, até 3 tentativas |
| LLM fora do ar | Disjuntor aberto → `503` **com os trechos recuperados**, sem esperar timeout |
| Busca sem contexto relevante | Não chama o LLM: evita custo e alucinação |

---

## As duas frentes da engenharia de IA

<table>
<tr>
<td width="50%" valign="top">

### Engenharia de software com foco em IA

| Projeto | O que mostra |
|---|---|
| [**Letters**](https://github.com/Andre-Quintela/Letters) | LLM integrado a um produto web em produção (.NET 8, Angular, Azure OpenAI, Azure SQL) |
| [**RAG Distribuído**](https://github.com/Andre-Quintela/C2-Howard) | Resiliência em volta do LLM em microsserviços |
| [**Inferência Distribuída**](https://github.com/Andre-Quintela/sd-2026-2-kit-c1a2) | Modelo servido por REST **e** gRPC, com fila Redis e workers |

</td>
<td width="50%" valign="top">

### Engenharia de IA e Machine Learning

| Projeto | O que mostra |
|---|---|
| [**Food Classification**](https://github.com/Andre-Quintela/Food-Classification) | Fine-tuning de ResNet-50 em 41 classes de pratos (PyTorch) |
| [**Sentimento em Avaliações**](https://github.com/Andre-Quintela/NLP-ANALISE-DE-SENTIMENTOS) | BERT em português, insights por aspecto |
| [**Recomendador de Restaurantes**](https://github.com/Andre-Quintela/Recomendador-De-Restaurantes) | Recomendação híbrida: conteúdo + SVD |
| [**Detecção de Capacete**](https://github.com/Andre-Quintela/CNN-Motoqueiros-sem-capacetes) | CNN para visão computacional |
| [**House Prices**](https://github.com/Andre-Quintela/House-Prices---Machine-Learning-Hackathon) | Competição do Kaggle de ponta a ponta |

</td>
</tr>
</table>

### IA no universo da comida

Três dos meus projetos nasceram do mesmo domínio — **comida e restaurantes**:

- **Classificar** o prato pela foto
- **Entender** o que os clientes dizem nas avaliações
- **Recomendar** o próximo restaurante

É um domínio onde dados e IA mudam a experiência de muita gente todos os dias.

---

## Como eu construo sistemas com IA

| | |
|---|---|
| **Planejo para quando der errado** | Timeout, retry com backoff e jitter, circuit breaker e degradação elegante |
| **Meço antes de confiar** | Separação treino/validação, métricas (acurácia, R², RMSE), avaliação automática das respostas do RAG e testes |
| **Segredo não vai pro código** | `user-secrets` e `.env`, além de modo simulado para rodar sem chave de API |
| **IA a serviço do usuário** | O modelo é uma parte; o valor aparece quando ele vira produto |

---

## Stack

<div align="center">

**LLMs & Machine Learning**

![Azure OpenAI](https://img.shields.io/badge/Azure%20OpenAI-0078D4?style=for-the-badge&logo=openai&logoColor=white)
![HuggingFace](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

**Servir IA em produção**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![gRPC](https://img.shields.io/badge/gRPC-244C5A?style=for-the-badge&logo=grpc&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white)

**Engenharia de software**

![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=csharp&logoColor=white)
![.NET](https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![Angular](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

</div>

---

<div align="center">

<img height="170em" src="https://github-readme-stats.vercel.app/api?username=Andre-Quintela&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true&hide_border=true"/>
<img height="170em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Andre-Quintela&layout=compact&langs_count=8&theme=tokyonight&hide_border=true&hide=jupyter%20notebook"/>

</div>

---

<div align="center">

### Vamos construir IA que gera impacto?

Estou aberto a oportunidades em **engenharia de IA**.
O jeito mais rápido de conhecer meu trabalho é o **[portfólio](https://andre-quintela.github.io)**.

[![Portfólio](https://img.shields.io/badge/-Portfólio-6C63FF?style=flat-square&logo=googlechrome&logoColor=white)](https://andre-quintela.github.io)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/andre-quintela/)
[![Gmail](https://img.shields.io/badge/-andre.lsquintela%40gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:andre.lsquintela@gmail.com)

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:48CAE4,100:6C63FF&height=120&section=footer" width="100%"/>

</div>
