  ### C
    #include <stdio.h>

    void porValor(int x) {
    x = x + 10;
    printf("Dentro da função porValor: x = %d\n", x);
    }

    void porReferencia(int *x) {
    *x = *x + 10;
    printf("Dentro da função porReferencia: x = %d\n", *x);
    }

    int main() {
    int a = 5;

    printf("Antes da função porValor: a = %d\n", a);
    porValor(a); // Passagem por valor (cópia da variável)
    printf("Depois da função porValor: a = %d\n\n", a);

    printf("Antes da função porReferencia: a = %d\n", a);
    porReferencia(&a); // Passagem por referência (endereço da variável)
    printf("Depois da função porReferencia: a = %d\n", a);

    return 0;
    }
  ### Python
  
    def por_valor(x):
    x += 10
    print("Dentro da função por_valor: x =", x)

    def por_referencia(lista):
    lista.append(10)
    print("Dentro da função por_referencia: lista =", lista)

    a = 5
    print("Antes da função por_valor: a =", a)
    por_valor(a)  # Inteiro é imutável em Python
    print("Depois da função por_valor: a =", a)

    print()
  
    b = [1, 2, 3]
    print("Antes da função por_referencia: b =", b)
    por_referencia(b)  # Lista é mutável em Python
    print("Depois da função por_referencia: b =", b)
