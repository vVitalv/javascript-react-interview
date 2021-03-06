## Вопросы на собеседовании frontend JavaScript React разработчика в 2022 году

Здесь собраны самые частые вопросы, встречающиеся на собеседовании frontend JS React разработчика.
Список вопросов постоянно актуализируется. Прошу принимать участие!

#### JavaScript

<details><summary>Что такое ООП</summary>

Общий принцип ООП заключается в разделении задач и ответственностей по сущностям.
Сущности создаются в коде как объекты. При этом каждая из них объединяет некую информацию (*свойства*) и действия (*методы*), которые может выполнять.

Ключевые принципы ООП:
1. **Наследование** – это возможность создавать классы на основе других классов. С помощью этого принципа можно определять родительский класс (с нужными свойствами и методами), а затем дочерний класс, который будет наследовать от родителя все свойства и методы.
2. **Инкапсуляция** — это размещение в одном компоненте данных и методов, которые с ними работают. Обеспечивает механизм сокрытия, позволяющий разграничивать доступ к различным компонентам программы.
3. **Абстракция** — это использование только тех характеристик объекта, которые с достаточной точностью представляют его в данной системе.
4. **Полиморфизм** означает «множество форм» и отражает способность метода возвращать разные значения, согласно определённым условиям.

</details>

<details><summary>Какие типы данных есть в JS</summary>

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

Для этого можно использовать встроенный метод `Array.isArray()`

</details>

<details><summary>Различия между let, const и var</summary>

|                                       | **var**                       | **let** | **const** |
|--------------------------------------:|-------------------------------|---------|-----------|
| **область видимости**                 | функциональная или глобальная | блочная | блочная   |
| **можно объявлять заново**            | да                            | нет     | нет       |
| **можно обновлять**                   | да                            | да      | нет       |
| **поднимается (hoisting)**            | да                            | да      | да        |
| **инициализируется при поднятии**     | как `undefined`               | нет     | нет       |
| **можно объявлять без инициализации** | да                            | да      | нет       |

</details>

<details><summary>Что такое hoisting</summary>

**Поднятие** (*hoisting*) - это поведение компилятора JavaScript, заключающееся в поднятии объявлений переменных и функций в начало области видимости.

Благодаря поднятию мы можем использовать функции до их объявления в коде. Однако, следует учитывать, что поднимаются только объявления, но не присваивания значений.

По этой причине, например, мы можем использовать до объявления функцию, объявленную через *Function Declaration*, но не можем ту, которая объявлена через *Function Expression*.

</details>

<details><summary>В чем разница между операторами == и ===</summary>

Разница между оператором `==` (абстрактное или нестрогое равенство) и оператором `===` (строгое равенство) состоит в том, что первый сравнивает значения после их преобразования или приведения к одному типу, а второй — без такого преобразования.

</details>

<details><summary>Для чего нужен двойной оператор логического отрицания !!</summary>

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

<details><summary>Что такое область видимости (Scope)</summary

**Область видимости** (*scope*) — это место, откуда мы имеем доступ к переменным или функциям. В JS есть три типа областей видимости: *глобальная*, *функциональная* и *блочная*.

- **Глобальная область видимости** — переменные и функции, объявленные в глобальном пространстве имен, имеют глобальную область видимости и доступны из любого места в коде.
- **Функциональная область видимости** (область видимости функции) — переменные, функции и параметры, объявленные внутри функции, доступны только внутри этой функции.
- **Блочная область видимости** — переменные (объявленные с помощью ключевых слов `let` и `const`) внутри блока `{ }`, доступны только внутри него.

Область видимости — это также набор правил, по которым осуществляется поиск переменной. 
Если переменной не существует в текущей области видимости, ее поиск производится выше, во внешней по отношению к текущей области видимости. 
Если и во внешней области видимости переменная отсутствует, ее поиск продолжается вплоть до глобальной области видимости. 
Если в глобальной области видимости переменная обнаружена, поиск прекращается, если нет — выбрасывается исключение. 
Поиск осуществляется по ближайшим к текущей областям видимости и останавливается с нахождением переменной. Это называется цепочкой областей видимости (*Scope Chain*).

</details>

<details><summary>Способы объявления функций</summary>

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

Важное отличие *Function Declaration* от *Function Expression* в том, ***когда*** создается функция движком JS.
- *Function Declaration* обрабатываются перед выполнением блока кода. Они видны во всём блоке.
- *Function Expression* создаются только когда поток выполнения достигает их.

Анонимные функции чаще всего используются в качестве функций обратных вызовов (*callback*).

[Подробнее](https://learn.javascript.ru/function-expressions#function-expression-v-sravnenii-s-function-declaration)

</details> 

<details><summary>Особенности стрелочных функций</summary>

`Стрелочные функции`:
- не содержат собственный контекст `this`, а используют значение `this` окружающего контекста.
- не имеют собственного объекта `arguments`, поэтому в теле стрелочных функций `arguments` будет ссылаться на переменную в окружающей области.
- не могут быть вызваны с `new`.

[Подробнее](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

</details> 

<details><summary>Что такое this</summary>

В глобальном контексте выполнения (за пределами каких-либо функций) `this` ссылается на глобальный объект вне зависимости от режима (строгий или нестрогий).

В пределах функции значение `this` зависит от того, каким образом вызвана функция.

Когда функция вызывается как метод объекта, используемое в этой функции ключевое слово `this` принимает значение объекта, по отношению к которому вызван метод.

В стрелочных функциях, `this` привязан к окружению, в котором была создана функция. В глобальной области видимости `this` будет указывать на глобальный объект.

Когда функция используется как обработчик событий, `this` присваивается элементу с которого начинается событие.

[Подробнее](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Operators/this)

</details>

<details><summary>Что такое замыкание</summary>

</details>

<details><summary>Как работает прототипное наследование</summary>

В JS объекты имеют специальное скрытое свойство `[[Prototype]]`, которое либо равно `null`, либо ссылается на другой объект.

При обращении к свойству или методу объекта сначала происходит поиск этого свойства у самого объекта. 
В случае неудачи поиск перенаправляется в его прототип, затем в прототип прототипа и так далее, пока искомое свойство не будет найдено, либо пока не закончится цепочка прототипов.

</details> 

<details><summary>Как работают события в JS</summary>

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

- `event.target` – самый глубокий элемент, на котором ***произошло*** событие.
- `event.currentTarget` – элемент, на котором ***навешен*** обработчик произошедшего события.

</details>

<details><summary>Как остановить распространение события</summary>

`event.stopPropagation()` прекращает дальнейшую передачу текущего события.

</details>

<details><summary>Как остановить выполнение цепочки событий на элементе</summary>

Если несколько обработчиков прикреплены к одному и тому же элементу с одинаковым типом события, тогда они будут вызваны в порядке своего добавления.
Если один из этих обработчиков вызовет `event.stopImmediatePropagation()` тогда события оставшихся обработчиков вызваны не будут.

</details>

<details><summary>Как отменить действие события по умолчанию</summary>

Метод `event.preventDefault()` сообщает `User agent`, что если событие не обрабатывается явно, его действие по умолчанию не должно выполняться так, как обычно.

</details>

#### React

<details><summary>Какие методы жизненного цикла компонента в React</summary>

</details>

<details><summary>Как можно управлять состоянием компонентов</summary>

</details>

<details><summary>Как работает Redux</summary>

</details>

<details><summary>Какие хуки есть в React</summary>

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

`useState` используется чтобы наделить функциональный компонент внутренним состоянием. React будет хранить это состояние между рендерами.

Хук `useState` возвращает новый *state* и функцию для его обновления.
```javascript
const [state, setState] = useState(initialState)
```
В качестве аргумента `useState` принимает первоначальное значение *стейта*, которое будет применено при первом рендеринге.

[Подробнее](https://ru.reactjs.org/docs/hooks-state.html)

</details>

<details><summary>Как работает хук useEffect</summary>

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

- Хук `useEffect` - *асинхронный* и переданная в него функция будет запускаться во время отложенного события ***после*** разметки и отрисовки в браузере.
- Хук `useLayoutEffect` - *синхронный* и переданная в него функция будет запускаться после разметки и ***перед*** тем, как браузер получит шанс осуществить отрисовку.
- `componentDidMount` и `componentDidUpdate` запускаются в той же фазе, что и `useLayoutEffect`.

`useLayoutEffect` и `componentDidMount`, в отличие от `useEffect` блокируют отрисовку в браузере.

</details>

<details><summary>Как работает хук useRef</summary>

</details>

<details><summary>Что такое мемоизация и как реализуется в React</summary>

**Мемоизация** — это сохранение результатов выполнения функций для предотвращения повторных вычислений. 
Это один из способов оптимизации, применяемый для увеличения скорости выполнения программ. 
Перед вызовом функции проверяется, вызывалась ли функция ранее:

- если не вызывалась, то функция вызывается, и результат её выполнения сохраняется;
- если вызывалась, то используется сохранённый результат.

</details>

<details><summary>Как работает хук useCallback</summary>

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

**Компонент высшего порядка** (*Higher-Order Component*) — это функция, которая принимает компонент и возвращает новый компонент.

[Подробнее](https://ru.reactjs.org/docs/higher-order-components.html)

</details>

<details><summary>Что такое Context</summary>

**Context** позволяет передавать данные через дерево компонентов без необходимости передавать пропсы на промежуточных уровнях.
Контекст разработан для передачи данных, которые можно назвать «глобальными» для всего дерева React-компонентов (например, текущий аутентифицированный пользователь, UI-тема или выбранный язык).

[Подробнее](https://ru.reactjs.org/docs/context.html)

</details>

<details><summary>Что такое Порталы</summary>

**Порталы** позволяют рендерить дочерние элементы в DOM-узел, который находится ***вне*** DOM-иерархии родительского компонента. Типовой случай применения порталов — когда в родительском компоненте заданы стили `overflow: hidden` или `z-index`, но нужно чтобы дочерний элемент визуально выходил за рамки своего контейнера. Например, диалоги, всплывающие карточки и всплывающие подсказки.

Создание портала:
```javascript
ReactDOM.createPortal(child, container)
```

[Подробнее](https://ru.reactjs.org/docs/portals.html)

</details>

<details><summary>Что такое Предохранители</summary>

**Предохранители** (*Error Boundary*) — это компоненты React, которые отлавливают ошибки JavaScript в любом месте деревьев их дочерних компонентов, сохраняют их в журнале ошибок и выводят запасной UI вместо рухнувшего дерева компонентов. 
Предохранители отлавливают ошибки при рендеринге, в методах жизненного цикла и конструкторах деревьев компонентов, расположенных под ними.
Предохранители могут использоваться только в классовых компонентах.

[Подробнее](https://ru.reactjs.org/docs/error-boundaries.html)

</details>

#### HTML и CSS

<details><summary>Для чего нужен &lt;!DOCTYPE&gt;</summary>

В HTML объявление типа документа тегом `<!DOCTYPE html>` - обязательная преамбула, расположенная в верхней части документа. 
Единственное предназначение тега - не допустить переключение браузера в режим совместимости (*quirks mode*) во время рендеринга документа.

</details>

<details><summary>Как выровнять элемент по центру</summary>

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

CSS свойство `box-sizing` определяет как вычисляется общая ширина и высота элемента. Может принимать 2 значения:
- `content-box` - это значение по умолчанию, определённое в CSS стандарте. Свойства `width` и `height` включают исключительно контент, и не включают `padding` и `border`
- `border-box` - свойства `width` и `height` включают контент, внутренний отступ и границы, но не включают внешний отступ, то есть внутренний отступ и граница будут внутри блока

</details>

<details><summary>Что такое позиционируемый элемент</summary>

**Позиционируемый элемент** — это элемент, у которого *вычисленное* значение `position` является `relative`, `absolute`, `fixed` либо `sticky`. 
(Другими словами, это все, кроме `static`)
- **Относительно позиционируемый элемент** является элементом, *вычисленное* значение `position` которого является `relative`. 
Свойства `top`, `bottom`, `left` и `right` определяют смещение от его нормального положения.
- **Абсолютно позиционируемый элемент** — это элемент, чьё *вычисленное* значение `position` является `absolute` или `fixed`. 
`top`, `right`, `bottom` и `left` задают смещения от краёв содержащего блок элемента.
- **Элемент с липкой позицией** — это элемент, у которого значение *вычисленного* `position` является `sticky`. Он рассматривается как относительно позиционированный до тех пор, пока содержащий его блок не пересечёт указанный порог внутри его корня потока (или в контейнере, в котором он прокручивается), после чего он обрабатывается как «застрявший» до тех пор, пока не встретит противоположный край содержащего его блока.

</details>
