📊 Sistema E-commerce 

📋 Descrição do Projeto
Sistema completo de e-commerce desenvolvido para a disciplina de Banco de Dados, implementando conceitos avançados de SQL, programação procedural e integração com aplicação Python.

🏗️ Arquitetura do Sistema
Banco de Dados (MySQL)
Database: ecommerce

Tabelas Principais: 8 tabelas relacionais

Registros Iniciais: 100 clientes, 5 vendedores, 20 produtos, 3 transportadoras

Tecnologias Utilizadas
Backend: MySQL com stored procedures, functions, triggers e views

Interface: Python com mysql.connector

Funcionalidades: CRUD completo, relatórios, estatísticas e gestão de usuários

🗃️ Estrutura do Banco de Dados
Tabelas Principais

clientes	Cadastro de clientes	id, nome, idade, sexo, data_nascimento

clientes_especiais	Clientes VIP	id_cliente, cashback

vendedores	Equipe comercial	id, nome, causa_social, tipo, nota_media

produtos	Catálogo	id, nome, descricao, quantidade_estoque, valor

vendas	Transações	id, id_cliente, id_produto, valor_total, data_venda

transportadoras	Logística	id, nome, cidade

cargos	Hierarquia	id, nome, salario_base

funcionarios_especiais	Vendedores destaque	id_vendedor, bonus

⚙️ Funcionalidades Implementadas


Calcula_Idade(p_id INT) → Calcula idade baseada na data atual

Soma_Fretes(p_destino VARCHAR) → Soma fretes por cidade destino

Arrecadado(p_data DATE, p_vendedor INT) → Total arrecadado por vendedor/dia

🔔 Triggers (SQL)

trg_vendedor_especial → Promove vendedor para "especial" ao atingir R$ 1000+ em vendas (5% bonus)

trg_cliente_especial → Promove cliente para "especial" ao gastar R$ 500+ (2% cashback)

trg_remove_cliente_especial → Remove cliente especial quando cashback zera

🔄 Stored Procedures (SQL)

Venda() → Registra nova venda com validações

Sorteio() → Sorteia cliente com prêmio diferenciado (R$ 100-200)

Reajuste() → Aplica reajuste salarial por cargo

Estatisticas() → Gera relatório completo de vendas

👁️ Views (SQL)

vw_vendas_detalhadas → JOIN completo de vendas com clientes, produtos e vendedores

vw_vendedores_bonus → Vendedores com seus respectivos bônus

vw_vendas_mensais → Agrupamento mensal de vendas totais

👤 Sistema de Usuários


admin@localhost	Todas as permissões	admin123

gerente@localhost	SELECT, UPDATE, DELETE	gerente123

funcionario@localhost	INSERT, SELECT em vendas	func123

🐍 Aplicação Python
Menu Principal
text
1. Registrar venda
2. Listar vendas detalhadas
3. Calcular idade de cliente
4. Estatísticas completas
5. Realizar sorteio
6. Calcular soma dos fretes por cidade
7. Calcular valor arrecadado
8. Aplicar reajuste salarial
9. Listar vendedores com bonus
10. Listar vendas mensais
11. Listar clientes especiais
12. Listar funcionários especiais
0. Sair

🎯 Destaques Técnicos
Constraints Implementadas
sexo ENUM('m','f','o')

tipo ENUM('vendedor','gerente','CEO')

Chaves estrangeiras em todas as relações

Valores padrão e auto-increment

Regras de Negócio

Controle de estoque automático

Sistema de cashback para clientes fiéis

Programa de bônus para vendedores

Hierarquia de cargos e salários

Logística com múltiplas transportadoras
