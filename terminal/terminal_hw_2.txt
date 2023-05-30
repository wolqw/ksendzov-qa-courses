```
Termial. HW_2
1. Сделать папку dir_1:
$ mkdir dir_1

2. Зайти в папку dir_1:
$ cd dir_1

3. Создать папку inner_dir_1:
$ mkdir inner_dir_1

4. Посмотреть где ты находишься:
$ pwd

5. Находясь в папке dir_1 создать пустой текстовый файл tf_1.txt:
$ > tf_1.txt

6. Находясь в папке dir_1 через команду cat создать текстовый файл tf_2.txt со следующими строками:
- the first 1
- the second 2-
- the third 3:
$ cat > tf_2.txt
- the first 1
- the second2--
- the third 3

7. Зайти в папку inner_dir_1:
$ cd inner_dir_1

8.Через cat сделать текстовый файл tf_3.txt  c любыми строками:
$ cat > tf_3.txt
the roses are red
the violets are blue
i got some awesome commit
but can't push it to you

9.Через cat добавить в текстовый файл $tf_3.txt строку  “the second 2”:
$ cat >> tf_3.txt
the second 2

10.Через cat добавить в текстовый файл tf_3.txt строку  “the sec 2”:
$ cat >> tf_3.txt
the sec 3

11.Через cat добавить в текстовый файл tf_2.txt строку “the sec 3”:
$ cat >> ../tf_2.txt
the sec 3

12.Через cat добавить в текстовый файл tf_3.txt строку “the SeCoNd 2”:
$ cat >> tf_3.txt
the SeCoNd 2

13.Через cat добавить в текстовый файл tf_2.txt строку “the seConD 2”:
$ cat >> ../tf_2.txt
the seConD 2

14. Сделать текстовый файл tf_4.txt в котором будет 15 строк.
$ for i in {1..15}; do echo "$i" >> tf_4.txt; done
ИЛИ
$ seq 15 | cat > tf_4.txt

15. Сделать текстовый файл tF_5.txt в котором будет 13 строк.
$ seq 13 | cat > tF_5.txt

16. Вывести список всех файлов в папке.
$ ls -1

17. Выйти из папки inner_dir_1
$ cd ..
18. Вывести содержимое файла tf_3.txt в терминал.
tail -n +1 inner_dir_1/tf_3.txt
или
$ cat inner_dir_1/tf_4.txt

19. Найти путь к файлу tf_4.txt
$ find -name "*tf*"
$ find -name tf_4.txt
$ find -type f -iname "tf_4.txt"

20. Очистить файл tf_4.txt от содержимого без удаления самого файла:
$ > inner_dir_1/tf_4.txt

21. Найти путь к файлам у которых есть “tf” в названии:
$find -type f -name "*tf*"

22. Найти путь к файлам у которых есть “tf” в названии и буквы в любом регистре:
$find -type f -iname "*tf*"
$ find -name "*tf*" -exec sh -c 'grep -iq "[[:lower:]][[:upper:]]\|[[:upper:]][[:lower:]]" {} && echo {}' \;

23. Найти строки в файлах где есть комбинация букв “sec” в текущей папке:
$ grep -r "sec" --include="*.txt"

24. Найти строки в файлах где есть комбинация букв “sec” в любом регистре в текущей папке:
$ grep -in "sec" * - maxdepth 1
$ find . -type f -name "*.txt" -exec grep -i -n "sec" {} \;

25. Найти строки в файлах где есть только комбинация букв “sec” в текущей папке:
$ grep -n 'sec' * - maxdepth 1

26. Найти строки в файлах где есть только комбинация букв “sec” в любом регистре в текущей папке:
$ grep -ni 'sec' * - maxdepth 1

27. Найти строки в файлах где есть комбинация букв “second” в текущей папке:
$ grep -n "second" * - maxdepth 1

28. Найти строки в файлах где есть комбинация букв “second” в любом регистре в текущей папке:
$ grep -ni "second" * - maxdepth 1

29. Найти строки в файлах где есть комбинация букв “second” во всех папках ниже уровнем:
$ grep -n 'second' ./*/

30. Найти только путь и название файла в строках которых есть комбинация букв “second” в текущей папке.
$ grep -l "second" * - maxdepth 1

31. Найти все строки во всех файлах где нет комбинации “second”:
$ grep -rnv "second"

32. Найти только название и путь к файлам где нет комбинации “second”
$ grep -r -l -v second * | xargs realpath

33. Вывести в терминал 4 последних строк любого текстового файла
$ tail -n 4 tf_2.txt

34. Вывести в терминал 4 первые строки любого текстового файла.
$ head -n 4 tf_2.txt

35. Команда в одну строку. Создать папку и создать текстовый файл с содержиммым.
$ mkdir folder1 | echo "just a new line for "$'\n'" 34 group padawans" > folder1/file9.txt
$ mkdir inner_dir_2 && cat >> inner_dir_2/tf_6.txt 

36. Команда в одну строку. Переместить в любую одну папку текстовые файлы у которых в содержимом есть слово “sec”:
$ grep -lr sec ./* | xargs mv --backup=numbered -t ./moved

37. Команда в одну строку. Скопировать в любую одну папку текстовые файлы у которых в содержимом есть слово “sec”
$ grep -lr sec ./* | xargs cp --backup=numbered -t ./copied

38. Команда в одну строку. Найти все строки c “sec” во всех текстовых файлах, скопировать и вставить эти строки в один новый созданный текстовый файл.
$ grep -r -i sec >> sec.txt

39. Команда в одну строку. Удалить текстовые файлы у которых в содержимом есть слово “sec”
$ grep -lr sec | xargs rm
$ grep -rlw sec | xargs rm

40. Просто вывести в терминал строку “Good job!!”
$ name="Good"
echo "${name} job!!"
```

