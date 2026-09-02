**AI Platform / Applied AI Engineer, Paris.** Permanent role from 16 October 2026, when my BPCE internship ends.

**[droit-de-retard](https://github.com/Wesper-Dev/droit-de-retard)** turns a photo of a boarding pass into an EU261 flight-compensation claim. 121 deterministic tests, no network, no install step.

Clone it, `cd` in, and run:

```console
$ python3 -m unittest discover
...
Ran 121 tests in 0.114s

OK
```

No `requirements.txt`, no virtualenv, no model running — a clean clone on the system Python. Your timing will differ; the 121 and the `OK` will not. CI runs the same suite on Python 3.10 to 3.13.

The model reads the ticket; Python decides eligibility, amount and refusal, with CJEU case law encoded. The tool dispatcher is allow-listed: instead of `globals()[name](**args)` it recomputes the expected arguments and rejects any call that differs — two tests hold it shut, one for reading a `.env`, one for personal data passed as a tool argument. An unknown airport code returns `needs_information`, not a guess.

The model runs locally through Ollama, and the one network tool is a minimised search the system does without when it is unavailable. `docs/EVALUATION.md` is the single source for the published figures, and carries `test_documented_test_count_is_accurate`, which fails if the documented count drifts from the real one.

The model proposes, the code decides — and what the code decides is tested, offline, on every commit.

The repo also records that its own zero-dependency CI guard verified nothing until 1 August 2026: the green badge of that period did not certify what it appeared to certify. And it records where the project comes from. It started as [a three-person hackathon project](https://github.com/Claken/Paris-Gemma-4-Hackaton) at the Gemma 4 Hackathon in Paris, 25–28 July 2026, and [the demo video](https://www.youtube.com/watch?v=tOn7xXNZ6s0) is the team's. I carried it into my own repository and hardened it there; the tests, the refusals and that CI fix are mine.

**Now.** AI platform engineering at BPCE: sandboxing and isolated execution of agent tools on Kubernetes/OpenShift, with containerised execution and namespace separation. It is an internal proof of concept. Before that, Data Scientist intern at BNP Paribas, IT Group Experimentation Lab — a multi-threaded document analysis pipeline, and Langfuse deployed fully on-premise across 75+ Docker containers for LLM cost and trace monitoring. The measured gains are internal to BNP and are not published.

**Where the deterministic half comes from.** École 42 Paris, 2019–2024: C, UNIX/POSIX, networking, concurrency. [Minishell](https://github.com/Wesper-Dev/Minishell) is a POSIX shell built from the system calls up; [Philosophers](https://github.com/Wesper-Dev/Philosophers) is threads and mutexes with no deadlock and no starvation; [Inception](https://github.com/Wesper-Dev/Inception) is NGINX/TLS, WordPress with PHP-FPM and MariaDB across three hand-written Dockerfiles. An agent that has to run offline, refuse cleanly and re-check itself is a systems problem before it is a prompt problem.

**Also.** A private harness driving `gemma4:12b` through Pokémon Emerald autonomously, with an explicit line between what the harness executes and what the model decides: 875 tests, 18 dated architecture decisions, and an engineering journal that is never rewritten. On an identical harness a frontier model succeeds where the 12B confabulates — so the bottleneck is knowledge, not mechanism.

A C2 coordination layer for counter-drone defence, at a defence hackathon in June 2026, in a private repository I do not own. A first-aid training platform for the French Red Cross, as a volunteer, shown at ChangeNow 2025 — I worked on part of the AI layer, and on framing the problem with the Red Cross trainers. Climate downscaling at GenHack 4, École polytechnique, November 2025 — RMSE from 2.45 °C to 1.24 °C, 9 km down to 80 m, on ERA5 and Sentinel-2. A robotic arm playing Connect 4 at the Hugging Face LeRobot hackathon, June 2025 — an Action Chunking Transformer on a hand-built demonstration set, board detection on 150 hand-labelled images. Co-lead organiser of [GDG on Campus 42 Paris](https://gdg.community.dev/gdg-on-campus-42-paris-paris-france/).

**What I am looking for.** A permanent role in AI platform or applied AI engineering, from 16 October 2026, where execution has to be isolated, measured and defensible. Not prompt-only work, and not anything that ships model output without a deterministic check in front of it.

Best way to reach me: [LinkedIn](https://www.linkedin.com/in/arnaud-durand42). French native, fluent English, conversational Spanish.

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Wesper-Dev/Wesper-Dev/output/github-snake-dark.svg">
  <img alt="A snake crossing my GitHub contribution graph, eating the squares one by one. Regenerated daily by a GitHub Action and committed to this repository." src="https://raw.githubusercontent.com/Wesper-Dev/Wesper-Dev/output/github-snake.svg">
</picture>
