### Python
    # Classe base
    class Transporte:
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo

    def mover(self):
        return f"O {self.__class__.__name__} está se movendo."

    def exibir_info(self):
        return f"Marca: {self.marca}, Modelo: {self.modelo}"

        # Subclasse Carro
    class Carro(Transporte):
    def __init__(self, marca, modelo, num_portas):
        super().__init__(marca, modelo)
        self.num_portas = num_portas

    def mover(self):
        return f"O carro {self.modelo} está dirigindo na estrada."

      # Subclasse Bicicleta
    class Bicicleta(Transporte):
    def __init__(self, marca, modelo, tipo):
        super().__init__(marca, modelo)
        self.tipo = tipo

    def mover(self):
        return f"A bicicleta {self.modelo} está pedalando na ciclovia."

    # Subclasse Avião
    class Aviao(Transporte):
    def __init__(self, marca, modelo, capacidade):
        super().__init__(marca, modelo)
        self.capacidade = capacidade

    def mover(self):
        return f"O avião {self.modelo} está voando nos céus."

    # Teste das classes
    meu_carro = Carro("Toyota", "Corolla", 4)
    minha_bike = Bicicleta("Caloi", "Elite", "Montanha")
    meu_aviao = Aviao("Boeing", "747", 416)

    transportes = [meu_carro, minha_bike, meu_aviao]

    for t in transportes:
    print(t.exibir_info())
    print(t.mover())
    print("---")
