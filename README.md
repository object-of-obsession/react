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
```javascript
import React, { Component } from 'react'

class Article extends Component {
  constructor() {
  
  }

  render() {
  
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

```javascript
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

## Хэндлер меняющий стейт
```javascript
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


### Обмен данными между компонентами
```javascript
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

```javascript
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

```javascript
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

## State Lifting (вынесение стейта на уровень выше)

## Inverse data flow (изменение состояние родителя из дочернего компонента)
