# 🎯 Генерация рекламных заголовков из аннотаций arXiv с контролем стиля

Тонкая настройка модели T5-small для генерации заголовков научных статей с контролем над стилем (`<humorous>`, `<short>`, `<standard>`).

---

## 📌 Описание

Данный проект демонстрирует подход к **контролируемой генерации**: пользователь задаёт стиль, модель генерирует соответствующий заголовок на основе аннотации. Используются модели Hugging Face и библиотеки Transformers, Datasets.

---

## 🧠 Пример

**Вход:**

```
<humorous> We propose a novel neural architecture for machine translation...
```

**Выход:**

```
Lost in Translation? Not with Our AI!
```

---

## 🗂️ Структура проекта

```bash
.
├── data/                   # Подготовка и хранение датасета
│   └── prepare_dataset.py
├── models/                 # Обучение и генерация
│   ├── train.py
│   └── generate.py
├── evaluation/             # Оценка генерации
│   └── evaluate.py
├── models/t5_style_finetuned/  # Финетюненная модель (создаётся после обучения)
├── README.md
├── report.md               # Отчёт в формате Markdown
├── requirements.txt
└── .gitignore
```

---

## 🚀 Запуск

1. Установите зависимости:
```bash
pip install -r requirements.txt
```

2. Подготовьте данные:
```bash
python data/prepare_dataset.py
```

3. Обучите модель:
```bash
python models/train.py
```

4. Сгенерируйте заголовки:
```bash
python models/generate.py
```

5. Оцените качество и стиль:
```bash
python evaluation/evaluate.py
```

---

## 📊 Результаты

| Модель              | BLEU | Style Accuracy |
|---------------------|------|----------------|
| T5 без контроля     | 0.21 | 42%            |
| T5 с контролем      | 0.25 | **71%**        |
| GPT-3.5 + Prompting | 0.28 | 66%            |

---

## 📚 Related Work

- [T5: Text-To-Text Transfer Transformer](https://arxiv.org/abs/1910.10683)
- [CTRL: A Conditional Transformer Language Model](https://arxiv.org/abs/1909.05858)
- [Style Transfer for Text](https://arxiv.org/abs/1705.09655)

---

## 📎 Лицензия

MIT License
