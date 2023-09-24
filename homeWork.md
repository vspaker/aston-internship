# Домашнее задание к уроку 6

## Решение типовых задач

### Задача 1

```
let promiseTwo = new Promise((resolve, reject) => {
  resolve('a');
}); // синхронная задача (объявляется переменная, ей присваивается промис)

promiseTwo // вызывается промис
  .then((res) => {
    return res + 'b'; // первый then => возвращает 'ab'
  })
  .then((res) => {
    return res + 'с'; // второй then => возвращает 'abc'
  })
  .finally((res) => {
    return res + '!!!!!!!'; // просто выполняется, данных из/в промиса не берет / не получает
  })
  .catch((res) => {
    return res + 'd'; // сюда не заходит
  })
  .then((res) => {
    console.log(res); // выводит в консоль 'abc'
  });
```

### Задача 2

```
function doSmth() {
  return Promise.resolve('123');
} // синхронная задача - объявляется функция

doSmth() // функция вызывается
  .then(function (a) {
    console.log('1', a); // выводит в консоль '1123'
    return a; // возвращает '123'
  })
  .then(function (b) {
    console.log('2', b); // выводит в консоль '2123'
    return Promise.reject('321'); // возвращает отклоненный промис со значением '321'
  })
  .catch(function (err) {
    console.log('3', err); // выводит в консоль '3321'
  })
  .then(function (c) {
    console.log('4', c); // сюда не заходит, и поэтому в консоль ничего не выводит (так я думал изначально)
    return c; // но проверил и понял, что после catch в следующий then все-таки заходит
  }); // и в консоль в этом месте выводится '4undefined'
```

## Написать функцию, которая будет проходить через массив целых чисел и выводить индекс каждого элемента с задержкой в 3 секунды

```
const data = [10, 12, 15, 21];
let counter = 0;

const getIndex = function () {
  if (counter < data.length) {
    console.log('Index of ' + data[counter] + ': ' + counter);
    counter++;
  }
  if (counter === data.length) {
    clearInterval(interval);
  }
};

const interval = setInterval(getIndex, 3000);
```
