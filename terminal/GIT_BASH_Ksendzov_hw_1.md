 #Юрий Волков 34 Группа @tomkcat#
```Javascript
Первая часть первого ДЗ
Linux terminal (GitBash) commands


1) Посмотреть где я
"pwd" (print working directory)
2) Создать папку
mkdir papka
3) Зайти в папку
cd  papka
4) Создать 3 папки
mkdir folder_1 folder_2 folder_3
5) Зайти в любую папку
cd folder_3
6) Создать 5 файлов (3 txt, 2 json)
touch file1.txt file2.txt file3.txt file4.json file5.json
7) Создать 3 папки
mkdir folder_4 folder_5 folder_6
8) Вывести список содержимого папки
ls -la
9) + Открыть любой txt файл
vim file1.txt
10) + написать туда что-нибудь, любой текст.
Нажать клавишу `i`
Privet this is 34 group
my name is YuraQA
my tg name is @tomkcat
nice to meet you
Privet this is 34 group
my name is YuraQA
my tg name is @tomkcat
nice to meet you
Privet this is 34 group
my name is YuraQA
my tg name is @tomkcat
nice to meet you
11) + сохранить и выйти.
нажать ESC
:wq + enter
12) Выйти из папки на уровень выше
cd ..
—
13) переместить любые 2 файла, которые вы создали, в любую другую папку.
mv folder_3/file1.txt folder_3/file5.json folder_2
14) скопировать любые 2 файла, которые вы создали, в любую другую папку.
cp folder_3/file3.txt folder_3/file4.json folder_1
15) Найти файл по имени
find -name file4.json
16) просмотреть содержимое в реальном времени (команда grep) изучите как она работает.
tail -n +1 -f my_file.txt
grep "." folder_2/file1.txt
17) вывести несколько первых строк из текстового файла
head -n 2 folder_2/file1.txt
18) вывести несколько последних строк из текстового файла
tail -n 2 folder_2/file1.txt
19) просмотреть содержимое длинного файла (команда less) изучите как она работает.
less folder_2/file1.txt
20) вывести дату и время
date +'ДАТА: %Y-%m-%d  ВРЕМЯ GMT+3 %H часов %M минут %S секунд'
=========
Задание *
1) Отправить http запрос на сервер.
http://162.55.220.72:5005/terminal-hw-request

curl -v  http://162.55.220.72:5006/terminal-hw-request
curl http://162.55.220.72:5006/get_method?name=Yuri_@tomkcat&age=33


2) Написать скрипт, который выполнит автоматически пункты 3, 4, 5, 6, 7, 8, 13
touch scr.sh
(if u use linux - chmod a+x scr.sh)
vim scr.sh
нажать i

#!/bin/bash
#3) Зайти в папку
cd papka
#4) Создать 3 папки
mkdir fldr_1 fldr_2 fldr_3
# 5) Зайти в любую папку
cd fldr_3
# 6) Создать 5 файлов (3 txt, 2 json)
touch file1.txt file2.txt file3.txt file4.json file5.json
# 7) Создать 3 папки
mkdir fldr_4 fldr_5 fldr_6
# 8) Вывести список содержимого папки
ls -la
#13) переместить любые 2 файла, которые вы создали, в любую другую папку.
cd ..
mv fldr_3/file1.txt fldr_3/file5.json fldr_2/

нажать
esc
:wq


```
