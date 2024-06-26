# theory-notes

1. 2 основных отличия `var` от `let/const`?
  <details>
    <summary>Ответ</summary>
    
    1. Переменные var не имеют блочной области видимости, они ограничены, как минимум, телом функции.
    
    2. Объявления (инициализация) переменных var производится в начале исполнения функции
    (или скрипта для глобальных переменных).
     
    3. (небольшое) В браузере глобальные функции и переменные, объявленные с помощью var (не let/const!),
    становятся свойствами глобального объекта.
  </details>

2. Что такое лексическое окружение?
<details>
 <summary>Ответ</summary>
  
    В JavaScript у каждой выполняемой функции, блока кода {...} и скрипта
    есть связанный с ними внутренний (скрытый) объект,
    называемый лексическим окружением LexicalEnvironment.
    
    Объект лексического окружения состоит из двух частей:
      
    Environment Record – объект, в котором как свойства хранятся все локальные переменные
    (а также некоторая другая информация, такая как значение this).
      
    Ссылка на внешнее лексическое окружение – то есть то, которое соответствует коду снаружи
    (снаружи от текущих фигурных скобок).
</details>

3. Что такое Замыкания?
<details>
 <summary>Ответ</summary>
  
    Замыкание – это функция, которая запоминает свои внешние переменные и может получить к ним доступ.
    
    В JavaScript, все функции изначально являются замыканиями (кроме синтаксиса "new Function").
  
    То есть они автоматически запоминают, где были созданы, с помощью скрытого свойства [[Environment]],
    которое хранит ссылку на лексическое окружение, в котором была создана функция
    независимо от того, где она вызывается.
    
    Ссылка на [[Environment]] устанавливается один раз и навсегда при создании функции.
</details>

4. Как работает лексическое окружение?
<details>
 <summary>Ответ</summary>
  
        При запуске скрипта лексическое окружение предварительно заполняется всеми объявленными переменными.
    
        Изначально они находятся в состоянии «Uninitialized». Это особое внутреннее состояние, которое означает,
        
        что движок знает о переменной, но на нее нельзя ссылаться, пока она не будет объявлена с помощью let.
        
        Это почти то же самое, как если бы переменная не существовала.
        
        Появляется определение переменной let phrase. У неё ещё нет присвоенного значения,
        поэтому присваивается undefined.
        
        С этого момента мы можем использовать переменную.
  
      Когда код хочет получить доступ к переменной – сначала происходит поиск во внутреннем лексическом окружении,
      затем во внешнем, затем в следующем и так далее, до глобального.
</details>
