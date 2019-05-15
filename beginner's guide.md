структура (драфт)

## React.js

Прежде чем мы приступим к делу, скажем пару слов о том, почему React можно считать наилучшей альтернативой среди средств для разработки веб-интерфейсов.

### Декларативный подход к описанию интерфейсов

React-разработка заключается в описании того, что нужно вывести на страницу (а не в составлении инструкций для браузера, посвящённых тому, как это делать). Это, кроме прочего, означает значительное сокращение объёмов шаблонного кода.

### Чёткий синтаксис

В React применяется синтаксис JSX, который **воспринимается** как обычный HTML (но не является ни строкой, ни HTML). Он максимально ясно описывает внешний вид UI, одновременно включая в себя всю мощь JavaScript. Вот как это выглядит:

```
const element = <h1>Hello, world!</h1>;

const Greetings = ({ firstName }) => (
   <div>Hi, {firstName}</div>
);
```

### Особенности механизма привязки данных

В React используется односторонняя привязка данных. Это — большой плюс, так как выражается это в том, что программист всегда точно знает о том, что привело к изменению состояния приложения. Подобный подход к привязке данных значительно упрощает отладку.

!!!!!!**от родителя к детям**

### Механики из графичеких редакторов

Компонентный подход React похож на компоненты Figma или символы Sketch. Компоненты можно вкладывать друг в друга и переопределять стили.

### Изи лайф — изи обучение

Кривая обучения — это важный фактор, который нужно учитывать при выборе UI-фреймворка. В этой связи надо отметить, что в React имеется меньше абстракций, чем, скажем, в Angular. Для того, чтобы разобраться, потребуется некоторое время, но приступить к работе можно очень и очень быстро.

## что умеет
—  

## отличия
—  

## Ссылки react
Официальная документация: [en](https://reactjs.org/) [ru](https://ru.reactjs.org/)  

[Шпаргалка по библиотеке](https://devhints.io/react) для версий 15 и 16 (en)
  *кратко изложены методы и подходы в виде сниппетов кода*

[Видео](https://youtu.be/gRs7NbEZMCg) основы React от создателя Framer (en)
  *???*

[Книга-курс](https://maxfarseer.gitbooks.io/react-course-ru-v2/content/) для начинающих (ru)
  *пошаговое создание небольшого приложения новостей (добавление, просмотр "подробнее")*

[Видео-курс](https://scrimba.com/playlist/p7P5Hd) с практикой (en)
  *пошаговое создание to do app*

Курс Евгения Родионова: [этап 1](https://erodionov.ru/courses/react/9wO7ihaBIk), [этап 2](https://erodionov.ru/courses/react/rHAh7OXEFL), [этап 3](https://erodionov.ru/courses/react/tHKYMIR4QG) (ru)
  *???*


## Ссылки js
[Опыт программирования на javascript](https://kaineer.gitbooks.io/coding-in-javascript/)  
[Базовый курс](https://code-basics.ru/languages/javascript) от Hexlet (ru)
[]()

## Желательно знать

html/css  
javascript:

типы данных  
циклы  
функции обычного js и es6  
массивы и методы работы с ними. в детали можно не вдаваться, просто иметь в виду. минимум:
[filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter), [map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map), [sort](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort), [reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce), [every](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every), [some](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some), [find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find), [findindex](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findindex)  
[модули](https://learn.javascript.ru/modules): import, export  
!!!**объекты**  
!!!**события**  
!!!**классы**  
!!!**шаблонные строки**  
!!!**DOM**

план
читаешь js
делаешь простую аппку с парой компонентов
дробим задачи по opencharge, раздаем



## Простое приложение
### установка
```
git clone  
cd react-simple-app  
```

### структура

## Источники


[React.js: понятное руководство для начинающих](https://habr.com/ru/company/ruvds/blog/428077/)
[text](#adress)