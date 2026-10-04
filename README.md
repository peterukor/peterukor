<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/banner-dark.svg">
  <img alt="Peter Ukor. Backend, cloud, distributed systems and AI." src="./assets/banner-light.svg" width="100%">
</picture>

<p>
  <a href="https://peterukor.com"><img alt="Website" src="https://img.shields.io/badge/Website-peterukor.com-16181D?style=flat-square&logo=googlechrome&logoColor=white"></a>
  <a href="https://www.linkedin.com/in/peter-ukor"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-peter--ukor-2C55D6?style=flat-square&logo=linkedin&logoColor=white"></a>
  <a href="mailto:peter@peterukor.com"><img alt="Email" src="https://img.shields.io/badge/Email-peter%40peterukor.com-16181D?style=flat-square&logo=maildotru&logoColor=white"></a>
  <a href="https://socrasage.com"><img alt="SocraSage live" src="https://img.shields.io/badge/SocraSage-live-2C55D6?style=flat-square"></a>
</p>

I'm a Computer Science student at **NJIT** (minor in AI) who likes understanding how systems work underneath: APIs, auth boundaries, consensus, cloud plumbing, and AI that reasons over real evidence. I learn by building things from the ground up, and I'm a research assistant on two projects in reinforcement learning and NLP. More at **[peterukor.com](https://peterukor.com)**.

---

## Featured work

### 🧠 [SocraSage](https://socrasage.com) · AI study companion &nbsp;`live`

Students upload their own course material, read it in the browser, and use AI to explain passages, answer questions, summarize pages, and build flashcards and quizzes from what they're studying.

- **Horizontally scaled Go API**: three stateless EC2 instances behind Cloudflare and an AWS Application Load Balancer
- **Event-driven file processing**: the browser uploads straight to S3 with presigned uploads; S3 events feed SQS, and Lambdas process and index each document
- **Retrieval-augmented AI**: answers draw on chunks from the student's own file, with OpenAI responses streamed back to the browser
- **Server-enforced usage controls**, Cognito sign-in, DynamoDB for app data, infrastructure defined with AWS SAM
- Solo: architecture, backend, cloud infrastructure, AI integration, and frontend

`Go` `React` `AWS` `DynamoDB` `S3` `SQS` `Lambda` `Cognito` `OpenAI` &nbsp;→ **[Try it at socrasage.com](https://socrasage.com)** <sub>(source is private)</sub>

### ⚙️ [kvraft](https://github.com/peterukor/kvraft) · Raft consensus from scratch in Go &nbsp;`in progress`

The foundation of a fault-tolerant key-value store: five independent nodes elect a leader, survive leader crashes, and replicate a log over real HTTP.

- Randomized election timeouts, parallel `RequestVote` RPCs, and majority-quorum wins
- One replication goroutine per follower, bound to the leader's term so stale leaders stop on their own
- Log replication with **conflict-index backtracking**: a diverged follower is repaired in one round trip
- Standard library only; each node is its own process, so crashes and partitions are real, not simulated
- Next: commit index, persistence, and the client API

`Go` `Raft` `HTTP/JSON RPC` `goroutines` `channels`

### 🛡️ [Guardian](https://github.com/peterukor/guardian) · AI pre-merge risk analyzer

A CLI that scores how risky a code change is *before* you merge it, using dependency-graph and git-history evidence, then lets an AI agent investigate that evidence and explain what reviewers should check.

- Deterministic 0–10 risk score from bug-fix history, fan-in, and ownership concentration (percentile-ranked, so one "god file" can't flatten the rest)
- **Hand-written tool-calling agent loop** (no framework) on IBM watsonx.ai; the AI cites evidence and never computes the score
- Moving the final answer to a `submit_findings` tool call eliminated malformed responses in live testing
- Python AST dependency analyzer with a pluggable language-adapter interface; blast radius via NetworkX
- Built solo for **IBM TechXchange 2026**, with a 79-test suite

`Python` `IBM watsonx.ai` `SQLite` `NetworkX` `AST` `Git`

### 📋 [Meridian](https://github.com/peterukor/meridian_ats) · Applicant tracking system for candidates &nbsp;`live`

A deployed, multi-user job-application tracker that turns a job search into a pipeline and drafts tailored résumés, cover letters, and company research from each user's own profile.

- Backend and authentication on a six-person team: registration, login, and a **PKCE password-reset flow** with single-use sessions
- **Ownership enforced on every route**: queries are scoped to the signed-in user, verified by attacker-vs-owner security tests
- AI routes check ownership before any profile data reaches the model; output is always an editable draft
- GitHub Actions runs format, lint, type-check, build, and **556 tests** on every pull request

`Next.js` `React` `TypeScript` `PostgreSQL` `Prisma` `GitHub Actions` &nbsp;→ **[Live app](https://meridian-1159.vercel.app)**

---

## More projects

| Project | What it is | Stack |
|---|---|---|
| [AI Lakehouse](https://github.com/peterukor/ai-lakehouse) | Versioned ML datasets with bronze/silver/gold layers, time travel, rollback, and a one-command rebuild | DuckDB · DuckLake · Docker · Python |
| [MCL Interpreter](https://github.com/peterukor/mcl-interpreter) | Lexer, recursive-descent parser, and interpreter for a small C-like language | C++17 |
| [Plumb Bros](https://github.com/peterukor/plumb-bros) | Staff app for customers, appointments, and supplies, with atomic cancellations and CSRF protection | Flask · SQLite |
| [SimpleChat](https://github.com/peterukor/simple-chat-app) | Room-code group chat for up to eight people, with cursor-based polling | Flask · SQLite |

## Tools I use

<p>
  <img alt="Go, Python, TypeScript, JavaScript, Java, C++, React, Next.js, PostgreSQL, AWS, Docker, Kubernetes, Flask, FastAPI, Git, Linux" src="https://skillicons.dev/icons?i=go,python,ts,js,java,cpp,react,nextjs,postgres,aws,docker,kubernetes,flask,fastapi,git,linux&perline=8">
</p>

<sub>Currently: adding persistence and a client API to kvraft. Open to internships and full-time software engineering roles in the NY/NJ area. Say hi at [peter@peterukor.com](mailto:peter@peterukor.com).</sub>
