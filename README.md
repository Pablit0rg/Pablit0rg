# Pablo Rosa Gomes

**Backend e segurança de aplicação, com foco em sistemas de IA · Python / FastAPI · Curitiba, PR · aberto a remoto**

Eu construo sistemas que continuam corretos e seguros quando alguém tenta quebrá-los de propósito.

Não tenho diploma. Passei pelas Ciências Sociais na UFPR, sem concluir, e de lá trouxe o hábito de ler política, geopolítica e negócios junto com tecnologia. Na computação, venho de escolher o problema, ler fundo a fonte primária antes de decidir, e provar com teste que a solução funciona — e por que funciona. Uso modelos de linguagem como ferramenta de análise no processo, e audito tudo que sai deles antes de qualquer commit. O que está aqui é vivência, não exercício de curso: cada repositório carrega um argumento técnico que você verifica rodando o código. Nenhum deles é o mais complexo ou o mais exótico possível. São o mais simples que resolve, e o mais seguro que eu consegui.

---

## O problema que eu escolhi resolver

Software moderno delega decisões a componentes que **não conseguem distinguir instrução de dado**. Foi verdade no fim dos anos 1970, quando um compilador em tempo compartilhado usava a própria autoridade para sobrescrever o arquivo de faturamento do sistema. É verdade de novo em 2026, com agentes de IA que leem um documento e obedecem ao que está escrito dentro dele.

O nome do problema é antigo — *confused deputy*, o "delegado confuso". A conclusão prática também: **não adianta pedir para o componente se comportar melhor. A permissão precisa ser negada por fora, em código determinístico, por algo que não pode ser persuadido.**

Na prática, isso virou uma regra de projeto: **IA com acesso a dados e dinheiro precisa de autoridade verificada em código.** Aprendi isso construindo. Num protótipo financeiro gerado por IA, o modelo somou um freela parcelado inteiro e mostrou **+1,4 mês** de fôlego, quando a conta certa dava **+0,2**. Desde então, a conta não fica a cargo do modelo.

É essa a linha que atravessa o meu trabalho.

---

## Repositórios

### [`confused-deputy-demo`](https://github.com/Pablit0rg/confused-deputy-demo)
Quatro demonstrações executáveis que ligam o bug do fim dos anos 1970 às vulnerabilidades de agentes de IA catalogadas no OWASP Top 10 for LLM Applications (2025). Cada ataque tem um teste que **asserta que a exploração funciona** na versão vulnerável — e para de funcionar na versão corrigida por capability. Na v1.1.0, auditei as minhas próprias mitigações em cinco rodadas adversariais, encontrei quatro bypasses e fechei todos, com 21 testes que falham antes de cada correção. Python puro, biblioteca padrão, sem dependência externa. Bilíngue EN/PT.

### [`flyup-folego`](https://github.com/Pablit0rg/flyup-folego)
MVP publicado ([flyup-folego.lovable.app](https://flyup-folego.lovable.app)) para quem está em transição de carreira: quantos meses você aguenta se der o salto. O cálculo é determinístico e roda no navegador — **os valores financeiros nunca saem dele**. O servidor guarda só o contato, com consentimento explícito (LGPD). Row Level Security em todas as tabelas, apenas a chave pública no front-end, e auditoria do bundle publicado e do histórico do repositório antes de abrir o código. TypeScript · Lovable Cloud (Supabase).

### [`Crivo`](https://github.com/Pablit0rg/cv-analyzer-pro)
Analisador de currículo para sistemas ATS ([crivo-ats.lovable.app](https://crivo-ats.lovable.app)). O match entre vaga e currículo é calculado em código, sem IA e sem adivinhação: o mesmo texto sempre dá o mesmo resultado. A IA só entra sob demanda, para reescrever, e passa por uma **verificação de fidelidade** que barra qualquer experiência que não esteja no currículo original. Vaga e currículo são tratados como dados, nunca como instrução. Entregue em out/2026 como projeto final do bootcamp Santander/DIO, com 33 testes automatizados.

*Em preparação:* um estudo sobre por que a defesa mais recomendada contra prompt injection (filtrar a entrada) falha na prática, e o que funciona no lugar dela; e um sobre uma falha silenciosa em busca vetorial que descarta a maior parte dos resultados corretos sem gerar erro nenhum.

---

## Mapa: a mesma pergunta em domínios diferentes

Cada projeto responde a mesma pergunta — **quem garante o número, ou a ação, em que a IA se apoia?**

1. **Produto** — FlyUp: o cálculo fica no código, não no modelo. *Publicado.*
2. **Regra em código** — Crivo: match determinístico e fidelidade verificada. *Entregue.*
3. **Ataque** — prompt injection contra o próprio FlyUp, para medir o que a defesa em código segura. *Planejado.*
4. **Defesa** — detecção de anomalias em transações financeiras. *Planejado.*
5. **Agente seguro** — agente de análise somente leitura, com permissão verificada em código e nunca decidida pelo modelo. *Planejado.*

Os projetos acompanham bootcamps de IA, dados e cibersegurança que estou cursando; o tema de cada um segue o que o curso pede, e a camada de segurança é o meu acréscimo.

---

## Como eu trabalho

- **Fonte antes de opinião.** Toda decisão técnica é ancorada em documentação oficial, artigo revisado ou engenharia reconhecida. Se eu não consigo citar, eu não afirmo.
- **Teste que prova o problema, não só a solução.** O teste do ataque tem que passar antes de o conserto existir. Senão não há prova de que o conserto conserta.
- **Auditoria antes de commit.** Nada entra sem revisão de segurança e de design, mesmo quando o código foi gerado com assistência de IA — principalmente quando foi.
- **Registro contínuo.** Decisões arquiteturais viram ADR, não memória. Já reverti conclusões minhas quando a evidência não sustentou.

Rotina diária: leitura técnica dirigida, prática de código escrita à mão e um registro de decisões versionado. O gráfico de contribuições aqui embaixo é o registro disso, mantido em paralelo a um emprego de tempo integral.

---

## Stack

- **Backend** Python 3.13 · FastAPI · LangGraph · PostgreSQL · Supabase (RLS, pgvector) · pytest
- **Segurança** OWASP LLM Top 10 · controle de acesso por capability · modelagem de ameaças · guardrails determinísticos
- **Infra** Git · Linux
- **Web** TypeScript · Next.js · Tailwind
- **Certificação** Santander/DIO — Construa seu primeiro App com IA (bootcamp, 22h) · Cibersegurança do Zero à Prática · Segurança em projetos com Vibe Code

---

## Trabalho não público

Mantenho um sistema de agentes proprietário, em repositório privado, com pipeline de recuperação vetorial, orquestração por grafo de estados e uma camada de guardrails com aplicação determinística, protegido por quality gate de CI no GitHub Actions (pytest, TypeScript e ESLint). É de onde vêm boa parte dos problemas que eu publico aqui, generalizados e sem o código do produto. Posso falar sobre a arquitetura em entrevista.

---

## O que eu procuro

Posição de desenvolvedor backend ou engenharia de plataforma/confiabilidade, júnior, remota ou em Curitiba. Time que revisa código de verdade e que valoriza quem pergunta "o que acontece quando isso falha?" antes do deploy.

Se você está avaliando um candidato sem diploma: abra o `confused-deputy-demo`, leia o README e rode `python run_demo.py`. Leva cinco minutos e responde melhor do que qualquer currículo.

**Contato:** [LinkedIn](https://linkedin.com/in/pablit0rg) · pablorosagomes@gmail.com

---

<details>
<summary><strong>English</strong></summary>

## Pablo Rosa Gomes

**Backend and application security, focused on AI systems · Python / FastAPI · Curitiba, Brazil · open to remote**

I build systems that stay correct and secure when someone is actively trying to break them.

I have no degree. I studied Social Sciences at UFPR without finishing, and kept the habit of reading politics, geopolitics and business alongside technology. In computing, I'm self-taught: I pick the problem, read the primary source before deciding, and prove with tests that the solution works — and why it works. I use language models as an analysis tool in that process, and I audit everything they produce before any commit. What's here is lived work, not coursework: every repository carries a technical argument you can verify by running the code. None of them is the most complex or the most exotic option. They're the simplest thing that solves the problem, and the most secure I could make it.

### The problem I picked

Modern software delegates decisions to components that **cannot tell an instruction from data**. That was true in the late 1970s, when a time-sharing compiler used its own authority to overwrite the system's billing file. It's true again in 2026, with AI agents that read a document and obey whatever is written inside it.

The problem has an old name — the *confused deputy* — and an old conclusion: **you can't ask the component to behave better. The permission has to be denied from the outside, by deterministic code that cannot be talked out of it.**

In practice, that became a design rule: **AI with access to data and money needs authority verified in code.** I learned it by building. In an AI-generated financial prototype, the model added up an entire instalment-based freelance payment and showed **+1.4 months** of runway when the correct figure was **+0.2**. Since then, the math never stays with the model.

### Repositories

**[`confused-deputy-demo`](https://github.com/Pablit0rg/confused-deputy-demo)** — Four runnable demos connecting the late-1970s bug to the AI-agent vulnerabilities in the OWASP Top 10 for LLM Applications (2025). Each attack ships with a test that **asserts the exploit succeeds** against the vulnerable build, and stops succeeding once capability-based mitigation is in place. In v1.1.0 I audited my own mitigations in five adversarial rounds, found four bypasses and closed them all, with 21 tests that fail before each fix. Pure Python, standard library only.

**[`flyup-folego`](https://github.com/Pablit0rg/flyup-folego)** — Published MVP ([flyup-folego.lovable.app](https://flyup-folego.lovable.app)) for people changing careers: how many months you can last if you make the jump. The calculation is deterministic and runs in the browser — **financial values never leave it**. The server stores only contact details, with explicit consent (LGPD). Row Level Security on every table, publishable key only on the front end, and an audit of the deployed bundle and repository history before opening the code.

**[`Crivo`](https://github.com/Pablit0rg/cv-analyzer-pro)** — ATS résumé analyser ([crivo-ats.lovable.app](https://crivo-ats.lovable.app)). Job-to-résumé matching is computed in code, with no AI and no guessing. AI only steps in on request to rewrite, behind a **fidelity check** that blocks any experience not present in the original résumé. Job posts and résumés are treated as data, never as instructions. Delivered in Oct 2026 as the final project of the Santander/DIO bootcamp, with 33 automated tests.

*In progress:* why input filtering fails as a prompt-injection defense and what replaces it; and a silent failure mode in vector search that discards most correct results without raising an error.

### Map: one question, different domains

Every project answers the same question — **who guarantees the number, or the action, the AI relies on?** Product (FlyUp, published) → rule in code (Crivo, delivered) → attack (prompt injection against FlyUp, planned) → defense (financial anomaly detection, planned) → safe agent (read-only analysis agent, planned).

### How I work

Sources before opinions — if I can't cite it, I don't claim it. Tests that prove the bug exists, not just that the fix works. Security and design review before every commit, especially on AI-assisted code. Architectural decisions recorded as ADRs, not remembered.

### Not public

I maintain a proprietary agent system in a private repository: vector retrieval pipeline, state-graph orchestration, and a guardrail layer with deterministic enforcement, behind a CI quality gate on GitHub Actions (pytest, TypeScript and ESLint). Most of the problems I publish here come from there, generalised and stripped of product code. Happy to walk through the architecture in an interview.

### Looking for

Backend or platform/reliability engineering, junior level, remote or Curitiba-based. A team that reviews code properly and values the person who asks "what happens when this fails?" before the deploy.

If you're evaluating a candidate with no degree: open `confused-deputy-demo`, read the README, run `python run_demo.py`. Five minutes, better signal than any CV.

[LinkedIn](https://linkedin.com/in/pablit0rg) · pablorosagomes@gmail.com

</details>
