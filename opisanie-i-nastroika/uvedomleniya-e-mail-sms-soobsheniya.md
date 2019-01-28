---
description: 2.4.9.0
---

# Уведомления \(e-mail, SMS-сообщения\)

## Уведомления и оповещения \(e-mail, SMS-сообщения\)

В Zeta Web реализовано 2 механизма отправки оповещений:

1. Отправка осуществляется веб-частью Zeta Web
2. Отправка происходит из 1С

## Отправляет веб-часть Zeta Web

### Регистрация нового пользователя

За отправку уведомлений о регистрации отвечает контрол [Регистрация нового веб-пользователя \(v2\)](../tekhnicheskaya-dokumentaciya/opisanie-kontrolov/2.-pokupateli/avtorizaciya-registraciya/registraciya-novogo-veb-polzovatelya-v1.md)

Для настройки уведомлений необходимо в контроле, который добавлен на страницу регистрации, настроить:

1. Заголовок
2. Учетную запись
3. Шаблон текста

Рассмотрим на примере регистрации физ. лица и реализации в типовом дизайне. На странице Регистрация добавлены 2 контрола регистрации: один для физ. лиц, второй для юр. лиц. Сделаем настройку для физ. лиц:

* Открываем страницу, выбираем первый контрол регистрации и нажимаем редактировать

![](../.gitbook/assets/image%20%28248%29.png)

* Заполняем необходимые поля

![](../.gitbook/assets/image%20%28311%29.png)

* Пример шаблона письма уведомления о регистрации:

```markup
<p>
	Вы зарегистрировались на сайте demo.zetaweb.ru.
</p>
<p>
	Ваш логин:&nbsp;
		[UserEmail]
			@Значение
		[/UserEmail]
</p>
<p>
	Ваш пароль:&nbsp;
		[UserPassword]
			@Значение
		[/UserPassword]
</p>
<p>
	Ваши вопросы и пожелания смело отправляйте на info@zetasoft.ru
</p>
<p>
	--
	<br />
	С уважением,
	<br />
	команда Zeta Web
</p>
```

* Сохраняем изменения и выполняем обмен с сайтом.
* В результате после регистрации на почту приходит письмо

![&#x41F;&#x438;&#x441;&#x44C;&#x43C;&#x43E; &#x43E; &#x440;&#x435;&#x433;&#x438;&#x441;&#x442;&#x440;&#x430;&#x446;&#x438;&#x438;](../.gitbook/assets/image%20%28301%29.png)

### Восстановление пароля

За отправку сообщений о восстановлении пароля отвечает контрол [Восстановление пароля](../tekhnicheskaya-dokumentaciya/opisanie-kontrolov/2.-pokupateli/avtorizaciya-registraciya/vosstanovlenie-parolya.md).

Для настройки уведомлений необходимо в контроле, который добавлен на страницу регистрации, настроить:

1. Заголовок
2. Учетную запись
3. Шаблон текста

Рассмотрим на примере реализации в типовом дизайне. На странице Восстановление пароля добавлен контрол восстановления пароля.

* Открываем страницу, выбираем первый контрол восстановления пароля, нажимаем редактировать и заполняем необходимые поля

![](../.gitbook/assets/image%20%28346%29.png)

* Пример шаблона письма о восстановлении пароля:

```markup
<p>
	Здравствуйте,
	[UserName]
		@Значение
	[/UserName]
	[UserLastName]
		&nbsp;@Значение
	[/UserLastName]
</p>
<p>
	Ваши имя пользователя и пароль:
</p>
<p>
	Имя пользователя - 
	<strong>
		[UserLogin]
			@Значение
		[/UserLogin]
		<br />
	</strong>
	Пароль - 
	<strong>
		[UserPassword]@Значение[/UserPassword]
	</strong>
</p>
```

* Сохраняем изменения и выполняем обмен с сайтом.

![](../.gitbook/assets/image%20%28305%29.png)

* В результате на сайте после ввода e-mail и защитного кода на почту придет письмо с учетными данными

![](../.gitbook/assets/image%20%2825%29.png)

## Отправляет 1С-часть Zeta Web

{% hint style="info" %}
За отправку сообщений из 1С отвечает регламентное задание "Отправка сообщений о заказах покупателя \(Zeta Web\)". Расписание настраивается через Консоль заданий.
{% endhint %}

Форма настроек отправки сообщений находится в меню _Zeta Web - Сообщения \(эл. поча и SMS\) - Настройки отправки сообщений_

![](../.gitbook/assets/image%20%28215%29.png)

![&#x424;&#x43E;&#x440;&#x43C;&#x430; &#x43D;&#x430;&#x441;&#x442;&#x440;&#x43E;&#x439;&#x43A;&#x438; &#x43E;&#x442;&#x43F;&#x440;&#x430;&#x432;&#x43A;&#x438; &#x441;&#x43E;&#x43E;&#x431;&#x449;&#x435;&#x43D;&#x438;&#x439;](../.gitbook/assets/image%20%2896%29.png)

### Общие настройки

#### Обязательные настройки для отправки e-mail:

* Поставить флаги на функциональных опциях и настройках, которые выделены на скриншоте:

![](../.gitbook/assets/image%20%28174%29.png)

* Настроить и выбрать учетную запись e-mail для отправки сообщений
* Создать и выбрать шаблон e-mail для нового заказа

![](../.gitbook/assets/image%20%28125%29.png)

Пример e-mail письма с html-кодом и переменными:

```markup
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html lang="ru">
<head>
<meta charset="UTF-8">
	<title>Письмо от компании ...</title>
</head>
<body>
<table align="center" style="border: 0px currentColor; border-image: none; width: 100%;" border="0" cellspacing="0" cellpadding="0">
	<tbody>
		<tr>
			<td align="center" style="text-align: center; color: rgb(34, 34, 34); line-height: 16px; font-family: Arial, Helvetica, sans-serif; font-size: 14px;">
				<div style="margin: 0px auto; width: 100%; max-width: 600px;">
					<table align="center" border="0" cellspacing="0" cellpadding="0">
						<tbody>
							<tr>
								<td align="center">
									<div>
										<table align="center" border="0" cellspacing="0" cellpadding="0">
											<tbody>
												<tr>
													<td>
														<img width="180" height="75" title="заголовок картинки" alt="" src="ссылка на лого" />
													</td>
												</tr>
												<tr>
													<td>
														Добрый день, [ЗаказПокупателя.СайтФИОРозничногоПокупателя]
													</td>
												</tr>
												<tr>
													<td>
														<div>
															Ваш заказ №[ЗаказПокупателя.СайтНомер] от [ЗаказПокупателя.Дата] принят.
														</div>
														<div>
															<a href="https://УРЛ/cart-info/?ordercode=[ЗаказПокупателя.зс_веб_УникальныйКодЗаказа]">
																Перейти к заказу
															</a>
														</div>
													</td>
												</tr>
												<tr>
													<td>
														<table width="100%" align="center" border="1" cellspacing="0" cellpadding="0">
															<tbody>
																<tr>
																	<td>
																		Артикул
																		<br />
																		Бренд
																	</td>
																	<td>
																		Наименование
																	</td>
																	<td>
																		Цена,&nbsp;[ЗаказПокупателя.ВалютаДокумента.Наименование]
																	</td>
																	<td>
																		Кол-во
																	</td>
																	<td>
																		Сумма,&nbsp;[ЗаказПокупателя.ВалютаДокумента.Наименование]
																	</td>
																</tr>
																[ЗаказПокупателя.ТоварыИУслуги.НачалоТаблицы]
																<tr>
																	<td>
																		[ЗаказПокупателя.ТоварыИУслуги.Артикул]
																		<br />
																		[ЗаказПокупателя.ТоварыИУслуги.Бренд]
																	</td>
																	<td>
																		[ЗаказПокупателя.ТоварыИУслуги.Номенклатура]
																	</td>
																	<td>
																		[ЗаказПокупателя.ТоварыИУслуги.Цена]
																	</td>
																	<td>
																		[ЗаказПокупателя.ТоварыИУслуги.Количество]
																	</td>
																	<td>
																		[ЗаказПокупателя.ТоварыИУслуги.Сумма]
																	</td>
																</tr>
																[ЗаказПокупателя.ТоварыИУслуги.КонецТаблицы]
																<tr>
																	<td colspan="4">
																		Итого, с учетом доставки:
																	</td>
																	<td>
																		[ЗаказПокупателя.СуммаДокумента] [ЗаказПокупателя.ВалютаДокумента.Наименование]
																	</td>
																</tr>
															</tbody>
														</table>
													</td>
												</tr>
												<tr>
													<td>
														<table width="100%" align="center" border="1" cellspacing="0" cellpadding="0">
															<tbody>
																<tr>
																	<td colspan="2">
																		Информация о заказе
																	</td>
																</tr>
																<tr>
																	<td>
																		Контактное лицо:
																	</td>
																	<td>
																		[ЗаказПокупателя.СайтФИОРозничногоПокупателя]
																	</td>
																</tr>
																<tr>
																	<td>
																		Email контактного лица:
																	</td>
																	<td>
																		[ЗаказПокупателя.СайтПочтаРозничногоПокупателя]
																	</td>
																</tr>
																<tr>
																	<td>
																		Телефон контактного лица:
																	</td>
																	<td>
																		[ЗаказПокупателя.СайтТелефонРозничногоПокупателя]
																	</td>
																</tr>
																<tr>
																	<td>
																		Способ доставки:
																	</td>
																	<td>
																		[ЗаказПокупателя.СайтВыбранныйТипДоставки.Наименование]
																	</td>
																</tr>
																<tr>
																	<td>
																		Адрес доставки:
																	</td>
																	<td>
																		[ЗаказПокупателя.АдресДоставки]
																	</td>
																</tr>
																<tr>
																	<td>
																		Вид оплаты:
																	</td>
																	<td>
																		[ЗаказПокупателя.СайтВыбранныйВидОплаты.Наименование]
																	</td>
																</tr>
															</tbody>
														</table>
													</td>
												</tr>
												<tr>
													<td>
														&nbsp;
													</td>
												</tr>
												<tr>
													<td>
														Вы можете связаться с нами: по почте 
														<a href="почта">
															почта
														</a>
														 или по телефону телефон
													</td>
												</tr>
												<tr>
													<td>
														Чтобы наши письма не попадали в папку с нежелательной почтой, пожалуйста, добавьте 
														почта в Вашу адресную книгу.
													</td>
												</tr>
												<tr>
													<td>
														Название юр. лица и адрес
													</td>
												</tr>
												<tr>
													<td>
														<a href="/terms/">
															Пользовательское соглашение
														</a>
														 
														<a href="/privacy/">
															Политика конфиденциальности
														</a>
													</td>
												</tr>
											</tbody>
										</table>
									</div>
								</td>
							</tr>
						</tbody>
					</table>
				</div>
			</td>
		</tr>
	</tbody>
</table>
</body>
</html>
```

#### Обязательные настройки для отправки SMS

* Поставить флаги на функциональных опциях и настройках, которые выделены на скриншоте:

![](../.gitbook/assets/image%20%28352%29.png)

* Выбрать провайдера и заполнить Логин и Пароль
* Указать имя отправителя



![](../.gitbook/assets/image%20%2868%29.png)

* Создать и выбрать шаблон SMS-сообщения

![](../.gitbook/assets/image%20%28209%29.png)

Пример шаблона SMS-сообщения о новом заказе с использованием переменных:

```text
Ваш заказ №[ЗаказПокупателя.СайтНомер] на сумму [ЗаказПокупателя.СуммаДокумента] р. принят. Наш сотрудник свяжется с вами в ближайшее время.
```

### Дополнительные настройки

#### E-mail:

* Адрес для скрытой копии. Можно указать один или несколько адресов на которые будут приходить копии сообщений о заказах и сообщениях с сайта
* Шаблон уведомления о сообщениях с сайта. Уведомления о сообщениях с сайта будут приходить на адреса, указанные в поле "Адрес для скрытой копии"

![](../.gitbook/assets/image%20%28402%29.png)

Пример шаблона для уведомлений о сообщениях с сайта:

```text
Дата сообщения:
[СайтПользователиЗапросыИСообщения.Дата]

Пользователь:
[СайтПользователиЗапросыИСообщения.Пользователь.Наименование]

Имя пользователя:
[СайтПользователиЗапросыИСообщения.Имя]

Телефон:
[СайтПользователиЗапросыИСообщения.Телефон]

Эл. почта:
[СайтПользователиЗапросыИСообщения.Email]

Тема:
[СайтПользователиЗапросыИСообщения.Тема]

Сообщение:
[СайтПользователиЗапросыИСообщения.Сообщение]
```

* Уведомления об измененных заказах - функционал будет добавлен в одном из ближайших релизов
