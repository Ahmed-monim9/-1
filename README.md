import pandas as pd
import random

# Функция для генерации случайных данных
def generate_employee_data(num_employees):
    first_names = ['Алексей', 'Мария', 'Иван', 'Ольга', 'Дмитрий', 'Анна', 'Евгений', 'Татьяна', 'Андрей', 'Елена']
    last_names = ['Иванов', 'Петров', 'Сидоров', 'Кузнецов', 'Попов', 'Смирнов', 'Морозов', 'Волков', 'Соколов', 'Лебедев']
    positions = ['Кассир', 'Менеджер', 'Аналитик', 'Операционист', 'Консультант', 'Охранник', 'Бухгалтер', 'Кредитный специалист']
    
    data = []
    for i in range(1, num_employees + 1):
        full_name = f"{random.choice(first_names)} {random.choice(last_names)}"
        position = random.choice(positions)
        age = random.randint(22, 60)
        salary = random.randint(40000, 120000)
        data.append([i, full_name, position, age, salary])
    
    return data

# Генерация данных для 25 сотрудников
employee_data = generate_employee_data(25)

# Создание DataFrame
df = pd.DataFrame(employee_data, columns=["ID Сотрудника", "ФИО", "Должность", "Возраст", "Зарплата (руб.)"])

# Сохранение данных в CSV-файл
file_path = "/mnt/data/employee_data.csv"
df.to_csv(file_path, index=False)

file_path
