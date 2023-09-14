# Домашнее задание к уроку 3

## Создание объекта

### Способ 1
```
const counter = {}
```

### Способ 2
```
const counter = new Object()
```

### Способ 3 
```
const counter = Object.create(Object.prototype)
```

### Способ 4 
```
const counter = Object.assign({}, new Object())
```

## Копирование объекта

### Способ 1
Метод деструктуризации.
```
const counterCopy = { ...counter }
```
### Способ 2
Метод `Object.assign()`
```
const counterCopy = Object.assign(counter)
```
### Способ 3
Метод `Object.create()`
```
const counterCopy = Object.create(counter)
```
### Способ 4
Метод JSON.parse / JSON.stringify
```
const counterCopy = JSON.parse(JSON.stringify(counter))
```
### Способ 5
Метод `structuredClone()`
```
const counterCopy = structuredClone(counter)
```
### Способ 6
Написание собственной функции вроде этой:
```
function copyObj(obj) {
  const copied = {};
  for (i in obj) copied[i] = typeof obj[i] === 'object' ? copyObj(obj[i]) : obj[i];
  return copied;
}
const counterCopy = copyObj(counter)
```
## Создание функций
Способы:
- function declaration
- function expression
- new Function
- arrow function
- IIFE

## Вопросы

1. Назвать метод массива, который определяет, содержится ли в нем указанный элемент ([].includes)
2. В чем особенность стрелочных функций с точки зрения лексического окружения (this берется снаружи)
3. Что такое замыкание (функция в совокупности с её лексическим окружением)