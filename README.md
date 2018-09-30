## React

- [Компоненты](#Компоненты)
- [Свойства и состояния](#Свойства-и-состояния)
- [События](#События)
- [Деструктуризация](#Деструктуризация)
- [Жизненный цикл компонентов](#Жизненный-цикл-компонентов)
- [State Lifting](#State-Lifting)
- [Inverse data flow ](#Inverse-data-flow )

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

constructor(props)

componentWillMount()
Часто используется для полученя необходимых данных, например отправка запроса за нашей статьей на сервер

затем вызывается метод rennder() 
От должен быть чистым не содержать никаких сет стейтов, запросов к серверу. Единственная его задача это построить виртуальный DOM нашего компонента, после аостроения виртуального DOM будет построен реальный DOM

и вызовется метод componentDidMount() в котором мы можем реагировать на появление нашего компонента в реальном DOM по оканчанию его инициализации, например мы можем получить размеры или позиционирование DOM узла в которой он отобразился, мы можем подписаться на изменение данных или повесить собственные листнеры на соответствующие DOM элементы



## State Lifting (вынесение стейта на уровень выше)

## Inverse data flow (изменение состояние родителя из дочернего компонента)
