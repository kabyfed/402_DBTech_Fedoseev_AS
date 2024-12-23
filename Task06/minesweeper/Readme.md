# Проект "Сапер" (Minesweeper)

## Описание проекта

Это веб-версия игры "Сапер" (Minesweeper), реализованная на JavaScript с использованием базы данных **IndexedDB** для сохранения данных игры. Игра сохраняет результаты партий в браузере пользователя, позволяя просматривать историю игр и воспроизводить ранее сыгранные партии.

Цель игры — открыть все ячейки, не содержащие мин. Если игрок открыл ячейку с миной, он проигрывает. Если ячейка не заминирована, в ней отображается количество мин, соседствующих с этой ячейкой.

### Правила игры

- Игрок открывает ячейки, избегая мин. Открыв мину, игрок проигрывает.
- Если ячейка не заминирована, отображается число соседних заминированных ячеек.
- Если рядом с открытой ячейкой нет мин, открывается область незаминированных ячеек.

### Требования

- **Размер поля и количество мин**: Вводятся пользователем перед началом игры.
- **Сохранение данных**: Вся информация об играх и ходах сохраняется в **IndexedDB**.
- **Хранение данных**:
  - Дата игры
  - Имя игрока
  - Размер поля и количество мин
  - Расположение мин
  - Исход игры
  - Запись ходов в формате: `номер хода | координаты ячейки | результат (мимо/взорвался/выиграл)`
- **Режимы игры**:
  - Новая игра
  - Просмотр списка сохраненных игр
  - Повтор сохраненной партии (воспроизведение ходов)

---

## Игровой процесс

### Начало игры

Перед началом партии пользователю будет предложено ввести следующие параметры:

1. **Размер поля**: Укажите размер игрового поля в формате `ширина высота` (например, `10 10` для поля 10x10).
2. **Количество мин**: Укажите общее количество мин на поле (например, `20`).

### Ввод координат

Игрок открывает ячейки, щелкая по ним на экране. При этом координаты автоматически обрабатываются в зависимости от положения ячейки на игровом поле.

### Открытие ячеек

Игрок кликает на ячейки игрового поля. Если игрок открывает ячейку с миной, игра заканчивается, и выводится сообщение о проигрыше. Если игрок открывает ячейку без мины, она отображает количество мин в соседних ячейках.

### Команды

1. **Сохранить игру**: Игра автоматически сохраняет состояние в **IndexedDB**, и пользователь может вернуться к ней позже.
2. **Просмотр списка сохраненных игр**: После окончания игры можно просмотреть список сохраненных игр с результатами.
3. **Повторить партию**: Воспроизведение ранее сыгранной партии, с возможностью просмотра ходов.

---

## Окружение и требования для запуска

1. **Браузер**:
   - Совместимость с современными браузерами, поддерживающими JavaScript и IndexedDB (Chrome, Firefox, Edge и другие).
2. **IndexedDB**:
   - Поддержка IndexedDB для хранения данных игры локально в браузере.

---

## Установка и запуск проекта

1. **Склонируйте репозиторий**:
   ```bash
   git clone https://github.com/kabyfed/MinesweeperGame.git

2. **Перейдите в каталог проекта**:

```bash
cd MinesweeperGame
```

3. **Откройте файл index.html в вашем браузере**: 
    Для начала игры откройте файл index.html в вашем любимом браузере. Игра будет загружена и готова к началу.

4. **Запуск через GitHub Pages**:

    Если вы не хотите загружать проект на свой локальный компьютер, вы можете запустить игру прямо из браузера, воспользовавшись [GitHub Pages](https://kabyfed.github.io/MinesweeperGame/). Для этого:

    - Перейдите на страницу игры на GitHub Pages.
        - Игра автоматически загрузится и будет готова к началу.

## Примечания
- Сохранение игры: 
Все игры сохраняются локально в IndexedDB вашего браузера. Убедитесь, что ваш браузер поддерживает эту технологию.
- Обновления: Для обновления локальной версии игры просто склонируйте последний вариант репозитория и откройте файл index.html.

## Ссылки
- [GitHub репозиторий](https://github.com/kabyfed/MinesweeperGame)
- [GitHub Pages](https://kabyfed.github.io/MinesweeperGame/)