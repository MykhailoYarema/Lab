# Lab_4
Код програми:

while True:
    
    file_path = input("Введіть шлях до файлу: ")

    try:
      
        with open(file_path, 'r') as f:
            
            total_lines = 0
            empty_lines = 0
            lines_with_z = 0
            z_count = 0
            lines_with_and = 0

           
            for line in f:
                total_lines += 1

               
                if line.strip() == "":
                    empty_lines += 1

               
                if "z" in line:
                    lines_with_z += 1
                    z_count += line.count("z")

               
                if "and" in line:
                    lines_with_and += 1

          
            print(f"Кількість рядків: {total_lines}")
            print(f"Кількість порожніх рядків: {empty_lines}")
            print(f"Кількість рядків з літерою 'z': {lines_with_z}")
            print(f"Кількість літер 'z' у файлі: {z_count}")
            print(f"Кількість рядків з групою символів 'and': {lines_with_and}")

    except FileNotFoundError:
        print("Файл не знайдено.")

  
    choice = input("Хочете проаналізувати інший файл? (y/n): ")
    if choice.lower() != "y":
        break
