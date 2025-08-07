def somar(a, b):
    return a + b

def subtrair(a, b):
    return a - b

def multiplicar(a, b):
    return a * b

def dividir(a, b):
    if b != 0:
        return a / b
    else:
        return "Erro: divisão por zero!"

def exibir_menu():
    print("\n" + "="*40)
    print("          CALCULADORA PYTHON")
    print("="*40)
    print("Selecione a operação:")
    print("1. Soma")
    print("2. Subtração")
    print("3. Multiplicação")
    print("4. Divisão")
    print("5. Sair")
    print("="*40)

def obter_numero(prompt):
    while True:
        try:
            return float(input(prompt))
        except ValueError:
            print("Por favor, digite um número válido.")

def main():
    while True:
        exibir_menu()
        escolha = input("Digite sua escolha (1-5): ")

        if escolha == '5':
            print("\nObrigado por usar a calculadora Python! 👋")
            break

        if escolha not in ('1', '2', '3', '4'):
            print("Opção inválida! Tente novamente.")
            continue

        num1 = obter_numero("Digite o primeiro número: ")
        num2 = obter_numero("Digite o segundo número: ")

        if escolha == '1':
            resultado = somar(num1, num2)
            operacao = "+"
        elif escolha == '2':
            resultado = subtrair(num1, num2)
            operacao = "-"
        elif escolha == '3':
            resultado = multiplicar(num1, num2)
            operacao = "*"
        elif escolha == '4':
            resultado = dividir(num1, num2)
            operacao = "/"

        print(f"\nResultado: {num1} {operacao} {num2} = {resultado}")

if __name__ == "__main__":
    main()
