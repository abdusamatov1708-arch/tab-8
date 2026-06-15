# tab-8
import random


def sonni_topish_oyini():
    print("Sonni topish o'yiniga xush kelibsiz!")
    print("Qiyinlik darajasini tanlang:")
    print("1. Oson (1 dan 50 gacha)")
    print("2. O'rta (1 dan 100 gacha)")
    print("3. Qiyin (1 dan 200 gacha)")

    tanlov = input("Darajani tanlang (1, 2 yoki 3): ")

    if tanlov == '1':
        maksimal_son = 50
    elif tanlov == '2':
        maksimal_son = 100
    elif tanlov == '3':
        maksimal_son = 200
    else:
        print("Noto'g'ri tanlov! Standart holatda 'O'rta' (100) daraja tanlandi.")
        maksimal_son = 100

    max_urinishlar = 10
    yashirin_son = random.randint(1, maksimal_son)
    urinishlar_soni = 0

    print(f"\nO'yin boshlandi! Men 1 dan {maksimal_son} gacha bo'lgan son o'yladim.")
    print("Istalgan vaqtda o'yinni to'xtatish uchun 'q' harfini kiriting.")

    while urinishlar_soni < max_urinishlar:
        taxmin = input(f"\nUrinish {urinishlar_soni + 1}/{max_urinishlar}. Sonni kiriting: ")

        if taxmin.lower() == 'q':
            print(f"O'yin tugadi. Men o'ylagan son: {yashirin_son}")
            break

        try:
            taxmin_son = int(taxmin)
        except ValueError:
            print("Iltimos, faqat butun son yoki 'q' harfini kiriting.")
            continue

        urinishlar_soni += 1

        if taxmin_son < yashirin_son:
            print("Kichik son kiritdingiz! Kattaroq son kiriting.")
        elif taxmin_son > yashirin_son:
            print("Katta son kiritdingiz! Kichikroq son kiriting.")
        else:
            print(f"Tabriklaymiz! Siz sonni {urinishlar_soni} ta urinishda topdingiz.")
            break

    else:
        print(f"\nAfsuski, urinishlar tugadi. Men o'ylagan son: {yashirin_son}")


if __name__ == "__main__":
    sonni_topish_oyini()
