def cifra_cesar(texto, chave):
    alfabeto_maiusculo = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
    alfabeto_minusculo = 'abcdefghijklmnopqrstuvwxyz'
    resultado = ""
    for char in texto:
        if char.isupper():
            pos = alfabeto_maiusculo.index(char)
            nova_pos = (pos + chave) % 26
            resultado += alfabeto_maiusculo[nova_pos]
        elif char.islower():
            pos = alfabeto_minusculo.index(char)
            nova_pos = (pos + chave) % 26
            resultado += alfabeto_minusculo[nova_pos]
        else:
            resultado += char
    return resultado

def gerador_de_senhas(frases):
    chave = int(input("Digite a chave para a cifra de César(número): "))
    for frase in frases:
        frase_cifrada = cifra_cesar(frase, chave)
        print(f'Frase original: {frase}')
        print(f'Frase cifrada: {frase_cifrada}')
        print("-" * 40)
        
frases = [
        "Empresa Junior de Mecatronica",
        "Processo seletivo",
        "ABCDE"
    ]
    
gerador_de_senhas(frases)
