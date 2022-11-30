# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #5 выполнил(а):
- Деньщик Дарья Дмитриевна
- РИ-210950
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 80 |
| Задание 2 | * | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
Научиться интегрировать экономическую систему в проект Unity и обучать ML-Agent.

## Задание 1
### Измените параметры файла. yaml-агента и определить какие параметры икак влияют на обучение модели.
Ход работы:
- Установить все библиотеки и обучить ML-Agent
![image](https://user-images.githubusercontent.com/104368430/204712113-6413d3da-17f2-468a-a545-54710509eb94.png)
- Полуить графики:
![image](https://user-images.githubusercontent.com/104368430/204712945-3595cd9d-e5ec-4584-98b4-01feb7df6a76.png)
![image](https://user-images.githubusercontent.com/104368430/204712975-21436605-68e6-4e52-8e9f-a2bb402710da.png)
- После я изменила параметры файла. yaml-агента и выяснила, какие параметры и как влияют на обучение модели:

1) num_epochs - Количество проходов через буфер опыта во время градиентного спуска. Если не указано, то по умолчанию будет указано количество эпох, установленное для PPO. Уменьшение этого параметра обеспечит более стабильные обновления за счет более медленного обучения. (значения от 3 до 10)

После изменения этого параметра 3 -> 8
![image](https://user-images.githubusercontent.com/104368430/204717273-b12ad904-6fcf-41af-8dc2-d13894adb437.png)
![image](https://user-images.githubusercontent.com/104368430/204717387-b17b2690-81c0-497c-938e-c2ef6d2bb5da.png)

2) learnin_rate - Начальная скорость обучения для градиентного спуска. Обычно это значение следует уменьшить, если тренировка нестабильна, а вознаграждение не увеличивается последовательно. (значения от 1e-5 до 1e-3)

3) epsilon - Соответствует допустимому порогу расхождения между старой и новой политиками обучения при обновлении с градиентным спуском. Установка этого значения небольшим приведет к более стабильным обновлениям, но также замедлит процесс обучения. (значения от 0.1 до 0.3)

После изменения этого параметра 0.2 -> 0.3


4) save_steps - Количество шагов тренажера между моментальными снимками (снапшотами) текущей политики обучения.

5) beta - Сила регуляризации энтропии. beta-значение должно быть скорректировано таким образом, чтобы энтропия (можно посмотреть в TensorBoard) медленно уменьшалась вместе с увеличением вознаграждения.

6) num_layers - Количество скрытых слоев в нейронной сети. Для простых задач меньшее количество слоев, скорее всего, будет обучаться быстрее и эффективнее. Для более сложных задач управления может потребоваться больше уровней. (значения от 1 до 3)

7) lambd - (по умолчанию = 0,95) Параметр регуляризации (лямбда), используемый при расчете обобщенной оценки преимущества (GAE). Это можно рассматривать как то, насколько агент полагается на свою текущую оценку стоимости при расчете обновленной оценки стоимости. Низкие значения соответствуют тому, что вы больше полагаетесь на текущую оценку ценности (что может быть большой погрешностью), а высокие значения соответствуют тому, что вы больше полагаетесь на фактические вознаграждения, полученные в окружающей среде (что может быть высокой дисперсией). Параметр обеспечивает компромисс между ними, и правильное значение может привести к более стабильному процессу обучения.

## Задание 2
### Опишите результаты, выведенные в TensorBoard. 



## Выводы
В ходе работы я познакомилась с работой перцептрона. Реализовала перцептрон, который умеет производить вычисления для разных логических функций, построила графики зависимостей, а так же визуализировала работу перцептрона на сцене Unity
