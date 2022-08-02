## Вопросы на собеседовании frontend JavaScript React разработчика в 2022 году

Здесь собраны **актуальные** вопросы, часто встречающиеся на собеседовании frontend JS React разработчика.
Список вопросов постоянно актуализируется. Прошу принимать участие!

#### JavaScript

<details><summary>Что такое ООП</summary>
<br/>

Общий принцип ООП заключается в разделении задач и ответственностей по сущностям.
Сущности создаются в коде как объекты. При этом каждая из них объединяет некую информацию (*свойства*) и действия (*методы*), которые может выполнять.

Ключевые принципы ООП:
1. **Наследование** – это возможность создавать классы на основе других классов. С помощью этого принципа можно определять родительский класс (с нужными свойствами и методами), а затем дочерний класс, который будет наследовать от родителя все свойства и методы.
2. **Инкапсуляция** — это размещение в одном компоненте данных и методов, которые с ними работают. Обеспечивает механизм сокрытия, позволяющий разграничивать доступ к различным компонентам программы.
3. **Абстракция** — это использование только тех характеристик объекта, которые с достаточной точностью представляют его в данной системе.
4. **Полиморфизм** означает «множество форм» и отражает способность метода возвращать разные значения, согласно определённым условиям.

</details>

<details><summary>Какие типы данных есть в JS</summary>
<br/>

**Примитивы** (примитивный тип данных) - это данные, которые не являются объектом и не имеют методов. Все примитивы неизменяемы (*immutable*).

В JS есть 7 примитивных типов данных:

1. **number** - используется как для целых, так и для дробных чисел.
Существуют специальные числовые значения `Infinity` (бесконечность) и `NaN` (not a number), также принадлежащие типу `number`.
2. **bigint** - содержит числа больше, чем 2<sup>53</sup> (или меньше, чем -2<sup>53</sup>), которые не может содержать тип `number`.
Чтобы создать значение типа `bigint`, необходимо добавить `n` в конец числового литерала.
3. **string** - строка.
4. **boolean** - логический тип данных, который может содержать одно из двух значений `true` или `false`.
5. **null** - тип данных, состоящий из единственного значения `null`, которое имеет смысл "*ничего*". 
Результат `typeof null == "object"` – это официально признанная ошибка в языке, которая сохраняется для совместимости.
6. **undefined** - тип данных, состоящий из одного единственного значения `undefined`, которое имеет смысл "*значение не присвоено*".
7. **symbol** - представляет собой уникальный идентификатор.

За исключением `null` и `undefined`, все примитивные значения имеют объектный аналог, который оборачивает значение примитивного типа: `String`, `Number`, `Boolean`, `Symbol`, которые, в свою очередь, имеют соответствующие методы. 

[Подробнее](https://developer.mozilla.org/ru/docs/Glossary/Primitive)

8. **object** - используется для коллекций данных и для объявления более сложных сущностей (функции, массивы и т.д.).

`object` относится к ссылочному (*reference*) типу данных и содержит ссылку на ячейку в памяти, где непосредственно записаны данные. Эти данные, в отличие от примитивов, изменяемы (*mutable*).

[Подробнее](https://learn.javascript.ru/object)

</details>

<details><summary>Как можно клонировать объект</summary>
<br/>

1. Использовать метод `Object.assign()`:
```javascript
const cloneObj = Object.assign({}, originObj)
```
2. Использовать `spread` оператор `...`:
```javascript
const cloneObj = {...originObj}
```

Но эти подходы не позволяют выполнить глубокое клонирование. Поэтому, если нужно клонировать объект со вложенными объектами, можно:

3. Использовать метод какой-либо библиотеки, например `_.cloneDeep()` из JavaScript-библиотеки `lodash`
4. Cделать это средствами встроенного объекта JSON:
```javascript
const cloneObj = JSON.parse(JSON.stringify(originObj))
```

</details>

<details><summary>Как проверить, является ли объект массивом</summary>
<br/>

Для этого можно использовать встроенный метод `Array.isArray()`

</details>

<details><summary>В чем разница между операторами == и ===</summary>
<br/>

Разница между оператором `==` (абстрактное или нестрогое равенство) и оператором `===` (строгое равенство) состоит в том, что первый сравнивает значения после их преобразования или приведения к одному типу, а второй — без такого преобразования.

</details>

<details><summary>Для чего нужен двойной оператор логического отрицания !!</summary>
<br/>

Двойной восклицательный знак позволяет конвертировать любое выражение в логическое значение.
Если выражение, с точки зрения JS, истинно — после обработки его двойным восклицательным знаком будет возвращено `true`. В противном случае будет возвращено `false`.
```javascript
!!null            // false
!!undefined       // false
!!false           // false
!!true            // true
!!""              // false
!!"string"        // true
!!0               // false
!!1               // true
!!{}              // true
!![]              // true
```

</details>

<details><summary>Что такое Контекст выполнения</summary>
<br/>

**Контекст выполнения** (*Execution context*) – специальная внутренняя структура данных, которая содержит информацию, необходимую для отслеживания хода выполнения связанного с ним кода. 

Виды контекста в JavaScript:
1. Глобальный контекст (*Global execution context*), с которого начинается исполнение скрипта
2. Контекст выполнения вызова (*Calling execution context*) - начинается с момента входа в тело функции

Один вызов функции имеет ровно один контекст выполнения, связанный с ним. При этом в  каждый момент времени в Javascript активен только один контекст выполнения.
Поэтому Javascript называют *однопоточным*, имея ввиду, что только одна инструкция исполняется в каждый момент времени.

Браузеры отслеживают контекст выполнения с помощью *стека*.

**Стек выполнения** (*стек вызовов*, *call stack*) - это структура данных, которая используется для хранения контекстов выполнения, создаваемых в ходе работы кода. 
Стек выполнения действует по принципу “первый вошедший уходит последним” (Last In First Out, LIFO), то есть последний объект, добавленный на стек, окажется на его вершине и будет предоставлен первым при извлечении объекта. Добавлять объекты можно только на вершину стека, и удалять их можно только с вершины.

Активный контекст выполнения находится на вершине стека. Он снимается со стека, когда выполнение кода активного контекста завершается, и выполнение продолжается в коде предыдущего контекста, который перемещается на вершину стека.

Каждый контекст выполнения содержит в себе следующие компоненты состояния:
- `LexicalEnvironment` (*Лексическое окружение*), которое содержит переменные и функции и используется для сопоставления идентификаторов (ссылок) внутри контекста выполнения (т.е. идентификаторы в лексическом окружении — это имена сущностей, таких как переменные и функции)
- `VariableEnvironment` (*Окружение переменных*) - таблица, связанная с лексическим окружением, в которой в качестве ключей занесены все имена переменных, используемые в инструкциях объявления переменных.
- `ThisBinding` -  значение `this`, связанное с этим контекстом выполнения.

</details>

<details><summary>Что такое Поднятие</summary>
<br/>

**Поднятие** (*Hoisting*) - это механизм выделения памяти для объявлений функций и переменных в стадии создания (*creation phase*) контекста выполнения (*execution context*).

JavaScript *поднимает* ***только*** объявления, а не инициализацию.

</details>

<details><summary>Различия между let, const и var</summary>
<br/>

|                                       | **var**                       | **let** | **const** |
|--------------------------------------:|-------------------------------|---------|-----------|
| **область видимости**                 | функциональная                | блочная | блочная   |
| **можно объявлять заново**            | да                            | нет     | нет       |
| **можно обновлять**                   | да                            | да      | нет       |
| **поднимается (hoisting)**            | да                            | да      | да        |
| **инициализируется при поднятии**     | как `undefined`               | нет     | нет       |
| **можно объявлять без инициализации** | да                            | да      | нет       |

</details>

<details><summary>Что такое Область видимости</summary>
<br/>

**Область видимости** (*Scope*) — это набор правил для хранения и поиска переменных и функций по их идентификатору. Область видимости определяет их доступность в текущем контексте выполнения.

Области видимости могут быть многоуровневыми, при этом действует правило: дочерние области имеют доступ к родительским областям, но не наоборот.

В процессе движения от дочернего окружения к родительскому, области видимости складываются в *цепочку областей видимости* (*Scope Chain*).

Типы областей видимости:
1. **Глобальная область видимости** — переменные и функции, объявленные в *глобальном контексте выполнения*, имеют глобальную область видимости и доступны из любого места в коде (посредством обращения к соответствующему свойству глобального объекта `window`).
2. **Локальные области видимости:**
- **Функциональная область видимости** (область видимости функции) — переменные, функции и параметры, объявленные внутри функции, доступны только внутри этой функции.
- **Блочная область видимости** — переменные (объявленные с помощью ключевых слов `let` и `const`) внутри блока `{ }`, доступны только внутри него.
3. **Модульная область видимости** - частные переменные (которые не экспортируются) доступны только внутри модуля (*ES6 modules*).

Область видимости — это механизм *инкапсуляции* для блоков кода, функций и модулей.

</details>

<details><summary>Что такое Лексическое окружение</summary>
<br/>

**Лексическое окружение** - это специальный внутренний объект `LexicalEnvironment`, который создается при ***вызове*** функции. Все аргументы, локальные функции и переменные являются свойствами этого объекта. Процесс инициализации выполняется в том же порядке, что и для *глобального объекта*, который, является частным случаем лексического окружения.

Лексическое окружение состоит из таблицы символов и ссылки на *внешнее лексическое окружение* (`null` для глобального окружения, т.к. глобальное окружение не имеет внешнего окружения):

1. `Environment Record` (*record*) – объект, в котором как свойства хранятся значения всех локальных переменных (а также некоторая другая информация, такая как значение `this`).
2. `[[Scope]]` (*outer*) – ссылка на *внешнее лексическое окружение* – то есть то, которое соответствует коду снаружи от текущих фигурных скобок.

Объекты `LexicalEnvironment` и `Scope` являются внутренними служебными объектами, они скрыты от прямого доступа.

Каждый *контекст выполнения* имеет лексическое окружение, которое  хранит переменные и их значения, а также имеет ссылку на *внешнее окружение*. 
Лексическим окружением может быть:
- Глобальное окружение (*Global environment*)
- Окружение модуля
- Окружение функции (созданное в процессе её вызова).

Новое лексическое окружение создаётся каждый раз при исполнении такого кода (например, при вызове функции).

</details>

<details><summary>Способы объявления функций</summary>
<br/>

1. **Function Declaration** (*объявление функции*) - "классическое" объявление функции. Объявляется отдельной конструкцией в основном потоке кода посредством служебного слова `function`. 
```javascript
function sum(a, b) {
  return a + b;
}
```
2. **Function Expression** (*функциональное выражение*) - функция, созданная внутри другого выражения или синтаксической конструкции. Такая функция может быть *анонимной*.
```javascript
let sum = function(a, b) {
  return a + b;
}
```
3. **Arrow Function** (*стрелочная функция*) - имеет более короткий синтаксис и особую лексику `this`. Стрелочные функции *анонимны*.
```javascript
let func = (args) => expression
```
4. **IIFE** (*Immediately Invoked Function Expression*, *немедленно вызываемое функциональное выражение*) - способ функционального выражения, не засоряющего внешнюю область видимости, т.к. функция обрабатывается и вызывается сразу, когда поток выполнения достигает ее.
Первая окружающая пара `( )` делает функцию выражением, а вторая `()` выполняет функцию:
```javascript
(function foo(){ .. })()
```
или
```javascript
(function foo(){ .. }())
```

Важное отличие *Function Declaration* от *Function Expression* в том, ***когда*** создается функция движком JS.
- *Function Declaration* обрабатываются перед выполнением блока кода. Они видны во всём блоке.
- *Function Expression* создаются только когда поток выполнения достигает их.

Анонимные функции чаще всего используются в качестве функций обратных вызовов (*callback*), но лучшей практикой считается использование именованных функций.

[Подробнее](https://learn.javascript.ru/function-expressions#function-expression-v-sravnenii-s-function-declaration)

</details> 

<details><summary>Особенности стрелочных функций</summary>
<br/>

1. Более лаконичный (краткий) синтаксис
2. Отсутствие псевдомассива `arguments`. 
Решается путём сочетания стрелочной функции с `rest` оператором:
```javascript
const foo = (...props) => console.log(props)
 ```
3. *Лексический* `this`, значение которого наследуются из `this` окружающего контекста.
4. Не могут использоваться:
- в качестве *конструкторов* (с оператором `new`)
- для создания *генераторов*
5. Всегда ***анонимны***, в результате чего:
- нельзя отследить имя функции или точный номер строки, где произошла ошибка
- нет самопривязки, т.е. функция не может ссылаться на саму себя (например, рекурсия, обработчик событий, который необходимо отменить, не сработают)

[Подробнее](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

</details> 

<details><summary>Что такое this</summary>
<br/>

`this` — это ключевое слово, которое имеет значение, зависящее от *контекста*, в котором оно применяется.

В *глобальном контексте выполнения* (за пределами каких-либо функций) `this` ссылается на *глобальный объект* вне зависимости от режима (строгий или нестрогий).

В пределах функции значение `this` зависит от того, каким образом вызвана функция.

Когда функция вызывается как метод объекта, используемое в этой функции ключевое слово `this` принимает значение объекта, по отношению к которому вызван метод.

В стрелочных функциях, `this` привязан к окружению, в котором была создана функция.

Когда функция используется как обработчик событий, `this` присваивается элементу с которого начинается событие.

[Подробнее](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Operators/this)

</details>

<details><summary>Что такое замыкание</summary>
<br/>

</details>

<details><summary>Как работает прототипное наследование</summary>
<br/>

В JS объекты имеют специальное скрытое свойство `[[Prototype]]`, которое либо равно `null`, либо ссылается на другой объект.

При обращении к свойству или методу объекта сначала происходит поиск этого свойства у самого объекта. 
В случае неудачи поиск перенаправляется в его прототип, затем в прототип прототипа и так далее, пока искомое свойство не будет найдено, либо пока не закончится цепочка прототипов.

</details> 

<details><summary>Как работают события в JS</summary>
<br/>

Стандарт [DOM Events](https://www.w3.org/TR/DOM-Level-3-Events/) описывает 3 фазы прохода события:

1. **Фаза погружения** (*capturing phase*) – событие сначала идёт сверху вниз, от корня документа (объекта `window`) к самому глубоко вложенному элементу, на котором оно произошло `event.target`.
2. **Фаза цели** (*target phase*) – событие достигло целевого(исходного) элемента `event.target`.
3. **Фаза всплытия** (*bubbling stage*) – событие всплывает до корневого элемента.

По умолчания события ловятся на стадии всплытия. Чтобы поймать событие на стадии погружения, нужно использовать третий аргумент обработчика событий `capture` со значением `true`:
```javascript
elem.addEventListener(event, callback, true)
```

[Подробнее](https://learn.javascript.ru/bubbling-and-capturing)

</details> 

<details><summary>В чем разница между event.target и event.currentTarget</summary>
<br/>

- `event.target` – самый глубокий элемент, на котором ***произошло*** событие.
- `event.currentTarget` – элемент, на котором ***навешен*** обработчик произошедшего события.

</details>

<details><summary>Как остановить распространение события</summary>
<br/>

`event.stopPropagation()` прекращает дальнейшую передачу текущего события.

</details>

<details><summary>Как остановить выполнение цепочки событий на элементе</summary>
<br/>

Если несколько обработчиков прикреплены к одному и тому же элементу с одинаковым типом события, тогда они будут вызваны в порядке своего добавления.
Если один из этих обработчиков вызовет `event.stopImmediatePropagation()` тогда события оставшихся обработчиков вызваны не будут.

</details>

<details><summary>Как отменить действие события по умолчанию</summary>
<br/>

Метод `event.preventDefault()` сообщает `User agent`, что если событие не обрабатывается явно, его действие по умолчанию не должно выполняться так, как обычно.

</details>

#### React

<details><summary>Какие методы жизненного цикла компонента в React</summary>
<br/>

</details>

<details><summary>Как можно управлять состоянием компонентов</summary>
<br/>

</details>

<details><summary>Что такое Flux</summary>
<br/>

При разрастании приложения Facebook, используемая тогда архитектура *MVC* становилась все более нестабильной.
Количество *models* и *views* возросло, так как Facebook добавлял новый функционал, и взаимодействие между ними становилось труднее контролировать.
Для решения этой проблемы в 2014 году на замену *MVC* приходит *Flux*.

**Flux** представляет архитектуру приложений, которые используют React. 

*Flux* имеет 4 главных компонента:

- Диспетчер (*Dispatcher*)
- Хранилище (*Stores*)
- Представления (*Views*) (React компонент)
- Действие (*Action*)

Во *Flux* все изменения проходят через одно направление, через *Dispatcher* данных. *Store* не может быть изменено само по себе, и тот же самый принцип работает для других *Actions*. Изменения, которые необходимо внести, должны пройти через *Dispatcher*, через *Actions*.

</details>

<details><summary>Как работает Redux</summary>
<br/>

1. Приложение отправляет `action` с определенным свойством `type` в хранилище Redux, с помощью встроенного в `store` метода `dispatch()`
2. Хранилище получает `action` и передает его *редьюсеру*, с которым был инициализирован `state`, вместе с текущим состоянием `store`
3. В соответствии с `action type`, *редьюсер* копирует текущий `state`, модифицирует копию, а затем возвращает обновленный `state`, заменяя оригинал. 
4. Затем Redux уведомляет компоненты, подписанные на `store`, об обновлении `state` и они повторно перерендерятся.

</details>

<details><summary>В чем разница между Flux и Redux</summary>
<br/>

|                | **Flux**                          | **Redux**                         |
|---------------:|-----------------------------------|-----------------------------------|
| **data flow**  | unidirectional (однонаправленный) | unidirectional (однонаправленный) |
| **store**      | multiple                          | single                            |
| **dispatcher** | singleton dispatcher              | no                                |
| **state**      | mutable                           | immutable                         |

</details>

<details><summary>Что такое хуки и для чего они нужны</summary>
<br/>

**Хук** — это функция javascript, которая позволяют работать с локальными состояниями и методами жизненного цикла компонента, без написания классов.
Хуки должны вызываться ***на верхнем уровне*** в функциях или других пользовательских обработчиках React.

Хуки позволяют извлечь логику состояния из компонента, чтобы её протестировать или повторно использовать, не затрагивая дерево компонентов при этом.

В некоторых случаях классовые компоненты невозможно разбить на более мелкие, потому что логика состояния раскидана повсюду. Такие компоненты сложно тестировать. 
Чтобы решить эту проблему, хуки позволяют разбить один компонент на маленькие функции по их назначению (например, подписке или загрузке данных), а не на основе методов жизненного цикла.

Использование хуков сокращает количество концепций, необходимых при разработке приложений React, так что нам не нужно постоянно переключаться между функциями, классами или элементами, чтобы выполнять аналогичные задачи; хуки предлагают нам однородность в экосистеме.

Жизненный цикл React был значительно упрощен за счет использования хуков, так что методы жизненного цикла классов `componentDidMount`, `componentDidUpdate` и `componentWillUnmount` суммированы в одном хуке `useEffect`, который действует как все три.

Классовые компоненты могут приводить к ненамеренным паттернам, сводящим оптимизации на нет. Классы плохо минифицируются, а горячая перезагрузка (*hot reloading*) ненадёжна и часто ломает их.
Чтобы решить эти проблемы, хуки позволяют использовать больше возможностей React без написания классов.

</details>

<details><summary>Какие хуки есть в React</summary>
<br/>

Основные хуки
- `useState`
- `useEffect`
- `useContext`

Дополнительные хуки
- `useReducer`
- `useCallback`
- `useMemo`
- `useRef`
- `useImperativeHandle`
- `useLayoutEffect`
- `useDebugValue`
- `useDeferredValue`
- `useTransition`
- `useId`

Library Hooks
- `useSyncExternalStore`
- `useInsertionEffect`

</details>

<details><summary>Как работает хук useState</summary>
<br/>

`useState` используется чтобы наделить функциональный компонент внутренним состоянием. React будет хранить это состояние между рендерами.

Хук `useState` возвращает новый *state* и функцию для его обновления.
```javascript
const [state, setState] = useState(initialState)
```
В качестве аргумента `useState` принимает первоначальное значение *стейта*, которое будет применено при первом рендеринге.

[Подробнее](https://ru.reactjs.org/docs/hooks-state.html)

</details>

<details><summary>Как работает хук useEffect</summary>
<br/>

`useEffect` позволяет выполнять побочные эффекты (загрузка данных, оформление подписки, изменение DOM вручную и т.д.) из функционального компонента ***после*** завершенного рендеринга. Он выполняет ту же роль, что и `componentDidMount`, `componentDidUpdate` и `componentWillUnmount` в React-классах, объединив их в единый API.

`useEffect` принимает функцию, которая содержит императивный код, возможно, с эффектами.
```javascript
useEffect(() => {
  // этот код будет выполнен при монтировании компонента (componentDidMount)
  // а также после обновления любого элемента из массива зависимостей (componentDidUpdate)
  return () => {
    // этот код будет выполнен при размонтировании компонента (componentWillUnmount)
    // а также до обновления любого элемента из массива зависимостей (componentWillUpdate)
    // очистка эффекта применятся опционально
  };
}, [dep1, dep2]) // Зависимости для условного срабатывания эффекта (опционально)
```
По умолчанию эффект будет срабатывать после каждого рендеринга. 
В качестве второго аргумента в `useEffect` можно передать список зависимостей из области видимости компонента, при изменении которых должен срабатывать эффект. 
Если указать пустой список `[]`, то эффект сработает только один раз при монтировании (размонтировании) компонента.

[Подробнее](https://ru.reactjs.org/docs/hooks-effect.html)

</details>

<details><summary>Разница между useEffect, useLayoutEffect и componentDidMount</summary>
<br/>

- Хук `useEffect` - *асинхронный* и переданная в него функция будет запускаться во время отложенного события ***после*** разметки и отрисовки в браузере.
- Хук `useLayoutEffect` - *синхронный* и переданная в него функция будет запускаться после разметки и ***перед*** тем, как браузер получит шанс осуществить отрисовку.
- `componentDidMount` и `componentDidUpdate` запускаются в той же фазе, что и `useLayoutEffect`.

`useLayoutEffect` и `componentDidMount`, в отличие от `useEffect` блокируют отрисовку в браузере.

</details>

<details><summary>Как работает хук useRef</summary>
<br/>

</details>

<details><summary>Что такое мемоизация и как реализуется в React</summary>
<br/>

**Мемоизация** — это сохранение результатов выполнения функций для предотвращения повторных вычислений. 
Это один из способов оптимизации, применяемый для увеличения скорости выполнения программ. 
Перед вызовом функции проверяется, вызывалась ли функция ранее:

- если не вызывалась, то функция вызывается, и результат её выполнения сохраняется;
- если вызывалась, то используется сохранённый результат.

</details>

<details><summary>Как работает хук useCallback</summary>
<br/>

Хук `useCallback` возвращает ***мемоизированный колбэк***.
```javascript
const memoizedCallback = useCallback(() => doSomething(a, b), [a, b])
```

Хук `useCallback` получает встроенный колбэк и массив зависимостей и возвращает мемоизированную версию колбэка, который изменяется только если изменяются значения одной из зависимостей. 
Это полезно при передаче колбэков оптимизированным дочерним компонентам, которые полагаются на равенство ссылок для предотвращения ненужных рендеров (например, `shouldComponentUpdate` или `React.memo()`).

> `useCallback(fn, deps)` — это эквивалент `useMemo(() => fn, deps)`

[Подробнее](https://ru.reactjs.org/docs/hooks-reference.html#usecallback)

</details>

<details><summary>Как работает хук useMemo</summary>
<br/>

Хук `useMemo` возвращает ***мемоизированное значение***.
```javascript
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b])
```

Хук `useMemo` получает *создающую* функцию и массив зависимостей и будет повторно вычислять мемоизированное значение только тогда, когда значение какой-либо из зависимостей изменилось. 
Эта оптимизация помогает избежать дорогостоящих вычислений при каждом рендере.

> `useMemo(() => fn, deps)` — это эквивалент `useCallback(fn, deps)`

[Подробнее](https://ru.reactjs.org/docs/hooks-reference.html#usememo)

</details>

<details><summary>Что такое HOC</summary>
<br/>

**Компонент высшего порядка** (*Higher-Order Component*) — это функция, которая принимает компонент и возвращает новый компонент.

[Подробнее](https://ru.reactjs.org/docs/higher-order-components.html)

</details>

<details><summary>Что такое Context</summary>
<br/>

**Context** позволяет передавать данные через дерево компонентов без необходимости передавать пропсы на промежуточных уровнях.
Контекст разработан для передачи данных, которые можно назвать «глобальными» для всего дерева React-компонентов (например, текущий аутентифицированный пользователь, UI-тема или выбранный язык).

[Подробнее](https://ru.reactjs.org/docs/context.html)

</details>

<details><summary>Что такое Порталы</summary>
<br/>

**Порталы** позволяют рендерить дочерние элементы в DOM-узел, который находится ***вне*** DOM-иерархии родительского компонента. Типовой случай применения порталов — когда в родительском компоненте заданы стили `overflow: hidden` или `z-index`, но нужно чтобы дочерний элемент визуально выходил за рамки своего контейнера. Например, диалоги, всплывающие карточки и всплывающие подсказки.

Создание портала:
```javascript
ReactDOM.createPortal(child, container)
```

[Подробнее](https://ru.reactjs.org/docs/portals.html)

</details>

<details><summary>Что такое Предохранители</summary>
<br/>

**Предохранители** (*Error Boundary*) — это компоненты React, которые отлавливают ошибки JavaScript в любом месте деревьев их дочерних компонентов, сохраняют их в журнале ошибок и выводят запасной UI вместо рухнувшего дерева компонентов. 
Предохранители отлавливают ошибки при рендеринге, в методах жизненного цикла и конструкторах деревьев компонентов, расположенных под ними.
Предохранители могут использоваться только в классовых компонентах.

[Подробнее](https://ru.reactjs.org/docs/error-boundaries.html)

</details>

<details><summary>Как можно оптимизировать производительность приложения</summary>
<br/>

</details>

<details><summary>Как можно оптимизировать SEO приложения</summary>
<br/>

</details>

#### HTML и CSS

<details><summary>Для чего нужен &lt;!DOCTYPE&gt;</summary>
<br/>

В HTML объявление типа документа тегом `<!DOCTYPE html>` - обязательная преамбула, расположенная в верхней части документа. 
Единственное предназначение тега - не допустить переключение браузера в режим совместимости (*quirks mode*) во время рендеринга документа.

</details>

<details><summary>Как выровнять элемент по центру</summary>
<br/>

1. Выравнивание по горизонтали:
- для инлайн элементов поставить родителю свойство `text-align: center`
- для блочных элементов применить элементу `margin: auto` (у элемента должна быть указана ширина)
- если размер центрируемого элемента известен, а родителя – нет, присвоисть родителю `position:relative`, потомку `position:absolute; left:50%` и сместить влево на половину ширины потомка `margin-left:-<половина-ширины-потомка>`
- создать `flex` контейнер с `justify-content:center` (или `align-items:center` для `flex-direction:column`)
2. Выравнивание по вертикали:
- сделать элемент-родитель ячейкой таблицы при помощи `display:table-cell` или реальной таблицы, и поставить ему `vertical-align:middle`
- если размер центрируемого элемента известен, а родителя – нет, присвоить родителю `position:relative`, потомку `position:absolute; top:50%` и приподнять на половину высоты потомка `margin-top:-<половина-высоты-потомка>`
- если нужно отцентрировать одну строку в блоке, высота которого известна, поставить блоку `line-height: <высота>`
- если высота родителя известна, а центрируемого элемента – нет, поставить `line-height` родителю во всю его высоту, а потомку поставить `display:inline-block`
- создать `flex` контейнер с `align-items:center` (или `justify-content:center` для `flex-direction:row`)

[Подробнее](https://learn.javascript.ru/css-center)

</details>

<details><summary>Что делает box-sizing</summary>
<br/>

CSS свойство `box-sizing` определяет как вычисляется общая ширина и высота элемента. Может принимать 2 значения:
- `content-box` - это значение по умолчанию, определённое в CSS стандарте. Свойства `width` и `height` включают исключительно контент, и не включают `padding` и `border`
- `border-box` - свойства `width` и `height` включают контент, внутренний отступ и границы, но не включают внешний отступ, то есть внутренний отступ и граница будут внутри блока

</details>

<details><summary>Что такое позиционируемый элемент</summary>
<br/>

**Позиционируемый элемент** — это элемент, у которого *вычисленное* значение `position` является `relative`, `absolute`, `fixed` либо `sticky`. 
(Другими словами, это все, кроме `static`)
- **Относительно позиционируемый элемент** является элементом, *вычисленное* значение `position` которого является `relative`. 
Свойства `top`, `bottom`, `left` и `right` определяют смещение от его нормального положения.
- **Абсолютно позиционируемый элемент** — это элемент, чьё *вычисленное* значение `position` является `absolute` или `fixed`. 
`top`, `right`, `bottom` и `left` задают смещения от краёв содержащего блок элемента.
- **Элемент с липкой позицией** — это элемент, у которого значение *вычисленного* `position` является `sticky`. Он рассматривается как относительно позиционированный до тех пор, пока содержащий его блок не пересечёт указанный порог внутри его корня потока (или в контейнере, в котором он прокручивается), после чего он обрабатывается как «застрявший» до тех пор, пока не встретит противоположный край содержащего его блока.

</details>
