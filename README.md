# CreatedCaptcha
### RUS:

Привет, раз ты попал сюда, значит тебе нужна капча. 
Ну короче это модуль для генерации капчи. Вот.

## Плюсы этого модуля: 
  1. Вы можете изменять размер капчи, а буквы в ней будут автоматический подстраиваться под ее размер
  2. Используется белый шум, который затрудянет распознование текста
  3. Разные шрифты, размеры и наклон букв обеспечивает гарантию защиты от ботов
  4. добавляйте свой фон, свои шрифты для капчи. Изменяйте ее содержимое, а так же ее длинну
  5. Простота работы с модулем.
***
Скачивание
## NPM
```
npm i CreatedCaptcha
```
Пример капчи:
***
![alt text](https://sun9-3.userapi.com/rsdbxNrBpyZX6C2qWEgelsaD2aLroJtqJ6Jxeg/ffyuF7OkwnI.jpg)
***
небольшие пояснения для понимания:
Вам необезательно самому настраивать капчу. Генератор уже автоматически настроен
Необязательная переменная будет отоброжаться как "Необ. Пер."


Пример использования
```js
const {CaptchaGenerator} = require("CreatedCaptcha") //импорт генератора из модуля

let CreatedCaptcha = new CaptchaGenerator() 

let options = {
  height: 200, //Необ. Пер. | Размер в высоту будущей капчи
  width: 600, //Необ. Пер. | Размер в длинну будущей капчи (если не указан, то он принимает значение height * 3)
  LengthOfText: 7, //Необ. Пер. | Кол-во символов в капче
  SlantText: true, //Необ. Пер. | Поворачивать или нет символы (поворачивает от -10 до 10 градусов)
  RandomTextHeight: true, //Необ. Пер. | Изменять ли высоту символа
  Lines: true //Необ. Пер. | Рисовать ли линии (все линии разной толщины и разного цвета)
  NumberOfFonts: 'all' //Необ. Пер. | Сколько шрифтов использовать при генерации (на каждый символ капчи накладывается случайный шрифт)
  // 'all'\true - все шрифты в папке, 'none'\false\1 - использовать 1 шрифт
  SymbolsUsed: ["A","B" ... 8,9,0] //массив символов которые будут использоваться
}
let newCaptcha = CreatedCaptcha.NewCaptcha(options) //{image: <Buffer с картинкой>, text: Ответ на капчу (строчка)}

```
> Пояснение: Если вы делаете ботов для вк и используете [vk-io](https://www.npmjs.com/package/vk-io), то для отправки картинки используйте метод context.sendPhoto(newCaptcha.image)
***
### Добавить задний фон
***
Для того, чтобы добавить задний фон, сделайте следущее:

1. Откройте папку с модулем
2. Перейдите в lib/backround
3. Закиньте туда картинку для заднего фона

```
Внимание! Недобовляйте фон слишком маленького размера, иначе капча выдадит ошибку
```


Учьтите, что это пока что стартовая версия и могут быть баги и недоработки.
О багах пишите в комментариях, мне на [почту](mailto:clownprogrammer@gmail.com) или же мне в [ВК](https://vk.com/clownprogrammer)

```
версия 10.0.0 - исправлены некоторые баги
версия 12.0.0 - Глобальное обновление. Переписан весь модуль! Исправлены баги с размерами текста, исправлен баг с изчезновением текста, исправлен баг 
версия 12.0.1 - Исправлена ошибка связанная с main
версия 12.0.2 - Исправлена ошибка связанная с fonts
версия 12.0.3 - Переписана система генерации заднего фона
```