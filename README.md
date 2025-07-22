Fundamentos-Linguagens-UFC/

├── README.md --> Explicação geral do trabalho e estrutura
do repositório

├── 01-introducao/ --> README.md com explicação e materiais da Introdução às Linguagens
<img width="1920" height="1080" alt="History of Borcelle (1)" src="https://github.com/user-attachments/assets/7c1c1282-a971-47f7-8f8b-55daa469dc0e" />


├── 02-ambientes/ --> README.md + diagramas de ambientes de programação
│<img width="1920" height="1080" alt="Ambientes de Programação" src="https://github.com/user-attachments/assets/350463cf-2d78-4573-b1dd-725b87875041" />

├── 03-sintaxe-semantica/ --> README.md + gramática criada

│
├── 04-tipos-de-dados/ --> README.md + comparativo de tipos
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



├── 05-estruturas-de-controle/--> README.md + código de exemplo
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
  

├── 06-subprogramas/ --> README.md + exemplos de funções

│
├── 07-implementacao-subprogramas/ --> README.md + desenho da pilha

│
├── 08-orientacao-objetos/ --> README.md + modelagem de classes

│
├── 09-concorrencia/ --> README.md + exemplo de concorrência

│
├── 10-gerenciamento-memoria/ --> README.md + quadro comparativo

│
├── 11-programacao-funcional/ --> README.md + exemplo funcional

│
├── 12-programacao-logica/ --> README.md + problema lógico

│
├── 13-scripts-web/ --> README.md + script criado

│
└── 14-tendencias/ --> README.md + análise crítica









