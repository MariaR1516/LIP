    import random
     Número secreto entre 1 e 10
     secreto = random.randint(1, 10)
    tentativas = 5
     pontos = 0

    print("Bem-vindo ao jogo de adivinhação!")
    print("Você tem 5 tentativas para acertar o número entre 1 e 10.\n")

    while tentativas > 0:
        palpite = int(input(f"Tentativa ({6 - tentativas}/5): Digite seu palpite: "))

    if palpite < 1 or palpite > 10:
        print("O número deve estar entre 1 e 10!")
        

    if palpite == secreto:
        pontos = tentativas * 2  # mais pontos se acertar com menos tentativas
        print(f"Parabéns! Você acertou o número {secreto}!")
        print(f"Pontuação: {pontos} pontos")
        break
    elif palpite < secreto:
        print("Muito baixo!")
    else:
        print("Muito alto!")

    tentativas -= 1

    else:
        print(f"\n Fim de jogo! O número era {secreto}.")
