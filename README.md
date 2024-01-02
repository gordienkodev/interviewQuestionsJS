# interviewQuestionsJS

### в чем отличие null и underfind

null и undefined - это два разных значения в JavaScript, и они оба представляют отсутствие значения, но в разных контекстах.
undefined:
undefined означает, что переменная была объявлена, но ей не было присвоено значение.
Когда переменной объявленной без присвоения значения, ее тип и значение по умолчанию будут undefined.
Также undefined является значением, возвращаемым функцией, если она ничего не возвращает явно.
null:
null также представляет отсутствие значения, но используется, когда программист явно присваивает переменной "ничего" или "пустоту".
Это явное присвоение значения, и если переменной присвоено null, это означает, что она не указывает на какой-либо объект или значение.
Во многих случаях undefined сигнализирует о том, что что-то не было инициализировано, в то время как null часто используется для явного указания на отсутствие значения. Однако, в некоторых ситуациях, они могут быть взаимозаменяемыми. Когда вы объявляете переменную без присвоения значения, она автоматически получает значение undefined.

### что возвращает асинхронная функция 

Асинхронная функция в JavaScript возвращает объект Promise. Promise - это объект, представляющий успешное выполнение или ошибку асинхронной операции и позволяющий обработать результат в будущем. Promise может находиться в одном из трех состояний: ожидание (pending), выполнено (fulfilled) или отклонено (rejected).

Если асинхронная функция не содержит оператора return или завершается без явного возврата значения, она также будет возвращать объект Promise с состоянием "выполнено" (fulfilled), и результатом этого Promise будет undefined. То есть, по умолчанию, если асинхронная функция завершается без явного возврата значения, её Promise будет разрешен значением undefined.

### что такое замыкание в JavaScript

Замыкание (closure) в JavaScript — это особенность языка, которая позволяет функции сохранять доступ к переменным из внешней области видимости, даже после завершения выполнения этой функции. Замыкания создаются тогда, когда функция определена внутри другой функции (родительской) и имеет доступ к переменным родительской функции.

Пример замыкания:

  function outerFunction() {
    var outerVariable = 10;
    function innerFunction() {
      console.log(outerVariable);
    }
    return innerFunction;
  }
  var closure = outerFunction();
  closure(); // Выведет 10

В приведенном примере innerFunction является замыканием, потому что она определена внутри outerFunction и имеет доступ к переменной outerVariable из внешней области видимости. Когда outerFunction вызывается и возвращает innerFunction, создается замыкание closure. Затем вызов closure() сохраняет доступ к переменной outerVariable, и она может быть использована внутри innerFunction.

Замыкания в JavaScript часто используются для создания приватных переменных, сохранения состояния функции между вызовами, а также для создания функций обратного вызова и функций высшего порядка.


### Что такое Promise (Промис)?

### Что такое микро и макро таски?

### Get и POST в чем их различие?

Они определяют тип запроса, который клиент отправляет серверу, и обычно используются в различных контекстах.
GET:
Используется для запроса данных от сервера.
Параметры передаются в URL (через строку запроса).
Данные ограничены по длине (ограничение URL-длины браузера).
Данные передаются открыто, видны в URL.
Часто используется для запросов, которые не изменяют состояние на сервере
POST:
Используется для отправки данных на сервер для обработки.
Параметры передаются в теле запроса.
Данные могут быть более объемными и безопасными, так как они не отображаются в URL.
Обычно используется для запросов, которые изменяют состояние на сервере (например, отправка данных формы).


### Можно ли передать данные в GET запросе?

Данные передаются через строку запроса (query string), которая добавляется к URL. Эти данные обычно представлены в виде параметров ключ-значение. Данные, передаваемые в GET-запросе, видны в URL, и они могут быть легко увидены пользователями, что может быть проблематичным с точки зрения безопасности, особенно если эти данные содержат чувствительную информацию, такую как пароли. Поэтому, для передачи более конфиденциальных данных, часто используется метод POST


### Что такое политика CORS про что она?

CORS (Cross-Origin Resource Sharing) — это механизм, предназначенный для обеспечения безопасности веб-приложений и позволяющий контролировать, как веб-страницы могут запрашивать ресурсы с других доменов, отличных от того, с которого была загружена текущая страница. CORS решает проблему Same-Origin Policy, которая безопасно ограничивает запросы к ресурсам на других доменах.

Политика CORS определяет, какие ресурсы с других доменов могут быть запрошены и загружены в браузере. Она использует HTTP-заголовки для определения разрешенных и недопустимых операций между разными источниками.

Некоторые ключевые заголовки CORS:
Origin: Определяет источник (origin) запроса.
Access-Control-Allow-Origin: Указывает, какие источники имеют право делать запрос на ресурс. Если значение этого заголовка равно "*", это означает, что любой источник разрешен.
Access-Control-Allow-Methods: Определяет разрешенные методы HTTP для запроса (например, GET, POST).
Access-Control-Allow-Headers: Определяет разрешенные заголовки HTTP.
Access-Control-Allow-Credentials: Указывает, могут ли запросы включать информацию аутентификации (например, куки).
Access-Control-Expose-Headers: Указывает, какие заголовки могут быть доступны в ответе.

CORS предотвращает атаки, такие как Cross-Site Request Forgery (CSRF), обеспечивая контроль того, какой код на странице имеет доступ к ресурсам на других доменах.

###  Если нужно хранить коллецию данных что использовать в зависимости от того какие это данные

В JavaScript существует несколько структур данных, которые могут использоваться для хранения коллекций данных в зависимости от особенностей этих данных и требований к их обработке. Вот несколько наиболее часто используемых структур данных:
Массивы (Array):
Используются для хранения упорядоченных коллекций элементов.
Обеспечивают быстрый доступ к элементам по индексу.
Хорошо подходят, когда порядок элементов важен.
Объекты (Object):
Используются для хранения неупорядоченных коллекций пар ключ-значение.
Позволяют быстро получать доступ к значениям по ключу.
Подходят для представления ассоциативных данных.
Map:
Предоставляет коллекцию пар ключ-значение, где ключи могут быть любого типа данных.
Поддерживает итерацию в порядке вставки.
Обеспечивает более гибкие возможности для определения ключей.
Set:
Предоставляет уникальные значения без дубликатов.
Обеспечивает быстрый поиск элементов.
Подходит, если нужно хранить только уникальные значения.

### Что такое виртуальный DOM в React
В React, виртуальный DOM (Virtual DOM) - это концепция, используемая для улучшения производительности обновления пользовательского интерфейса. Основная идея заключается в том, чтобы минимизировать количество фактических манипуляций с реальным DOM, что может быть ресурсоемким, и вместо этого работать с виртуальным представлением документа.
Процесс обновления виртуального DOM включает следующие шаги:
Изменение состояния:
Когда в React происходит изменение данных (например, изменение состояния компонента), React создает новое виртуальное дерево DOM, представляющее обновленное состояние.
Сравнение виртуальных деревьев:
React сравнивает новое виртуальное дерево DOM с предыдущим (предыдущим виртуальным деревом).
Нахождение различий (Diffing):
React вычисляет различия между двумя виртуальными деревьями, определяя, какие части дерева были добавлены, изменены или удалены.
Генерация пакета изменений (Reconciliation):
На основе вычисленных различий React создает минимальный пакет изменений, который нужно применить к реальному DOM, чтобы отобразить обновленное состояние.
Применение изменений к реальному DOM:
Только необходимые изменения применяются к реальному DOM, минимизируя операции на самом DOM и, таким образом, повышая производительность.
Использование виртуального DOM помогает избежать многих операций прямого взаимодействия с реальным DOM, что может быть медленным и затратным с точки зрения ресурсов. Реакт самостоятельно управляет обновлением и оптимизирует процесс, чтобы обеспечить более эффективные изменения интерфейса пользователя.

### Какие  хуки могут  оптимизировать React?

В React существует несколько хуков, которые могут быть использованы для оптимизации компонентов и улучшения производительности приложения. Ниже перечислены некоторые из таких хуков:
useMemo:
Хук useMemo используется для мемоизации (кэширования) результатов дорогостоящих вычислений.
Он принимает функцию и массив зависимостей и возвращает закэшированное значение, которое будет пересчитано только при изменении зависимостей.
useCallback:
useCallback мемоизирует колбэк-функции, предотвращая их пересоздание при каждом рендере компонента.
Это особенно полезно, когда колбэк используется в качестве зависимости для других хуков, чтобы избежать лишних повторных рендеров.
useEffect:
useEffect позволяет выполнять побочные эффекты в функциональных компонентах, например, подписку на внешние данные или обновление DOM.
Определенное использование useEffect может помочь избежать побочных эффектов и неопределенного поведения.
React.memo:
React.memo - это функция высшего порядка, которая мемоизирует компоненты на основе их пропсов.
Это предотвращает ненужные повторные рендеры компонентов, если их пропсы не изменились.
useRef:
useRef позволяет сохранять мутабельное значение между рендерами без вызова повторного рендера компонента.
Это может быть полезно для сохранения мутабельных данных или для обращения к DOM-элементам напрямую.
Использование этих хуков помогает уменьшить ненужные повторные рендеры, улучшая производительность React-приложений. Важно применять их с умом в зависимости от конкретных требований и контекста приложения.

### методы массива видоизменющие и нет

Методы, **видоизменяющие** исходный массив:
splice(): Изменяет содержимое массива, удаляя или заменяя существующие элементы и/или добавляя новые элементы.
pop(): Удаляет последний элемент из массива.
push(): Добавляет один или несколько элементов в конец массива.
shift(): Удаляет первый элемент из массива.
unshift(): Добавляет один или несколько элементов в начало массива.
reverse(): Изменяет порядок элементов в массиве на противоположный.
sort(): Сортирует элементы массива.
fill(): Заполняет все элементы массива одним и тем же значением.
copyWithin(): Копирует последовательность элементов массива внутри него самого.
forEach(): Итерирует по элементам массива, применяя функцию к каждому элементу. Внутри функции обратного вызова можно изменять внешние переменные, что может повлиять на исходный массив.

Методы, **не видоизменяющие** исходный массив:
concat(): Создает новый массив, объединяя один или несколько массивов или значений.
slice(): Создает новый массив, выбирая элементы из исходного массива.
map(): Создает новый массив, применяя функцию к каждому элементу исходного массива.
filter(): Создает новый массив, включая только те элементы исходного массива, для которых функция возвращает true.
join(): Создает строку, объединяя все элементы массива с заданным разделителем.
reduce(): Применяет функцию редукции к элементам массива, чтобы получить единое значение. Этот метод возвращает результат редукции, но сам массив не изменяется.








вопросы
Акредитованная ли ай ти компания?
Есть ли в компании удаленная работа?
Согласны ли они на мою вилку?
Какие этапы собеса, что на них будут спрашивать? будут ли алгоритмы? будут ли практические задачи?
(если много этапов, много подготовки и маленькая вилка -)
