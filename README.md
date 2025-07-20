## Desafio 1
<img width="1920" height="1080" alt="History of Borcelle (1)" src="https://github.com/user-attachments/assets/7c1c1282-a971-47f7-8f8b-55daa469dc0e" />

## Desafio 2
<img width="1920" height="1080" alt="Ambientes de Programação" src="https://github.com/user-attachments/assets/350463cf-2d78-4573-b1dd-725b87875041" />

## Desafio 4:
  ### Python
    num = 0
    nome = "Rita"
    valor = 1.5
  Em python, não é necessário definir explicitamente o tipo de dado da variável.
  ### C
    int num = 0;
    char *nome = "Rita";
    float valor = 1.5;
  Em C, a declaração do tipo é obrigatória, é uma linguagem rígida.
  ### JavaScript
    let num = 0;
    let nome = "Rita";
    let valor = 1.5;
  Em JavaScript, não é necessário especificar o tipo, a linguagem é dinamicamente tipada.

  ## Desafio 5 
    import random
    # Número secreto entre 1 e 10
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
  
  
