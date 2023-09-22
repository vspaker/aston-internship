# Домашнее задание к уроку 5

## Алгоритмы сортировок (некоторые)

- сортировка слиянием (Merge Sort)
- сортировка вставками (Insertion Sort)
- быстрая сортировка Хоара (Quick Sort)
- сортировка Шэлла (Shell Sort)
- сортировка подсчетом (Counting Sort)
- гномья сортировка (Gnome Sort)
- пузырьковая сортировка (Bubble Sort)

## Создание объекта Person и Person2 с унаследованным методом

Способ 1:

```
function Person() {
  this.logInfo = function () {
    console.log('info');
  };
}

const Person2 = new Person();
```

Способ 2:

```
const Person = {
  logInfo: function () {
    console.log('info');
  },
};

const Person2 = {
  __proto__: Person,
};
```

## Создание класса-наследника PersonThree

```
class Person {
  constructor(name) {
    this.name = name;
  }
  logInfo() {
    console.log('info');
  }
}

class PersonThree extends Person {
  super() {}
  get name() {
    return this._name;
  }
  set name(value) {
    this._name = value;
  }
}

const vasya = new PersonThree('Vasya');
```

## БОНУС-задание

Пишем функцию, которая вернет массив с первой парой чисел, сумма которых равна `total`:

```
const arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
const total = 13;
// result = [4, 9]

const firstSum = (arr, total) => {
  for (let i = 0; i <= arr.length; i++) {
    let firstNumber = arr[i];
    for (let j = i + 1; j <= arr.length; j++) {
      if (arr[i] + arr[j] == total) {
        console.log([arr[i], arr[j]]);
        return [arr[i], arr[j]];
      }
    }
  }
};

firstSum(arr, total);
```

Сложность алгоритма: `O(n^2)` (лучше избегать)

## Вопросы

1. Назвать расшифровку каждой буквы в SOLID
2. Что делает ключевое слово `super`
