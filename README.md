# Lavka RecSys

Рекомендации товаров против оттока для маркетплейса Neon на данных Яндекс Лавки:
эвристики («Популярное», «Купить снова»), item-based и user-based CF, content-based (TF-IDF), ALS из `implicit` и гибрид.
Код и результаты - в `lavka_churn_recsys.ipynb`.

## Требования

- Python 3.12
- [uv](https://docs.astral.sh/uv/): `curl -LsSf https://astral.sh/uv/install.sh | sh`
- около 1 ГБ свободного места под датасет (~430 МБ)

## 1. Установка проекта

```bash
uv sync
```

`uv sync` ставит зависимости вместе с dev-группой (Jupyter).

## 2. Данные

Датасет [YSDA RecSys 2025 - Lavka](https://www.kaggle.com/datasets/thekabeton/ysda-recsys-2025-lavka-dataset)
скачивается автоматически через `kagglehub` при первом запуске ноутбука и кэшируется в `~/.cache/kagglehub`.

## 3. Запуск ноутбука

```bash
uv run jupyter lab lavka_churn_recsys.ipynb
```

Выполнение ячеек по порядку. Первый запуск дольше из-за скачивания данных; всё считается на CPU.

Запуск без интерфейса, с сохранением результатов в ноутбук:

```bash
uv run jupyter nbconvert --to notebook --execute --inplace lavka_churn_recsys.ipynb
```
