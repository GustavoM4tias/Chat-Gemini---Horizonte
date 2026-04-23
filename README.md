# 🏗️ Construtora Horizonte — Chatbot com Google AI Studio

> Projeto educativo para aula prática de 3 horas.  
> Os alunos **configuram a IA no painel visual do Google AI Studio** e conectam ao site com poucas linhas de código.

---

## 🎯 Proposta Pedagógica

A diferença deste projeto para outros tutoriais:

> **Você configura a IA visualmente no Google AI Studio, não no código.**

O site apenas *conecta* ao modelo que você criou. Isso significa:
- Os alunos entendem o conceito de **System Instruction** (a personalidade e conhecimento da IA)
- Vêem a IA respondendo em tempo real dentro do próprio Studio antes de colocar no site
- Aprendem o que é uma **API Key** e por que ela existe
- O código do site fica simples: apenas envia o histórico de mensagens

---

## 📁 Estrutura do Projeto

```
horizonte-gemini/
├── index.html                ← Site completo (HTML + Tailwind CDN + JS puro)
├── data/
│   └── empreendimentos.json  ← Dados dos empreendimentos (simula uma API)
└── README.md                 ← Este guia
```

---

## 🛠️ Ferramentas Necessárias

| Ferramenta | Para quê | Gratuito? |
|---|---|---|
| VS Code | Editar código | ✅ Sim |
| Extensão Live Server | Rodar o site localmente | ✅ Sim |
| Conta Google | Acessar o AI Studio | ✅ Sim |
| Google AI Studio | Configurar e testar a IA | ✅ Sim |

---

## 📋 PARTE 1 — Preparar o Ambiente (20 min)

### 1.1 — Instalar o VS Code

1. Acesse **[https://code.visualstudio.com](https://code.visualstudio.com)**
2. Clique em **Download for Windows** (ou Mac/Linux)
3. Execute o instalador → Próximo → Próximo → Instalar

### 1.2 — Instalar a extensão Live Server

O Live Server simula um servidor web para que o arquivo JSON carregue corretamente.

1. Abra o VS Code
2. Tecle `Ctrl + Shift + X` (abre o painel de extensões)
3. Pesquise: **Live Server**
4. Instale a extensão de **Ritwick Dey**

### 1.3 — Abrir o projeto

1. No VS Code: **File → Open Folder**
2. Selecione a pasta `horizonte-gemini`
3. Estrutura esperada no painel lateral:

```
📁 horizonte-gemini
  📁 data
    📄 empreendimentos.json
  📄 index.html
  📄 README.md
```

### 1.4 — Rodar o site

1. Clique com **botão direito** no arquivo `index.html`
2. Selecione **"Open with Live Server"**
3. O navegador abre em `http://127.0.0.1:5500`
4. ✅ O site da construtora deve aparecer!

---

## 📋 PARTE 2 — Configurar a IA no Google AI Studio (60 min)

> 💡 Esta é a parte mais importante da aula. Os alunos vão *criar* o chatbot visualmente.

### 2.1 — O que é o Google AI Studio?

O **Google AI Studio** é o playground oficial do Google para modelos de IA Generativa (Gemini). Você pode:
- Escrever uma "personalidade" para a IA (System Instruction)
- Testar conversas em tempo real
- Ajustar o comportamento sem escrever código
- Gerar a API Key para conectar em qualquer projeto

**URL:** [https://aistudio.google.com](https://aistudio.google.com)

---

### 2.2 — Criar uma conta e acessar

1. Acesse [https://aistudio.google.com](https://aistudio.google.com)
2. Clique em **Sign in** com sua conta Google
3. Aceite os termos de uso

---

### 2.3 — Criar um novo Prompt (o "cérebro" do chatbot)

1. Na tela inicial do AI Studio, clique em **"Create new prompt"**
2. No topo, selecione o tipo **"Chat prompt"** *(ícone de balão de conversa)*
3. Você verá a interface dividida em:
   - **Esquerda:** Configurações do modelo
   - **Centro:** Área de System Instruction
   - **Direita:** Área de teste da conversa

---

### 2.4 — Configurar a System Instruction ⭐

> A **System Instruction** é onde você diz à IA *quem ela é* e *o que ela sabe*.  
> É aqui que colocamos todos os dados dos empreendimentos.

1. Na parte superior central, clique na área **"System instructions"**
2. Apague o texto padrão
3. **Cole exatamente o texto abaixo** (ou adapte com os dados reais):

---

```
Você é o assistente virtual da Construtora Horizonte, uma empresa com 15 anos de experiência em imóveis residenciais em São Paulo e interior.

Seu nome é "Horizonte IA". Você é simpático, profissional e direto. Responde sempre em português brasileiro. Use emojis com moderação. Máximo de 3 parágrafos por resposta.

Quando não souber algo sobre os empreendimentos, direcione para o telefone (11) 4002-8922 ou WhatsApp (11) 99999-1234.

═══════════════════════════════════════
DADOS DOS EMPREENDIMENTOS
═══════════════════════════════════════

1. RESIDENCIAL VISTA VERDE
   - Tipo: Apartamento | Status: LANÇAMENTO
   - Localização: Tatuapé, São Paulo (próximo ao metrô)
   - Área: 52 a 89m² | 2 ou 3 dormitórios | 1 ou 2 suítes | 1 ou 2 vagas
   - Preços: R$ 380.000 a R$ 620.000
   - Entrega: Dezembro 2026
   - Disponível: 48 de 120 unidades
   - Lazer: Piscina adulto e infantil, Academia, Salão de festas, Playground, Portaria 24h, Energia solar

2. ALTO DA SERRA RESIDÊNCIAS
   - Tipo: Casa em Condomínio | Status: EM OBRAS
   - Localização: Sousas, Campinas
   - Área: 180 a 320m² | Lotes de 400 a 650m² | 3 ou 4 dormitórios | 2 ou 3 suítes | 2 ou 3 vagas
   - Preços: R$ 850.000 a R$ 1.500.000
   - Entrega: Junho 2026
   - Disponível: 22 de 60 unidades
   - Lazer: Portaria blindada, Piscina olímpica, Quadra poliesportiva, Trilha ecológica, Pet place

3. HORIZONTE PRIME TOWER
   - Tipo: Apartamento Alto Padrão | Status: PRONTO PARA MORAR
   - Localização: Perdizes, São Paulo (vista para o Parque Água Branca)
   - Área: 110 a 210m² | 3 ou 4 dormitórios | 2 a 4 suítes | 2 ou 3 vagas
   - Preços: R$ 1.200.000 a R$ 2.800.000
   - Entrega: PRONTO — pode morar imediatamente
   - Disponível: 11 de 48 unidades (últimas unidades!)
   - Lazer: Acabamento premium, Varanda gourmet, Spa com sauna, Coworking, Rooftop lounge, Concierge

4. JARDINS DO IPÊ
   - Tipo: Apartamento | Status: LANÇAMENTO
   - Localização: Nova Aliança, Ribeirão Preto
   - Área: 44 a 72m² | 1 ou 2 dormitórios | 0 ou 1 suíte | 1 vaga
   - Preços: R$ 260.000 a R$ 410.000
   - Entrega: Março 2027
   - Disponível: 96 de 96 unidades (TODAS disponíveis — primeiro da Horizonte em Ribeirão!)
   - Lazer: Piscina com raia, Espaço gourmet, Bicicletário, Horta comunitária, Área kids

5. HORIZONTE STUDIOS VILA MADALENA
   - Tipo: Studio | Status: EM OBRAS
   - Localização: Vila Madalena, São Paulo (500m do metrô)
   - Área: 24 a 38m² | Studio completo com 1 suíte | Vaga opcional
   - Preços: R$ 280.000 a R$ 420.000
   - Entrega: Setembro 2026
   - Disponível: 87 de 200 unidades
   - Destaque: Ideal para investidores — alto potencial de locação por temporada
   - Lazer: Mobiliado opcional, Coworking 24h, Rooftop bar, Lavanderia automática, Pet friendly

═══════════════════════════════════════
FINANCIAMENTO
═══════════════════════════════════════
- Bancos parceiros: Caixa Econômica, Bradesco, Itaú, Santander
- Aceita FGTS: Sim, como entrada ou amortização
- Entrada mínima: 20% do valor do imóvel
- Prazo máximo: 420 meses (35 anos)
- Programas: Minha Casa Minha Vida (até R$350mil), financiamento convencional, consórcio Horizonte

═══════════════════════════════════════
CONTATO
═══════════════════════════════════════
- Telefone: (11) 4002-8922
- WhatsApp: (11) 99999-1234
- E-mail: vendas@horizonteconstrutora.com.br
- Atendimento: Segunda a Sábado, 9h às 18h
```

---

4. Clique **fora da caixa** para salvar a System Instruction

---

### 2.5 — Ajustar parâmetros do modelo

Na coluna **esquerda** do AI Studio, configure:

| Parâmetro | Valor Recomendado | O que faz |
|---|---|---|
| **Model** | `Gemini 2.0 Flash` | Modelo mais rápido e gratuito |
| **Temperature** | `0.65` | Menos criativo, mais preciso para dados |
| **Max output tokens** | `500` | Limita o tamanho das respostas |

---

### 2.6 — Testar a IA no Studio ⭐

> Antes de colocar no site, teste aqui! É mais fácil ajustar.

No painel direito, envie essas mensagens e veja as respostas:

```
Quais empreendimentos vocês têm disponíveis?
```
```
Qual o preço do Residencial Vista Verde?
```
```
Tenho R$ 500 mil para investir, qual empreendimento você indica?
```
```
Aceita FGTS?
```
```
Quero um apartamento em Campinas
```

Se as respostas estiverem boas → IA configurada corretamente! ✅

Se quiser **ajustar o comportamento**, edite a System Instruction e teste de novo.

---

### 2.7 — Gerar a API Key 🔑

Agora vamos gerar a chave que permite o site "conversar" com essa IA.

1. No menu lateral esquerdo, clique em **"Get API key"**
   *(ou acesse: [https://aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey))*

2. Clique em **"Create API key"**

3. Selecione **"Create API key in new project"** (ou escolha um projeto existente)

4. Sua chave vai aparecer:
   ```
   AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
   ```

5. Clique em **"Copy"** e guarde em lugar seguro

> ⚠️ **Nunca compartilhe sua API Key publicamente!**  
> Com ela, qualquer pessoa pode usar sua cota do Google gratuitamente.

---

## 📋 PARTE 3 — Conectar a IA ao Site (20 min)

### 3.1 — Abrir o chat no site

Com o site rodando via Live Server:

1. Clique no **botão no canto inferior direito** da página
2. A janela do chat vai abrir
3. Você verá um **banner amarelo** pedindo a API Key

### 3.2 — Inserir a API Key

1. Cole a API Key no campo do banner amarelo
2. Clique em **"OK"**
3. ✅ Banner some — chatbot está ativo!

> A chave fica salva no navegador automaticamente.  
> Na próxima vez que abrir, não precisa inserir novamente.

### 3.3 — Testar no site

Envie as mesmas perguntas que testou no Studio:

- "Quais empreendimentos vocês têm?"
- "Quero um apartamento de 2 quartos em São Paulo"
- "Como funciona o financiamento?"

---

## 📋 PARTE 4 — Entender o Código (30 min)

### Como o site chama o Gemini?

No arquivo `index.html`, a função `callGemini()` é simples:

```javascript
async function callGemini() {
  const url = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent?key=${APIKEY}`;

  const body = {
    // A System Instruction aqui é o FALLBACK local.
    // Se você quiser usar só o que configurou no AI Studio,
    // pode deixar essa parte vazia!
    system_instruction: { parts: [{ text: "..." }] },
    
    // Histórico da conversa (o que o usuário já digitou)
    contents: hist,
    
    // Configurações
    generationConfig: { temperature: 0.65, maxOutputTokens: 500 }
  };

  const res = await fetch(url, {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify(body)
  });

  const d = await res.json();
  return d.candidates[0].content.parts[0].text;
}
```

**É só isso.** Uma requisição HTTP com o histórico de mensagens. O Gemini responde com base na System Instruction que você configurou no AI Studio.

### O que é `hist` (histórico)?

```javascript
let hist = [];

// Quando usuário envia:
hist.push({ role: 'user',  parts: [{ text: 'Oi!' }] });

// Quando IA responde:
hist.push({ role: 'model', parts: [{ text: 'Olá! Como posso ajudar?' }] });

// Na próxima mensagem, enviamos TODO o histórico.
// Assim a IA "lembra" do que foi dito antes.
```

Isso se chama **multi-turn conversation** — a IA tem memória dentro da sessão.

### O JSON como "banco de dados"

O arquivo `data/empreendimentos.json` simula dados que viriam de um servidor real:

```json
{
  "empreendimentos": [
    {
      "nome": "Residencial Vista Verde",
      "preco_min": 380000,
      ...
    }
  ]
}
```

O JavaScript carrega esse arquivo e usa os dados para:
1. Renderizar os cards na tela
2. Enviar como contexto para a IA (na System Instruction local/fallback)

---

## ✏️ PARTE 5 — Personalizar (20 min)

### Adicionar um novo empreendimento

1. Abra `data/empreendimentos.json`
2. Copie um dos objetos existentes e cole no final do array `empreendimentos`
3. Edite os dados
4. **Importante:** Atualize também a System Instruction no Google AI Studio com os novos dados!

### Mudar a personalidade da IA

Volte ao Google AI Studio, edite a System Instruction. Experimente:

```
Você é a Laura, consultora de vendas da Construtora Horizonte.
Você é entusiasmada, usa emojis frequentemente e sempre destaca
os benefícios emocionais de cada empreendimento...
```

Salve e teste — a IA muda de comportamento imediatamente!

### Testar diferentes temperaturas

No AI Studio, mude o parâmetro **Temperature**:
- `0.1` → Respostas mais objetivas e repetitivas
- `1.0` → Respostas mais criativas e variadas
- `0.65` → Equilíbrio (nossa recomendação)

---

## 🐛 Problemas Comuns

| Problema | Causa | Solução |
|---|---|---|
| Cards não aparecem | Arquivo aberto diretamente (sem servidor) | Use o Live Server no VS Code |
| "API key not valid" | Chave errada ou expirada | Gere uma nova no AI Studio |
| IA não sabe sobre empreendimentos | System Instruction vazia ou sem dados | Copie o texto do item 2.4 |
| Erro HTTP 429 | Muitas requisições (limite gratuito) | Aguarde 1 min e tente novamente |
| Banner amarelo não some | Chave não foi salva | Clique em "OK" após colar a chave |

### Verificar erros no navegador

1. Pressione **F12** (abre as Ferramentas do Desenvolvedor)
2. Aba **Console** → erros aparecem em vermelho

---

## 📐 Arquitetura do Projeto (para mostrar na aula)

```
┌─────────────────────────────────────────────────────┐
│                   GOOGLE AI STUDIO                  │
│                                                     │
│  ┌─────────────────────────────────────────────┐   │
│  │  SYSTEM INSTRUCTION (você configura aqui)   │   │
│  │  "Você é o assistente da Construtora..."    │   │
│  │  "Empreendimento 1: Vista Verde..."         │   │
│  └─────────────────────────────────────────────┘   │
│                        ↓                           │
│  ┌─────────────────────────────────────────────┐   │
│  │  MODELO GEMINI 2.0 FLASH                    │   │
│  │  (processa tudo e gera respostas)           │   │
│  └─────────────────────────────────────────────┘   │
│                        ↑↓                          │
│              API KEY (sua senha de acesso)          │
└─────────────────────────────────────────────────────┘
                          ↑↓
            Requisição HTTP (fetch no JavaScript)
                          ↑↓
┌─────────────────────────────────────────────────────┐
│                   SEU SITE (index.html)             │
│                                                     │
│  ┌──────────────┐    ┌──────────────────────────┐  │
│  │ INTERFACE    │    │ JAVASCRIPT               │  │
│  │ (HTML/CSS)   │←──→│ callGemini()             │  │
│  │ - Cards      │    │ hist[] (histórico)        │  │
│  │ - Chatbot    │    │ localStorage (API Key)    │  │
│  └──────────────┘    └──────────────────────────┘  │
│                                                     │
│  ┌──────────────┐                                  │
│  │ JSON (dados) │ ← empreendimentos.json            │
│  └──────────────┘                                  │
└─────────────────────────────────────────────────────┘
```

---

## 📅 Roteiro Sugerido das 3 Horas

| Horário | Duração | Conteúdo |
|---------|---------|----------|
| 0:00 | 20 min | Instalar VS Code + Live Server + abrir o site |
| 0:20 | 10 min | Tour pelo projeto: o que é cada arquivo |
| 0:30 | 15 min | O que é uma API? O que é JSON? Como funciona a web |
| 0:45 | 35 min | 🌟 **Google AI Studio: criar prompt, escrever System Instruction, testar** |
| 1:20 | 10 min | Gerar a API Key |
| 1:30 | 15 min | Conectar a chave no site e testar o chatbot |
| 1:45 | 15 min | Entender o código JavaScript (callGemini, histórico) |
| 2:00 | 25 min | Personalizar: adicionar empreendimento, mudar System Instruction |
| 2:25 | 20 min | Como publicar na internet (Vercel/Netlify) — teoria |
| 2:45 | 15 min | Dúvidas + próximos passos |

---

## 🔒 Segurança — Aviso Importante

> ⚠️ **Para demonstração/aprendizado, a API Key fica no `localStorage` do navegador.**  
> Isso é seguro para uso pessoal e em ambiente de aula.

**Em um projeto real/profissional:**
1. Crie um servidor (Node.js, Python, etc.)
2. Guarde a API Key como variável de ambiente no servidor
3. O frontend chama seu servidor → servidor chama o Gemini
4. A Key nunca fica exposta no navegador

---

## 🚀 Próximos Passos

1. **Publicar online grátis:** [vercel.com](https://vercel.com) ou [netlify.com](https://netlify.com)
2. **Aprender Git:** [git-scm.com](https://git-scm.com) — controle de versão
3. **Criar um backend:** Node.js ou Python para proteger a API Key
4. **Banco de dados real:** Supabase, Firebase (gratuito para projetos pequenos)
5. **Vue.js ou React:** Para sites mais dinâmicos e complexos

---

## 🔗 Links Úteis

| Recurso | Link |
|---|---|
| Google AI Studio | https://aistudio.google.com |
| Gerar API Key | https://aistudio.google.com/app/apikey |
| Documentação Gemini API | https://ai.google.dev/docs |
| VS Code | https://code.visualstudio.com |
| Tailwind CSS | https://tailwindcss.com |
| Publicar com Vercel | https://vercel.com |

---

*Projeto educativo · Construtora Horizonte é fictícia · Livre para modificar e distribuir*
