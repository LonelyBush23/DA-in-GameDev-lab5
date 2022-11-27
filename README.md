# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #4 выполнил(а):
- Деньщик Дарья Дмитриевна
- РИ-210950
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
Ознакомиться с работой перцептрона.

## Задание 1
### В проекте Unity реализовать перцептрон, который умеет производить вычисления:
Ход работы:
- Создайть новый пустой 3D проект на Unity. Добавить EmptyObgect и скрипт Perceptron
![image](https://user-images.githubusercontent.com/104368430/203922880-3d623e7b-1901-4acb-bb48-1aa673750b1f.png)

- Для каждого Element заполняем поле Input и запускаем проект:
 1) OR - понадобилось 4 эпохи для обучкеия, начиная с 5ой эпохи он корректно выполняет вычисления
![image](https://user-images.githubusercontent.com/104368430/203927994-78a46e36-56ec-425f-9bf2-9d95794d0165.png)
![image](https://user-images.githubusercontent.com/104368430/203928752-9cffd4c9-a06a-40cb-be69-92fbdafe4246.png)
![image](https://user-images.githubusercontent.com/104368430/203928802-a9f6ba4a-f0d7-4c9d-8e2c-671aa5f257b8.png)
![image](https://user-images.githubusercontent.com/104368430/203928849-1eb04c07-207d-42a6-b7f8-f27091a1029f.png)
![image](https://user-images.githubusercontent.com/104368430/203928892-1c3a5eaf-1076-41d5-9fab-ffbe4366a119.png)

 2) AND - понадобилось 5 эпох для обучкеия, начиная с 6ой эпохи он корректно выполняет вычисления
![image](https://user-images.githubusercontent.com/104368430/203930371-f328d6a4-4764-41e2-9a9b-4b60b9b13bd1.png)
![image](https://user-images.githubusercontent.com/104368430/203930474-b3ddac6b-64a7-4a07-b321-c02bd4ad4ec8.png)
![image](https://user-images.githubusercontent.com/104368430/203930508-616aed56-8bfd-4d6e-81b3-1214a9a86fdb.png)
![image](https://user-images.githubusercontent.com/104368430/203930551-d4c2ca3b-9136-4b2a-9c58-dbf63b26a976.png)
![image](https://user-images.githubusercontent.com/104368430/203930582-0b6dc10e-42de-4f4f-8197-8b279be182b8.png)

 3) NAND - понадобилось 6 эпох для обучкеия, начиная с 7ой эпохи он корректно выполняет вычисления
![image](https://user-images.githubusercontent.com/104368430/203930915-10d2697f-fbd7-4a27-abe0-4bbd63313d4c.png)
![image](https://user-images.githubusercontent.com/104368430/203930953-6b274b14-e6ee-4a6c-b7a8-db19420217a9.png)
![image](https://user-images.githubusercontent.com/104368430/203930971-7552f463-de3f-4218-83c9-98abaf8c8211.png)
![image](https://user-images.githubusercontent.com/104368430/203930999-83b4c92e-f6bf-4663-9acb-bbb984532d70.png)
![image](https://user-images.githubusercontent.com/104368430/203931021-55ddcb72-8bc8-412c-baa8-b2e7d05478ee.png)

 4) XOR - даже после прохождения 1000 эпох перцептрон не смог обучиться, он некорректно выполняет вычисления
![image](https://user-images.githubusercontent.com/104368430/203931521-0d27d4b5-8b24-4daf-b8ec-7be3a4dcc4d9.png)
![image](https://user-images.githubusercontent.com/104368430/203932711-687b6444-a01c-4018-9926-dd124245792e.png)
![image](https://user-images.githubusercontent.com/104368430/203932890-46e3304a-a911-4d01-accd-ecbdcabc9bdc.png)

## Задание 2
### Построить графики зависимости количества эпох от ошибки обучения. Указать от чего зависит необходимое количество эпох обучения.

![image](https://user-images.githubusercontent.com/104368430/203941457-e88be278-4419-44c9-9bea-72a0e08299a2.png)
необходимое количество эпох обучения зависит от bias (смещение) и weights (вес) =>
```
double DotProductBias(double[] v1, double[] v2) 
	{
		if (v1 == null || v2 == null)
			return -1;
	 
		if (v1.Length != v2.Length)
			return -1;
	 
		double d = 0;
		for (int x = 0; x < v1.Length; x++)
		{
			d += v1[x] * v2[x];
		}

		d += bias;
	 
		return d;
	}

	double CalcOutput(int i)
	{
		double dp = DotProductBias(weights,ts[i].input);
		if(dp > 0) return(1);
		return (0);
	}
```

## Задание 3
### Построить визуальную модель работы перцептрона на сцене Unity. 
Ход работы: 
 - Создадим модель для работы фунции OR. Черные кубы - единицы, белые - нули. Результат работы = результат логического сложения.
  
![image](https://user-images.githubusercontent.com/104368430/203980095-88e12f5d-c187-4358-b992-dbcd3f1c6184.png)
 - Создадим скрипт для изменения цвета при столкновении.

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class ChangeColor : MonoBehaviour
{
    private void OnTriggerEnter(Collider other)
    {
        if (other.gameObject.GetComponent<Renderer>().material.color == Color.white && this.gameObject.GetComponent<Renderer>().material.color == Color.white)
        {
            other.gameObject.GetComponent<Renderer>().material.color = Color.white;
            this.gameObject.GetComponent<Renderer>().material.color = Color.white;
        }
        else
        {
            other.gameObject.GetComponent<Renderer>().material.color = Color.black;
            this.gameObject.GetComponent<Renderer>().material.color = Color.black;
        }
    }
}

```

 - При запуске программы видим, что все работает корректно (цвета кубов правильно меняются в зависимости от выполнения логического сложения)
  
![movie_001](https://user-images.githubusercontent.com/104368430/203983746-7860cde5-f3ca-4371-96ff-e3ca284eb3fa.gif)

## Выводы
В ходе работы я познакомилась с работой перцептрона. Реализовала перцептрон, который умеет производить вычисления для разных логических функций, построила графики зависимостей, а так же визуализировала работу перцептрона на сцене Unity
