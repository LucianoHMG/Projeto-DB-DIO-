# Projeto-DB-DIO-
# Projeto Conceitual de Banco de Dados – E-commerce

Este repositório contém o modelo conceitual de banco de dados para um cenário de e-commerce, criado com ferramentas simples e gratuitas.

## Contexto

Um e-commerce precisa gerenciar:
- **Clientes** (pessoas físicas ou jurídicas);
- **Produtos** disponíveis para venda;
- **Pedidos** feitos pelos clientes, contendo vários itens;
- **Pagamentos** associados a cada pedido (um pedido pode ter várias formas de pagamento);
- **Entregas** dos pedidos, com status e código de rastreamento.

## Entidades e Atributos

1. **Cliente**  
   - **id_cliente** (PK)  
   - nome  
   - cpf_cnpj  
   - tipo_cliente (PF ou PJ)  
   - email  
   - telefone  

2. **Produto**  
   - **id_produto** (PK)  
   - nome  
   - descrição  
   - preço  
   - estoque  

3. **Pedido**  
   - **id_pedido** (PK)  
   - id_cliente (FK → Cliente)  
   - data_pedido  
   - status (Ex: Aguardando, Enviado, Entregue)  
   - código_rastreio  

4. **Item_Pedido**  
   - **id_item** (PK)  
   - id_pedido (FK → Pedido)  
   - id_produto (FK → Produto)  
   - quantidade  
   - preço_unitário  

5. **Pagamento**  
   - **id_pagamento** (PK)  
   - id_pedido (FK → Pedido)  
   - forma_pagamento (Ex: Cartão, Boleto, Pix)  
   - valor  
   - status_pagamento (Pago, Pendente, Cancelado)  

6. **Entrega**  
   - **id_entrega** (PK)  
   - id_pedido (FK → Pedido)  
   - status_entrega (Aguardando, Em Rota, Entregue)  
   - data_envio  
   - data_entrega  
   - código_rastreio  

## Relacionamentos

- Um **Cliente** pode fazer vários **Pedidos**.
- Um **Pedido** contém vários **Itens_Pedido**, cada um referenciando um **Produto**.
- Um **Pedido** pode ter vários **Pagamentos**.
- Um **Pedido** gera uma **Entrega** (com status e rastreio).

## Ferramentas Sugeridas

- **diagrams.net (Draw.io)**  
  - Arraste e solte para criar seu diagrama ER.  
  - Exporte como PNG, SVG ou PDF.

- **MySQL Workbench** (opcional)  
  - Para quem quiser avançar e criar o modelo lógico com PKs e FKs.

## Como usar

1. Abra o arquivo de diagrama no **diagrams.net** ou na ferramenta de sua preferência.  
2. Veja as entidades, atributos e relacionamentos.  
3. Se quiser implementar, crie as tabelas no seu SGBD favorito (MySQL, PostgreSQL, etc.) seguindo as PKs e FKs indicadas.  
4. Faça o versionamento no GitHub para acompanhar mudanças.

## Autor

**Luciano Henrique Morais Girão**  
- GitHub: [LucianoHMG](https://github.com/LucianoHMG)  
- LinkedIn: [luciano-girão](https://www.linkedin.com/in/luciano-gir%C3%A3o)
