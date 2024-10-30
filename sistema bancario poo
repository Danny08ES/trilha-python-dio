from datetime import date

class Transacao:
    def registrar(self, conta):
        pass

class Deposito(Transacao):
    def __init__(self, valor):
        self.valor = valor

    def registrar(self, conta):
        conta.depositar(self.valor)

class Saque(Transacao):
    def __init__(self, valor):
        self.valor = valor

    def registrar(self, conta):
        conta.sacar(self.valor)

class Historico:
    def __init__(self):
        self.transacoes = []

    def adicionar_transacao(self, transacao):
        self.transacoes.append(transacao)

class Conta:
    def __init__(self, saldo, numero, agencia, cliente):
        self.saldo = saldo
        self.numero = numero
        self.agencia = agencia
        self.cliente = cliente
        self.historico = Historico()

    def saldo(self):
        return self.saldo

    def nova_conta(self, cliente, numero):
        return Conta(0, numero, self.agencia, cliente)

    def sacar(self, valor):
        if valor <= self.saldo:
            self.saldo -= valor
            self.historico.adicionar_transacao(Saque(valor))
            return True
        return False

    def depositar(self, valor):
        self.saldo += valor
        self.historico.adicionar_transacao(Deposito(valor))
        return True

class ContaCorrente(Conta):
    def __init__(self, saldo, numero, agencia, cliente, limite, limite_saques):
        super().__init__(saldo, numero, agencia, cliente)
        self.limite = limite
        self.limite_saques = limite_saques

class Cliente:
    def __init__(self, endereco):
        self.endereco = endereco
        self.contas = []

    def realizar_transacao(self, conta, transacao):
        transacao.registrar(conta)

    def adicionar_conta(self, conta):
        self.contas.append(conta)

class PessoaFisica(Cliente):
    def __init__(self, cpf, nome, data_nascimento, endereco):
        super().__init__(endereco)
        self.cpf = cpf
        self.nome = nome
        self.data_nascimento = data_nascimento

# Exemplo de uso
cliente = PessoaFisica("12345678900", "João Silva", date(1990, 1, 1), "Rua A, 123")
conta_corrente = ContaCorrente(1000, 12345, "0001", cliente, 500, 3)
cliente.adicionar_conta(conta_corrente)

# Realizar depósito
deposito = Deposito(200)
cliente.realizar_transacao(conta_corrente, deposito)

# Realizar saque
saque = Saque(150)
cliente.realizar_transacao(conta_corrente, saque)

print(f"Saldo final: {conta_corrente.saldo}")
print("Histórico de transações:")
for transacao in conta_corrente.historico.transacoes:
    print(type(transacao).__name__, transacao.valor)
