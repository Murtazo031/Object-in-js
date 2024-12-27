# Объекты в JavaScript

## Обзор
Объект в JavaScript — это самостоятельная сущность с свойствами и типом. Это один из самых важных типов данных в JavaScript, который позволяет хранить коллекции данных или более сложные сущности. Объекты состоят из пар ключ-значение, где ключи являются строками (или символами), а значения могут быть любого типа.

## Создание объекта
Существует несколько способов создания объектов в JavaScript:

### 1. Литерал объекта
```javascript
const obj = {
  key1: 'value1',
  key2: 42,
  key3: function() {
    console.log('Привет, мир!');
  }
};
```

### 2. Использование конструктора `Object`
```javascript
const obj = new Object();
obj.key1 = 'value1';
obj.key2 = 42;
obj.key3 = function() {
  console.log('Привет, мир!');
};
```

### 3. Использование фабричной функции
```javascript
function createPerson(name, age) {
  return {
    name,
    age,
    greet() {
      console.log(`Привет, меня зовут ${name} и мне ${age} лет.`);
    }
  };
}

const person = createPerson('Алиса', 30);
person.greet();
```

### 4. Использование функции-конструктора
```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
  this.greet = function() {
    console.log(`Привет, меня зовут ${this.name} и мне ${this.age} лет.`);
  };
}

const person = new Person('Боб', 25);
person.greet();
```

## Доступ к свойствам объекта

### Точечная нотация
```javascript
console.log(obj.key1); // 'value1'
```

### Квадратные скобки
```javascript
console.log(obj['key1']); // 'value1'
```

## Изменение свойств объекта
Вы можете добавлять, обновлять или удалять свойства объекта.

### Добавление/обновление свойств
```javascript
obj.key4 = 'newValue';
obj.key1 = 'updatedValue';
```

### Удаление свойств
```javascript
delete obj.key2;
```

## Основные методы и операции

### Перебор свойств объекта
Используйте цикл `for...in` для итерации по перечисляемым свойствам объекта:
```javascript
for (const key in obj) {
  if (obj[key]) {
    console.log(`${key}: ${obj[key]}`);
  }
}
```

### Методы объекта

- **`Object.keys(obj)`**: Возвращает массив ключей объекта.
- **`Object.values(obj)`**: Возвращает массив значений объекта.
- **`Object.entries(obj)`**: Возвращает массив пар ключ-значение.

Пример:
```javascript
const obj = { key1: 'value1', key2: 42 };
console.log(Object.keys(obj)); // ['key1', 'key2']
console.log(Object.values(obj)); // ['value1', 42]
console.log(Object.entries(obj)); // [['key1', 'value1'], ['key2', 42]]
```

### Проверка существования свойства
- **Оператор `in`**:
```javascript
console.log('key1' in obj); // true
```
## Прототипы объектов и наследование
Объекты в JavaScript имеют прототип, который тоже является объектом. Прототип предоставляет механизм для наследования.

### Установка прототипа
```javascript
const parent = {
  greet() {
    console.log('Привет от родителя!');
  }
};

const child = Object.create(parent);
child.sayHi = function() {
  console.log('Привет от ребенка!');
};

child.greet(); // 'Привет от родителя!'
child.sayHi(); // 'Привет от ребенка!'
```

### Изменение прототипа
```javascript
Object.setPrototypeOf(child, anotherPrototype);
```

## Заключение
Объекты в JavaScript являются универсальными и лежат в основе многих возможностей языка. Понимание того, как создавать, получать доступ и манипулировать объектами, крайне важно для эффективного программирования на JavaScript.

