Задача
======

Необходимо разработать приложение, по учету автомобилей и водителей в транспортной компании. Приложение должно позволять вести справочник автомобилей, 
справочник водителей, а также закреплять автомобили за водителями. За одним водителем может быть закреплено несколько автомобилей, один автомобиль может 
быть закреплен за несколькими водителями. 
Справочник водителей в приложении доступен только для чтения. Необходимо сгенерировать тестовые данные для справочника.

Страницы пользовательского интерфейса:
 
* **Справочник водителей:**
Отображает список водителей для каждой строки списка доступно действие «Просмотреть».
* **Просмотр данных водителя:**
Выводит подробную информацию о водителе (ФИО, год рождения, паспортные данные, данные водительского удостоверения). 
 
* **Справочник автомобилей**
Отображает список автомобилей, причем для каждого автомобиля указываются закрепленные водители. 
Для каждой строки списка доступны действия «Удалить», «Редактировать». 
Также на странице доступно действие «Добавить». 
Пример:

```
[Добавить]
· Ford Focus А123ВС777 Остаточная цена: 250 000р [Редактировать][Удалить]
	o Иванов И.И.
	o Петров С.С.
· Ford Focus А124ВС777 Остаточная цена: 300 000р [Редактировать][Удалить]
	o Пупкин В.Е.
	o Петров С.С.
```

4. **Редактирования данных автомобиля**
Позволяет изменить реквизиты автомобиля (Марка, модель, госномер, год выпуска и т.п.), а также добавить и удалить водителей, прикрепленных к автомобилю. 
Пример:
```
	Марка: _________________________
	Модель: ________________________
	Гос. Номер: ____________________
	Год выпуска: ___________________
	Остаточная цена: _______________
	
	Водители:
	[Добавить]

	| Водитель    	|           	|
	|-------------	|-----------	|
	| Иванов И.И. 	| [Удалить] 	|
	| Петров С.С. 	| [Удалить] 	|	

	[Сохранить] [Отменить]
```
Изменения должны сохраняться в БД только после нажатия кнопки «Сохранить» 

Дополнительные требования (реализация необязательна, но рекомендуется):
1. Страница просмотра данных водителя должна отображаться в виде модального окна поверх списка 
водителей.
1. Перед сохранением данных в форме редактирования должна быть произведена проверка их 
корректности, в случае непрохождения проверки – выводится сообщение об ошибке, сохранение 
не производится. Для выполнения проверки следует использовать предназначенные для этого средства
фреймворков. Списки должны иметь возможность разбивки по страницам, сортировки по каждому полю 
(активируется кликом на заголовок столбца), поиска по одному из полей. 

# Требования

Приложение должно быть разработано на:

## Server side:
* Языке C#
* Хранение данных должно быть организовано на Microsoft SQL Server
* Работа с БД должна осуществляться с помощью Microsoft Entity Framework
* Запросы должны строиться с использованием LINQ
* Страницы должны строиться с использованием фреймворка Microsoft ASP.NET MVC или Asp.Net WebForms

## Client side:
* JQuery
* AJAX

## Environment:
* Допускается использование любой версии Microsoft Visual Studio
* Допускается использование любого подхода в работе с Entity Framework 
– Code First, Database First, Model First.
* Entity Framework не ниже 5 версии
* Хранение исходных кодов допускается в системе контроля версий Git.
* Результат должен быть опубликован в репозитории сервиса GitHub и выслана ссылка на него.

### Оформление кода:
* Названия переменных, методов и свойств будут отражать суть происходящего в программе. 
* Код должен быть оформлен в нотации ___________________
* Все публичные члены класса будут именоваться заглавной буквы

### Будет бонусом если:
* Код будет покрыт Unit тестами
* В программе будет предустмотрена возможность конвертации ___________________
* Будет организован показ остаточной цены в 3 валютах. Рубли Доллары Евро. Для получения данных о курсах 
можно воспользоваться [Вебсервис курсов ЦБ!](https://www.cbr.ru/scripts/Root.asp?PrtId=DWS) или любой другой вам удобный.
