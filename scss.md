# 🌟 Полное руководство по SCSS: Основы, карты, миксины и функции 🌟

Добро пожаловать в **яркий и подробный** гайд по SCSS — мощному препроцессору CSS, который сделает ваш код структурированным, масштабируемым и выразительным! 🚀 Этот конспект охватывает всё: от базовых концепций до современных методик, включая углублённое изучение **карт (maps)**, **миксинов (mixins)** и **функций (functions)**. Гайд написан для начинающих и опытных разработчиков, с примерами, лучшими практиками и яркими акцентами на ключевых моментах. Все данные актуальны на **2025 год**.

---

## 📋 Оглавление

1. [Введение в SCSS](#1-введение-в-scss)
2. [Установка и настройка](#2-установка-и-настройка)
3. [Основные концепции SCSS](#3-основные-концепции-scss)
   - [Переменные](#31-переменные)
   - [Вложенность (Nesting)](#32-вложенность-nesting)
   - [Partials и @import](#33-partials-и-import)
4. [Mixins и функции](#4-mixins-и-функции)
   - [Mixins (@mixin и @include)](#41-mixins-mixin-и-include)
   - [Функции (@function)](#42-функции-function)
5. [Наследование (@extend)](#5-наследование-extend)
6. [Контроль потока и операторы](#6-контроль-потока-и-операторы)
   - [Условные конструкции (@if, @else)](#61-условные-конструкции-if-else)
   - [Циклы (@for, @each, @while)](#62-циклы-for-each-while)
   - [Операторы](#63-операторы)
7. [Работа с картами (Maps)](#7-работа-с-картами-maps)
   - [Что такое карты?](#71-что-такое-карты)
   - [Синтаксис и создание карт](#72-синтаксис-и-создание-карт)
   - [Доступ к значениям в картах](#73-доступ-к-значениям-в-картах)
   - [Основные функции для работы с картами](#74-основные-функции-для-работы-с-картами)
   - [Итерация по картам с @each](#75-итерация-по-картам-с-each)
   - [Практические примеры использования карт](#76-практические-примеры-использования-карт)
   - [Лучшие практики работы с картами](#77-лучшие-практики-работы-с-картами)
   - [Продвинутые техники с картами](#78-продвинутые-техники-с-картами)
8. [Самые распространённые карты, миксины и функции](#8-самые-распространённые-карты-миксины-и-функции)
   - [Популярные карты](#81-популярные-карты)
   - [Популярные миксины](#82-популярные-миксины)
   - [Популярные функции](#83-популярные-функции)
   - [Почему они популярны?](#84-почему-они-популярны)
   - [Лучшие практики и рекомендации](#85-лучшие-практики-и-рекомендации)
   - [Практическое задание](#86-практическое-задание)
9. [Современные методики и модули](#9-современные-методики-и-модули)
   - [Модули (@use и @forward)](#91-модули-use-и-forward)
   - [Интеграция с фреймворками](#92-интеграция-с-фреймворками)
   - [Лучшие практики](#93-лучшие-практики)
10. [Практические советы и отладка](#10-практические-советы-и-отладка)
11. [Заключение](#11-заключение)

---

```markdown
 Полное руководство по SCSS: Основы, карты, миксины и функции 🌟

Добро пожаловать в **яркий и подробный** гайд по SCSS — мощному препроцессору CSS, который сделает ваш код структурированным, масштабируемым и выразительным! 🚀 Этот конспект охватывает всё: от базовых концепций до современных методик, включая углублённое изучение **карт (maps)**, **миксинов (mixins)** и **функций (functions)**. Гайд написан для начинающих и опытных разработчиков, с примерами, лучшими практиками и яркими акцентами на ключевых моментах. Все данные актуальны на **2025 год**.

---

## 📋 Оглавление

1. [Введение в SCSS](#1-введение-в-scss)
2. [Установка и настройка](#2-установка-и-настройка)
3. [Основные концепции SCSS](#3-основные-концепции-scss)
   - [Переменные](#31-переменные)
   - [Вложенность (Nesting)](#32-вложенность-nesting)
   - [Partials и @import](#33-partials-и-import)
4. [Mixins и функции](#4-mixins-и-функции)
   - [Mixins (@mixin и @include)](#41-mixins-mixin-и-include)
   - [Функции (@function)](#42-функции-function)
5. [Наследование (@extend)](#5-наследование-extend)
6. [Контроль потока и операторы](#6-контроль-потока-и-операторы)
   - [Условные конструкции (@if, @else)](#61-условные-конструкции-if-else)
   - [Циклы (@for, @each, @while)](#62-циклы-for-each-while)
   - [Операторы](#63-операторы)
7. [Работа с картами (Maps)](#7-работа-с-картами-maps)
   - [Что такое карты?](#71-что-такое-карты)
   - [Синтаксис и создание карт](#72-синтаксис-и-создание-карт)
   - [Доступ к значениям в картах](#73-доступ-к-значениям-в-картах)
   - [Основные функции для работы с картами](#74-основные-функции-для-работы-с-картами)
   - [Итерация по картам с @each](#75-итерация-по-картам-с-each)
   - [Практические примеры использования карт](#76-практические-примеры-использования-карт)
   - [Лучшие практики работы с картами](#77-лучшие-практики-работы-с-картами)
   - [Продвинутые техники с картами](#78-продвинутые-техники-с-картами)
8. [Самые распространённые карты, миксины и функции](#8-самые-распространённые-карты-миксины-и-функции)
   - [Популярные карты](#81-популярные-карты)
   - [Популярные миксины](#82-популярные-миксины)
   - [Популярные функции](#83-популярные-функции)
   - [Почему они популярны?](#84-почему-они-популярны)
   - [Лучшие практики и рекомендации](#85-лучшие-практики-и-рекомендации)
   - [Практическое задание](#86-практическое-задание)
9. [Современные методики и модули](#9-современные-методики-и-модули)
   - [Модули (@use и @forward)](#91-модули-use-и-forward)
   - [Интеграция с фреймворками](#92-интеграция-с-фреймворками)
   - [Лучшие практики](#93-лучшие-практики)
10. [Практические советы и отладка](#10-практические-советы-и-отладка)
11. [Заключение](#11-заключение)

---

## 1. Введение в SCSS 🎨

**SCSS** (Syntactically Awesome Style Sheets) — это препроцессор CSS, который расширяет его возможности, делая код **читаемым**, **масштабируемым** и **удобным для поддержки**. SCSS компилируется в обычный CSS и полностью совместим с ним. 😎

**Почему SCSS?**
- **Переменные** для повторного использования значений.
- **Вложенность** для удобной работы с селекторами.
- **Миксины** и **функции** для переиспользуемых стилей.
- **Модульность** с разделением на файлы.
- **Логика** (условия, циклы, операторы).

**Когда использовать?** В любых проектах: от простых лендингов до сложных приложений на React, Vue или Angular. 🚀

> **Заметка:** SCSS — это синтаксис Sass, использующий фигурные скобки и точки с запятой (как CSS). Sass (без точек с запятой) менее популярен.

---

## 2. Установка и настройка 🛠️

Чтобы начать работать с SCSS, нужно установить Sass и настроить окружение.

### Шаги установки:
1. **Через npm (рекомендуемый способ):**
   - Установите Node.js.
   - В терминале: `npm install -g sass` (глобально) или `npm install sass --save-dev` (локально).
   - Компиляция: `sass input.scss output.css`.

2. **Через инструменты:**
   - **VS Code:** Установите расширение **Live Sass Compiler** для автоматической компиляции.
   - **Фреймворки:** React (с `sass`), Vue CLI, Angular — поддерживают SCSS из коробки.

3. **Компиляция:**
   - Ручная: `sass --watch styles.scss:styles.css` (наблюдение за изменениями).
   - Автоматическая: Используйте Webpack, Vite или Parcel.

**💡 Совет:** В 2025 году используйте Vite для быстрой сборки SCSS в современных проектах! 

---

## 3. Основные концепции SCSS 🌟

### 3.1. Переменные
Переменные хранят значения (цвета, размеры, строки) для повторного использования.

**Пример:**
```scss
$primary-color: #007bff; // 🔥 Основной цвет
$font-size-base: 16px;

body {
  color: $primary-color;
  font-size: $font-size-base;
}
```

**Компилируется в:**
```css
body {
  color: #007bff;
  font-size: 16px;
}
```

**💡 Совет:** Используйте переменные для тем (light/dark) и экспорта в CSS Custom Properties.

### 3.2. Вложенность (Nesting)
Вложенность позволяет писать стили, отражая структуру HTML.

**Пример:**
```scss
nav {
  ul {
    margin: 0;
    li {
      list-style: none;
      a {
        color: $primary-color;
        &:hover { // 🔥 & — ссылка на родителя
          text-decoration: underline;
        }
      }
    }
  }
}
```

**Компилируется в:**
```css
nav ul {
  margin: 0;
}
nav ul li {
  list-style: none;
}
nav ul li a {
  color: #007bff;
}
nav ul li a:hover {
  text-decoration: underline;
}
```

**⚠️ Внимание:** Избегайте вложенности глубже 3 уровней, чтобы не создавать слишком специфичные селекторы. 

### 3.3. Partials и @import
**Partials** — это файлы SCSS (с префиксом `_`, например, `_variables.scss`), которые не компилируются отдельно.

**Пример:**
В `_variables.scss`:
```scss
$primary-color: #007bff;
```

В `main.scss`:
```scss
@import 'variables'; // Без _ и .scss
body {
  color: $primary-color;
}
```

**🔥 Важно:** В современном Sass используйте `@use` вместо `@import` (см. раздел 9.1).

---

## 4. Mixins и функции 🛠️

### 4.1. Mixins (@mixin и @include)
Миксины — это переиспользуемые блоки стилей, как функции в программировании.

**Пример:**
```scss
@mixin flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  @include flex-center;
  height: 100vh;
}
```

**Компилируется в:**
```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
```

**С параметрами:**
```scss
@mixin button($bg-color: #fff, $text-color: #000) {
  background: $bg-color;
  color: $text-color;
  padding: 10px;
}

.btn-primary {
  @include button(#007bff, #fff);
}
```

### 4.2. Функции (@function)
Функции возвращают вычисленные значения.

**Пример:**
```scss
@function calculate-rem($px) {
  @return ($px / 16) * 1rem;
}

h1 {
  font-size: calculate-rem(32); // 2rem
}
```

---

## 5. Наследование (@extend) 🧬
Позволяет классам наследовать стили от других.

**Пример:**
```scss
.btn {
  padding: 10px;
  border: 1px solid;
}

.btn-primary {
  @extend .btn;
  background: $primary-color;
}
```

**Компилируется в:**
```css
.btn, .btn-primary {
  padding: 10px;
  border: 1px solid;
}
.btn-primary {
  background: #007bff;
}
```

**💡 Совет:** Используйте `@extend` с осторожностью, чтобы избежать ненужного дублирования.

---

## 6. Контроль потока и операторы ⚙️

### 6.1. Условные конструкции (@if, @else)
**Пример:**
```scss
@mixin theme($mode: light) {
  @if $mode == dark {
    background: #000;
    color: #fff;
  } @else {
    background: #fff;
    color: #000;
  }
}

body {
  @include theme(dark);
}
```

### 6.2. Циклы (@for, @each, @while)
**Пример (@for):**
```scss
@for $i from 1 through 3 {
  .col-#{$i} {
    width: ($i / 3) * 100%;
  }
}
```

**Компилируется в:**
```css
.col-1 { width: 33.3333%; }
.col-2 { width: 66.6667%; }
.col-3 { width: 100%; }
```

### 6.3. Операторы
- Математика: `+`, `-`, `*`, `/`, `%`.
- Строки: `+` для конкатенации.

---

## 7. Работа с картами (Maps) 🗺️

### 7.1. Что такое карты?
Карты — это структуры данных в формате ключ-значение, идеальные для хранения настроек (цвета, размеры, темы).

**Пример:**
```scss
$colors: (
  primary: #007bff,
  secondary: #6c757d,
  success: #28a745
);
```

### 7.2. Синтаксис и создание карт
Карты создаются в круглых скобках `()` с парами ключ-значение.

**Пример:**
```scss
$theme: (
  font-size: 16px,
  primary-color: #007bff,
  margins: (10px, 20px, 30px),
  nested: (
    border: 1px solid black,
    radius: 5px
  )
);
```

### 7.3. Доступ к значениям в картах
Используйте `map-get($map, $key)`.

**Пример:**
```scss
body {
  background: map-get($colors, primary); // #007bff
}
```

**Вложенные карты:**
```scss
$theme: (colors: (primary: #007bff));
.btn {
  color: map-get(map-get($theme, colors), primary); // #007bff
}
```

### 7.4. Основные функции для работы с картами
- **`map-get($map, $key)`**: Получает значение.
- **`map-has-key($map, $key)`**: Проверяет наличие ключа.
- **`map-keys($map)`**: Возвращает ключи.
- **`map-values($map)`**: Возвращает значения.
- **`map-merge($map1, $map2)`**: Объединяет карты.
- **`map-remove($map, $keys...)`**: Удаляет ключи.
- **`map-get-nested($map, $keys...)`**: Для вложенных карт.

**Пример:**
```scss
$colors: (primary: #007bff);
@if map-has-key($colors, primary) {
  body {
    color: map-get($colors, primary);
  }
}
```

### 7.5. Итерация по картам с @each
**Пример:**
```scss
$colors: (
  primary: #007bff,
  secondary: #6c757d,
  success: #28a745
);

@each $name, $value in $colors {
  .text-#{$name} {
    color: $value;
  }
}
```

**Компилируется в:**
```css
.text-primary { color: #007bff; }
.text-secondary { color: #6c757d; }
.text-success { color: #28a745; }
```

### 7.6. Практические примеры использования карт
**Темизация:**
```scss
$themes: (
  light: (
    background: #fff,
    text: #000,
    primary: #007bff
  ),
  dark: (
    background: #333,
    text: #fff,
    primary: #0d6efd
  )
);

@mixin apply-theme($theme-name) {
  $theme: map-get($themes, $theme-name);
  background: map-get($theme, background);
  color: map-get($theme, text);
}

body.light {
  @include apply-theme(light);
}
body.dark {
  @include apply-theme(dark);
}
```

**Breakpoints:**
```scss
$breakpoints: (
  small: 576px,
  medium: 768px,
  large: 992px
);

@each $name, $size in $breakpoints {
  @media (min-width: $size) {
    .#{$name}-hidden {
      display: none;
    }
  }
}
```

### 7.7. Лучшие практики работы с картами
- **Организация:** Группируйте данные (цвета, размеры) в логические карты.
- **Модульность:** Храните карты в `_maps.scss` и импортируйте через `@use`.
- **Проверка ключей:** Используйте `map-has-key` перед `map-get`.
- **CSS Custom Properties:**
  ```scss
  $colors: (primary: #007bff);
  :root {
    @each $name, $value in $colors {
      --#{$name}: #{$value};
    }
  }
  ```

### 7.8. Продвинутые техники с картами
**Динамическое создание:**
```scss
@function create-theme($mode) {
  @if $mode == dark {
    @return (
      background: #333,
      text: #fff
    );
  } @else {
    @return (
      background: #fff,
      text: #000
    );
  }
}

$theme: create-theme(dark);
body {
  background: map-get($theme, background);
}
```

**Рекурсивная обработка:**
```scss
@function deep-get($map, $keys...) {
  $result: $map;
  @each $key in $keys {
    $result: map-get($result, $key);
  }
  @return $result;
}

$theme: (ui: (button: (primary: #007bff)));
.btn {
  color: deep-get($theme, ui, button, primary); // #007bff
}
```

---

## 8. Самые распространённые карты, миксины и функции 🔥

### 8.1. Популярные карты
1. **Карта цветов:**
   ```scss
   $colors: (
     primary: #007bff,
     secondary: #6c757d,
     success: #28a745
   );
   ```
   **Зачем?** Для цветовой палитры и тем.

2. **Карта breakpoints:**
   ```scss
   $breakpoints: (
     xs: 0,
     sm: 576px,
     md: 768px
   );
   ```
   **Зачем?** Для адаптивного дизайна.

3. **Карта размеров:**
   ```scss
   $sizes: (
     small: 10px,
     medium: 20px,
     large: 30px
   );
   ```
   **Зачем?** Для отступов, шрифтов.

4. **Карта тем:**
   ```scss
   $themes: (
     light: (background: #fff, text: #000),
     dark: (background: #333, text: #fff)
   );
   ```
   **Зачем?** Для светлого/тёмного режима.

5. **Карта компонентов:**
   ```scss
   $buttons: (
     primary: (background: #007bff, color: #fff)
   );
   ```
   **Зачем?** Для стилизации компонентов.

### 8.2. Популярные миксины
1. **Media Query:**
   ```scss
   @mixin media($breakpoint) {
     @media (min-width: map-get($breakpoints, $breakpoint)) {
       @content;
     }
   }
   ```

2. **Flexbox:**
   ```scss
   @mixin flex($direction: row, $justify: flex-start, $align: stretch) {
     display: flex;
     flex-direction: $direction;
     justify-content: $justify;
     align-items: $align;
   }
   ```

3. **Button:**
   ```scss
   @mixin button($bg: #007bff, $color: #fff) {
     background: $bg;
     color: $color;
     padding: 10px 20px;
     &:hover {
       background: darken($bg, 10%);
     }
   }
   ```

4. **Font:**
   ```scss
   @mixin font($size: 16px, $weight: normal) {
     font-size: $size;
     font-weight: $weight;
   }
   ```

5. **Animation:**
   ```scss
   @mixin animate($name, $duration: 0.3s) {
     animation: $name $duration ease-in-out;
   }
   ```

### 8.3. Популярные функции
1. **Цветовые функции:**
   - `lighten($color, $amount)`
   - `darken($color, $amount)`
   - `rgba($color, $alpha)`

2. **Map-get:**
   ```scss
   $color: map-get($colors, primary);
   ```

3. **Конвертация единиц:**
   ```scss
   @function rem($px, $base: 16px) {
     @return ($px / $base) * 1rem;
   }
   ```

4. **Пропорции:**
   ```scss
   @function calc-width($columns, $total: 12) {
     @return percentage($columns / $total);
   }
   ```

5. **Замена строк:**
   ```scss
   @function str-replace($string, $search, $replace) {
     $index: str-index($string, $search);
     @if $index {
       @return str-slice($string, 1, $index - 1) + $replace + str-slice($string, $index + str-length($search));
     }
     @return $string;
   }
   ```

### 8.4. Почему они популярны?
- **Универсальность:** Решают типичные задачи (цвета, адаптивность, типографика).
- **Масштабируемость:** Упрощают поддержку крупных проектов.
- **Интеграция:** Используются в фреймворках (Bootstrap, Tailwind).
- **Экономия времени:** Снижают дублирование кода.

### 8.5. Лучшие практики и рекомендации
- Комбинируйте карты, миксины и функции для мощных решений.
- Проверяйте ключи с `map-has-key`.
- Храните код в partials: `_maps.scss`, `_mixins.scss`.
- Минимизируйте лишние стили в циклах.
- Документируйте код комментариями.

**Пример структуры:**
```
scss/
├── base/
│   └── _typography.scss
├── utilities/
│   └── _maps.scss
│   └── _mixins.scss
├── components/
│   └── _buttons.scss
└── main.scss
```

### 8.6. Практическое задание
Создайте систему стилей для карточек:
- Карта с вариантами (default, highlighted).
- Миксин для стилизации.
- Функция для вычисления тени.

**Решение:**
```scss
$cards: (
  default: (
    background: #fff,
    border: 1px solid #ddd,
    shadow: 0 2px 4px rgba(0, 0, 0, 0.1)
  ),
  highlighted: (
    background: #f8f9fa,
    border: 1px solid #007bff,
    shadow: 0 4px 8px rgba(0, 123, 255, 0.2)
  )
);

@function get-shadow($variant) {
  @return map-get(map-get($cards, $variant), shadow);
}

@mixin card($variant) {
  $styles: map-get($cards, $variant);
  background: map-get($styles, background);
  border: map-get($styles, border);
  box-shadow: get-shadow($variant);
  padding: 20px;
}

.card-default {
  @include card(default);
}
.card-highlighted {
  @include card(highlighted);
}
```

---

## 9. Современные методики и модули 🚀

### 9.1. Модули (@use и @forward)
С 2019 года `@use` заменил `@import` для модульности. 

**Пример (@use):**
В `_colors.scss`:
```scss
$colors: (
  primary: #007bff,
  secondary: #6c757d
);
```

В `main.scss`:
```scss
@use 'colors' as c;
body {
  color: c.$primary;
}
```

**@forward:** Передаёт содержимое модуля.
```scss
// _index.scss
@forward 'colors';
```

### 9.2. Интеграция с фреймворками
- **React/Vue/Angular:** Импортируйте SCSS в компоненты.
- **CSS-in-JS:** Комбинируйте SCSS со styled-components для динамики.
- **Vite/Parcel:** Автоматическая поддержка SCSS.

### 9.3. Лучшие практики
- **Архитектура:** Используйте ITCSS или BEM.
- **Производительность:** Минимизируйте nesting, экспортируйте в CSS-переменные.
- **Организация:** Разделяйте на папки: `base/`, `components/`, `themes/`.
- **Избегайте ошибок:** Не используйте `!important`.

---

## 10. Практические советы и отладка 🐞
- **Отладка:** Используйте `--source-map` для сопоставления SCSS и CSS.
- **Производство:** Компилируйте в minified CSS: `sass input.scss output.min.css --style=compressed`.
- **Обучение:** Изучайте исходники Bootstrap или Tailwind.

---

## 11. Заключение 🎉
SCSS — это мощный инструмент для создания масштабируемых, поддерживаемых стилей. Карты, миксины и функции — основа для автоматизации и унификации. Практикуйтесь с примерами, экспериментируйте в проектах и изучайте документацию Sass! 

**💡 Следующий шаг:** Попробуйте создать дизайн-систему с картой `$components`, миксинами для компонентов и функциями для вычислений. Если нужна помощь, напишите! 😄
```