# AI-Інженерія — нотатки та домашні завдання

Мої конспекти й практика з курсу **«AI-Інженерія»**: від класичного NLP і архітектури Transformer до embeddings, RAG, LLM-агентів і продакшну.

## Програма і прогрес

| # | Урок | Тип | Статус |
|---|------|-----|--------|
| 1 | [LLM: історія, еволюція та чому вони змінили світ](lessons/01-llm-history) | теорія | 🟡 в процесі |
| 2 | [Transformer — архітектура, яка змінила все](lessons/02-transformer) | теорія | ⚪ |
| 3 | [Як насправді працює ChatGPT та сучасні LLM](lessons/03-how-chatgpt-works) | теорія | ⚪ |
| 4 | [Токенізація: very deep dive](lessons/04-tokenization) | теорія | ⚪ |
| 5 | [Generation mechanics: чому LLM нестабільні](lessons/05-generation-mechanics) | теорія | ⚪ |
| 6 | [Prompting best practices](lessons/06-prompting) | теорія | ⚪ |
| 7 | [Embeddings: семантика у векторному просторі](lessons/07-embeddings) | теорія | ⚪ |
| 8 | [Застосування embeddings на прикладних задачах](lessons/08-workshop-embeddings) | воркшоп | ⚪ |
| 9 | [Retrieval як система і фундамент RAG](lessons/09-retrieval-rag) | теорія | ⚪ |
| 10 | [Побудова production RAG](lessons/10-workshop-production-rag) | воркшоп | ⚪ |
| 11 | [LLM-агенти: коли модель починає діяти](lessons/11-llm-agents) | теорія | ⚪ |
| 12 | [LLM-агенти та автоматизації](lessons/12-workshop-agents) | воркшоп | ⚪ |
| 13 | [Продакшн: latency, cost, масштабування](lessons/13-production) | теорія | ⚪ |
| 14 | [Фінальний проєкт](lessons/14-final-project) | фінал | ⚪ |

## Структура

```
lessons/NN-slug/
  notes.md   # конспект уроку
  *.py       # код домашніх завдань і воркшопів
```

## Запуск

Потрібен [uv](https://docs.astral.sh/uv/) (Python 3.12 він поставить сам).

```bash
uv sync
uv run python -c "import nltk; [nltk.download(p) for p in ['vader_lexicon','movie_reviews','punkt_tab','averaged_perceptron_tagger_eng','maxent_ne_chunker_tab','words','stopwords']]"
uv run lessons/<NN-slug>/<script>.py
```

Ключі API (коли знадобляться) кладуться в `.env`, він у `.gitignore`.
