### MiniDraw 
    Objetivo: Executar comandos para desenhar formas simples com apenas uma palavra.
    | Token       | Tipo          | Exemplo     |
    | ----------- | ------------- | ----------- |
    | `CIRCULO`   | Palavra-chave | `CIRCULO`   |
    | `QUADRADO`  | Palavra-chave | `QUADRADO`  |
    | `TRIANGULO` | Palavra-chave | `TRIANGULO` |
    | `EOL`       | Fim da linha  | `\n`        |
    ### Pseudocódigo
    <programa>    ::= <forma> <programa> | 

    <forma>   ::= 'CIRCULO'
               | 'QUADRADO'
               | 'TRIANGULO'
    ### Análise Léxica 
    codigo = '''
    CIRCULO
    QUADRADO
    TRIANGULO
    CIRCULO
    '''
    tokens = []

    linhas = codigo.strip().split('\n')

    for linha in linhas:
    comando = linha.strip()
    if comando in ['CIRCULO', 'QUADRADO', 'TRIANGULO']:
        tokens.append(('FORMA', comando))

    for token in tokens:
    print(token)
