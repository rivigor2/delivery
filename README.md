Тестовое задание: Расчет доставки. Стек: laravel 8.*, php 7.*

Условия:


Требуется спроектировать модуль расчета стоимости доставки.

Есть две службы доставки:


1. «Быстрая доставка»:

base_url: string

@var sourceKladr string //кладр откуда везем

@var targetKladr string //кладр куда везем

@var weight float //вес отправления в кг

@return json

{

&quot;price&quot;: float //стоимость

&quot;period&quot;: int //количество дней начиная с сегодняшнего, но после 18.00

заявки не принимаются.

&quot;error&quot;: string

}


2. «Медленная доставка»:

имеет базовую стоимость 150р

base_url: string

@var sourceKladr string //кладр откуда везем

@var targetKladr string //кладр куда везем

@var weight float //вес отправления в кг

@return json

{

&quot;coefficient&quot;: float //коэффициент (конечная цена есть произведение базовой стоимости и коэффициента)

&quot;date&quot;: string //дата доставки в формате 2017-10-20

&quot;error&quot;: string

}


Задача в том, чтобы получить для набора отправлений стоимость и сроки доставки в контексте списка транспортных компаний и одной выбранной. Формат полученных от транспортных компаний данных должен быть приведен к единому виду (

{

&quot;price&quot;: float //стоимость

&quot;date&quot;: string //дата доставки в формате 2017-10-20

&quot;error&quot;: string

}

).


Набор данных с отправлениями можно создать произвольно, взаимодействие с сервисами транспортных компаний эмулировать. Наличие экранных форм приветствуется, но не обязательно. Реализация предполагает решение задачи с использованием основных паттернов ООП. Версия PHP — 7.0+, использование реляционных баз данных возможно, но не обязательно. Модуль должен легко расширяться в контексте транспортных компаний и их входных данных для расчета стоимости доставки.
Решение требуется предоставить в виде исходного кода, готового для развертывания на веб-сервере (приложить файловый архив или ссылку на github, например), при использовании БД приложить дампы созданных таблиц и указать тип и версию использованной БД.
