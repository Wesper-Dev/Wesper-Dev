## Arnaud Durand

AI Platform / Applied AI Engineer. I build LLM systems for contexts where a model output triggers a decision that costs something, and where the data must not leave the machine.

The rule I apply everywhere: **the model proposes, the code decides — and what the code decides is tested, offline, on every commit.**

Trained at École 42 (Paris) in C, UNIX/POSIX, networking and concurrency. That is where the deterministic half of my work comes from. An agent that has to run without a network, refuse cleanly and re-check itself is a systems problem before it is a prompt problem.

## Start here

**[droit-de-retard](https://github.com/Wesper-Dev/droit-de-retard)** — a local-first agent that prepares an EU261 flight compensation claim from a photo or PDF of a boarding pass.

- The model reads the ticket. The code computes eligibility, amount and refusal, in deterministic Python, with CJEU case law encoded.
- The tool dispatcher is allow-listed: instead of the usual `globals()[name](**args)`, the code recomputes the expected arguments and rejects any call that differs. Two tests lock this down — reading a `.env` is refused, and personal data passed as a tool argument is refused.
- 121 deterministic tests run in under 0.05 s, with no network and no Ollama. CI on Python 3.10 to 3.13.
- An unknown airport code returns `needs_information` — never an approximate distance.
- `docs/EVALUATION.md` holds a test that fails if the documented numbers drift. That guard silently verified nothing in CI for several weeks; it is written up in the repo, with what I changed since.

To check it yourself: `git clone https://github.com/Wesper-Dev/droit-de-retard && cd droit-de-retard && make test`

## Other work

**Pokémon Gemma Agent** — an agent harness driving `gemma4:12b` through Pokémon Emerald autonomously, with an explicit, non-negotiable line between what the harness executes and what the model decides. 875 tests, 18 dated architecture decisions, and an engineering journal that is never rewritten — including where a later measurement disproved an earlier entry. Ablation result: on an identical harness, a frontier model succeeds where the 12B model confabulates, which isolates knowledge rather than mechanism as the bottleneck. *Private repository for now; happy to walk through it.*

**C2 coordination for counter-drone defence** — European Tech Defence Hackathon, Paris, June 2026. A centralised command-and-control layer assigning three interceptor systems against simultaneous drone threats and decoys, in a deterministic simulation with a seeded benchmark comparing a global assignment policy to a greedy baseline. *Private team repository.*

## Systems, École 42

- **[Minishell](https://github.com/Wesper-Dev/Minishell)** — POSIX shell in C: lexer, parser, pipes, redirections, heredocs, signals, builtins.
- **[Inception](https://github.com/Wesper-Dev/Inception)** — NGINX/TLS, WordPress + PHP-FPM and MariaDB across three hand-written Dockerfiles.
- **[Philosophers](https://github.com/Wesper-Dev/Philosophers)** — POSIX threads and mutexes, no deadlock or starvation, death detection under 10 ms.
- **[Pipex](https://github.com/Wesper-Dev/Pipex)** — `cmd1 < infile | cmd2 > outfile` in C: pipe(), fork(), dup2(), execve, PATH resolution.

## Experience

- **AI Platform Engineering Intern, BPCE** — until 16 October 2026. Building the isolation layer of an internal proof-of-concept platform for agent execution on Kubernetes/OpenShift: containerised execution with namespace separation, evaluating Kata Containers and Podman for stronger isolation. Python.
- **Data Scientist Intern, BNP Paribas** — IT Group Experimentation Lab. Multi-threaded document analysis pipeline. Deployed Langfuse fully on-premise across 75+ Docker containers for LLM cost and trace monitoring. Measured gains are internal; I go through them in interviews.
- **Full-stack AI developer, French Red Cross** *(volunteer)* — first-aid training platform: LightRAG over 700+ pages, Socratic scenarios, Next.js / FastAPI / PostgreSQL. Shown at ChangeNow 2025.

## Hackathons

Titled by the technical result, not by the ranking.

- **GenHack 4**, École polytechnique (Nov 2025) — climate downscaling: RMSE from 2.45 °C to 1.24 °C, 9 km → 80 m, residual ML pipeline on ERA5 + Sentinel-2.
- **LeRobot, Hugging Face @ 42** (June 2025) — robotic arm playing Connect 4: Action Chunking Transformer on a hand-built demonstration dataset, YOLOv5 board detection.
- **ShipFast × Unaite × 42AI** (July 2025) — emergency call assistance. My commits are in the team's upstream repository.

## Community

Co-Lead Organizer of **GDG on Campus 42 Paris**, with Colin Peugnet.

## Education

**École 42 Paris** — 2019 to 2024. C/C++, UNIX/POSIX, networking, concurrent programming.

## Looking for

An AI Platform / Applied AI engineering role on systems where execution has to be isolated, measured and defensible. Available from 16 October 2026.

French native · English C1 · Spanish B2 · [LinkedIn](https://www.linkedin.com/in/arnaud-durand42)
