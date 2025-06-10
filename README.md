# 🛠️ OficinaDB - Banco de Dados para Oficina Mecânica 🚗🔧

## 📋 Descrição

OficinaDB é um banco de dados relacional completo, desenvolvido para **gerenciar de forma eficiente as operações de uma oficina mecânica**. Com ele, você pode controlar desde o cadastro detalhado de clientes (pessoa física e jurídica), veículos, funcionários e fornecedores, até o gerenciamento das ordens de serviço, serviços realizados, peças utilizadas, estoque e pagamentos.

Este banco facilita o acompanhamento de cada etapa do atendimento, possibilitando rastrear quais serviços foram realizados em quais veículos, quais funcionários participaram, as peças utilizadas e o histórico financeiro relacionado às ordens.

---

## ⚙️ Como funciona o OficinaDB

- **Clientes**: São divididos em pessoa física (`client_pf`) e pessoa jurídica (`client_pj`), com dados específicos para cada tipo, como CPF ou CNPJ, contato e endereço.  
- **Veículos**: Cada veículo está associado a um cliente pessoa física, permitindo registrar informações como placa, modelo e ano.  
- **Funcionários**: Cadastro dos colaboradores da oficina, categorizados por função (mecânico, atendente, administrador).  
- **Serviços**: Lista dos serviços oferecidos pela oficina, com descrição e preço.  
- **Peças e fornecedores**: Controle de peças disponíveis, seus fornecedores e estoque.  
- **Ordens de serviço**: Registra cada atendimento, relacionando cliente, veículo, serviços prestados, funcionários envolvidos e peças usadas. Também guarda o status da ordem e a data do atendimento.  
- **Pagamentos**: Controle dos pagamentos realizados para cada ordem, com informações sobre data, valor e método (dinheiro, cartão, Pix, cheque).

---

## 🗂️ Estrutura do Banco

### Tabelas principais:

| Tabela                | Descrição                                    | 
|-----------------------|----------------------------------------------|
| `client_pf`           | Clientes pessoa física                       |
| `client_pj`           | Clientes pessoa jurídica                     |
| `vehicle`             | Veículos associados aos clientes             |
| `employee`            | Funcionários da oficina                      |
| `service`             | Serviços oferecidos                          |
| `work_order`          | Ordens de serviço                            |
| `work_order_service`  | Serviços vinculados às ordens (N:N)          |
| `work_order_employee` | Funcionários responsáveis por ordens (N:N)   |
| `part`                | Peças utilizadas                             |
| `work_order_part`     | Peças usadas nas ordens (N:N)                |
| `supplier`            | Fornecedores de peças                        |
| `part_supplier`       | Relação peças x fornecedores (N:N)           |
| `stock`               | Estoque de peças                             |
| `payment`             | Pagamentos realizados                        |

---

## 🚀 Como usar

1. **Criação do banco e tabelas**  
   Execute o script SQL completo para criar o banco `OficinaDB` e todas as tabelas com seus relacionamentos.

2. **Inserção de dados**  
   Popule as tabelas com dados reais ou de teste utilizando comandos `INSERT`. É importante inserir clientes, veículos, funcionários e serviços antes de criar ordens de serviço.

3. **Gerenciamento de ordens**  
   Cada ordem de serviço (`work_order`) relaciona cliente, veículo, serviços realizados, peças usadas e funcionários envolvidos, possibilitando rastrear todo o atendimento.

4. **Controle de estoque e fornecedores**  
   A tabela `stock` permite controlar a quantidade disponível de cada peça. As relações com fornecedores facilitam o gerenciamento de compras e reposição.

5. **Registro e consulta de pagamentos**  
   Acompanhe pagamentos vinculados às ordens, com datas, valores e formas de pagamento.

6. **Consultas e relatórios**  
   Utilize consultas SQL para extrair relatórios, como ordens pendentes, faturamento, peças mais usadas, funcionários mais produtivos, entre outros.

