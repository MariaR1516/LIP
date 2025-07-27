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
