# Lab_4
Код програми:
file_name = "example.txt"
with open(file_name, 'r') as file:
    lines = file.readlines()
    num_lines = len(lines)
    print("Кількість рядків:", num_lines)
    num_empty_lines = lines.count('\n')
    print("Кількість порожніх рядків", num_empty_lines)
    num_lines_with_z = 0
    for line in lines:
        if 'z' in line:
            num_lines_with_z += 1
    print("Кількість рядків з літерою \"z\":", num_lines_with_z)
    num_z = ''.join(lines).count('z')
    print("Кількість літер \"z\" у файлі", num_z)
    num_lines_with_and = 0
    for line in lines:
        if 'and' in line:
            num_lines_with_and += 1
    print("Кількість рядків з групою символів \"and\":", num_lines_with_and)
