# ========================
# Sistema Bancário Simples
# ========================

# Menu apresentado ao usuário com as opções disponíveis
menu = """
[d] Depositar
[s] Sacar
[e] Extrato
[q] Sair
=> """

# Variáveis iniciais do sistema
saldo = 0                       # Saldo inicial da conta do usuário
limite = 500                   # Limite máximo de valor permitido por saque
extrato = ""                   # Histórico de transações (depósitos e saques)
numero_saques = 0              # Contador de saques feitos
LIMITE_SAQUES = 3              # Máximo de saques permitidos por sessão

# Laço principal do programa que permanece até o usuário escolher sair
while True:
    # Mostra o menu e lê a opção digitada
    opcao = input(menu)

    # --------------------------------
    # Opção de DEPÓSITO
    # --------------------------------
    if opcao == "d":
        valor = float(input("Valor do depósito: "))

        if valor > 0:
            saldo += valor  # Adiciona o valor ao saldo
            extrato += f"Depósito: R$ {valor:.2f}\n"  # Registra no extrato
        else:
            print("Operação falhou! O valor é inválido.")

    # --------------------------------
    # Opção de SAQUE
    # --------------------------------
    elif opcao == "s":
        valor = float(input("valor do saque: "))

        # Verificações de regras antes de permitir o saque
        excedeu_saldo = valor > saldo                    # Tentativa de saque maior que o saldo
        excedeu_limite = valor > limite                  # Tentativa maior que o limite por saque
        excedeu_saques = numero_saques >= LIMITE_SAQUES  # Verifica se já fez o número máximo de saques

        if excedeu_saldo:
            print("Operação falhou! saldo suficiente.")

        elif excedeu_limite:
            print("Operação falhou! O saque excede o limite.")

        elif excedeu_saques:
            print("Operação falhou! saques excedido.")

        elif valor > 0:
            saldo -= valor  # Subtrai o valor do saldo
            extrato += f"Saque: R$ {valor:.2f}\n"  # Registra no extrato
            numero_saques += 1  # Aumenta o contador de saques
        else:
            print("Operação falhou! Valor inválido.")

    # --------------------------------
    # Opção de EXTRATO
    # --------------------------------
    elif opcao == "e":
        print("\n================ EXTRATO ================")
        # Se não houve movimentações, exibe mensagem padrão
        print("Não foram realizadas movimentações." if not extrato else extrato)
        print(f"\nSaldo: R$ {saldo:.2f}")
        print("==========================================")

    # --------------------------------
    # Opção de SAIR
    # --------------------------------
    elif opcao == "q":
        print("Obrigado por utilizar nosso sistema. Até logo!")
        break  # Sai do laço e encerra o programa

    # --------------------------------
    # Opção INVÁLIDA
    # --------------------------------
    else:
        print("Operação inválida. Por favor, selecione novamente a operação desejada.")
