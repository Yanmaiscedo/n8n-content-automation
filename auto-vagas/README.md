# 🚀 Alerta de Vagas Automático com n8n

## 📌 Sobre o Projeto

Este projeto consiste em uma automação criada com **n8n** que monitora vagas de tecnologia em tempo real e envia notificações automaticamente.

A automação realiza:

* 🔎 Busca de vagas em APIs públicas
* 🧠 Filtragem inteligente por palavras-chave
* 📩 Envio automático de vagas via Telegram ou email

O objetivo é criar um fluxo prático e funcional que ajude na busca por oportunidades na área de tecnologia.

---

## 🧠 Como Funciona

O fluxo automatizado segue a seguinte lógica:

```text
Cron → HTTP Request → Function → IF → Telegram
```

### 🔁 Etapas do Workflow

#### 1. ⏰ Cron (Trigger)

Executa automaticamente em intervalos definidos (ex: a cada 1 hora).

#### 2. 🌐 HTTP Request

Realiza requisição para APIs de vagas, como:

* Remotive API
* Arbeitnow API

#### 3. 🧠 Function (Filtro)

Filtra vagas com base em palavras-chave como:

* Python
* Dados
* Estágio

Exemplo de código utilizado:

```javascript
return items.filter(item => 
  item.json.title.toLowerCase().includes("python") ||
  item.json.title.toLowerCase().includes("dados") ||
  item.json.title.toLowerCase().includes("estágio")
);
```

#### 4. 🔀 IF (Validação)

Verifica se existem vagas relevantes antes de prosseguir.

#### 5. 📩 Notificação (Telegram/Email)

Envia automaticamente uma mensagem com os dados da vaga:

```
🚀 Nova vaga encontrada!

💼 Cargo: Data Analyst
🏢 Empresa: Empresa XYZ
🔗 Link: https://...
```

---

## ⚙️ Tecnologias Utilizadas

* n8n (automação de workflows)
* Docker (execução local)
* APIs de vagas
* JavaScript (filtros e lógica)

---

## 🚀 Como Executar o Projeto

### 1. Clonar o repositório

```bash
git clone https://github.com/seu-usuario/n8n-content-automation.git
cd n8n-content-automation
```

### 2. Subir o n8n com Docker

```bash
docker-compose up -d
```

### 3. Acessar o n8n

Abra no navegador:

```
http://localhost:5678
```

### 4. Importar o workflow

* Vá em "Import"
* Selecione o arquivo dentro da pasta `/workflows`

---

## 📂 Estrutura do Projeto

```
n8n-content-automation/
│
├── workflows/
│   └── jobs_alert.json
│
├── data/
│
├── docker-compose.yml
├── .env.example
└── README.md
```

---

## 📈 Melhorias Futuras

* 💾 Armazenar vagas em banco de dados (evitar duplicadas)
* 🤖 Integração com IA para resumo das vagas
* 📊 Dashboard com estatísticas
* 🏷️ Classificação automática (junior, pleno, sênior)
* 🌎 Filtro por localização

---

## 🎯 Objetivo

Este projeto faz parte do meu portfólio com foco em:

* Automação de processos
* Integração com APIs
* Engenharia de dados (nível inicial)
* Desenvolvimento de soluções práticas

---

## 👨‍💻 Autor

Desenvolvido por **[Seu Nome]**

---

## 📄 Licença

Este projeto está sob a licença MIT.
