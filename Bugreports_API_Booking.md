####  Багрепорт по результатам  тестирования API https://restful-booker.herokuapp.com/apidoc/index.html

## #Bug 1
	
#### Описание	
В поле "totalprice" записывается «1»  при  вводе больших значений при создании нового пользователя
	
#### Шаги воспроизведения	
1) отправляем запрос на создание нового пользователя по ссылке url = "https://restful-booker.herokuapp.com/booking/" с полем  "totalprice" равным 1000000000000000000000

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/11.jpg)

2) получаем ответ системы, в котором поле"totalprice"  = 1

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/12.jpg)
	
	
#### Фактический результат	
В поле "totalprice" при создании нового пользователя выводится значение 1

#### Ожидаемый результат 	
Выводится сообщение об ошибке

## #Bug 2
	
#### Описание	
В поле "totalprice" записываются отрицательные значения  при создании нового пользователя
	
#### Шаги воспроизведения	
1) отправляем запрос на создание нового пользователя по ссылке url = "https://restful-booker.herokuapp.com/booking/" с полем  "totalprice" равным -99

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/21.jpg)

2) получаем ответ системы, в котором поле"totalprice"  = -99

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/22.jpg)
	
	
#### Фактический результат	
В поле "totalprice" при создании нового пользователя выводится значение -99
	
#### Ожидаемый результат 	
Выводится сообщение об ошибке

## #Bug 3
	
#### Описание	
Система принимает поле "chekin" более поздней даты чем поле "chekout" при создании нового пользователя
	
#### Шаги воспроизведения	
1) отправляем запрос на создание нового пользователя по ссылке url = "https://restful-booker.herokuapp.com/booking/" с полями "checkin": "2023-05-25", "checkout": "2020-03-20"

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/31.jpg)

2) система принимает эти данные 

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/32.jpg)
	
	
#### Фактический результат	
Система принимает поле "chekin" более поздней даты чем поле "chekout"

#### Ожидаемый результат 	
Выводится сообщение об ошибке

## #Bug 4
	
#### Описание	
Система выдает некорректную дату по  полям "chekin" и "chekout" при вводе числа(положительного, отрицательного, дробного, нуля при создании нового пользователя
	
#### Шаги воспроизведения	
1) отправляем запрос на создание нового пользователя по ссылке url = "https://restful-booker.herokuapp.com/booking/" с полем "checkin": 500, "checkout": "2020-03-20"

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/41.jpg)

2) система выдает в ответ 

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/42.jpg)
	
	
#### Фактический результат	
При воде числа  в поля "chekin" "chekout" в соответствующем поле записывается дата 1970-01-01 (для нуля и положительных чисел) или 1969-12-31 (для отрицательных)

#### Ожидаемый результат 	
Выводится сообщение об ошибке

## #Bug 5
	
#### Описание	
Система принимает невалидные данные по  полям "chekin" и "chekout" при вводе пробела при создании нового пользователя
	
#### Шаги воспроизведения	
1) 1 отправляем запрос на создание нового пользователя по ссылке url = "https://restful-booker.herokuapp.com/booking/" с полем "checkin":"  " , "checkout": "2020-03-20"

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/51.jpg)

2) система выдает в ответ 

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/52.jpg)
	
	
#### Фактический результат	
При воде невалидных данных  в поля "chekin" "chekout" система записывает в соответствующем поле "0NaN-aN-aN" (указание на нечисловое значение)

#### Ожидаемый результат 	
Выводится сообщение об ошибке

## #Bug 6
	
#### Описание	
Система принимает невалидные данные по  полям  "firstname" и "lastname" при вводе 0 при создании нового пользователя
	
#### Шаги воспроизведения	
1) 1 отправляем запрос на создание нового пользователя по ссылке url = "https://restful-booker.herokuapp.com/booking/" с полем "firsname"= 0 

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/61.jpg)

2) система выдает в ответ 

![](https://github.com/OlgaOFrolova/API_Restfull_booker_tests_documentation/blob/pictures_for_bugreports/62.jpg)
	
	
#### Фактический результат	
При воде невалидных данных  в поля"firstname" и "lastname" система записывает в соответствующем поле не строковое значение 0

#### Ожидаемый результат 	
Выводится сообщение об ошибке
