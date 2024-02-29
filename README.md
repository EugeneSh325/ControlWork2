# ControlWork2
file = open('file.txt', 'a')
file.close()

def read_direct():
    file = open('file.txt', 'r')
    list_direct = file.readlines()
    list_direct_end = []
    for i in list_direct:
        i = i_split('/')
        list_direct_end.append(i)
        list_direct_end.append(' ')
    file.close()
    return list_direct_end
def append_contakt():
    file = open('file.txt', 'a')
    print("Пример добавления контакта: Иванов Иван Иванович / +7-914-000-00-00 / Сотрудник")
    contakt = input("")
    file.writelines(contakt)
    file.close()
def check_contakt(list1, check):
    list_cheks = []
    for i in range(len(list1)):
        if list1[i] == check:
            list_cheks.append(list1[i])
            list_cheks.append(list1[i+1])
            list_cheks.append(list1[i+2])
    return list_cheks
def change_file(list1):
    file = open('file.txt', 'w')
    for i in range(len(list1)):
        end_string = list1[i] + '/' + list[i + 1] + '/' + list1[i + 2]
        file.writelines(end_string)
    file.close()
def change_direct(list1):
    change = input("Введите фамилию и имя, которые хотите изменить: ")
    changeble = input("Пример изменения: Иванов Иван Иванович / +7-914-000-00-00/ сотрудник")
    changeble_list = changeble.split('/')
    for i in range(len(list1)):
        if list1[i] == change:
            list1[i] = changeble_list[0]
            list[i + 1] = changeble_list[1]
            list[i + 2] = changeble_list[2]
    return list1
def delete_element(list1: list):
    delete_element = input("Введите имя отчество и фамилию, которые хотите удалить: ")

def main():
    print("Выберите действие: \n 1.Показать все контакты \n 2.Добавить контакты \n 3.Поиск контакта \n 4.Изменение контакта \n 5.Удаление контакта")
    check = int(input(" "))
    if check == 1:
        list_direct = read_direct()
        for i in list_direct:
            print(i)
    elif check == 2:
        append_contakt()
    elif check == 3:
        list_direct = read_direct()
        checking = input("Какую фамилию вы хотите найти: ")
        list_checks = check_contakt(list_direct, checking)
        if len(list_checks) > 0:
            for i in list_checks:
                print(i)
        else:
            print("Такого контакта не существует")
    elif check == 4:
        list_direct = read_direct()
        new_list_direck = change_direct(list_direct)
        change_file(new_list_direck)
    elif check == 5:
        555
    else:
        print("Вы ввели неправильное число, такой команды нет")
