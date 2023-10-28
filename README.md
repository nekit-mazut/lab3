# DAinGD-lab3
# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #3 выполнил(а):
- Дюпин Никита Александрович
- РИ220936
- 
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

## Цель работы
Разработать оптимальный баланс для десяти уровней игры Dragon Picker

## Задание 1
### Предложите вариант изменения найденных переменных для 10 уровней в игре. Визуализируйте изменение уровня сложности в таблице.
Ход работы:
- Были наёдены 4 переменные отвечающие за сложность игры и на основе значений этих переменных для первой сцены, были придуманы и протестированы ещё по 4 значения для переменных для уровней 2-10.

![image](https://github.com/nekit-mazut/lab3/assets/145917921/c77af85e-682e-4209-af7b-289c4d404afc)


## Задание 2
###  Создайте 10 сцен на Unity с изменяющимся уровнем сложности. 
Ход работы:
- Были созданы 9 сцен повторяющих первую кроме переменных "Speed", "TimeBetweenEgg", "LeftRightDistance", "ChanceDirection".

![image](https://github.com/nekit-mazut/lab3/assets/145917921/52f2a5ba-ff34-49fd-a6ef-2f83ec78dd37)


## Задание 3
### Решение в 80+ баллов должно заполнять google-таблицу данными из Python. В Python данные также должны быть визуализированы.
Ход работы:
- Я создала новую таблицу, подключила API и вставила данные, которые получила в первом задании. Также я добавила рандомное число для того, чтобы каждую загрузку слегка отличались значения переменных, но не так сильно, чтобы это слишком влияло на игру.

```py
import gspread
import numpy as np
gc = gspread.service_account(filename='work4-402209-5356a8a03952.json')
sh = gc.open("UnityWorkShop 3")
speed = 4.00
timeEgg = 2.00
lrDist = 10.00
chanceDir = 0.01
i = 0
end = 8
while i <= end:   
    tempRand = np.random.randint(-100, 100, 3)    
    i += 1
    if i == 0:
        continue
    else:        
        sh.sheet1.update(('A' + str(i+2)), speed+2.3*i+(tempRand[0]/1000))
        sh.sheet1.update(('B' + str(i+2)), timeEgg-0.15*i+(tempRand[1]/1000))
        sh.sheet1.update(('C' + str(i+2)), lrDist+0.5*i+(tempRand[2]/1000))
        sh.sheet1.update(('D' + str(i+2)), chanceDir+0.0005*i)
        sh.sheet1.update(('E' + str(i+1)), i)
        print('ok')
```

![image](https://github.com/knightalli/DAinGD-lab3/assets/127225486/6b4ddf02-7a79-489e-8555-17826b373248)


## Выводы

Я создала 10 сцен в игре Dragon Picker, проанализировала входные данные. Попробовала разные изменения переменных и создала уровни с разными сложностями. Ещё раз заполнила таблицу с помощью Python. 


| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
