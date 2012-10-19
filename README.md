SIP API v1.0 - (C) 2012 www.standart-n.ru

***

Функционал представляет собой прослойку между asterisk'ом и базой firebird<br>
для более гибкой настройки ip-телефонии в программе документооборота Стандарт-Н.

# Использование: #

## sip
Команда sip позволяет найти данные о пользователях по ID их профиля.<br/>
Команда используется при переадресации звонков.<br/>
**пример**:<br/>
`php5 api.php sip -g phone -pid 2,3,5 --t`<br/>
`php5 api.php sip get user profileid 2,3,5 -inc 1`<br/>

## msg
Команда msg позволяет отправить UPD сокет на определенный ip-адрес.<br/>
В параметрах указывается текст сообщения, ip-адрес и порт<br/>
**пример**:<br/>
`php5 api.php msg -s 'hello' -ip 192.168.67.44 -p 80`<br/>

## getip
Команда getip находит в базе компьютер клиента по номеру его телефона и возвращает его ip-адрес<br/>
**пример**:<br/>
`php5 api.php getip -p 4444`<br/>

## updatesrc
Команда в mysql базе в таблице cdr берет посл. строчку и в ней берет номер телефона в поле clid<br/>
и вставляет его в поле src<br/>
**пример**:<br/>
`php5 api.php updatesrc`<br/>

## phone
Команда для удаления пробелов и т.п. символов из номера телефона<br/>
**пример**:<br/>
`php5 api.php phone -s '8 904 316 38 8 4'`<br/>


## Дополнительно:
Параметр --t нужен, чтобы в конце ответа был переход на новую строку.<br/>
При использовании команд в asterisk'e, этот параметр не нужен<br/>
