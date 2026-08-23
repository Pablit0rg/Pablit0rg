# Pablo Rosa Gomes

**Backend e segurança de aplicação, com foco em sistemas de IA · Python / FastAPI · Curitiba, PR · aberto a remoto**

Eu construo sistemas que continuam corretos e seguros quando alguém tenta quebrá-los de propósito.

Não venho da faculdade. Venho de escolher o problema, ler fundo a fonte primária antes de decidir, e provar com teste que a solução funciona — e por que funciona. Uso modelos de linguagem como ferramenta de análise no processo, e audito tudo que sai deles antes de qualquer commit. O que está aqui é vivência, não exercício de curso: cada repositório carrega um argumento técnico que você verifica rodando o código. Nenhum deles é o mais complexo ou o mais exótico possível. São o mais simples que resolve, e o mais seguro que eu consegui.

---

## O problema que eu escolhi resolver

Software moderno delega decisões a componentes que **não conseguem distinguir instrução de dado**. Foi verdade em 1970, quando um compilador em tempo compartilhado usava a própria autoridade para sobrescrever o arquivo de faturamento do sistema. É verdade de novo em 2026, com agentes de IA que leem um documento e obedecem ao que está escrito dentro dele.

O nome do problema é antigo — *confused deputy*, o "delegado confuso". A conclusão prática também: **não adianta pedir para o componente se comportar melhor. A permissão precisa ser negada por fora, em código determinístico, por algo que não pode ser persuadido.**

É essa a linha que atravessa o meu trabalho.

---

## Repositórios

### [`confused-deputy-demo`](https://github.com/Pablit0rg/confused-deputy-demo)
Quatro demonstrações executáveis que ligam o bug de 1970 às vulnerabilidades de agentes de IA catalogadas pela OWASP em 2026. Cada ataque tem um teste que **asserta que a exploração funciona** na versão vulnerável — e para de funcionar na versão corrigida por capability. Python puro, biblioteca padrão, sem dependência externa. Bilíngue EN/PT.

*Em preparação:* um estudo sobre por que a defesa mais recomendada contra prompt injection (filtrar a entrada) falha na prática, e o que funciona no lugar dela; e um sobre uma falha silenciosa em busca vetorial que descarta a maior parte dos resultados corretos sem gerar erro nenhum.

---

## Como eu trabalho

- **Fonte antes de opinião.** Toda decisão técnica é ancorada em documentação oficial, artigo revisado ou engenharia reconhecida. Se eu não consigo citar, eu não afirmo.
- **Teste que prova o problema, não só a solução.** O teste do ataque tem que passar antes de o conserto existir. Senão não há prova de que o conserto conserta.
- **Auditoria antes de commit.** Nada entra sem revisão de segurança e de design, mesmo quando o código foi gerado com assistência de IA — principalmente quando foi.
- **Registro contínuo.** Decisões arquiteturais viram ADR, não memória. Já reverti conclusões minhas quando a evidência não sustentou.

Rotina diária: leitura técnica dirigida, prática de código escrita à mão e um registro de decisões versionado. O gráfico de contribuições aqui embaixo é o registro disso, mantido em paralelo a um emprego de tempo integral.

---

## Stack

- **Backend** Python 3.13 · FastAPI · PostgreSQL · Supabase (RLS, pgvector) · pytest
- **Segurança** OWASP LLM Top 10 · controle de acesso por capability · modelagem de ameaças · guardrails determinísticos
- **Infra** Git · GitHub Actions (CI) · Docker · Linux
- **Web** TypeScript · Next.js · Tailwind
- **Certificação** Segurança da Informação — Santander Open Academy / DIO

---

## Trabalho não público

Mantenho um sistema de agentes proprietário, em repositório privado, com pipeline de recuperação vetorial, orquestração por grafo de estados e uma camada de guardrails com aplicação determinística. É de onde vêm boa parte dos problemas que eu publico aqui, generalizados e sem o código do produto. Posso falar sobre a arquitetura em entrevista.

---

## O que eu procuro

Posição de desenvolvedor backend ou engenharia de plataforma/confiabilidade, júnior ou pleno, remota ou em Curitiba. Time que revisa código de verdade e que valoriza quem pergunta "o que acontece quando isso falha?" antes do deploy.

Se você está avaliando um candidato sem diploma: abra o `confused-deputy-demo`, leia o README e rode `python run_demo.py`. Leva cinco minutos e responde melhor do que qualquer currículo.

**Contato:** [LinkedIn](https://linkedin.com/in/pablo-gomes-933161323) · pablorosagomes@gmail.com

---

<details>
<summary><strong>English</strong></summary>

## Pablo Rosa Gomes

**Backend and application security, focused on AI systems · Python / FastAPI · Curitiba, Brazil · open to remote**

I build systems that stay correct and secure when someone is actively trying to break them.

I'm self-taught. My method is to pick the problem, read the primary source before deciding, and prove with tests that the solution works — and why it works. I use language models as an analysis tool in that process, and I audit everything they produce before any commit. What's here is lived work, not coursework: every repository carries a technical argument you can verify by running the code. None of them is the most complex or the most exotic option. They're the simplest thing that solves the problem, and the most secure I could make it.

### The problem I picked

Modern software delegates decisions to components that **cannot tell an instruction from data**. That was true in the 1970s, when a time-sharing compiler used its own authority to overwrite the system's billing file. It's true again in 2026, with AI agents that read a document and obey whatever is written inside it.

The problem has an old name — the *confused deputy* — and an old conclusion: **you can't ask the component to behave better. The permission has to be denied from the outside, by deterministic code that cannot be talked out of it.**

### Repositories

**[`confused-deputy-demo`](https://github.com/Pablit0rg/confused-deputy-demo)** — Four runnable demos connecting the 1970s bug to the AI-agent vulnerabilities catalogued by OWASP in 2026. Each attack ships with a test that **asserts the exploit succeeds** against the vulnerable build, and stops succeeding once capability-based mitigation is in place. Pure Python, standard library only.

*In progress:* why input filtering fails as a prompt-injection defense and what replaces it; and a silent failure mode in vector search that discards most correct results without raising an error.

### How I work

Sources before opinions — if I can't cite it, I don't claim it. Tests that prove the bug exists, not just that the fix works. Security and design review before every commit, especially on AI-assisted code. Architectural decisions recorded as ADRs, not remembered.

### Not public

I maintain a proprietary agent system in a private repository: vector retrieval pipeline, state-graph orchestration, and a guardrail layer with deterministic enforcement. Most of the problems I publish here come from there, generalised and stripped of product code. Happy to walk through the architecture in an interview.

### Looking for

Backend or platform/reliability engineering, junior to mid-level, remote or Curitiba-based. A team that reviews code properly and values the person who asks "what happens when this fails?" before the deploy.

If you're evaluating a candidate with no degree: open `confused-deputy-demo`, read the README, run `python run_demo.py`. Five minutes, better signal than any CV.

[LinkedIn](https://linkedin.com/in/pablo-gomes-933161323) · pablorosagomes@gmail.com

</details>
