## React

- [Компоненты](#Компоненты)
- [Свойства и состояния](#Свойства-и-состояния)
- [Ref](#Ref)
- [Children](#Children)
- [События](#События)
- [Деструктуризация](#Деструктуризация)
- [Жизненный цикл компонентов](#Жизненный-цикл-компонентов)
- [State Lifting](#State-Lifting)
- [Inverse data flow ](#Inverse-data-flow )
- [Тестирование](#Тестирование)
- [Анимация] (#Анимация)

## Компоненты
Реакт компонент можно представить как компонент пользовательского интерфейса. Это может быть кнопка, меню, виджет или даже целое приложение)

### Простые
Представляется в виде функций
```jsx
function Hero() {
  return (
    <div className="container">
        <img src="facebook.github.io/react/img/logo.svg">
        <h1>React</h1>
        <p>Библиотека для создания пользовательских интерфейсов</p>
    </div>
  )
}
```

Для того чтобы описывать состояния компонента, нам не достаточно использовать простой синтаксис в виде функции. Этот синтаксис придуман специально для простых компонентов к которых есть небольшая часть логики. Это так называемые Stateless компоненты. Но если мы хотим использовать состояния для наших компонентов, то нам придется использовать второй синтаксис компонентов с использованием ES6 классов.

В классе есть обязательный метод, который нужно реализовать. Это метод render. Он собственно и отвечает за то, как должен выглядеть наш компонент.

### Сложные
Представляются в виде объектов
```jsx
import React, { Component } from 'react'

class Article extends Component {
  constructor() {
  
  }

  render() {
  	return (
	
	)
  }
}
```

## Свойства и состояния
Свойства не меняются а состояния меняются

Свойства определяются от родителя к ребёнку, а состояния для каждого родителя индивидуально

Свойства отпределяют как будет выглядеть компонент при создании, а состояния про то как будет выглядеть компонент при изменении


## Props

## PropTypes
Для осуществления проверки типов свойств (props) компонента, вы можете определить специальное свойство класса компонента — propTypes
```jsx
class Greeting extends React.Component {
  render() {
    return (
      <h1>Hello, {this.props.name}</h1>
    );
  }
}

Greeting.propTypes = {
  name: React.PropTypes.string
};
```
В этом примере мы используем валидатор React.PropTypes.string. В случае, если в свойство будет передано невалидное значение — в консоли JavaScript будет показано предупреждение.

## Children

Существует ещё одно небольшое свойство, доступное в объекте props — children. Вы можете использовать его для передачи элементов вашим компонентам сверху, которые неизвестны самому компоненту, что позволяет образовывать компоненты друг из друга. Давайте посмотрим, как это выглядит при передаче строки текста в качестве дочернего элемента в компонент Search.

```jsx
class App extends Component {

  ...

  render() {
    const { searchTerm, list } = this.state;
    return (
      <div className="App">
        <Search
          value={searchTerm}
          onChange={this.onSearchChange}
        >
          Поиск
        </Search>
        <Table
          list={list}
          pattern={searchTerm}
          onDismiss={this.onDismiss}
        />
      </div>
    );
  }
}
```

Теперь компонент Search может деструктурировать свойство children из объекта props, а затем указать, где он должен отображаться.

```jsx
class Search extends Component {
  render() {
    const { value, onChange, children } = this.props;
    return (
      <form>
        {children} <input
          type="text"
          value={value}
          onChange={onChange}
        />
      </form>
    );
  }
}
```
## Ref
refs используются для получения ссылки на узел DOM (Document Object Model) или компонента в React. Если кратко, то Refs возвращает ссылку на элемент. Почти как в старые добрые getElementById.

Такая как:
1. Фокус элемента, выделение текста.
2. Анимации.
3. Интеграция с DOM библиотеками.


### Лучшие практики
Выносите функции для получения ref в методы

```jsx
getInputRef = (node) => {this._inputEl = node};

render(){
	return (
		<input ref={this.getInputRef}>
	)
}
```


### Когда их вообще надо использовать?
Желательно никогда. Только, если в них есть необходимость.
Такая как:
- Фокус элемента, выделение текста.
- Анимации.
- Интеграция с DOM библиотеками.



## События
Название события всегда задается в кемел кейсе, обработчик передается как функция.
Особенность функции при анонимном вызове в том что они выполняются в контексте глобального объекта, соответственно первая проблема которая стоит перед нами это задать контекст объекта в которм будет вызван обработчик (объектов классов). Есть два способа:
1. Использование стрелочной функции;
2. Явно забиндиться на объект.

```jsx
import React, { Component } from 'react'

class Sample extends Component {
	render() {
		<input 
			onPaste={this.handlePaste.bind(this)}
			onKeyPres={this.handleKeyPress}
		/>
	}

	handlePaste(event) {
		console.log('Paste')
	}

	handleKeyPress = event => {
		console.log('Press')
	}
}
```

У класса есть конструктор, чтобы сделать его инстанцируемым (иметь возможность создавать из него объекты). Конструктор может принимать аргументы, чтобы их можно было в качестве свойств назначить экземпляру класса. Кроме того, в классе можно определять функции. Поскольку функция связана с классом, она называется. “функция связана с классом, она называется методом. Часто он упоминается как метод класса.

Вы можете создать несколько экземпляров класса путём его вызова. Он похож на компонент класса ES6, который имеет объявление, но вы должны использовать его в другом месте для создания экземпляра.

В основном, когда вы объявляете компонен, он наследуется от другого компонента. Что значит “наследуется”? В объектно-ориентированном программировании у вас есть принцип наследования, который означает, что функциональные возможности могут передаваться из одного класса в другой.

Более конкретно — он наследует функциональность из класса Component. Класс Component используется для наследования базового класса ES6 в класс компонента ES6. Он имеет всю функциональность, которую имеет компонент в React”



## Хэндлер меняющий стейт
```jsx
class App extends Component {
	constructor (props) {
		super(props);
		this.state={ 
			name: 'Will',
		}
	}

	handleClick() {
		alert('this is:', this);
		setTimeout(() => {
			this.setState({ name: 'Bob' });
		}, 1000);
	}

	render() {
		return (
			<div>
				<div>{ this.state.name }</div>
				<div onClick={ this.handleClick.bind(this) }>Клик</div>
			</div>
		);
	}
}
```

### Изменение переменных в зависимости от стейта 
```jsx
import React, { Component } from 'react';
import './Checkbox.css';

class Checkbox extends Component {
  constructor(props) {
    super(props);
    this.handleChecked = this.handleChecked.bind(this);
    this.state = { checked: true };
  }

  handleChecked() {
		this.setState({ checked: !this.state.checked })
	}

	render() {
		var msg;
		if(this.state.checked) {
			msg = 'checked'
		} else {
			msg = 'unchecked'
		}
		return (
			<div>
				<input type="checkbox" onChange={ this.handleChecked} defaultChecked={ this.state.checked } />
				<h3> Checkbox is {msg} </h3>
			</div>
		);
	}
}

export default Checkbox;
```

### Обмен данными между компонентами
```jsx
import React, { Component } from 'react';
import './App.css';
import Button from './Button';
import Text from './Text';

class App extends Component {
	constructor (props) {
		super(props);
		this.handleClick = this.handleClick.bind(this);
		this.state={ 
			counter: 0,
		}
	}

	handleClick() {
		this.setState({ counter: ++this.state.counter})
	}

	render() {
		return (
			<div>
				<Button
					handler={this.handleClick}
				/>
				<Text
					counter={this.state.counter}
				/>
			</div>
		)
	}
}
```

```jsx
import React, { Component } from 'react';
import './Button.css';

class Button extends Component {
	render() {
		return (
			<button onClick={this.props.handler}>
				Жмакни!
			</button>
		);
	}
}

export default Button;
```

```jsx
import React, { Component } from 'react';
import './Text.css';

class Text extends Component {
	render() {
		return (
			<div>Уже нажали {this.props.counter} раз!</div>
		);
	}
}

export default Text;

```


## Деструктуризация
```javascript
const { name, title } = this.props
```

Вместо

```javascript
const title = this.props.title
const name = this.props.name
```


## Жизненный цикл компонентов
Методы жизненного цикла доступны исключительно для классовых компонент

### Инициализация
**constructor()**

**componentWillMount()**
Часто используется для полученя необходимых данных, например отправка запроса за нашей статьей на сервер

затем вызывается метод **render()** 
От должен быть чистым не содержать никаких сет стейтов, запросов к серверу. Единственная его задача это построить виртуальный DOM нашего компонента, после аостроения виртуального DOM будет построен реальный DOM

и вызовется метод **componentDidMount()** в котором мы можем реагировать на появление нашего компонента в реальном DOM по оканчанию его инициализации, например мы можем получить размеры или позиционирование DOM узла в которой он отобразился, мы можем подписаться на изменение данных или повесить собственные листнеры на соответствующие DOM элементы

### Обновление
Обновление может происходить по двум причинам:
1. Либо у нас изменился setState() компонента
2. Либо setState() произошёл у кого-то из наших родителей

Когда родительский компонент будет перестраивать все виртуальное дерево, реакт вызовет у компонента **componentWillReceiveProps(nextProps)** в которые передаст новые свойства, которыми строиться новый виртуальный DOM

**shouldComponentUpdate(nextProps, nextState)**

**сomponentWillUpdate(nextProps, nextState)**

**render()** 

**сomponentDidUpdate(prevProps, prevState)**


Один важный нюанс **componentWillReceiveProps()** будет вызываться исключительно если у нас кто-то перестраивается из родителей и у нас могли поменться просы, а **shouldComponentUpdate()** и **сomponentWillUpdate()** будут вызываться независимо от того перестривается у нас кто-то из родителей или у нас просто произошёл setState в нашем же компоненте


### Удаление
Последний этап жизни нашего компонента (когда наз компонент будет удаляться из виртуального, а затем и из реального DOM) **componentwillunmount** это прекрасное место чтобы все подчистить (подписки на события, изменения в даннах итд)


## State Lifting (вынесение стейта на уровень выше)

## Inverse data flow (изменение состояние родителя из дочернего компонента)

## Тестирование
В Реакте есть отличное возможность обойтесь при тестировании без участи в браузере так как у нас нет привязки к реальному DOM. У нас есть библиотека react, которя с троит наши виртуальные деревья (то есть иерархию наших компонент) и от отдельная библиотека react-doc, которая может взять нашу иерархию и построить по нему реальный DOM. Но тем не менее мы не обязаны все рендерить в реальное DOM-дерево  дл того чтобы протестировать логику приложения. Примерно 80-90% процентов вашего приложения можно покрыть UNIT тестами
### Jest

### Enzyme

## Анимация
Анимация в Реакте одна из самых не удобных вещей. В Реактовском подходе важно как выглядит компонент в состоянии **А** и в состоянии **B** (типа у меня поменялись данные и приведи DOM в соответствии с новыми данными). Cама Реакт вас абстрагирует от перехода. Но в случае с анимациями все наоборот, так как анимация это как раз переход между состояниями **А** и **B**, то делать их во многом не удобно. 

Тем не менее в для CSS Анимации используется библиотека ReactCSSTransitionGroup

Реакте по сути мы анимируем в **появления** / **скрытия** элементов. На самом деле вы все что угодно можете реализовать в терминях **появления** / **скрытия**

Для того, чтобы анимировать компонент нужно его обернуть в компонент ReactCSSTransitionGroup и передать несколько обязательных аргументов: это название и таймауты на появление/исчезновение

```
import ReactCSSTransitionGroup from 'react-addons-css-transition-group';
```

``` JSX
<ReactCSSTransitionGroup
    transitionName="example"
    transitionEnterTimeout={500}
    transitionLeaveTimeout={300}>
        ...
</ReactCSSTransitionGroup>
```

После обертки в DOM появятся классы

``` HTML
<div class="example-enter example-enter-active">...</div>
```

На которые можно написать CSS анимацию


``` CSS
.example-enter {
  opacity: 0.01;
}

.example-enter.example-enter-active {
  opacity: 1;
  transition: opacity 500ms ease-in;
}

.example-leave {
  opacity: 1;
}

.example-leave.example-leave-active {
  opacity: 0.01;
  transition: opacity 300ms ease-in;
}
```


## Примеры
- Поиск
- Фильтрация
- Добавление пунктов
