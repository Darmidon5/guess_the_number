#попытка сделать рекорд более юзабельным
previous_left_border = 0
previous_right_border = 0
# рекорд
score = 1000
# старт
ans = '+'
while ans == '+':
    print('Добро пожаловать в числовую угадайку')


    # Проверка границ на адекватность
    def is_border_valid(num):
        if num.isdigit() != True:
            return False
        return True

    #установление границ
    while True:
        # проверка левой границы на правильность
        print('Введите левую границу промежутка, в котором будет содержаться загаданное число')
        while True:
            left_border = input()
            if is_border_valid(left_border) is False:
                print('Введите, пожалуйста, целое положительное число ')
                continue
            break
        # проверка правой границы на правильность
        print('Введите правую границу промежутка, в котором будет содержаться загаданное число')
        while True:
            right_border = input()
            if is_border_valid(right_border) is False:
                print('Введите, пожалуйста, целое положительное число ')
                continue
            break
        if int(right_border) < int(left_border):
            print('Левая граница должна быть меньше правой')
            continue
        break

    # преобразование границ в рабочий формат
    right_border = int(right_border)
    left_border = int(left_border)

    # создание случайного числа
    import random
    random_number = random.randint(left_border, right_border)

    # счетчик попыток
    counter = 1

    # проверка числа на соответствие промежутку
    def is_valid(num):
        num = str(num)
        if num.isdigit() != True:
            return False
        if int(num) not in range(left_border ,right_border + 1):
            return False
        return True

    # проверка вводимого числа на адекватность
    while True:
        print('Введите число от', left_border, 'до', right_border)
        num = input()
        if is_valid(num) is False:
            print('А может все-таки введем целое число от', left_border, 'до', right_border, '?')
            continue
        break

    # превращение введенного номер из строки в число
    num = int(num)

    # сравнение введенного числа с загаданным
    while num != random_number:
        if num < random_number:
            print('Ваше число меньше загаданного, попробуйте еще разок')
        elif num > random_number:
            print('Ваше число больше загаданного, попробуйте еще разок')
        counter += 1
        num = input()
        while is_valid(num) is False:
            print('Введите целое число, входящее в промежуток от', left_border, 'до', right_border)
            num = input()
        num = int(num)

    #если границы в двух партиях подряд одинаковы, то подсчитывается рекорд
    if left_border == previous_left_border and right_border == previous_right_border:
        if counter <= score:
            score = counter
    else:
        score = counter
    # во избежание грамматических ошибок
    attempt_counter = ''
    if counter % 10 == 1 and counter != 11:
        attempt_counter = 'попытка'
    elif counter % 10 in [2, 3, 4]:
        attempt_counter = 'попытки'
    else:
        attempt_counter = 'попыток'
    attempt_score = ''
    if (counter % 10 == 1 or counter == 1) and counter != 11:
        attempt_score = 'попытка'
    elif counter % 10 in [2, 3, 4] or counter in [2, 3, 4] :
        attempt_score = 'попытки'
    else:
        attempt_score = 'попыток'

    # после победы
    print('Вы угадали, поздравляем!')
    print("Вам потребовалось", counter, attempt_counter)

    # тоже нужно для рекорда
    if left_border == previous_left_border and right_border == previous_right_border:
        print('Ваш рекорд:', score, attempt_score)
    else:
        previous_left_border = left_border
        previous_right_border = right_border

    # перезапуск
    print('Вы хотите сыграть еще? (да = +, нет = -)')
    ans = input()
    while ans not in '+-':
        print("Выберите вариант: да = +, нет = - ")
        ans = input()
    if ans == '-':
        print('Спасибо, что играли в числовую угадайку. Еще увидимся...')