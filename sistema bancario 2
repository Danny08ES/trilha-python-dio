class Cliente:
    def __init__(self, nome, cpf):
        self.nome = nome
        self.cpf = cpf

class Banco:
    def __init__(self, saldo_inicial=0):
        self.saldo = saldo_inicial
        self.clientes = {}
        self.contas = {}

    def cadastrar_cliente(self, nome, cpf):
        if cpf not in self.clientes:
            self.clientes[cpf] = Cliente(nome, cpf)
            print(f"Cliente {nome} cadastrado com sucesso!")
        else:
            print("Cliente já cadastrado!")

    def cadastrar_conta(self, cpf, saldo_inicial=0):
        if cpf in self.clientes:
            conta = Banco(saldo_inicial)
            self.contas[cpf] = conta
            print(f"Conta criada para {self.clientes[cpf].nome} com saldo inicial de R${saldo_inicial:.2f}!")
        else:
            print("Cliente não encontrado!")

    def depositar(self, cpf, valor):
        if cpf in self.contas:
            if valor > 0:
                self.contas[cpf].saldo += valor
                print(f"Depósito de R${valor:.2f} realizado com sucesso na conta de {self.clientes[cpf].nome}!")
            else:
                print("Valor de depósito inválido!")
        else:
            print("Conta não encontrada!")

    def sacar(self, cpf, valor):
        if cpf in self.contas:
            if valor > self.contas[cpf].saldo:
                print("Saldo insuficiente!")
            elif valor <= 0:
                print("Valor de saque inválido!")
            else:
                self.contas[cpf].saldo -= valor
                print(f"Saque de R${valor:.2f} realizado com sucesso na conta de {self.clientes[cpf].nome}!")
        else:
            print("Conta não encontrada!")

    def visualizar_saldo(self, cpf):
        if cpf in self.contas:
            print(f"Saldo atual da conta de {self.clientes[cpf].nome}: R${self.contas[cpf].saldo:.2f}")
        else:
            print("Conta não encontrada!")

# Exemplo de uso
banco = Banco()
banco.cadastrar_cliente("João Silva", "123.456.789-00")  # Cadastra um cliente
banco.cadastrar_conta("123.456.789-00", 1000)  # Cria uma conta para o cliente
banco.visualizar_saldo("123.456.789-00")  # Exibe o saldo atual da conta
banco.depositar("123.456.789-00", 500)  # Deposita R$ 500
banco.visualizar_saldo("123.456.789-00")  # Exibe o saldo atual após o depósito
banco.sacar("123.456.789-00", 300)  # Realiza um saque de R$ 300
banco.visualizar_saldo("123.456.789-00")  # Exibe o saldo atual após o saque
banco.sacar("123.456.789-00", 1500)  # Tenta sacar um valor maior que o saldo
