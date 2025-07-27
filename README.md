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


├── 10-gerenciamento-memoria/ --> README.md + quadro comparativo


├── 11-programacao-funcional/ --> README.md + exemplo funcional


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


