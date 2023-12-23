# 📌 bash common commands

## Task 1
#### Working with files and directories
```bash
1. Открыть домашнюю директорию
$ cd # если трактовать задание буквально
$ cd ~/OneDrive/Рабочий\ стол/IT/TESTING/CORE_training # если суть задания - перейти в папку, привязанную к репозиторию

2. Определить имя папки, в которой вы находитесь
$ pwd

3. Создать внутри этой папки каталог с именем test1
$ mkdir test1

4. Перейти в папку test1
$ cd test1

5. Создать файл 1,2 и 3 внутри каталога test1
$ touch 1 2 3 

6. Проверить содержимое каталога test1
echo "Содержимое каталога test1:"; ls

7. Перейти в домашнюю директорию
$ cd # если трактовать задание буквально
$ cd .. # в данном случае рабочая директория находится выше в иерахии каталогов

8. Создать папку test2 внутри домашней директории
$ mkdir test2

9. Удалить папку test2
$ rmdir test2

10. Удалить файл 2 из папки test1
$ rm test1/2

11. Создать папку в домашней директории test3 и добавить в нее два файла
$ mkdir test3; touch test3/file1 test3/file2

12. Удалить папку test3
rm -r test3

13. Создать папку test4 в домашней директории
$ mkdir test4

14. Переместить файлы 1 и 3 из папки test1 в папку test4
$ mv test1/1 test1/3 test4

15. Добавить в файл 1 три строки со словами line
$ echo -e "line1\nline2\nline3" >> test4/1

16. Посмотреть содержимое файла 1
$  echo "Содержимое файла 1:"; cat test4/1

17. Добавьте в файл 3 три строки со словами line
$ echo -e "line1\nline2\nline3" >> test4/3

18. Просмотрите содержимое двух файлов (1 и 3) сразу
$ echo "Содержимое файлов 1 и 3:"; cat test4/1 test4/3

19. Используя один из редакторов замените все строки в файле 1
$ nano test4/1 # далее - вручную заменить все строки
# OR
$ sed -i -e '1s/.*/Это новая строка 1/' -e '2s/.*/Это новая строка 2/' -e '3s/.*/Это новая строка 3/' test4/1
```

## Task 2
#### Editing files, checking and killing proccesses, pinging websites
```bash
1. Зайти в домашнюю директорию
$ cd # если трактовать задание буквально
$ cd ~/OneDrive/Рабочий\ стол/IT/TESTING/CORE_training # если суть задания - перейти в папку, привязанную к репозиторию

2. Создать папку test 3 # полагаю, речь идёт о создании папки test3
$ mkdir test3

3. Добавить в папку test 3 три файла 4, 5 и 6, в каждом из которых должно быть по 4 строки row1, row2, row3, row4
for i in {4..6}; do
  echo -e "row1\nrow2\nrow3\nrow4" > test3/$i
done

4. Найдите строку row2 в файле 5
$ grep "row2" test3/5

5. Найдите строку row в папке test3
$ grep -r "row2" test3

6. Посчитайте сколько строк с содержимым row в файле 6
$ grep -c "row" test3/6

7. Найдите файл 5 внутри папки test3
$ find test3 -name 5

8. Используя команду find, удалите файл 5
$ find test3 -name 5 -exec rm {} \; # удаляет только файл с именем "5"
# OR
$ find test3 -type f -name "5" -delete # удаляет только файл с именем "5"
# OR
$ find test3 -name "5" -delete # может удалить как файл так и директорию с именем "5"

9. Используя команду echo, добавьте слово test в файл 4
$ echo "test" > test3/4 # добавление производится поверх всего содержимого файла
# OR
$ echo "test" >> test3/4 # добавление производится к текущему содержимому файла, без затирки

10. Замените слово test в файле 4 на fail
$ sed -i "s/test/fail/g" test3/4

11. Добавьте в файл 4 слово test так, чтобы сохранилось содержимое
$ echo "test" >> test3/4

12. Просмотрите все процессы для юзеров не только в консоли, которые происходят в системе
$ ps all
# OR
$ ps aux

13. Убейте процесс 666 в консоли
$ kill 666

14. Узнайте доступность ресурса artsiomrusau.com, используя ping
$ ping artsiomrusau.com

15. Отправьте 5 пакетов на сайт artsiomrusau.com
$ ping -c 5 artsiomrusau.com

16. Используя GET и команду curl, получите информацию о зарегистрированных питомцах на https://petstore.swagger.io/
$ curl https://petstore.swagger.io/v2/pet/findByStatus?status=available # по умолчанию curl выполняет GET-запрос
#OR
$ curl -X GET https://petstore.swagger.io/v2/pet/findByStatus?status=available

17. Используя POST и команду curl, создайте нового пользователя на https://petstore.swagger.io/
$ curl -X POST -H "Content-Type: application/json" -d '{"id": 321, "username": "LeoCrane", "firstName": "Leo", "lastName": "Crane", "email": "leocrane@example.com", "password": "qwerty123", "phone": "202030304040"}' https://petstore.swagger.io/v2/user

```
