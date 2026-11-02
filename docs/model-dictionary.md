# Словник полів моделі — «Породи тварин» (ЛР №4, варіант 3)

Назви полів (атрибут `name`) — camelCase, надалі використовуються без змін у JavaScript, TypeScript та JSON.

## Модель породи (форми адміністратора)

| name | Зміст | Тип даних | Елемент керування | Обмеження |
|---|---|---|---|---|
| `id` | Ідентифікатор (лише редагування) | number | `input type="hidden"` | — |
| `title` | Назва породи | string | `input type="text"` | required, minlength=2, maxlength=60 |
| `code` | Код породи | string | `input type="text"` | required, pattern=`[A-Z]{2}-[0-9]{3}`, maxlength=6 |
| `category` | Категорія | enum: dogs, cats, rabbits, other | `select` (перший пункт порожній) | required |
| `sizeGroup` | Розмірна група | enum: small, medium, large | `select` (перший пункт порожній) | required |
| `weight` | Середня вага, кг | number | `input type="number"` | required, min=0.1, max=100, step=0.1 |
| `addedAt` | Дата додавання | date (YYYY-MM-DD) | `input type="date"` | required, min=2024-01-01, max=2027-12-31 |
| `image` | Зображення | file | `input type="file"` | accept=SVG, WebP, PNG; не обов'язкове |
| `description` | Опис | string | `textarea` | maxlength=500 |
| `apartmentFriendly` | Підходить для квартири | boolean | `input type="checkbox"` | — |

## Форма відвідувача (запит на консультацію, details.html)

| name | Зміст | Тип даних | Елемент керування | Обмеження |
|---|---|---|---|---|
| `breedCode` | Код породи зі сторінки | string | `input type="hidden"` | — |
| `name` | Ім'я | string | `input type="text"` | maxlength=60, autocomplete=name |
| `email` | Електронна пошта | string | `input type="email"` | required, autocomplete=email |
| `phone` | Телефон | string | `input type="tel"` | pattern=`\+380[0-9]{9}`, autocomplete=tel |
| `contactDate` | Бажана дата зв'язку | date | `input type="date"` | required, min=2026-11-02, max=2027-12-31 |
| `contactMethod` | Зручний спосіб зв'язку | string | `input type="text"` + `datalist` | maxlength=40 |
| `rating` | Оцінка зацікавленості | number 1–5 | `input type="radio"` у `fieldset` | required |
| `experience` | Досвід утримання тварин | number 0–5 | `input type="range"` | min=0, max=5, step=1 |
| `comment` | Коментар | string | `textarea` | minlength=10, maxlength=500 |
| `agree` | Згода з правилами | boolean | `input type="checkbox"` | required |
