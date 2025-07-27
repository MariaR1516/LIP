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
