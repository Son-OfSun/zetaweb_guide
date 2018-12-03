# Кроссы \(аналоги\) номенклатуры

## Описание кроссировки номенклатуры

Одним из важных элементов работы в автозапчастях является понятие кроссировки.

{% hint style="info" %}
**Кросс-номер** - это номер артикула какой-либо номенклатуры, с которым сопоставляется выбранный товар.
{% endhint %}

**Кроссировка** - проставление кросс-номеров для номенклатурных позиций.

Рассмотрим это на примере производства любой неоригинальной запчасти.

{% hint style="info" %}
**Пример:**  
Компания VAG производит позицию **"**Пробка сливная масляного поддона двигателя с прокладкой" с артикулом "N 908 132 02".

Компания TOPRAN производит аналог этой позиции с артикулом "109035785".

Чтобы позицию компании TOPRAN можно было найти, то в качестве кросс-номера к своему изделию она указывает артикул компании VAG - "N 908 132 02".
{% endhint %}

В подавляющем большинстве распространенных систем используется поиск по кросс-номеру. Таким образом, получается, что оригинальная запчасть имеет в качестве кросс-номера собственный номер и бренд, а все аналоги - номер и бренд оригинальной запчасти.

{% hint style="info" %}
Кроме типа кросс-номера "сам на себя", кросс-номера к аналогу, существуют и другие типы кросс-номеров - например, короткий номер производителя и т.п.
{% endhint %}



## Настройка кроссирования номенклатуры в системе Zeta Web

### Выбор варианта использования кросс-номеров

В первую очередь необходимо выбрать, какой вариант кроссирования наиболее вам подходит.

Выбор варианта устанавливается в основных настройках системы через меню "Zeta Web - Настройка и администрирование - Настройки Zeta Web", вкладка "Подбор товаров".



![&#x412;&#x430;&#x440;&#x438;&#x430;&#x43D;&#x442;&#x44B; &#x43A;&#x440;&#x43E;&#x441;&#x441;&#x438;&#x440;&#x43E;&#x432;&#x430;&#x43D;&#x438;&#x44F;](../../.gitbook/assets/image%20%28300%29.png)

В продукте доступны 3 варианта:

* Прямая
* Прямая и обратная
* Полная

При **прямой** кроссировке для любой номенклатуры вы просто задаете кросс-номер, которому она соответствует. Более никаких действий не происходит.  
  
**Пример:**  
Номенклатура "Аналог" получает кросс-номер \(артикул\) от номенклатуры "Оригинал".  Таким образом, получается, что при поиске по артикулу оригинала вы найдете и оригинальную запчасть, и её аналог.   
Используется, когда требуется устанавливать заменяемость каких-либо запчастей "в одну сторону".

{% hint style="info" %}
**Важно!** В этом случае при поиске по артикулу аналога сразу же вы не найдете оригинал, поскольку для этого придется создать еще одну запись - установить для номенклатуры "Оригинал" кросс-номер от номенклатуры "Аналог".
{% endhint %}

Для автоматического создания таких записей используется **прямая и обратная** кроссировка.   
Она подразумевает, что при записи кросс-номера от номенклатуры "Оригинал" к номенклатуре "Аналог" автоматически сформируется обратная запись, и к оригиналу будет установлен кросс-номер от аналога. Это прекрасно подходит для полностью взаимозаменяемых запчастей.

В третьем варианте, при **полной** кроссировке будут автоматически созданы кроссы для всех пар номенклатурных позиций, имеющих кросс-номера друг к другу.

_**Пример:**_  
При **прямой** кроссировке:  
Номенклатура "Аналог №1"  имеет кросс-номер от номенклатуры "Оригинал".  
Номенклатура "Аналог №2"  имеет кросс-номер от номенклатуры "Оригинал".

При **прямой и обратной** кроссировке автоматически добавятся:  
Номенклатура "Оригинал"  получит запись с кросс-номером от номенклатуры "Аналог №1".  
Номенклатура "Оригинал"  получит запись кросс-номером от номенклатуры "Аналог №2".  
  
При **полной** ещё дополнительно сформируются:  
Номенклатура "Аналог №1"  получит запись с кросс-номером от номенклатуры "Аналог №2".  
Номенклатура "Аналог №2"  получит запись кросс-номером от номенклатуры "Аналог №1".

{% hint style="info" %}
**Важно!** Запись с типом кросса "сам на себя" создается автоматически, при записи номенклатуры и в любом варианте кроссирования.
{% endhint %}

После выбора варианта кроссирования необходимо проверить необходимые типы кроссов и правила их установки в автоматическом режиме.

### Типы кроссов и правила установки типов при автоматическом кроссировании

Система поддерживает неограниченное количество типов кроссов, в том числе ряд предопределенных. Для ведения типов кроссов используется справочник "Типы кроссов", расположенный в меню "Zeta Web - Каталог и товары - Кроссы номенклатуры - Типы кроссов".

![&#x422;&#x438;&#x43F;&#x44B; &#x43A;&#x440;&#x43E;&#x441;&#x441;&#x43E;&#x432; &#x43D;&#x43E;&#x43C;&#x435;&#x43D;&#x43A;&#x43B;&#x430;&#x442;&#x443;&#x440;&#x44B;](../../.gitbook/assets/image%20%2864%29.png)

Наиболее используемыми являются кросс "сам на себя" \(записывается автоматически\) и аналог \(сравнительный номер\).   
  
При автоматическом создании пар кроссов иногда возникает необходимость иметь разные типы кроссов для прямого и обратного кросса.  
  
Для установки, какой тип кросса должна получить запись, служит регистр "Правила конвертации типов кроссов", расположенный в меню "Zeta Web - Каталог и товары - Кроссы номенклатуры - Правила конвертации типов кроссов". 

![&#x41F;&#x440;&#x438;&#x43C;&#x435;&#x440; &#x43F;&#x440;&#x430;&#x432;&#x438;&#x43B; &#x442;&#x438;&#x43F;&#x43E;&#x432; &#x43A;&#x440;&#x43E;&#x441;&#x441;&#x43E;&#x432;](../../.gitbook/assets/image%20%2885%29.png)

Этот регистр заполняется до начала использования для всех необходимых типов.

{% hint style="info" %}
**Важно!** При использовании **полной** перекроссировки в некоторых случаях нет возможности однозначно определить, какой тип кросса необходимо установить. Для таких ситуаций автоматически поставится предопределенный тип  "Полная кроссировка" с кодом 100.   
Подобные записи рекомендуется впоследствии разобрать вручную.
{% endhint %}

###  Установка кросс-номеров

Для хранения пар кроссированных позиций используется справочник "Кроссы номенклатуры", расположенный в меню "Zeta Web - Каталог и товары - Кроссы номенклатуры - Кроссы номенклатуры". 

![&#x412;&#x438;&#x434; &#x441;&#x43F;&#x438;&#x441;&#x43A;&#x430; &#x441;&#x43F;&#x440;&#x430;&#x432;&#x43E;&#x447;&#x43D;&#x438;&#x43A;&#x430; &quot;&#x41A;&#x440;&#x43E;&#x441;&#x441;&#x44B; &#x43D;&#x43E;&#x43C;&#x435;&#x43D;&#x43A;&#x43B;&#x430;&#x442;&#x443;&#x440;&#x44B;&quot;](../../.gitbook/assets/image%20%28304%29.png)

{% hint style="info" %}
**Важно!** Для поиска на сайте используется поле "Кросс-артикул" в очищенном виде.
{% endhint %}

Вы можете создавать кроссы как из карточки номенклатуры, так и непосредственно в справочнике кроссов.

![&#x41A;&#x430;&#x440;&#x442;&#x43E;&#x447;&#x43A;&#x430; &#x43D;&#x43E;&#x43C;&#x435;&#x43D;&#x43A;&#x43B;&#x430;&#x442;&#x443;&#x440;&#x44B; &#x441; &#x43A;&#x440;&#x43E;&#x441;&#x441;&#x43E;&#x43C; &quot;&#x441;&#x430;&#x43C; &#x43D;&#x430; &#x441;&#x435;&#x431;&#x44F;&quot;](../../.gitbook/assets/image%20%28254%29.png)

В элементе справочника, кроме полей номенклатуры и кросс-номера, хранится пользователь, последний редактирующий запись, а также дата и время редактирования.

{% hint style="info" %}
**Алгоритмы заполнения полей**:

* при заполнении артикула, если в базе есть уникальная номенклатура, то бренд и ссылка на номенклатуру заполнятся автоматически
* при заполнении ссылки на номенклатуру артикул и бренд подставятся из позиции автоматически
* поле кросс-номера "Артикул очищенный" заполняется на основании артикула кросс-номера и исключает пробелы, точки, тире и другие разделители
* подставится наиболее вероятный тип кросса \(если кросс-номер от производителя автомобилей, то "Оригинал", если слева и справа одна и та же позиция, то "Кросс "сам на себя" и т.п.\)

**Важно!** Вы можете устанавливать кроссировки и для отсутствующих в номенклатуре позицийт \(т.е. просто по артикулу и бренду\). В этом случае подобные взаимосвязи будут участвовать в поиске по остаткам поставщиков - по веб-сервисам или виртуальным складам.
{% endhint %}

![&#x412;&#x438;&#x434; &#x44D;&#x43B;&#x435;&#x43C;&#x435;&#x43D;&#x442;&#x430; &#x441;&#x43F;&#x440;&#x430;&#x432;&#x43E;&#x447;&#x43D;&#x438;&#x43A;&#x430; &quot;&#x41A;&#x440;&#x43E;&#x441;&#x441;&#x44B; &#x43D;&#x43E;&#x43C;&#x435;&#x43D;&#x43A;&#x43B;&#x430;&#x442;&#x443;&#x440;&#x44B;&quot;](../../.gitbook/assets/image%20%28138%29.png)

Вы можете добавить комментарий для любой записи, но значимым изменением, влияющим на ответственного или дату изменения являются артикул, бренд и номенклатура.

### Технические особенности

Важно понимать, что при работе с большими массивами данных возникает большая нагрузка на систему. В связи с этим, формирование записей в справочнике кроссов номенклатуры в ряде случаев \(например, при полной кроссировке\) выполняется с помощью регламентного задания.
