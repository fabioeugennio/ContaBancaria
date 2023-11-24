# ContaBancaria
Sistema bancário em Python é um projeto simples que pode expandir conforme necessário.
class ContaBancaria:
    def __init__(self, saldo_inicial=0):
        self.saldo = saldo_inicial
        self.transacoes = []

    def deposito(self, valor):
        self.saldo += valor
        self.transacoes.append(f'Depósito: +{valor}')

    def saque(self, valor):
        if valor <= self.saldo:
            self.saldo -= valor
            self.transacoes.append(f'Saque: -{valor}')
        else:
            print("Saldo insuficiente. Operação de saque não realizada.")

    def extrato(self):
        print("Extrato:")
        for transacao in self.transacoes:
            print(transacao)
        print(f'Saldo atual: {self.saldo}')

# Exemplo de uso
if __name__ == "__main__":
    # Criar uma conta com saldo inicial de 1000
    minha_conta = ContaBancaria(1000)

    # Realizar operações
    minha_conta.deposito(500)
    minha_conta.saque(200)
    minha_conta.extrato()

