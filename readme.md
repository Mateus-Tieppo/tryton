🧭 Jornada do Usuário – Ciclo Completo de Venda com Faturamento (Tryton)

Esta jornada representa um fluxo real e essencial em sistemas ERP: o processo completo de venda desde a criação do cliente até a geração da fatura. Ela foi utilizada como base para os testes unitários, de integração e de sistema implementados neste trabalho.

📌 Objetivo da Jornada

Simular o comportamento de um usuário final realizando uma venda simples no Tryton, validando:

Cálculos de linha de venda

Transições de workflow

Integração entre módulos

Geração automática da fatura

🔄 Fluxo Completo da Jornada

A jornada segue sete passos principais, envolvendo múltiplos módulos do Tryton.

1. Criação do Cliente (Party)

O usuário registra um novo cliente no sistema.
Este cliente será associado ao pedido de venda.

2. Criação do Produto

É cadastrado um produto com as seguintes informações:

Nome

Unidade de medida

Preço de venda

Tipo de produto (bem ou serviço)

Esse produto será utilizado nas linhas do pedido.

3. Criação do Pedido de Venda (Sale)

O usuário cria um pedido de venda e define:

Cliente associado

Produtos inseridos

Quantidades

Preço unitário

É o início da jornada comercial.

4. Validação dos Cálculos

O sistema deve calcular corretamente:

Total da linha (quantidade × preço unitário)

Total do pedido

Este cálculo pode envolver métodos específicos do Tryton, como on_change_quantity().

5. Cotação da Venda (quote)

O usuário converte o pedido para estado de cotação.
O sistema valida os dados e prepara o pedido para confirmação.

6. Confirmação da Venda (confirm)

O pedido é confirmado e passa para o estado confirmed.
O Tryton preenche automaticamente:

Data da venda (sale_date)

Campos calculados

Estados internos de workflow

7. Geração da Fatura (Invoice)

Ao processar a venda:

O Tryton gera automaticamente uma fatura em rascunho.

O valor da fatura deve corresponder ao total do pedido.

A fatura deve:

Estar no estado draft

Conter o valor correto

Estar vinculada à venda

🎯 Resultado Final

Ao final da jornada, o sistema deve ter:

Cliente criado

Produto configurado

Venda confirmada

Fatura gerada automaticamente

Todos os cálculos corretos

Este fluxo garante que o módulo de vendas do Tryton funciona de ponta a ponta e foi a base para a implementação dos testes deste trabalho.