# Ksendzov_Git_branches_HW_2
>## 1. На локальном репозитории сделать ветки для:
- Postman
- Jmeter
- CheckLists
- Bag Reports
- SQL
- Charles
- Mobile testing

```
Create Github repo branches_hw_git_2
$ git clone https://github.com/wolqw/branches_hw_git_2.git
$ git branch Postman     
$ git branch Jmeter 
$ git branch Bag_Reports
$ git branch SQL
$ git branch CheckLists
$ git branch Charles
$ git branch Mobile_testing
$ git add .
$ git commit -m "pushbranches"
```

>## 2. Запушить все ветки на внешний репозиторий
```
$ git push -u origin master Bag_Reports Charles SQL Postman Mobile_testing Jmeter CheckLists
```
>## 3. В ветке Bag Reports сделать текстовый документ со структурой баг репорта
```
$ git checkout Bag_Reports | cat >> bugreport_id_1.txt
Title
Description
StepsToReproduce
ExpectResult
ActualResult
Attachment
```

>## 4. Запушить структуру багрепорта на внешний репозиторий.
```
$ git add.
$ git commit -m "bug"
$ git push
```
>## 5. Вмержить ветку Bag Reports в Main.
```
$ git checkout -
$ git merge Bag_Reports
```
>## 6. Запушить main на внешний репозиторий.
```
$ git push
```
>## 7. В ветке CheckLists набросать структуру чек листа.
```
$ git checkout CheckLists
$ cat > Checklist_1.txt
title | envioriment | STR | EX | result check box | bugreport link
```

>## 8. Запушить структуру на внешний репозиторий.
```
$ git add .
$ git commit -m "checklist"
$ git push
```
>## 9. На внешнем репозитории сделать Pull Request ветки CheckLists в main.
```
После пуша check_list.txt на локальный репозиторий ветки CheckLists ,появляется зеленая кнопка Compare&pull requset.	
```

>## 10. Синхронизировать Внешнюю и Локальную ветки Main.
```
git pull
```
