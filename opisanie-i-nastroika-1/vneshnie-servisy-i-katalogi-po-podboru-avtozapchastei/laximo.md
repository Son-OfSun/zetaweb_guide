# Laximo

## Laximo. OEM

### Описание

В системе Zeta Web поддерживается полный функционал сервиса Laximo.OEM, предоставляемый компанией Laximo.

{% hint style="info" %}
Пример реализации вы можете посмотреть [на официальном сайте](http://wsdemo.laximo.ru/index.php?lang=ru).
{% endhint %}

Для работы с сервисом в системе реализованы следующие контролы:

* Laximo. Этапы 1, 2. Условия поиска моделей автомобилей \(vin, frame, параметры\)
* Laximo. Этап 1. Список каталогов \(производители автомобилей\)
* Laximo. Этап 2. Результаты поиска моделей автомобилей
* Laximo. Этап 3.1. Каталог от производителя. Дерево групп
* Laximo. Этап 3.1. Общий каталог.  Дерево групп \(структура дерева запчастей TecDoc\)
* Laximo. Этап 3.2. Каталог от производителя. Список узлов и агрегатов
* Laximo. Этап 3.2. Общий каталог. Список узлов и агрегатов
* Laximo. Этап 4. Информация о выбранном узле / агрегате \(схема, запчасти / детали\)
* Laximo. Этапы 1, 2, 3, 4. Текущее состояние поиска

### Настройка 1С

Для настройки учетной записи в 1С необходимо открыть **Панель управления** и перейти в раздел **Настройки.**  
В разделе настроек открыть вкладку **Домены** и открыть нужный вам домен на редактирование.

![&#x41D;&#x430;&#x441;&#x442;&#x440;&#x43E;&#x439;&#x43A;&#x430; &#x430;&#x432;&#x442;&#x43E;&#x440;&#x438;&#x437;&#x430;&#x446;&#x438;&#x438; Laximo](../../.gitbook/assets/image%20%2825%29.png)

Укажите в поле **Настройка авторизации лаксимо** существующую настройку или создайте новую \(см. ниже\).

![&#x41D;&#x430;&#x441;&#x442;&#x440;&#x43E;&#x439;&#x43A;&#x430; &#x443;&#x447;&#x435;&#x442;&#x43D;&#x43E;&#x439; &#x437;&#x430;&#x43F;&#x438;&#x441;&#x438; &#x441;&#x435;&#x440;&#x432;&#x438;&#x441;&#x430; Laximo](../../.gitbook/assets/image%20%28205%29.png)

Укажите следующие значения:

* Логин _Значение: **Адрес электронной почты \(логин\)** от сервиса Laximo_
* Пароль _Значение: **Пароль**, указанный при регистрации_
* Файл _Значение: Оставьте это поле **пустым**_

Сохраните настройку ааторизации.  
Сохраните настройку домена.

### Пример реализации

![&#x42D;&#x442;&#x430;&#x43F; &#x2116;1. &#x41F;&#x43E;&#x438;&#x441;&#x43A; &#x43F;&#x43E; VIN / &#x41F;&#x43E;&#x438;&#x441;&#x43A; &#x43F;&#x43E; Frame / &#x412;&#x44B;&#x431;&#x43E;&#x440; &#x43A;&#x430;&#x442;&#x430;&#x43B;&#x43E;&#x433;&#x430; \(&#x43F;&#x440;&#x43E;&#x438;&#x437;&#x432;&#x43E;&#x434;&#x438;&#x442;&#x435;&#x43B;&#x44F; &#x430;&#x432;&#x442;&#x43E;&#x43C;&#x43E;&#x431;&#x438;&#x43B;&#x44F;\)](../../.gitbook/assets/image%20%28443%29.png)

![&#x42D;&#x442;&#x430;&#x43F; &#x2116;2. &#x41F;&#x43E;&#x438;&#x441;&#x43A; &#x43F;&#x43E; VIN / &#x41F;&#x43E;&#x438;&#x441;&#x43A; &#x43F;&#x43E; Frame / &#x41F;&#x43E;&#x438;&#x441;&#x43A; &#x43F;&#x43E; &#x43F;&#x430;&#x440;&#x430;&#x43C;&#x435;&#x442;&#x440;&#x430;&#x43C;](../../.gitbook/assets/image%20%28307%29.png)

{% hint style="info" %}
Не все каталоги поддерживают все виды поиска. Например, в каталогах SKODA недоступен поиск по параметрам, а в каталоге LANCIA - доступен только поиске по VIN.
{% endhint %}

![&#x42D;&#x442;&#x430;&#x43F; &#x2116;3. &#x414;&#x435;&#x440;&#x435;&#x432;&#x43E; &#x433;&#x440;&#x443;&#x43F;&#x43F; &#x43A;&#x430;&#x442;&#x430;&#x43B;&#x43E;&#x433; &#x43F;&#x440;&#x43E;&#x438;&#x437;&#x432;&#x43E;&#x434;&#x438;&#x442;&#x435;&#x43B;&#x44F; &#x438; &#x441;&#x43F;&#x438;&#x441;&#x43E;&#x43A; &#x443;&#x437;&#x43B;&#x43E;&#x432; &#x438; &#x430;&#x433;&#x440;&#x435;&#x433;&#x430;&#x442;&#x43E;&#x432;](../../.gitbook/assets/image%20%28118%29.png)

![&#x42D;&#x442;&#x430;&#x43F; &#x2116;3. &#x414;&#x435;&#x440;&#x435;&#x432;&#x43E; &#x433;&#x440;&#x443;&#x43F;&#x43F; &#x43E;&#x431;&#x449;&#x435;&#x433;&#x43E; &#x43A;&#x430;&#x442;&#x430;&#x43B;&#x43E;&#x433;&#x430; &#x438; &#x441;&#x43F;&#x438;&#x441;&#x43E;&#x43A; &#x443;&#x437;&#x43B;&#x43E;&#x432; &#x438; &#x430;&#x433;&#x440;&#x435;&#x433;&#x430;&#x442;&#x43E;&#x432; ](../../.gitbook/assets/image%20%28318%29.png)

{% hint style="info" %}
Для некоторых узлов могут отсутствовать изображения
{% endhint %}

![&#x42D;&#x442;&#x430;&#x43F; &#x2116;4. &#x421;&#x445;&#x435;&#x43C;&#x430; &#x443;&#x437;&#x43B;&#x430; / &#x430;&#x433;&#x440;&#x435;&#x433;&#x430;&#x442;&#x430; &#x438; &#x441;&#x43F;&#x438;&#x441;&#x43E;&#x43A; &#x434;&#x435;&#x442;&#x430;&#x43B;&#x435;&#x439;](../../.gitbook/assets/image%20%28448%29.png)

Результатом поиска оригинальных запчастей будет переход к поиску товаров по артикулу или по паре артикул и бренд \(в зависимости от настроек, указанных при верстке четвертого этапа поиска\).

## Laximo.AM

На данный момент поддержка сервиса Laximo.AM не реализована.
