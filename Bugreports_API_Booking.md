####  Багрепорт по результатам  тестирования API https://restful-booker.herokuapp.com/apidoc/index.html

## Bug1
	
#### Описание	
В поле "totalprice" записывается «1»  при  вводе больших значений при создании нового пользователя
	
#### Шаги воспроизведения	
1) отправляем запрос на создание нового пользователя по ссылке url = "https://restful-booker.herokuapp.com/booking/", с полем  "totalprice" равным 1000000000000000000000

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/11.jpg)

2) получаем ответ системы, в котором поле"totalprice"  = 1

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/12.jpg)
	
	
#### Фактический результат	
В поле "totalprice" при создании нового пользователя выводится значение 1

#### Ожидаемый результат 	
Выводится сообщение об ошибке

## Bug2
	
#### Описание	
В поле "totalprice" записываются отрицательные значения  при создании нового пользователя
	
#### Шаги воспроизведения	
1) отправляем запрос на создание нового пользователя по ссылке url = "https://restful-booker.herokuapp.com/booking/", с полем  "totalprice" равным -99

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/21.jpg)

2) получаем ответ системы, в котором поле"totalprice"  = -99

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/22.jpg)
	
	
#### Фактический результат	
В поле "totalprice" при создании нового пользователя выводится значение -99
	
#### Ожидаемый результат 	
Выводится сообщение об ошибке

## Bug3
	
#### Описание	
Система принимает поле "chekin" более поздней даты чем поле "chekout" при создании нового пользователя
	
#### Шаги воспроизведения	
1) отправляем запрос на создание нового пользователя по ссылке url = "https://restful-booker.herokuapp.com/booking/", с полями "checkin": "2023-05-25", "checkout": "2020-03-20"

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/31.jpg)

2) система принимает эти данные 

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/32.jpg)
	
	
#### Фактический результат	
Система принимает поле "chekin" более поздней даты чем поле "chekout"

#### Ожидаемый результат 	
Выводится сообщение об ошибке