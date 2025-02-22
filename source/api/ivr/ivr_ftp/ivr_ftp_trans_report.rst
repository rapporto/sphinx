Отчет о выполненных операциях
===================================

После выполнения операций, например, создания рассылки, создается текстовый файл в следующем формате:

* кодировка Windows-1251;
* в файле между заголовком с параметрами и описанием ошибок пустая строка.

Пример файла:

.. code-block:: 

    Наименование операции («создание рассылки»)
    Дата/время операции (в формате YYYY-MM-DD HH:MI:SS)
    Результат операции (возможные значения: Success/Fail)

    Описание ошибки (номер телефона в строке с ошибкой, если результат операции *Success*).


При результате операции *Success* некоторые строки исходного файла могут не загрузиться. Возможные причины:

* номер в черном списке;
* дубликат номера в файле;
* неверный номер;
* ошибочный формат строки файла.

.. note:: Если в файле содержатся одинаковые номера телефонов, обработан будет только первый встречающийся в списке. Остальные номера будут отклонены системой.

Если результат операции *Fail*, то загрузка не выполнена. Описание ошибки указывает на причину, например:

* значение параметра *name* отсутствует или параметр не найден;
* значение параметра *service_number* отсутствует или параметр не найден;
* некорректное значение параметра *date_start=10.03.2020*. Допустимый формат: yyyy-MM-dd;
* некорректный интервал: *time_end=22:00* больше значения *time_begin=21:00*, заданного в пользовательских настройках.
