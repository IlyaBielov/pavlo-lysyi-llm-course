# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

Personal workspace for the course **«AI-Інженерія»** (14 lessons). Use it only for course work:
notes, explanations, exercises, workshops and the final project. Don't add anything unrelated.

- Talk to the user in **Ukrainian**. Keep English technical terms (attention, embeddings, RAG, ...)
  as they are, and add a short Ukrainian explanation the first time a term appears.
- The user is a working developer. Skip programming basics and spend the effort on the ML/LLM
  concepts and on how they apply in production.
- When explaining a concept, start with the intuition, then the mechanism (formulas or diagrams
  only where they help), then a small runnable example.

## Layout

```
lessons/NN-slug/
  notes.md      # the user's notes for the lesson (sections: Ключові ідеї, Терміни, Питання, Практика)
  ...           # code and exercises for the lesson go in the same folder
```

- In `notes.md`, add to or tidy the user's notes. Don't overwrite them without asking.
- Workshops (lessons 8, 10, 12) and the final project (14) are hands-on: put their code in that
  lesson's folder.
## Stack and commands

The course uses Python. The project is managed with `uv` (Python 3.12; dependencies live in
`pyproject.toml` and `uv.lock`).

```bash
uv sync                                         # install dependencies into .venv
uv add <pkg>                                    # add a dependency
uv run lessons/01-llm-history/sentiment.py      # run a lesson script
```

- spaCy's English model `en_core_web_sm` is pinned in `pyproject.toml` as a wheel URL, because
  `python -m spacy download` doesn't work inside a uv venv. When upgrading spaCy, pick the model
  wheel whose version matches.
- NLTK data (vader_lexicon, movie_reviews, punkt_tab, the tagger and NE chunker) is downloaded to
  `~/nltk_data` and is not stored in the repo.
- Write scripts that the lesson generates (HTML/SVG and the like) to `lessons/NN-slug/out/`.

## Git

The remote is `git@github.com:IlyaBielov/pavlo-lysyi-llm-course.git` (public, branch `main`).
Commit and push only when the user asks.

## Course program

The lesson titles below are authoritative. The subtitles on the course platform look shifted
relative to the titles, so ignore them.

| # | Урок | Тип |
|---|------|-----|
| 1 | LLM: історія, еволюція та чому вони змінили світ | теорія |
| 2 | Transformer — архітектура, яка змінила все | теорія |
| 3 | Як насправді працює ChatGPT та сучасні LLM | теорія |
| 4 | Токенізація: very deep dive | теорія |
| 5 | Generation mechanics: чому LLM нестабільні | теорія |
| 6 | Prompting best practices (based on science methodology research) | теорія |
| 7 | Embeddings: семантика у векторному просторі | теорія |
| 8 | Застосування embeddings на прикладних задачах | воркшоп |
| 9 | Retrieval як система і фундамент RAG | теорія |
| 10 | Побудова production RAG | воркшоп |
| 11 | LLM-агенти: коли модель починає діяти | теорія |
| 12 | LLM-агенти та автоматизації | воркшоп |
| 13 | Продакшн: latency, cost, масштабування | теорія |
| 14 | Презентація фінального проєкту | фінал |

## Conventions

- Secrets (API keys) go in `.env`, which git ignores. Commit only a `.env.example`.
- When an example calls an LLM API, use the provider the lesson uses. If the lesson doesn't name
  one, ask the user.
