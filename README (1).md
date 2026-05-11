# MIG Expert Dashboard

Dashboard de estudo, treino de pitch e portfólio para times comerciais da **MIGNOW** — software company de automação SAP (ECC → S/4HANA, upgrades, Clean Core).

Jornada de **15 semanas em 4 fases**, **4 pilares diários** de execução, **11 produtos do portfólio**, mapa de **módulos SAP**, **mercado e concorrência**, **diagnóstico (Ballpark · EP · Readiness Check)** e **18 etapas do pitch** consolidadas em uma única página estática.

---

## ✨ Funcionalidades

### Jornada de 15 semanas em 4 fases
- **Fase 1 — Fundamentos (S1-S4):** origem MIGNOW, mercado SAP, ECC vs S/4HANA, módulos, funcionalidades-âncora.
- **Fase 2 — Produto (S5-S8):** modelos de conversão (Brownfield, Shell, Upgrade, Lift & Shift — sem Greenfield), metodologia 5 fases, portfólio 11 produtos, vocabulário.
- **Fase 3 — Comercial (S9-S11):** ambientes/ciclos, como o MIG funciona, Ballpark/EP/Readiness Check.
- **Fase 4 — Venda (S12-S15):** Clean Core → cases flagship → **Subscrição MIGNOW (S14 dedicada)** → venda consultiva e simulação final.

### 4 pilares diários
Estudo · Aprenda & Fixe · Pitch · **Revisão**. Cada pilar tem checkbox próprio, persiste no `localStorage` e contribui para o histórico de 30 dias.

### Abas principais
- **Visão geral (Hoje)** — KPIs do dia, semana ativa, próximo tema, pilar do dia, streak, subtópicos da semana e **Pitch da semana / Pitch de hoje** rotacionando etapas.
- **Roadmap 15 semanas** — visão completa da jornada.
- **Semana ativa** — guia detalhado com tópicos e entregáveis.
- **Vocabulário** — glossário editável com termos técnico-comerciais.
- **Checklist base** — autoavaliação de conhecimento.
- **Rotina diária** — framework de execução.
- **Pitch MIGNOW** — 18 etapas do pitch.
- **Histórico de pilares** — heatmap de 30 dias com breakdown por pilar.
- **Apresentações reais** — tracker de apresentações com agendamento e histórico.
- **Portfólio MIG** — 11 produtos com dor/benefício/valor/pitch. Subscrição MIGNOW destacada como **★ FLAGSHIP** com top objeções + edge competitivo. PDF do portfólio anexado.
- **Mercado SAP** — 8 números-chave (40k clientes ECC mundo, 2027/2030 deadlines, 5.326 funcionalidades, 22% manutenção, 97% custom code auto) e 6 concorrentes (Rimini, SNP, Spinnaker, SAP SDT, SAP NZDT, consultorias).
- **Módulos SAP** — 11 módulos (FI, CO, MM, SD, LE-TRA, HCM, WM, BW, GRC, BP/CVI, FSCM) com função, mudança no S/4 e notas MIG.
- **Ballpark · EP · Readiness Check** — onde achar no SAP for Me, o que ler, como traduzir em escopo.
- **Perfis de cliente** — 6 personas (CIO, Basis, Negócio, Sponsor, Usuário, CFO) com bullets de adaptação.

### Persistência local
Tudo é salvo no `localStorage` do navegador (chaves `mig.*`). Botões de **Exportar** e **Importar** permitem backup/restauração em JSON.

---

## 🚀 Como rodar localmente

Nenhuma build, nenhuma dependência. É HTML/CSS/JS puro.

```bash
# Opção 1: abrir direto no navegador
open index.html      # macOS
xdg-open index.html  # Linux
start index.html     # Windows

# Opção 2: servir com Python (recomendado para evitar bloqueio de file://)
python3 -m http.server 8080
# Depois acesse http://localhost:8080
```

---

## 🌐 Como publicar no GitHub Pages

1. Crie um repositório público no GitHub (ex: `mig-expert`).
2. Faça upload destes arquivos para a raiz do repositório:
   - `index.html`
   - `PORTFOLIO-MIGNOW.pdf`
   - `README.md`
3. Em **Settings → Pages**:
   - Source: `Deploy from a branch`
   - Branch: `main` · Folder: `/ (root)`
   - Salvar.
4. Aguarde 1-2 minutos. A URL será algo como:
   `https://<seu-usuario>.github.io/<nome-do-repo>/`

Pronto. Não precisa de nada além disso.

---

## 📁 Estrutura do projeto

```
mig-expert-site/
├── index.html                 # Dashboard completo (HTML + CSS + JS inline)
├── PORTFOLIO-MIGNOW.pdf       # Portfólio oficial MIGNOW (11 produtos)
└── README.md                  # Este arquivo
```

Tudo é single-file. O `index.html` contém:
- HTML semântico com 14 painéis navegáveis.
- CSS interno com sistema de design tokens (cores, espaçamentos, tipografia Inter + Fraunces).
- JavaScript em IIFE com dados (`WEEKS`, `PRODUCTS_PORTFOLIO`, `SAP_MODULES`, `MARKET_SAP`, `BALLPARK_GUIDE`, `EP_GUIDE`, `READINESS_CHECK_GUIDE`, `PITCH_STAGES`, `GLOSSARY`) e lógica de renderização.

---

## 🎨 Modelo de venda em destaque: Subscrição MIGNOW

A **Subscrição MIGNOW** ganhou semana própria (S14) e está marcada como flagship no portfólio porque é o coração comercial da empresa:

- Contrato de 3 anos · 1 upgrade SAP por ano
- Custom Code 97% automatizado
- Hypercare (~2 semanas + 1 fechamento)
- Suporte UAT + novos Fiori Lighthouse
- Evolução Clean Core a cada ciclo

A aba inclui top 5 objeções com respostas modelo e edge competitivo vs Rimini Street, SNP e SAP direto.

---

## 🛠️ Personalização

Para editar conteúdos sem mexer no layout:

- **Semanas:** procure por `const WEEKS = [` no `index.html` — array de 15 objetos com `title`, `objective`, `topics[]`, `deliverables[]`.
- **Produtos:** procure por `const PRODUCTS_PORTFOLIO = [` — 11 objetos com `name`, `whatIs`, `problem`, `benefit`, `valueGen`, `pitchPhrase`.
- **Módulos SAP:** procure por `const SAP_MODULES = [`.
- **Mercado:** procure por `const MARKET_SAP = {`.
- **Diagnósticos:** procure por `const BALLPARK_GUIDE`, `EP_GUIDE`, `READINESS_CHECK_GUIDE`.
- **Etapas do pitch:** procure por `const PITCH_STAGES = [`.

---

## 📜 Licença

Uso interno MIGNOW.

---

## 🤝 Créditos

- Conteúdo: time comercial e técnico MIGNOW.
- Portfólio: documento oficial MIGNOW (`PORTFOLIO-MIGNOW.pdf`).
- Estrutura: jornada de 4 fases inspirada nos temas do site original [mig-expert](https://brunamaiab1609-ux.github.io/mig-expert/) e refinada com pitch, portfólio e diagnóstico.
