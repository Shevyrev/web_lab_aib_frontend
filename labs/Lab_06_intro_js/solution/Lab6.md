**Задание 1. Работа с переменными**

// Создаем переменную apple со значением 10
let apple = 10;

// Выводим эту переменную с помощью операторов: alert(); console.log();
alert(apple);
console.log(apple);

// Создаем переменную condition, значение должно быть случайной строкой
let condition = "случайная строка";

// Посмотрим, что будет при выполнении операции console.log('Good game is ' + condition)
console.log('Good game is ' + condition);

**Задание 2. Магия конкатенации**

// Создаем произвольную целочисленную переменную
let someInt = 5;

// Создаем строковую переменную, которая будет со значением '100'
let someText = '100';

// Создаем произвольную булевую переменную
let someBool = true;

// Делаем конкатенацию всех этих переменных, выводим в консоль каждую
console.log(someText + someInt);
console.log(someText + someBool);
console.log(someInt + someBool);

**Задание 3. Работа с массивами**

// Создаем массив длинной 10 элементов
let arr = new Array(10);

// Заполняем этот массив рандомными числами с помощью оператора for
for(let i=0; i<arr.length; i++) {
    arr[i] = Math.random();
}

// Используя метод filter убираем из массива числа меньше 0
let filteredArr = arr.filter(num => num >= 0);

**Задание 4. Работа с функциями**

// Создаем функцию, которая будет возвращать случайное число.
function getRandomNumber() {
    return Math.random();
}

// Проверяем работу функции и выводим в консоль
console.log(getRandomNumber());

// Создаем функцию, которая будет принимать массив в качестве первого параметра, а в качестве второго параметра число.
function multiplyArray(arr, num) {
    return arr.map(element => element * num);
}

// Создаем анонимную функцию которая будет генерировать случайное слово, выводим в консоль сгенерированное слово
let generateWord = function() {
    let text = "";
    let possible = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz";
    for (let i = 0; i < 5; i++)
        text += possible.charAt(Math.floor(Math.random() * possible.length));
    return text;
};

console.log(generateWord());


**Работа с объектами**

// Создаем простой пустой объект
let obj = {};

// Добавляем поля: firstName, surname, patronymic, birthday, hobby и group
obj.firstName = "Иван";
obj.surname = "Иванов";
obj.patronymic = "Иванович";
obj.birthday = "01.01.2000";
obj.hobby = "футбол";
obj.group = "101";

// Добавляем метод, который будет возвращать ФИО, год рождения, хобби и возраст
obj.getInfo = function() {
    let currentYear = new Date().getFullYear();
    let age = currentYear - this.birthday.split(".")[2];
    return this.surname + " " + this.firstName + " " + this.patronymic + ", " + this.birthday + ", " + this.hobby + ", " + age;
};

// Вызываем этот метод и выводим результат через alert
alert(obj.getInfo());

// Создаем объект, где будут храниться зарплаты 10 сотрудников по правилу: ключ - фамилия, а значение - зарплата
let salaries = {
    "Иванов": 1000,
    "Петров": 1200,
    "Сидоров": 1100,
};

// Посчитываем общую зарплату сотрудников
let totalSalary = 0;
for(let key in salaries) {
    totalSalary += salaries[key];
}
console.log(totalSalary);