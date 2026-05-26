import random

def gra():

    print("\n=== SYMULATOR WYPRAWY ŁAZIKA ===")

    try:
        x = int(input("Pozycja startowa 
        y = int(input("Pozycja startowa 
    except:
        x = 0
        y = 0
        print("Błąd → ustawiono (0,0)")

    try:
        energia = 
    except:
        energia = 100

    poziom = input(
        "Poziom trudności (łatwy/trudny): "
    ).lower()

    limit = 20 if poziom=="łatwy" else 12

    print("\n=== PARAMETRY ===")
    print("Świat: od -10 do 10")
    print("Cel: dotrzeć do bazy (8,8)")
    print("Koniec gdy:")
    print("- brak energii")
    print("- limit kroków")
    print("- dotarcie do celu")

    cel=(8,8)

    przeszkody=[(2,2),(-1,3),(5,-2)]
    bonusy=[(4,1),(-2,-2)]
    niebezpieczne=[(1,-3),(6,4)]

    krok=0
    wydarzenia=[]

    powod=""

    while True:


        krok+=1

        print("\n====================")
        print("KROK:",krok)

        print("Pozycja przed:",(x,y))
        print("Energia przed:",energia)

        ruch=input(
        "Ruch [góra/dół/lewo/prawo]: "
        ).lower()

        stary_x=x
        stary_y=y




        energia-=5


        # GRANICE ŚWIATA
        if x>10 or x<-10 or y>10 or y<-10:

            print(
            "Uderzono w granicę świata"
            )

            x=stary_x
            y=stary_y

            energia-=5


        # BONUS
        if (x,y) in bonusy:

            energia+=20

            print(
            "🔋 Znaleziono energię +20"
            )

            wydarzenia.append(
            "bonus energii"
            )


        # NIEBEZPIECZEŃSTWO
        if (x,y) in niebezpieczne:

            energia-=15

            print(
            "☠ Niebezpieczny teren -15"
            )

            wydarzenia.append(
            "niebezpieczny teren"
            )


        # PRZESZKODA
        if (x,y) in przeszkody:

            print(
            "⛰ Skały → cofnięcie"
            )

            x=stary_x
            y=stary_y

            wydarzenia.append(
            "przeszkoda"
            )


        # LOSOWE ZDARZENIA
        los=random.randint(1,8)

        if los==1:

            energia+=10

            print(
            "🎁 Znaleziono zapasy +10"
            )

            wydarzenia.append(
            "znaleziono zapasy"
            )


        elif los==2:

            energia-=10

            print(
            "⚡ Burza pyłowa -10"
            )

            wydarzenia.append(
            "burza"
            )


        print("Pozycja po:",(x,y))
        print("Energia po:",energia)


    # WYNIK
    if powod=="Dotarto do celu":
        wynik="SUKCES"

    elif energia<=0:
        wynik="PORAŻKA"

    else:
        wynik="CZĘŚCIOWY SUKCES"


    print("\n=========== RAPORT ===========")

    print("Łazik:",nazwa)

    print(
    "Pozycja końcowa:",
    (x,y)
    )

    print(
    "Liczba kroków:",
    krok
    )

    print(
    "Pozostała energia:",
    energia
    )

    print(
    "Najważniejsze wydarzenia:",
    wydarzenia
    )

    print(
    "Powód zakończenia:",
    powod
    )

    print(
    "Wynik końcowy:",
    wynik
    )



while True:

    gra()

    znowu=input(
    "\nUruchomić ponownie? t/n: "
    )

    if znowu!="t":
        print("Koniec programu")
        break
