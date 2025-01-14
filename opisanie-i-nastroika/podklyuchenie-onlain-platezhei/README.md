# Подключение онлайн-платежей

{% hint style="info" %}
Для подключения онлайн-платежей на сайт должен быть установлен [SSL-сертификат](../../ustanovka-i-obnovlenie/ssl-sertifikat-https.md)
{% endhint %}

## Провайдеры онлайн-платежей

1. [Яндекс.Касса](yandeks.kassa-yandex.kassa.md) \(с поддержкой онлайн-касс\)
2. [Ассист](assist-assist.md)
3. [Сбербанк](https://help-zetaweb.zetasoft.ru/~/edit/drafts/-LYCU2gYFNYKqr6dH7Cd/opisanie-i-nastroika/podklyuchenie-onlain-platezhei/sberbank-sberbank) \(с поддержкой онлайн-касс\)

## Алгоритм работы с интернет-кассой по ФЗ-54

1. Интернет-магазин Zeta Web принимает оплату на сайте с помощью платежного шлюза, например, Яндекс.Кассы;
2. Платежный шлюз передает данные об оплате в онлайн-кассу \(фискальный регистратор\), указанную в настройках шлюза. Перечень онлайн-касс, поддерживаемый шлюзом Яндекс.Касса: [https://kassa.yandex.ru/54fz.html](https://kassa.yandex.ru/54fz.html);
3. Онлайн-касса высылает данные об оплате в ОФД;
4. ОФД высылает чек пользователю \(если необходимо\).

## Последовательность действий для подключения

1. Купить или взять в аренду онлайн-кассу, совместимую с выбранным платежным шлюзом;
2. Зарегистрировать и настроить кассу;
3. Настроить платежный шлюз;
4. Настроить Zeta Web для приема онлайн-платежей \(необходим [сертификат SSL и подключение по протоколу https](https://help-zetaweb.zetasoft.ru/ustanovka-i-obnovlenie/ssl-sertifikat-https#ustanovka-ssl-sertifikata-https)\).

## Привязка платежной системы к ролям.

После того, как вы настроите вашу платежную систему \([Яндекс.Кассу](yandeks.kassa-yandex.kassa.md), [Сбербанк ](https://help-zetaweb.zetasoft.ru/~/edit/drafts/-LYCU2gYFNYKqr6dH7Cd/opisanie-i-nastroika/podklyuchenie-onlain-platezhei/sberbank-sberbank)или [Ассист](assist-assist.md)\), необходимо привязать настройки платежной системы к роли клиента.

Настройки платежной системы указываются в разрезе **Роли** клиента.  
Для настройки в 1С необходимо открыть **Панель управления** и перейти в раздел **Пользователи.**  
В разделе пользователей открыть вкладку **Группы пользователей \(роли\)** и открыть нужную вам роль для редактирования.

![&#x41D;&#x430;&#x441;&#x442;&#x440;&#x43E;&#x439;&#x43A;&#x430; &#x434;&#x43E;&#x441;&#x442;&#x443;&#x43F;&#x43D;&#x43E;&#x433;&#x43E; &#x432;&#x438;&#x434;&#x430; &#x43E;&#x43F;&#x43B;&#x430;&#x442;&#x44B; &#x434;&#x43B;&#x44F; &#x43A;&#x43B;&#x438;&#x435;&#x43D;&#x442;&#x430;](../../.gitbook/assets/image%20%28541%29.png)

Укажите в поле **Настройка видов оплат** - ****_настройку платежной системы._ Сохраните роль.

### Настройка загрузки документов "Оплата платежной картой"

Для того, чтобы документ _**"Оплата от покупателя платежной картой"**_  успешно загрузился с сайта, необходимо для пользователя, под которым выполняется обмен _\(обычно, это пользователь "Сайт"\)_, установить, как минимум, флаг в настройках пользователя - _**"Отражать документы в управленческом учете".**_

![](../../.gitbook/assets/image%20%28351%29.png)

{% hint style="info" %}
При использовании тестового режима оплаты и проведения платежа на сайте, документ _"Оплата от покупателя платежной картой"_ будет записан, но не проведен.
{% endhint %}

