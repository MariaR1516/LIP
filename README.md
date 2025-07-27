Fundamentos-Linguagens-UFC/

├── 01-introducao/ --> README.md com explicação e materiais da Introdução às Linguagens


├── 02-ambientes/ --> README.md + diagramas de ambientes de programação


├── 03-sintaxe-semantica/ --> README.md + gramática criada


├── 04-tipos-de-dados/ --> README.md + comparativo de tipos


├── 05-estruturas-de-controle/--> README.md + código de exemplo


├── 06-subprogramas/ --> README.md + exemplos de funções


├── 07-implementacao-subprogramas/ --> README.md + desenho da pilha


├── 08-orientacao-objetos/ --> README.md + modelagem de classes


├── 09-concorrencia/ --> README.md + exemplo de concorrência
### Diferença 
    Threads compartilham a mesma área de memória dentro de um processo, o que torna a comunicação entre elas mais simples e rápida. Por serem mais leves, são ideais para tarefas que envolvem espera, como leitura de arquivos ou chamadas de rede (I/O-bound). No entanto, esse compartilhamento pode causar conflitos se não for bem controlado. Já Processos, por outro lado, têm memória isolada, o que os torna mais seguros e estáveis, pois um processo não afeta diretamente outro. Eles são mais indicados para tarefas pesadas de cálculo (CPU-bound), mas possuem maior custo de criação e comunicação, já que exigem mecanismos como pipes ou sockets.
  ### Threads 
    import threading
    import time

    def preparar_prato(nome):
    print(f"Começando a preparar {nome}...")
    time.sleep(2)
    print(f"Prato {nome} pronto!")

    # Criando threads para cada prato
    pratos = ['Lasanha', 'Sopa', 'Salada']
    threads = []

    for prato in pratos:
    t = threading.Thread(target=preparar_prato, args=(prato,))
    threads.append(t)
    t.start()

    # Espera todos os pratos ficarem prontos
    for t in threads:
    t.join()

    print("Todos os pratos foram preparados.")
    
### Multiprocessing

    from multiprocessing import Process
    import time

    def calcular_calorias(prato, calorias_por_ingrediente):
    total = sum(calorias_por_ingrediente)
    print(f"{prato} tem aproximadamente {total} calorias.")
    time.sleep(1)

    if __name__ == '__main__':
    pratos_info = {
        "Lasanha": [200, 300, 150],
        "Sop
        a": [100, 80, 90],
        "Salada": [50, 40, 30]
    }

    processos = []

    for prato, calorias in pratos_info.items():
        p = Process(target=calcular_calorias, args=(prato, calorias))
        processos.append(p)
        p.start()

    for p in processos:
        p.join()

    print("Cálculos de calorias finalizados.")


├── 10-gerenciamento-memoria/ --> README.md + quadro comparativo
| Característica                | Java (GC Automático)                                | C (malloc/free Manual)                          |
|------------------------------|------------------------------------------------------|-------------------------------------------------|
| Tipo de gerenciamento        | Automático (Garbage Collector)                      | Manual (Programador gerencia com malloc e free) |
| Alocação de memória          | new para objetos (heap)                             | malloc, calloc, realloc (heap)            |
| Liberação de memória         | Feita automaticamente pelo Garbage Collector        | Responsabilidade do programador (free)        |
| Risco de vazamento de memória| Baixo (mas ainda possível se houver referências não liberadas) | Alto (se free não for usado corretamente)  |
| Risco de uso de memória inválida | Baixo (uso após liberação não é possível diretamente) | Alto (uso de ponteiros para memória já liberada)|
| Controle de ponteiros        | Não há acesso direto a ponteiros                    | Controle completo de ponteiros                  |
| Performance                  | Leve impacto por coleta automática                  | Alto desempenho se bem gerenciado               |
| Segurança                    | Mais seguro contra erros de memória                 | Mais propenso a bugs de alocação/liberação      |
| Complexidade para o programador | Baixa (GC cuida da limpeza)                       | Alta (programador cuida de toda a gestão)       |


├── 11-programacao-funcional/ --> README.md + exemplo funcional
 ### Python
 
    from functools import reduce

    # Lista de dicionários (funcionários)
    funcionarios = [
    {"nome": "Ana", "salario": 4000, "ativo": True},  
    {"nome": "Bruno", "salario": 3500, "ativo": False},
    {"nome": "Carla", "salario": 5000, "ativo": True},
    {"nome": "Diego", "salario": 4500, "ativo": True},
    ]
    # Função de alta ordem: filtra os ativos
    ativos = list(filter(lambda f: f["ativo"], funcionarios))

    # Função de alta ordem: aplica desconto de 15%
    salarios_liquidos = list(map(lambda f: f["salario"] * 0.85, ativos))

    # Função de alta ordem: soma os salários líquidos
    soma_salarios = reduce(lambda acc, val: acc + val, salarios_liquidos)

    print(f"Total em salários líquidos dos funcionários ativos: R$ {soma_salarios:.2f}")


├── 12-programacao-logica/ --> README.md + problema lógico
### pseudocódigo
    fatos:
    pai(joao, maria)
    pai(joao, jose)
    mae(ana, maria)
    mae(ana, jose)

    regras:
    progenitor(X, Y) := pai(X, Y) OU mae(X, Y)

    irmao(X, Y) :=
    pai(P, X) = pai(P, Y) E
    mae(M, X) = mae(M, Y) E
    X ≠ Y

├── 13-scripts-web/ --> README.md + script criado
### Python

    import os
    import shutil

    # Caminho da pasta a ser organizada
    pasta_alvo = "Downloads"

    # Tipos de arquivo e suas pastas
    tipos_arquivos = {
    "PDFs": [".pdf"],
    "Imagens": [".jpg", ".jpeg", ".png", ".gif"],
    "Documentos": [".doc", ".docx", ".txt"],
    "Compactados": [".zip", ".rar", ".7z"],
    "Planilhas": [".xls", ".xlsx", ".csv"]
    }

    # Cria as pastas, se ainda não existirem
    for pasta in tipos_arquivos:
    caminho_pasta = os.path.join(pasta_alvo, pasta)
    os.makedirs(caminho_pasta, exist_ok=True)

    # Varre os arquivos na pasta
    for nome_arquivo in os.listdir(pasta_alvo):
    caminho_arquivo = os.path.join(pasta_alvo, nome_arquivo)
    
    if os.path.isfile(caminho_arquivo):
        extensao = os.path.splitext(nome_arquivo)[1].lower()

        # Move para a pasta correspondente
        for pasta, extensoes in tipos_arquivos.items():
            if extensao in extensoes:
                destino = os.path.join(pasta_alvo, pasta, nome_arquivo)
                shutil.move(caminho_arquivo, destino)
                print(f"Movido: {nome_arquivo} → {pasta}/")
                break


└── 14-tendencias/ --> README.md + análise crítica

### Rust: Uma Linguagem Emergente com Foco em Segurança e Desempenho

    Rust é uma linguagem de programação emergente que combina segurança, desempenho e expressividade. É compilada, multiparadigma e voltada para sistemas de baixo nível, mas também se adapta bem ao desenvolvimento web e outras aplicações modernas.

    Pontos Fortes
    Segurança de Memória
    - Utiliza um sistema de ownership e borrowing que garante segurança em tempo de compilação.
    - Elimina a necessidade de coletor de lixo, evitando vazamentos e acessos inválidos.
    Desempenho
    - Oferece performance próxima ao C/C++.
    - Ideal para sistemas operacionais, jogos e ferramentas que exigem uso intensivo de recursos.
    Concorrência
    - Suporte seguro a threads e futures, permitindo programação paralela eficiente e sem erros de concorrência.
    Ecossistema
    - Possui bibliotecas e ferramentas para diversas áreas: web (Rocket, Actix), CLI, sistemas embarcados e WebAssembly.
    Comunidade
    - Comunidade ativa que contribui com documentação, ferramentas e suporte para desenvolvedores iniciantes e avançados.
  
    Pontos Fracos
    Curva de Aprendizado
    - Conceitos como ownership e borrowing podem ser desafiadores para iniciantes.
    Complexidade
    - Pode parecer mais verbosa ou complexa que outras linguagens para tarefas simples.
    Tempo de Compilação
    - Compilação mais lenta devido às verificações rigorosas de segurança e tipos.

    Aplicações
    - Sistemas Operacionais: Segurança e controle de baixo nível tornam Rust ideal.
    - Desenvolvimento Web: Com suporte a frameworks como Rocket e Actix, além de WebAssembly.
    - Ferramentas de Linha de Comando / DevOps: Segurança e eficiência impulsionam o uso.
    - Jogos e Aplicativos: Excelente escolha para alto desempenho com segurança.


