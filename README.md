import math


def calculate_a_b(x, y, z):
    # Проверка входных данных
    if not (isinstance(x, (int, float)) and isinstance(y, (int, float)) and isinstance(z, (int, float))):
        raise ValueError("x, y и z должны быть числами.")

    if x <= 1 or 1 + math.log10(1 + y) == 0:
        raise ValueError("x должен быть больше 1 и log10(1+y) не должен быть -1.")

    # Вычисление a и b
    a = math.sqrt(5 / (x - 1)) / (math.sin(x) + math.log10(1 + y))
    b = math.sin(math.sqrt(z + 7)) + math.cos(math.sqrt(5)) + math.sqrt(x) + math.sqrt(y)

    return a, b


# Примеры использования:
try:
    x = float(input("Введите x: "))
    y = float(input("Введите y: "))
    z = float(input("Введите z: "))
    a, b = calculate_a_b(x, y, z)
    print(f"a = {a}, b = {b}")
except ValueError as e:
    print(f"Ошибка: {e}")
