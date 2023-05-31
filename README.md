# Lab_6

Код програми:

import math

#Запитуємо користувача про завдання та їх оцінки

tasks = []
while True:
    a = float(input("Введіть оцінку a для завдання: "))
    m = float(input("Введіть оцінку m для завдання: "))
    b = float(input("Введіть оцінку b для завдання: "))
    tasks.append((a, m, b))
    more_tasks = input("Хочете додати ще завдання? (y/n): ")
    if more_tasks.lower() == 'n':
        break

#Обчислюємо оцінки та стандартні відхилення для кожного завдання

estimates = []
for task in tasks:
    a, m, b = task
    e = (a + 4 * m + b) / 6
    sd = (b - a) / 6
    estimates.append((e, sd))

#Обчислюємо оцінку та стандартне відхилення для проекту

project_e = sum([e[0] for e in estimates])
project_sd = math.sqrt(sum([e[1]**2 for e in estimates]))

#Обчислюємо довірчий інтервал для проекту

ci_min = project_e - 2 * project_sd
ci_max = project_e + 2 * project_sd

#Виводимо результат

print("Project's 95% confidence interval: {} ... {} points".format(ci_min, ci_max))
