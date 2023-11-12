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
> git log --pretty=format:"%h - %ar, %an : %s"

```
52143a4 - 4 minutes ago, CremanTop : В отчёт добавлен лог команд
9ab96a5 - 8 minutes ago, CremanTop : Все изображения перенесены в отчёт
161bebc - 17 minutes ago, CremanTop : Отчёт продолжает оформляться, с исправление переноса строк
ad2cd5c - 29 minutes ago, CremanTop : Начало оформления отчёта
9ef4578 - 59 minutes ago, CremanTop : Revert "Изменён файл mergefile.txt"
45932d2 - 63 minutes ago, CremanTop : Изменён файл mergefile.txt
bb9b79e - 65 minutes ago, CremanTop : Изменён файл new.txt
b727708 - 80 minutes ago, CremanTop : Слияние ветки branch1 с master
54461a0 - 2 hours ago, CremanTop : Create new.txt
921f53b - 3 years ago, Kurtyanik : Обновление информации
0f9f50d - 3 years ago, Kurtyanik : Заполнил файл
c08a654 - 3 years ago, Kurtyanik : Файл создан пустым
3c6e913 - 3 years ago, Kurtyanik : Initial commit
```

## **Вывод**
Изучили базовые возможностей системы управления версиями, получили опыт работы с Git Api и опыт работы с локальным и удаленным репозиторием. 