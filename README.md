# LR6
## **Цель лабораторной работы**
Изучение базовых возможностей системы управления версиями, опыт работы с Git Api, опыт работы с локальным и удаленным репозиторием. 

## **Ход работы**
Сначала был создан форк репозитория лабораторной работы. Он клонирован в локальный репозиторий (см. рис. 1).  

Далее в интерфейсе GitHub был создан файл **new.txt** (см. рис. 2) и эти изменения извлечены в локальный репозиторий командами _fetch_ и _merge_ (см рис. 3)  

Следующим шагом на рисунках 4, 5 и 6 показана история веток **master**, **branch1** и изменения последнего коммита, соответственно.  

Далее совершено слияние веток **master** и **branch1** (см. рис. 7). Произошёл конфликт слияния в файле **mergefile.txt**, показан на рисунке 8. Результат после исправление кофликта на рисунке 9.  

После этого ветка **branch1** была удалена (см. рис. 10) и это изменение отправлено в удалённый репозиторий (см. рис. 11).  

Сделано несколько коммитов с изменениями в файлах **new.txt** и **mergefile.txt** (см. рис. 12). Последний из этих коммитов отменён командой _revert_.  

Создана ветка **report** для отчёта по работе (см. рис. 13).  

## **Лог команд**
```
git clone https://github.com/CremanTop/LR6
cd LR6
git fetch
git merge
git log
git checkout branch1
git log
git checkout master
git log -n 1 -p
git merge branch1
git status
git add mergefile.txt
git commit -m “Слияние ветки branch1 с master”
git push origin master
git branch -d branch1
git push origin :branch1
git status
git add new.txt
git commit -m “Изменён файл new.txt”
git status
git add mergefile.txt
git commit -m “Изменён файл mergefile.txt”
git revert HEAD
git push origin master
git branch report
git checkout report
git add README.md
git add image/
git commit -m "Начало оформления отчёта"
git push origin report
git add README.md
git add image/
git commit -m "Отчёт продолжает оформляться, с исправление переноса строк"
git push origin report
git add image/
git commit -m "Все изображения перенесены в отчёт"
git push origin report
```

## **Форматированная история операция**

Выведена с использованием команды:
> git log --pretty=format:"%h - %ad, %an : %s"

```
333b097 - Sun Nov 12 16:18:57 2023 +0300, CremanTop : Финальная фиксация. В отчёт добавлен форматированный лог команд и вывод
52143a4 - Sun Nov 12 16:11:17 2023 +0300, CremanTop : В отчёт добавлен лог команд
9ab96a5 - Sun Nov 12 16:06:59 2023 +0300, CremanTop : Все изображения перенесены в отчёт
161bebc - Sun Nov 12 15:58:22 2023 +0300, CremanTop : Отчёт продолжает оформляться, с исправление переноса строк
ad2cd5c - Sun Nov 12 15:45:45 2023 +0300, CremanTop : Начало оформления отчёта
9ef4578 - Sun Nov 12 15:16:11 2023 +0300, CremanTop : Revert "Изменён файл mergefile.txt"
45932d2 - Sun Nov 12 15:11:37 2023 +0300, CremanTop : Изменён файл mergefile.txt
bb9b79e - Sun Nov 12 15:09:58 2023 +0300, CremanTop : Изменён файл new.txt
b727708 - Sun Nov 12 14:54:37 2023 +0300, CremanTop : Слияние ветки branch1 с master
54461a0 - Sun Nov 12 14:34:24 2023 +0300, CremanTop : Create new.txt
921f53b - Sat Nov 21 20:09:49 2020 +0300, Kurtyanik : Обновление информации
0f9f50d - Sat Nov 21 20:08:33 2020 +0300, Kurtyanik : Заполнил файл
c08a654 - Sat Nov 21 20:02:16 2020 +0300, Kurtyanik : Файл создан пустым
3c6e913 - Sat Nov 21 19:58:20 2020 +0300, Kurtyanik : Initial commit
```

## **Вывод**
Изучили базовые возможностей системы управления версиями, получили опыт работы с Git Api и опыт работы с локальным и удаленным репозиторием. 