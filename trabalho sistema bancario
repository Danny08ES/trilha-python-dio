class Banco:
    def __init__(self, saldo_inicial=0):
        self.saldo = saldo_inicial

    def depositar(self, valor):
        if valor > 0:
            self.saldo += valor
            print(f"Depósito de R${valor:.2f} realizado com sucesso!")
        else:
            print("Valor de depósito inválido!")

    def sacar(self, valor):
        if valor > self.saldo:
            print("Saldo insuficiente!")
        elif valor <= 0:
            print("Valor de saque inválido!")
        else:
            self.saldo -= valor
            print(f"Saque de R${valor:.2f} realizado com sucesso!")

    def visualizar_saldo(self):
        print(f"Saldo atual: R${self.saldo:.2f}")

# Exemplo de uso
conta = Banco(1000)  # Inicia com um saldo de R$ 1000
conta.visualizar_saldo()  # Exibe o saldo atual
conta.depositar(500)  # Deposita R$ 500
conta.visualizar_saldo()  # Exibe o saldo atual após o depósito
conta.sacar(300)  # Realiza um saque de R$ 300
conta.visualizar_saldo()  # Exibe o saldo atual após o saque
conta.sacar(1500)  # Tenta sacar um valor maior que o saldo
