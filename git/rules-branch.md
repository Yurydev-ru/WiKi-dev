# 🛠 3. Правила ведения веток feature‑ветки

### **1. Создаёшь ветку от develop**
```
git checkout develop
git pull
git checkout -b feature/ui-sidebar-fixes
```

### **2. Работаешь, коммитишь, пушишь**
```
git add .
git commit -m "Improve sidebar layout and fix spacing"
git push -u origin feature/ui-sidebar-fixes
```

### **3. Когда закончил — создаёшь Pull Request → develop**
Это даёт:

- чистую историю  
- возможность ревью  
- отсутствие конфликтов  

---

# 🔥 4. Как вести hotfix‑ветки

Используются, когда нужно срочно исправить баг в продакшене.

### Шаги:
```
git checkout main
git pull
git checkout -b hotfix/fix-nav-bug
```

После исправления:

```
git commit -m "Fix nav bug in production"
git push -u origin hotfix/fix-nav-bug
```

PR → `main`  
и **обязательно** PR → `develop`, чтобы develop не отстал.

---

# 🚀 5. Как вести релизы (если нужно)

Если проект растёт, можно включить релизные ветки:

```
git checkout develop
git checkout -b release/1.2.0
```

В них:

- финальная полировка  
- версия  
- changelog  

После релиза:

- merge → `main`
- merge → `develop`

---
