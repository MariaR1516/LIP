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
