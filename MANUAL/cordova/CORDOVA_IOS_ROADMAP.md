# Дорожная карта: Сборка WebView проекта под iOS (Cordova/Capacitor)

> **Важно:** Для сборки под iOS (включая симуляторы и реальные устройства) обязательно требуется **macOS** с установленным **Xcode**.

## 1. Подготовка окружения (Prerequisites)

Перед началом убедитесь, что у вас установлены:
- **Node.js & npm** (рекомендуется версия LTS).
- **Xcode** (из App Store). После установки запустите его один раз для принятия лицензии.
- **CocoaPods** — менеджер зависимостей для iOS:
  ```bash
  sudo gem install cocoapods
  ```

---

## 2. Вариант А: Apache Cordova (Классический путь)

### Шаг 1: Установка и создание проекта
```bash
# Установка Cordova глобально
npm install -g cordova

# Создание проекта (папка, ID приложения, Название)
cordova create myApp com.example.myapp MyApp
cd myApp
```

### Шаг 2: Добавление платформы
```bash
cordova platform add ios
```

### Шаг 3: Разработка
- Ваш код (HTML, CSS, JS) должен находиться в папке `www/`.
- Главный файл — `index.html`.

### Шаг 4: Сборка
```bash
# Подготовка файлов (синхронизация www с платформой ios)
cordova prepare ios

# Компиляция проекта
cordova build ios
```

---

## 3. Вариант Б: Capacitor (Современный путь, рекомендуется)

Capacitor лучше работает с современными фреймворками (React, Vue, Angular).

```bash
# Инициализация в существующем веб-проекте
npm install @capacitor/core @capacitor/cli
npx cap init [name] [id]

# Добавление iOS
npm install @capacitor/ios
npx cap add ios

# Синхронизация кода (после каждого билда вашего веб-проекта)
npx cap copy
```

---

## 4. Финальный шаг в Xcode (Обязательно для обоих вариантов)

Cordova или Capacitor создадут нативный проект Xcode. Чтобы запустить его:

1. Откройте файл проекта в Xcode:
   - Для Cordova: `platforms/ios/MyApp.xcworkspace`
   - Для Capacitor: `npx cap open ios`
2. В левой панели выбери проект (**Project Root**).
3. Перейдите во вкладку **Signing & Capabilities**.
4. Выберите свой **Team** (Apple ID). Если его нет — добавьте (Settings -> Accounts).
5. Убедитесь, что галочка **Automatically manage signing** включена.
6. Выберите целевое устройство (Simulator или iPhone) сверху.
7. Нажмите кнопку **Play (Run)**.

---

## 5. Если вы на Windows (Альтернативы)

Напрямую собрать `.ipa` файл на Windows нельзя. Доступные варианты:
1. **Облачные сборщики:** [Appflow (Ionic)](https://ionic.io/appflow) или [Codemagic](https://codemagic.io/).
2. **Виртуальная машина:** Установка macOS через VMWare/VirtualBox (сложно и может тормозить).
3. **Expo (только для React Native):** Позволяет тестировать на iOS через приложение-песочницу без Mac.
