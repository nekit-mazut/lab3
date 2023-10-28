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

![image](https://github.com/nekit-mazut/lab3/assets/145917921/ffc335dc-11de-4db8-8b78-7a5f6a5a82c1)

## Задание 2
###  Создайте 10 сцен на Unity с изменяющимся уровнем сложности. 
Ход работы:
- Были созданы 9 сцен повторяющих первую кроме переменных "Speed", "TimeBetweenEgg", "LeftRightDistance", "ChanceDirection".
  
![image](https://github.com/nekit-mazut/lab3/assets/145917921/c80ec28a-874a-4c25-8393-7ad7b1ecc9e4)

## Задание 3
### Решение в 80+ баллов должно заполнять google-таблицу данными из Python. В Python данные также должны быть визуализированы.
Ход работы:
- Был оформлен код Python, который по API в ранее созданную таблицу добавляет ранее определённые значения для разных уровней сложности. Также была оформлена диаграмма-график.

```py
import gspread
import numpy as np
gc = gspread.service_account(filename='primeval-jet-400706-64d34c322687.json')
sh = gc.open("lab2")
speed = 4.00
timeEgg = 2.00
lrDist = 10.00
chanceDir = 0.01
i = 0
end = 9

sh.sheet1.update(('B' + str(2)), speed)

sh.sheet1.update(('C' + str(2)), timeEgg)

sh.sheet1.update(('D' + str(2)), lrDist)

sh.sheet1.update(('E' + str(2)), chanceDir)

sh.sheet1.update(('A' + str(2)), 1)
        
while i < end:   
    i += 1

    sh.sheet1.update(('B' + str(i+2)), speed*1.25**(i))
    
    sh.sheet1.update(('C' + str(i+2)), timeEgg*0.8**(i))
    
    sh.sheet1.update(('D' + str(i+2)), lrDist*1.05**(i))
    
    sh.sheet1.update(('E' + str(i+2)), chanceDir*1.1**(i))
    
    sh.sheet1.update(('A' + str(i+2)), i+1)
    
    print("^_^")
```

![image](https://github.com/nekit-mazut/lab3/assets/145917921/066e9f38-3251-4f5f-bc0f-490f4e7a852b)


## Выводы

По итогу работы, я научился работать с gspread и готовыми проектами в unity.


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
