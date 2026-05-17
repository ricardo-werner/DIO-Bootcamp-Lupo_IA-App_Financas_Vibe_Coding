# DIO_Bootcamp-Lupo_IA-App_Financas_Vibe_Coding
Projeto conceitual de um app de finanças pessoais com IA, criado com a abordagem Vibe Coding para orientar ferramentas como Copilot e Lovable através de prompts estratégicos, criativos e focados no desenvolvimento de soluções para o mercado.

# Orby — App de Organização de Finanças Pessoais com Vibe Coding

**Orby** é um aplicativo financeiro mobile focado em criar consistência financeira e ajudar na construção da reserva de emergência, especialmente desenhado para profissionais de renda variável e iniciantes no controle financeiro.

> **Visão resumida:** Orby é um PWA mobile com interface conversacional que facilita o registro rápido de receitas e despesas, reduzindo fricção e aumentando engajamento.

---

## Índice
- [Motivação e Problema](#motivação-e-problema)  
- [Público Alvo](#público-alvo)  
- [Proposta de Valor](#proposta-de-valor)  
- [Escopo do MVP](#escopo-do-mvp)  
- [Funcionalidades Principais](#funcionalidades-principais)  
- [Requisitos Funcionais e Regras](#requisitos-funcionais-e-regras)  
- [Requisitos Técnicos e Stack](#requisitos-técnicos-e-stack)  
- [Estrutura de Pastas Sugerida](#estrutura-de-pastas-sugerida)  
- [Entregáveis Esperados](#entregáveis-esperados)  
- [Critérios de Aceitação e Métricas](#critérios-de-aceitação-e-métricas)  
- [Roadmap V2](#roadmap-v2)  
- [Instruções para a IA Geradora](#instruções-para-a-ia-geradora)  
- [Design System e Acessibilidade](#design-system-e-acessibilidade)  
- [Como Rodar o Projeto Localmente](#como-rodar-o-projeto-localmente)  
- [Contribuição e Contato](#contribuição-e-contato)

---

## Motivação e Problema
Muitas pessoas desistem de monitorar seus gastos porque as ferramentas atuais exigem muita entrada manual de dados. Além disso, a maioria dos aplicativos padrão não se adapta à falta de previsibilidade de quem não tem um salário fixo mensal, frustrando freelancers e desenvolvedores independentes.

---

## Público Alvo
- **Primário:** Iniciantes que buscam organizar suas finanças de forma prática e sem complicação.  
- **Secundário:** Desenvolvedores, freelancers e profissionais autônomos com renda variável que buscam consistência financeira e construção de reserva de emergência.

---

## Proposta de Valor
- Substituir formulários e planilhas por um fluxo conversacional simples.  
- Extrair automaticamente valor e categoria de mensagens em texto e voz.  
- Fornecer planejamento e simulação para construção de reserva de emergência.  
- Oferecer insights educativos por um agente financeiro leve.

---

## Escopo do MVP
**Hipótese:** Uma interface de chat em linguagem natural reduz o abandono do registro de despesas e aumenta o engajamento financeiro.

**Telas e Jornada do MVP**
- **Onboarding Express:** coleta rápida do perfil (renda variável média mensal e valor alvo da reserva).  
- **Dashboard + Chat Central:** saldo geral, progresso da reserva e campo de input imediato.  
- **Motor de Conversa:** registro por chat e exibição de TransactionCard para confirmação.  
- **Planning & Simulator:** recálculo simplificado de metas com variação de renda.  
- **Insights:** feed leve com recomendações do agente financeiro.

---

## Funcionalidades Principais
1. **Registro de Gastos via Chat** (texto e voz).  
2. **Classificação Automática** de transações por NLP local.  
3. **Definição e Acompanhamento de Metas** com Planning e Simulator.  
4. **Insights e Agente Financeiro** em formato de feed.  
5. **Dashboard Visual** com ProgressBar da reserva de emergência.  
6. **Acessibilidade Básica** conforme WCAG.

---

## Requisitos Funcionais e Regras
**Requisitos MVP Prioridade Alta**
- Registro de transações por chat (texto e voz).  
- Extração automática de valor e categoria; exibir TransactionCard para revisão.  
- Persistência local via LocalStorage usando React Context.  
- Dashboard minimalista com ProgressBar e botão de privacidade.  
- Planning & Simulator simplificados.  
- Insights do agente financeiro em feed leve.  
- Acessibilidade básica (alto contraste, semântica, touch targets).

**Regras e Fallbacks**
- Se Web Speech API não suportada, ocultar microfone e permitir apenas texto.  
- Se NLP local não identificar categoria, atribuir **Outros** e permitir edição.  
- Transação só afeta saldo após confirmação do usuário.

---

## Requisitos Técnicos e Stack
- **Frontend:** React v18+  
- **Estilos:** Tailwind CSS v4  
- **PWA:** manifest e service worker básicos  
- **Speech-to-Text:** Web Speech API (com fallback)  
- **Persistência:** LocalStorage via React Context  
- **Testes:** Jest e React Testing Library (instruções para testes manuais e unitários)  
- **Observação:** Não integrar LLMs pagos, Open Finance ou bots externos no MVP.

---

## Estrutura de Pastas Sugerida
```MATKDOWN
/src
/components
  OnboardingExpress.jsx
  DashboardChat.jsx
  TransactionCard.jsx
  PlanningSimulator.jsx
  InsightsFeed.jsx
  AccessibilityWrapper.jsx
  VoiceInput.jsx
/hooks
  useLocalStorageContext.js
  useNlpLocal.js
/styles
  tailwind.config.js
  design-system.css
/utils
  nlp-rules.js
  mock-data.js
/pages
  index.jsx
  onboarding.jsx
/tests
package.json
README.md
prompt.txt
```

---

## Entregáveis Esperados
1. Estrutura de pastas para app React PWA mobile-first com Tailwind CSS v4.  
2. Componentes React iniciais com comentários e TODOs.  
3. Implementação MVP de NLP local (Regex e mapeamento de palavras-chave).  
4. Fluxo de confirmação com TransactionCard antes de atualizar saldo.  
5. Exemplo de integração com Web Speech API e fallback.  
6. Estilos base seguindo o Design System.  
7. Mock data e exemplos de testes manuais.  
8. README.md completo com visão, features, telas, métricas e instruções.

---

## Critérios de Aceitação e Métricas
**Critérios de Aceitação**
- Registrar transação por chat em < 5s.  
- TransactionCard exibe valor, categoria sugerida e botão Confirmar.  
- Persistência local entre sessões.  
- Dashboard com ProgressBar e botão de privacidade.  
- Web Speech API funcional em navegadores compatíveis; fallback disponível.  
- Acessibilidade básica implementada.

**Métricas para Validação**
- Retenção D7 e D14 (principal).  
- Número médio de transações por usuário/semana.  
- Taxa de assertividade da categorização.  
- Tempo médio para registrar transação.

---

## Roadmap V2
- Integração com LLMs e agentes avançados.  
- Conexão Open Finance e sincronização bancária.  
- Comandos financeiros complexos por voz.  
- Integração com WhatsApp/Telegram.  
- Backend escalável e autenticação.

---

## Instruções para a IA Geradora
- Priorizar estrutura do projeto e componentes essenciais do fluxo de chat.  
- Gerar código com comentários explicativos e pontos TODO.  
- Incluir mock data e testes unitários básicos.  
- Garantir que o código inicial seja executável localmente com os comandos fornecidos.  
- Produzir README.md completo baseado neste prompt.

---

## Design System e Acessibilidade
- **Tipografia:** Inter  
- **Cores:** Primária `#2D6CDF`; Acento `#00C48C`  
- **Grid:** 8pt base  
- **Touch Targets:** ≥ 44x44px  
- **Resolução Alvo:** 375px (mobile-first)  
- **Acessibilidade:** alto contraste, semântica para leitores de tela, labels e roles adequados

---

## Como Rodar o Projeto Localmente
Comandos iniciais sugeridos:
```bash
npx create-react-app orby --template cra-template-pwa
cd orby
npm install -D tailwindcss@4 postcss autoprefixer
npm install react-router-dom
npm install --save-dev jest @testing-library/react
# configurar Tailwind e Design System conforme /src/styles
```

## Contribuição e Contato
•	Tom do projeto: pragmático, educativo e orientado à ação.
•	Público: Português BR, mobile-first.
•	Para contribuições, abra issues e PRs seguindo o checklist do primeiro sprint e o roadmap V2.

## Conclusão
Vibe Coding é sobre clareza, curiosidade e criatividade, não sobre perfeição técnica. O verdadeiro objetivo é aprender a pensar junto com a IA transformando ideias em conceitos reais e enxergando a tecnologia como extensão do raciocínio criativo.




## 🪄 Etapas do Desafio

### 1. Saber o que Pedir é a Chave! Otimize seus Prompts!

Antes de pedir para a IA “criar um app”, é importante definir com clareza o que será desenvolvido e qual problema a solução pretende resolver. 
Para isso, você irá criar um **PRD (Product Requirements Document)** com as especificações que funcionam como briefing para ajudar a IA a compreender a proposta do projeto.

Um bom PRD deve descrever o problema, o público beneficiado, as principais funcionalidades e os resultados esperados da IA. Utilize o modelo abaixo como ponto de partida e adapte conforme seu estilo e objetivos.

```MARKDOWN
Projeto: Orby - aplicativo financeiro mobile conversacional
Idioma: Português (BR)
Resumo:
Orby é um aplicativo mobile PWA que facilita o controle financeiro por meio de uma interface conversacional (chat) para registro rápido de receitas e despesas. Público-alvo: iniciantes em finanças e profissionais com renda variável (freelancers, devs autônomos). Objetivo do MVP: validar que o registro por chat reduz abandono e aumenta engajamento (meta: retenção D7 e D14; tempo de registro < 5s).

Visão e proposta de valor:
- Substituir formulários e planilhas por um fluxo conversacional simples.
- Extrair automaticamente valor e categoria de mensagens em texto e voz.
- Fornecer planejamento e simulação para construção de reserva de emergência.
- Oferecer insights educativos por um agente financeiro leve.

Entregáveis esperados:
1. Estrutura de pastas para um app React PWA mobile-first com Tailwind CSS v4.
2. Componentes React iniciais com comentários:
   - OnboardingExpress
   - DashboardChat
   - TransactionCard
   - PlanningSimulator
   - InsightsFeed
   - AccessibilityWrapper
   - VoiceInput (Web Speech API fallback)
   - useLocalStorageContext (hooks e mock data)
3. Implementação MVP de NLP local:
   - Extração de valor e categoria via Regex e mapeamento de palavras-chave.
   - Fluxo de confirmação: gerar TransactionCard antes de atualizar saldo.
4. Exemplo de integração com Web Speech API (com fallback para texto).
5. Estilos base seguindo Design System:
   - Tipografia: Inter
   - Cores: Primária #2D6CDF; Acento #00C48C
   - Grid: 8pt; touch targets ≥ 44x44px; mobile width 375px
6. Mock data e exemplos de testes manuais para validação de métricas.
7. README.md do repositório com visão, features, telas, métricas e instruções de execução.
8. Checklist de tarefas para o primeiro sprint e roadmap V2 (itens fora do escopo do MVP).

Requisitos funcionais MVP (prioridade alta):
- Registro de transações por chat (texto e voz).
- Extração automática de valor e categoria; exibir TransactionCard para revisão.
- Persistência local via LocalStorage usando React Context.
- Dashboard minimalista com ProgressBar da reserva de emergência e botão de privacidade (ocultar saldos).
- Planning & Simulator simplificados para recalcular metas com variação de renda.
- Insights do agente financeiro em formato de feed leve.
- Acessibilidade básica (WCAG): alto contraste, semântica para leitores de tela, touch targets adequados.

Regras e fallbacks:
- Se Web Speech API não suportada, ocultar microfone e permitir apenas entrada por texto.
- Se NLP local não identificar categoria, atribuir "Outros" e permitir edição no TransactionCard.
- Transação só afeta saldo após confirmação do usuário.

Requisitos técnicos:
- Frontend: React (v18+) + Tailwind CSS v4.
- PWA: configuração básica (manifest, service worker).
- Speech-to-Text: Web Speech API.
- Persistência: LocalStorage via React Context.
- Testes: instruções para testes manuais e unitários básicos (Jest/React Testing Library).
- Não integrar LLMs pagos, Open Finance ou bots externos no MVP.

Estrutura de pastas sugerida:
- /src
  - /components
    - OnboardingExpress.jsx
    - DashboardChat.jsx
    - TransactionCard.jsx
    - PlanningSimulator.jsx
    - InsightsFeed.jsx
    - AccessibilityWrapper.jsx
    - VoiceInput.jsx
  - /hooks
    - useLocalStorageContext.js
    - useNlpLocal.js
  - /styles
    - tailwind.config.js
    - design-system.css
  - /utils
    - nlp-rules.js
    - mock-data.js
  - /pages
    - index.jsx
    - onboarding.jsx
  - /tests
- package.json
- README.md
- prompt.txt

Comandos iniciais (exemplo):
- npx create-react-app orby --template cra-template-pwa
- cd orby
- npm install -D tailwindcss@4 postcss autoprefixer
- npm install react-router-dom
- npm install --save-dev jest @testing-library/react
- configurar Tailwind e Design System conforme /src/styles

Critérios de aceitação MVP:
- Usuário consegue registrar uma transação por chat em < 5s (fluxo medido em teste manual).
- TransactionCard exibe valor, categoria sugerida e botão Confirmar.
- Persistência local funciona entre sessões (LocalStorage).
- Dashboard mostra ProgressBar da reserva e botão de privacidade.
- Web Speech API funciona em navegadores compatíveis; fallback de texto disponível.
- Acessibilidade básica implementada (labels, roles, contraste).

Métricas para validação:
- Retenção D7 e D14 (principal).
- Número médio de transações por usuário/semana.
- Taxa de assertividade da categorização (correções manuais / total).
- Tempo médio para registrar transação.

Roadmap V2 (fora do escopo do MVP):
- Integração com LLMs e agentes avançados.
- Conexão Open Finance e sincronização bancária.
- Comandos financeiros complexos por voz (parcelamento, transferências).
- Integração com WhatsApp/Telegram.
- Backend escalável e autenticação.

Instruções para a IA geradora:
- Priorizar primeiro a estrutura do projeto e os componentes essenciais do fluxo de chat.
- Gerar código com comentários explicativos e pontos TODO para melhorias.
- Incluir exemplos de mock data e testes unitários básicos.
- Garantir que o código inicial seja executável localmente com os comandos fornecidos.
- Produzir um README.md completo baseado neste prompt.

Contexto adicional:
- Tom: pragmático, educativo e orientado à ação.
- Público: Português BR, mobile-first.
- Meta do MVP: validar retenção e reduzir fricção no registro financeiro.

Fim do prompt.

```

### Prévia da Interface 

<p align="center">
  <img width="480" src="./src/assets/to_readme/" alt="imagem das telas das páginas projeto App Finanças Pessoais"
</p>

#### Deploy
---
https://orby-fintech.onrender.com/
---

_Projeto desenvolvido para o Desafio Lupo da DIO._
## 👨‍💻 Autor

**Ricardo Werner**  
Desenvolvedor Front-end com foco em acessibilidade, UX e inclusão digital. 
</br>
Apaixonado por mergulho, fotografia,tecnologia e inovação.
