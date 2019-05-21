структура (драфт)

# React.js

Прежде чем мы приступим к делу, скажем пару слов о том, почему React можно считать наилучшей альтернативой среди средств для разработки веб-интерфейсов.


### **Декларативный подход к описанию интерфейсов**

React-разработка заключается в описании того, что нужно вывести на страницу (а не в составлении инструкций для браузера, посвящённых тому, как это делать). Это, кроме прочего, означает значительное сокращение объёмов шаблонного кода.


### **Чёткий синтаксис**

В React применяется синтаксис JSX, который **воспринимается** как обычный HTML (но не является ни строкой, ни HTML). Он максимально ясно описывает внешний вид UI, одновременно включая в себя всю мощь JavaScript. Вот как это выглядит:

```
const element = <h1>Hello, world!</h1>;

const Greetings = ({ firstName }) => (
   <div>Hi, {firstName}</div> // в JSX фигурные скобки используются для выражений
);
```
Подробнее о [выражениях](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Expressions).


### **Особенности механизма привязки данных**

В React используется односторонняя привязка данных: от родительского элемента к дочерним. Это — большой плюс: вы всегда знаете что привело к изменению состояния приложения. Подобный подход к привязке данных значительно упрощает отладку.


### **Механики из графичеких редакторов**

Компонентный подход React похож на компоненты Figma или символы Sketch. Компоненты можно вкладывать друг в друга и переопределять стили.


### **Легкий старт**

Кривая обучения — это важный фактор, который нужно учитывать при выборе UI-фреймворка. В этой связи надо отметить, что в React имеется меньше абстракций, чем, скажем, в Angular. Для того, чтобы разобраться, потребуется некоторое время, но приступить к работе можно **очень и очень быстро**.


# Материалы по react.js  

Официальная документация: [en](https://reactjs.org/) [ru](https://ru.reactjs.org/)  

[Шпаргалка по библиотеке](https://devhints.io/react) для версий 15 и 16 (en)  
  *кратко изложены методы и подходы в виде сниппетов кода*

[Видео](https://youtu.be/gRs7NbEZMCg) основы React от создателя Framer (en)  
  *нет описания*

[Книга-курс](https://maxfarseer.gitbooks.io/react-course-ru-v2/content/) для начинающих (ru)  
  *пошаговое создание небольшого приложения новостей (добавление, просмотр "подробнее")*

[Видео-курс](https://scrimba.com/playlist/p7P5Hd) с практикой (en)  
  *пошаговое создание to do app*

Курс Евгения Родионова: [этап 1](https://erodionov.ru/courses/react/9wO7ihaBIk), [этап 2](https://erodionov.ru/courses/react/rHAh7OXEFL), [этап 3](https://erodionov.ru/courses/react/tHKYMIR4QG) (ru)  
  *нет описания*


# Ссылки js

[Опыт программирования на javascript](https://kaineer.gitbooks.io/coding-in-javascript/)  
[Базовый курс](https://code-basics.ru/languages/javascript) от Hexlet (ru)


# Необходимые знания

html, css. javascript:

- Типы данных [mdn](https://developer.mozilla.org/ru/docs/Web/JavaScript/Data_structures), [learnjs](http://learn.javascript.ru/types-intro)  
- Массивы [mdn](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays)
Методы работы с массивами: [filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter), [map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map), [reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce), [find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find), библиотека [lodash](https://lodash.com/)  
- Шаблонные строки  [mdn](hhttps://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/template_strings), [learnjs](https://learn.javascript.ru/es-string) (обратите внимание на \`**кавычки**\`)  
- Циклы [mdn](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration), [learnjs](https://learn.javascript.ru/while-for)  
- Функции [mdn](https://developer.mozilla.org/ru/docs/Web/JavaScript/Guide/Functions) (обратите внимание на краткую запись =>, скоуп)
- Модули [import, export](https://learn.javascript.ru/modules), модули [в рамках React](https://www.geeksforgeeks.org/reactjs-importing-exporting/), [шпаргалка](https://stackoverflow.com/questions/36795819/when-should-i-use-curly-braces-for-es6-import/36796281#36796281) на stackoverflow  
- Объекты [mdn](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)  
- События [mdn](https://developer.mozilla.org/en-US/docs/Web/API/Event). Что такое [preventDefault](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault), [stopPropagation](https://developer.mozilla.org/en-US/docs/Web/API/Event/stopPropagation)  
- !!!**классы** в реакте (?)  
- DOM в React, [как работает](https://reactjs.org/docs/faq-internals.html). **!!!** [картинка1](https://images.app.goo.gl/Ppg7ZQA2o3GYZ3J38), [картинка2](https://images.app.goo.gl/QwodrmEwwf3Mv2ye6), [картинка3 - самая удачная](https://images.app.goo.gl/qr4ewDahPrLmiQ559)  
- LifeCycle [документация](https://reactjs.org/docs/state-and-lifecycle.html), **!!!** [схема работы](https://medium.com/@it_root.corp/react-component-life-cycle-bbe583ca4cb), [схема работы](https://tproger.ru/translations/react-after-learning-basics/), [схема работы](https://habr.com/ru/post/358090/)  
- Routing **!!!** [схема работы](http://prgssr.ru/development/pogruzhenie-v-react-router.html), [схема работы](https://getinstance.info/articles/react/learning-react-router/), [тутор](https://habr.com/ru/post/329996/)


# Простое приложение  

### **Установка**  

Для удобства в репозитории уже залит `create-react-app`. Необходимо выполнить две команды:
```
git clone .. ??
cd .. ??
npm i  ??
npm start  ??
```
[Полное руководство](https://github.com/facebook/create-react-app) по установке `create-react-app`  
Если все сделано правильно, на экране появится анимированное лого React.
<!-- ```
npx create-react-app my-app  
cd create-react-app  
npm i  
npm start  
```
*[npx](https://medium.com/devschacht/introducing-npx-an-npm-package-runner-a72a658cd9e6) — утилита для запуска npm-пакетов*   -->


### **Cтруктура**  
```
app
├── README.md
├── node_modules
├── package.json
├── .gitignore
├── public                //
│   ├── favicon.ico
│   ├── index.html        // в этом файле будет рендериться приложение
│   └── manifest.json     // информация о приложении
└── src
    ├── App.css           // стили компонента App
    ├── App.js            // файл компонента App
    ├── App.test.js       // тесты компонента App
    ├── index.css         // стили страницы index.html
    ├── index.js          // файл с инструкцией рендеринга
    ├── logo.svg          // графика, используемая в приложении
    └── serviceWorker.js  // файл сервис-воркера
```

Почитать про [манифест](https://developer.mozilla.org/en-US/docs/Web/Manifest), [сервис-воркеры](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API/Using_Service_Workers)


### **Как тут всё работает, кратко**

<!-- Приложение смотрит компонент `App`, закидывая в него стили `App.css` и графику `logo.svg`. Затем файл `index.js` смотрит, что мы хотим отрендерить `App`   -->
<!-- ![Image alt](assets_guide/1-create-react-app-structure.png) -->
<!-- ![Image alt](assets_guide/pic2.png) -->

В `index.js` описаны компоненты, которые необходимо отрендерить. В нашем случае это единственный `App`, но их может быть больше. Если импорт описан корректно, приложение смотрит внутрь каждого компонента и собирает сопутствующие файлы, для `App` это стили `App.css`, графика `logo.svg`. Далее метод `getElementById` находит контейнер с `id="root"` в `public/index.html` и рендерит в html-файле компонент `App`, попутно применяя к `index.html` стили `index.css`  

![create-react-app-structure](assets_guide/1-create-react-app-structure.png)  

### **Файлы**

**index.js**
```jsx
                                                  // импорт
import React from 'react';                        // React
import ReactDOM from 'react-dom';                 // ReactDOM
import './index.css';                             // стили для index.html
import App from './App';                          // компонент App
import * as serviceWorker from './serviceWorker'; // сервис-воркер

// метод render модуля ReactDOM, на вход (в круглых скобках) принимает два аргумента:  
// компонент App и место, где его нужно отрендерить*
ReactDOM.render(<App />, document.getElementById('root'));
```
\* если не импортировать модуль ```ReactDOM```, метод ```render``` не сработает, то же касается файла стилей. **Всегда следите за импортами**


**index.html**
```html
...
<div id="root"></div> // здесь React рендерит компонент App
...
```

**App.js**
```jsx
                                  // импорт
import React from 'react';        // React, нужен для создания функционального компонента и читения JSX
import logo from './logo.svg';    // графика
import './App.css';               // стили компонента

// компонент App, функциональный*
function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App; // экспорт компонента App
```
\* в React компоненты делятся на функциональные и классовые, [почитать](https://reactjs.org/docs/components-and-props.html)

Обратите внимание, что в теле `return` есть один общий `div` с `className="App"`, в него завернуто тело компонента. Дело в том, что в React функция может вернуть только один `div` — **ТРЕБУЕТ УТОЧНЕНИЯ РАЗРАБОТЧИКА**

Содержимое css файлов вам знакомо, сервис-воркеры не понадобятся.

# Практика  

Установите `react dev tools` для вашего браузера.

В нашей обучалке мы закастомим `create-react-app`:
1. изменим структуру файлов
2. добавим несколько компонентов
3. научимся стилизовать компоненты
4. настроим роутинг

Этот флоу похож на некоторые моменты работы дизайнера в графических редакторах. Последний пункт поможет связывать разные страницы в рамках одной задачи.


### **1. Меняем структуру**

Компонентный подход — мощная парадигма, используемая в разработке и в дизайне. Если взглянуть на работу в Sketch, каждый символ лежит на своем артборде (в React символ = компонент). Попоробуем применить этот подход в проекте. Дефолтный `create-react-app` складывает файлы в `/src`. Если компонентов будет больше, поддержка затруднится.  

Вытащим комопнент `App.js`, `App.css`, `App.test.js` в свою папку c названием `App`. Получим структуру
внутри `src`:
```
└── src
    └── App
        ├── App.css
        ├── App.js
        └── App.test.js
    ├── index.css
    ├── index.js
    ├── logo.svg
    └── serviceWorker.js
```

Если вы успели посмотреть, страница браузера/консоль/терминал выдают ошибку:
```
Failed to compile.
...
Error: ENOENT: no such file or directory / can't resolve path ...
```
Мы переместили файлы, но не изменили пути импорта модулей. Без исправления билд не запустится.  
Посомтрим в `index.js`. Он использует перемещённый компонент `App`. 
```jsx
import App from './App';
```
`./` означает, что `index.js` будет искать компонент в `src` (в той папке, где находится сам), а нам нужна папка с имененем компонента `App`:
```jsx
import App from './App/App';
```
Есть еще ошибка, связанная с svg-файлом. Попробуйте разобраться в чем дело.  

Все новые компоненты будем складывать по папкам с именем компонента в `/src`, имя папки должно начинаться с большой буквы, так React поймет, что это хранилище компонета. Если все ок, приступаем ко второму шагу.


### **2. Добавим компоненты**

Пока у нас есть единственный функциональный компонент `App`. Добавим еще один компонент, но [классовый](https://reactjs.org/docs/react-component.html). Чтобы не возиться с версткой, возьмем тег \<p> и его содержимое из `App` и сделаем его компонентом.
```html
<p>
  Edit <code>src/App.js</code> and save to reload.
</p>
```

Первым делом нужна папка с имененем компонента, я назвал его Instruction.

<!-- # Источники

[React.js: понятное руководство для начинающих](https://habr.com/ru/company/ruvds/blog/428077/)
[text](#adress) -->