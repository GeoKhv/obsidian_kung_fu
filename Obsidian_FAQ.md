Полезная инфа, лайвхаки, hotkeys и ссылки

==[Help](https://help.obsidian.md/Home)==
___
## Обучалки по Obsidian

- [ ] [Курс по Obsidian (9 видео)](https://www.youtube.com/playlist?list=PLeDR6lYFEHWEUxwSA8OplPLvk50DCVraH)
- [ ] [Философия и практика Obsidian (Диджитализируй!)](https://www.youtube.com/watch?v=unvwJRgX2bs)

___
## Hotkeys

- `Command + ,` - открыть окно настроек
- `Command + O` - поиск и создание новых заметок
- `Command + Shift + F` - поиск заметки по содержимому
- `Option + Enter` - создание заметки при связывании `[[]]`
- `Command + E` - переключение между режимом `чтения` и `просмотра`
- `Command + Space` - создание и редактирование чек-бокса (таски)
- `Command + N` - создание новой заметки
___
## Форматирование текста

- Выделение текста
   ==Highlights==

- Форматирование кода в строке
  Необходимо вставить код `run("Hello, World!")` прямо в строке!

- Форматирование кода языка программирования
```python
def run(text: str):
    print(text)
```

- Изменение размера изображений
  ![[Kotlin_Icon.png|200]]

- Inline связанных заметок
  `![[Some Note]]`

- [Callouts](https://help.obsidian.md/Editing+and+formatting/Callouts)
  >[!info] Info
  >Текст заметки
  
  >[!info]- Сворачиваемая заметка
  >А внутри спрятан текст
  
  >[!question] Question
  >Aliases: `help`, `faq`
  
  >[!note] Note
  >Текст заметки

>[!tip] Tips
>Тест заметки

  >[!todo] Todo
  >Текст todo
  
  >[!success] Success
  >Aliases:`check`, `done`
  
  >[!warning] Warning
  >Aliases: `caution`, `attention`
  
  >[!failure] Failure
  >Aliases: `fail`, `missing`
  
  >[!Bug] Bug
  >Текст
  
  >[!example] Example
  >Текст
  
  >[!quote] Quote
  >Текст
  
___
## Настройка Obsidian

- Вставка и хранение изображений
  ![[files_directory.png]]

- Настройка шаблонов
  ![[templates_directory.png]]

- Настройка ежедневных заметок
  ![[daily_notes.png]]

- DataView (plugin)
- [Tasks](https://publish.obsidian.md/tasks/Introduction) (plugin)
  ![[tasks_settings_date.png]]

## Waiting и daily v2

Для разделения действий и ожиданий используйте [daily v2](templates/daily-v2.md) и [инструкцию установки](README.md#установка-daily-v2). Waiting: свободный символ `w`, тип `ON_HOLD`, следующий статус — Todo (пробел).

`not done` включает ON_HOLD. В старом Unfinished добавьте `status.type is not ON_HOLD`, если ожидания должны быть отдельно. Исторические заметки автоматически не изменяются. `show tree` может показать Waiting под активным родителем; в v2 задачи выводятся отдельно с сохранением исходного Markdown.
