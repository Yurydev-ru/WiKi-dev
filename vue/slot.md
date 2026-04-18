**Подробное руководство по использованию `<slot/>` в Nuxt 4**

Nuxt 4 (на базе Vue 3.5+) полностью сохраняет и расширяет систему **слотов** Vue. Слоты — это основной механизм **content projection** (проецирования контента), который позволяет родительскому компоненту «вставлять» произвольный HTML/компоненты/текст в заранее определённые места дочернего компонента. Это делает компоненты максимально переиспользуемыми и гибкими.

### 1. Основные понятия

- **Слот** — это «дырка» в шаблоне компонента, куда родитель может положить свой контент.
- **Default slot** — безымянный слот (самый частый).
- **Named slot** — именованный слот (для нескольких разных мест в компоненте).
- **Scoped slot** (слот с пропсами) — слот, который получает данные из дочернего компонента (аналогично `v-for` с `item`).

### 2. Как объявлять слоты в дочернем компоненте

#### Default slot (самый простой)

```vue
<!-- UiContainer.vue (как у вас в проекте) -->
<template>
  <div class="ui-container">
    <slot />          <!-- ← сюда вставится любой контент от родителя -->
  </div>
</template>
```

#### Named slots

```vue
<template>
  <div class="card">
    <slot name="header" />           <!-- заголовок -->
    <slot name="image" />            <!-- картинка -->
    <slot />                         <!-- основной контент (default) -->
    <slot name="footer" />           <!-- футер -->
  </div>
</template>
```

#### Слоты с fallback-контентом (по умолчанию)

```vue
<slot name="image">
  <img src="/placeholder.jpg" alt="placeholder">  <!-- будет показан, если родитель ничего не передал -->
</slot>
```

#### Scoped slots (слот с данными от ребёнка)

```vue
<!-- ProductCard.vue -->
<template>
  <div class="product-card">
    <slot 
      :product="product" 
      :is-new="isNewProduct"
      :discount="calculateDiscount()"
    />
  </div>
</template>
```

### 3. Как использовать слоты в родительском компоненте (Nuxt 4)

#### Синтаксис v-slot (рекомендуется в Nuxt 4)

**Короткий синтаксис `#` (самый современный и удобный):**

```vue
<!-- pages/category/[slug].vue -->
<template>
  <UiContainer>
    <!-- default slot -->
    <h2 class="category-title">{{ slug }}</h2>

    <!-- named slots -->
    <template #header>
      <AppHeader />
    </template>

    <template #image>
      <BgVideo />
    </template>

    <!-- scoped slot -->
    <template #default="{ product, isNew }">
      <div class="card" :class="{ 'is-new': isNew }">
        <img :src="product.image" alt="">
        <h3>{{ product.title }}</h3>
        <p>{{ product.price }}₽</p>
      </div>
    </template>
  </UiContainer>
</template>
```

**Полный синтаксис `v-slot:` (если нужно передать props в слот):**

```vue
<template #default="slotProps">
  <div>{{ slotProps.product.title }}</div>
</template>
```

### 4. Nuxt-специфичные особенности (Nuxt 4)

#### 1. Layouts — это компоненты со слотом по умолчанию
В `layouts/default.vue` (или любом другом) почти всегда используется:

```vue
<template>
  <div class="app-wrapper">
    <AppHeader />
    <main>
      <slot />          <!-- ← сюда Nuxt автоматически вставляет содержимое страницы -->
    </main>
    <AppFooter />
    <!-- или SidebarSection с named слотами -->
  </div>
</template>
```

Вы можете создавать несколько layout'ов и использовать named slots:

```vue
<!-- layouts/with-sidebar.vue -->
<template>
  <div class="app-wrapper">
    <aside><slot name="sidebar" /></aside>
    <main><slot /></main>
  </div>
</template>
```

Использование в странице:

```vue
<script setup>
definePageMeta({ layout: 'with-sidebar' })
</script>

<template>
  <template #sidebar>
    <SidebarSection />
  </template>

  <!-- default content страницы -->
  <div class="menu">...</div>
</template>
```

#### 2. Компоненты Nuxt (NuxtLink, NuxtImg и т.д.) тоже поддерживают слоты
```vue
<NuxtLink to="/menu">
  <template #default>Перейти в меню</template>
  <template #icon>
    <Icon name="mdi:cart" />
  </template>
</NuxtLink>
```

#### 3. Dynamic named slots (очень полезно в ваших категориях)

```vue
<!-- DynamicCategory.vue -->
<template>
  <div v-for="section in sections" :key="section.name">
    <slot :name="section.name" />
  </div>
</template>
```

Использование:

```vue
<DynamicCategory>
  <template #Myaso>Мясные блюда...</template>
  <template #Rolls>Роллы...</template>
  <template #Drink>Напитки...</template>
</DynamicCategory>
```

### 5. Лучшие практики и нюансы в вашем проекте

1. **Улучшение вашего UiContainer.vue**
   Сейчас у вас только default slot. Добавьте named slots для большей гибкости:

   ```vue
   <template>
     <div class="ui-container">
       <slot name="sidebar" />        <!-- боковая панель -->
       <slot />                       <!-- основной контент -->
       <slot name="aside" />          <!-- дополнительная колонка -->
     </div>
   </template>
   ```

2. **HeroSection + BgVideo**
   Вы можете вынести видео в слот, чтобы легко менять фоновое видео/изображение:

   ```vue
   <!-- HeroSection.vue -->
   <BgVideo>
     <template #background>
       <video ... />
     </template>
     <template #content>
       <div class="hero-sections_content">...</div>
     </template>
   </BgVideo>
   ```

3. **Product cards в [slug].vue**
   Вместо жёсткого шаблона используйте scoped slot в отдельном компоненте `ProductCard.vue`:

   ```vue
   <!-- ProductCard.vue -->
   <template>
     <div class="card">
       <slot name="image" :image="image" />
       <slot name="title" :title="title" />
       <slot />
     </div>
   </template>
   ```

   Тогда в `[slug].vue` можно делать:

   ```vue
   <ProductCard v-for="product in products">
     <template #image="{ image }">
       <img :src="image" alt="">
     </template>
   </ProductCard>
   ```

4. **Edge cases и частые ошибки**

   - **Слот не отображается** → проверьте, что в родителе нет `v-if` на `<template #name>`.
   - **Несколько default слотов** → Vue берёт только первый. Остальные игнорируются.
   - **Scoped slot без имени** → всегда `v-slot:default` или `#default`.
   - **Производительность** — слоты рендерятся лениво, но если слот очень тяжёлый — используйте `v-memo` или `keep-alive`.
   - **TypeScript + slots** — в Nuxt 4 отлично работает:

     ```ts
     defineSlots<{
       default?: (props: { product: Product }) => any
       header?: () => any
     }>()
     ```

### 6. Полезные ссылки (актуально для Nuxt 4)

- Официальная документация Vue 3 Slots: https://vuejs.org/guide/components/slots.html
- Nuxt 4 Layouts & Slots: https://nuxt.com/docs/guide/directory-structure/layouts
- Advanced slots patterns (Nuxt community): https://nuxt.com/docs/guide/concepts/rendering#slots

