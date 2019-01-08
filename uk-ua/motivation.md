---
layout: default
language: 'uk-ua'
version: '0.11'
---
# Why Zephir?

Сьогоднішні програми на PHP повинні збалансувати ряд проблем, таких як стабільність, продуктивність та функціональність. Кожна PHP програма базується на збірці загальних компонентів, які також є основою для багатьох інших програм.

Цими загальними компонентами є бібліотеки, фреймворки або й те й інше в одному флаконі. Після встановлення фреймворки змінюються рідко і будучи основою для програми мусять бути багатофункціональними, а також дуже швидкими.

Пошук швидких та надійних бібліотек може бути складним, як правило через високі рівні абстракції, на яких вони реалізовані. Виходячи з того, що базові бібліотеки або фреймворки змінюються рідко, існує можливість побудувати розширення, які нададуть цю ж функціональність, скориставшись швидкістю вже скомпільованої програми та економією ресурсів.

З Zephir ви можете реалізувати об'єктно-орієнтовані бібліотеки/фреймворки/програми, які можна використовувати з-під PHP, тим самим зберігши дорогоцінні секунди, які можуть зробити вашу програму швидшою та покращити користувацький досвід.

<a name='if-you-are-a-php-programmer'></a>

## If You Are a PHP Programmer...

PHP є однією з найпопулярніших мов, що використовуються для розробки веб-програм. Інтерпретовані мови з динамічною типізацією, такі як PHP, пропонують дуже високу продуктивність завдяки їхній гнучкості.

Починаючи з версії 4, PHP базується на реалізації Zend Engine. Це віртуальна машина, яка виконує PHP-код з його байт-код представлення. Zend Engine присутній практично у кожній установці PHP. За допомогою Zephir ви можете створювати розширення для PHP, які працюватимуть під управлінням Zend Engine.

Zephir базується на PHP, тому вони, очевидно, мають багато спільного, проте вони мають і суттєві відмінності, які надають Zephir свою власну індивідуальність. Наприклад, Zephir є більш суворим, і це може зробити вас менш продуктивним у порівнянні з PHP через крок компіляції.

<a name='if-you-are-a-c-programmer'></a>

## If You Are a C Programmer...

C — одна з найпотужніших та найпопулярніших мов програмування, серед мов, коли-небудь створених. Насправді сам PHP написаний на C. Це одна з причин, чому розширення для PHP сумісні із C. C дає вам свободу керування пам'яттю, використання типів низького рівня та навіть виконання підпрограм асемблера прямо з-під C коду.

Однак, розробка великих програм на C може тривати довше, ніж очікувалося в порівнянні з PHP або Zephir. Крім того деякі помилки може бути складно знайти, якщо ви не є досвідченим розробником.

Zephir був розроблений для безпечної роботи з пам'яттю. Тому в ньому не передбачено реалізації вказівників ручного керування пам'яттю. Отже, якщо ви C-програміст то Zephir для вас відчуватиметься дещо урізаним, проте більш дружнім.

<a name='compilation-vs-interpretation'></a>

## Compilation vs Interpretation

Компіляція зазвичай гальмує розробку програм; вам буде потрібно трохи терпіння, щоб скомпілювати код перш ніж запустити його. З іншого боку, інтерпретація має тенденцію до зниження швидкодії програми на користь збільшення темпів розробки продукту. Щоправда, в деяких випадках немає ніякої помітної різниці між швидкістю інтерпретованого та скомпонованого коду.

Zephir вимагає компіляції коду, але функціональність використовується з PHP, який інтерпретується.

Після компіляції коду не потрібно робити це знову. Інтерпретований код інтерпретується кожного разу, коли він запускається. Розробники можуть вирішити, які частини їхньої програми мають бути на Zephir, а які ні.

<a name='statically-typed-versus-dynamically-typed-languages'></a>

## Statically Typed Versus Dynamically Typed Languages

У цілому, в статичнотипізованій мові змінна пов'язана з певним типом протягом всього життєвого циклу програми. Тип змінної неможливо змінити й вона може лише посилатися на сумісні з типом екземпляри та операції. Мови, такі як C/C++, були реалізовані за такою схемою:

```zephir
int a = 0;
a = "hello"; // not allowed
```

У динамічнотипізованих мовах тип прив'язується до значення, а не до змінної. Таким чином, змінна може мати значення одного типу, а потім бути перевизначеною значенням невизначеного типу. JavaScript/PHP є прикладами мов з динамічною типізацією:

```zephir
var a = 0;
a = "hello"; // allowed
```

Попри свої переваги швидшої розробки динамічнотипізовані мови не завжди будуть кращим вибором для всіх програм, особливо для тих у яких дуже велика кодова база або для яких критична швидкодія.

Оптимізація швидкодії динамічної мови на кшталт PHP, є складнішою, ніж для статичної мови, як C. У статичній мові оптимізатори для прийняття рішень можуть використовувати інформацію про змінні на основі їхнього типу. У динамічній мові для оптимізатора доступно менше таких підказок, що робить вибір оптимізації складнішим.

Хоча останні досягнення в оптимізації для динамічних мов є перспективними (наприклад, компіляція JIT), вони відстають від сучасних статичнотипізованих мов. Отже, якщо вам потрібна швидкодія - статичнотипізована мова, ймовірно, будуть надійнішим вибором.

Ще однією перевагою статичнотипізованих мов є додаткова перевірка, яку виконує компілятор. Компілятор не може знайти логічних помилок, проте компілятор може заздалегідь знайти помилки, які в статичнотипізованій мові можна знайти лише під час виконання.

Zephir поєднує в собі статичну та динамічну типізацію, що дозволяє вам скористатися обома підходами, де це можливо.

<a name='compilation-scheme'></a>

## Compilation Scheme

Zephir пропонує генерацію власного коду (в даний час через компіляцію в C). Компілятор, подібний до gcc/clang/vc++, оптимізує та компілює код до машинного коду. На наступній діаграмі показано, як працює цей процес:

![схема компіляції](/assets/content/scheme.png)

На додаток до того, що надає Zephir, З часом, в компіляторі був реалізований ряд оптимізацій, які покращують продуктивність скомпільованих додатків:

* [GCC оптимізація](http://gcc.gnu.org/onlinedocs/gcc-4.1.0/gcc/Optimize-Options.html)
* [LLVM проходи](http://llvm.org/docs/Passes.html)
* [Visual C/C++ оптимізації](http://msdn.microsoft.com/en-us/library/k1ack8f1.aspx)

<a name='code-protection'></a>

## Code Protection

У певних випадках компіляція може не дати великого приросту швидкодії. Це може бути тому, що вузьким місцем програми може бути система вводу/виводу, (що цілком імовірно) а не обчислення чи ліміт пам'яті. Однак, компіляція коду також може забезпечити певний рівень інтелектуального захисту до вашої програми. З Zephir-ом ви створюєте двійковий файл, що дає вам можливість «приховати» оригінальний вихідний код для користувачів чи клієнтів.

<a name='conclusion'></a>

## Conclusion

Zephir не був створений для заміни PHP або C. Навпаки, ми вважаємо, що він доповнює їх, дозволяючи PHP-розробникам спробувати свої сили в написанні компілювального коду та статичній типізації. Zephir є спробою поєднати краще з C та PHP світів у пошуках можливостей зробити програми швидшими.