import random

print("=== SYMULATOR MISJI ŁAZIKA ===")
print("Twoim zadaniem jest dotrzeć do bazy badawczej.\n")

# Parametry od użytkownika
nazwa = input("Podaj nazwę łazika: ")
energia = int(input("Podaj początkową energię (np. 100): "))
zapasy = int(input("Podaj ilość zapasów (np. 50): "))

# Pozycja początkowa
x = 0
y = 0

# Cel wyprawy
cel_x = random.randint(5, 10)
cel_y = random.randint(5, 10)

tura = 0
przebyta_droga = 0
odkrycia = 0

print("\n--- START WYPRAWY ---")
print(f"Łazik {nazwa} startuje z punktu ({x}, {y})")
print(f"Cel misji znajduje się gdzieś w pobliżu ({cel_x}, {cel_y})")
print()

while energia > 0 and zapasy > 0:

# RAPORT KOŃCOWY
print("\n========================")
print("KONIEC WYPRAWY")
print("========================")

if energia <= 0:
    print("Łazik zatrzymał się - brak energii.")

elif zapasy <= 0:
    print("Łazik zakończył misję - brak zapasów.")

else:
    print("Misja zakończona sukcesem!")

print("\n--- RAPORT ---")
print(f"Nazwa łazika: {nazwa}")
print(f"Liczba tur: {tura}")
print(f"Końcowa pozycja: ({x}, {y})")
print(f"Pozostała energia: {energia}")
print(f"Pozostałe zapasy: {zapasy}")
print(f"Przebyta droga: {przebyta_droga}")
print(f"Odkryte minerały: {odkrycia}")

print("\nDziękujemy za udział w misji.")
