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
