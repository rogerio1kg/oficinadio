# Oficina da DIO - Modelo de Banco de Dados

Este projeto tem como objetivo modelar o sistema de controle e gerenciamento de ordens de serviço em uma oficina mecânica. O esquema conceitual foi elaborado com base na narrativa fornecida, visando mapear as entidades, atributos e relacionamentos do sistema.

---

## Estrutura do Banco de Dados

### Tabelas

1. **Cliente**
   - `idCliente`: Identificador único do cliente.
   - `Nome`: Nome completo do cliente.
   - `Endereço`: Endereço do cliente.
   - `Telefone`: Telefone de contato.

2. **Veículo**
   - `idVeículo`: Identificador único do veículo.
   - `Modelo`: Modelo do veículo.
   - `Marca`: Marca do veículo.
   - `Ano`: Ano de fabricação do veículo.
   - **Relacionamento**: Cada veículo está vinculado a um único cliente.

3. **Equipe**
   - `idEquipe`: Identificador único da equipe.
   - `Nome da Equipe`: Nome da equipe responsável pela execução da ordem de serviço.
   - `Mecânico_idMecânico`: Chave estrangeira referenciando os mecânicos da equipe.

4. **Mecânico**
   - `idMecânico`: Identificador único do mecânico.
   - `Nome`: Nome do mecânico.
   - `Endereço`: Endereço do mecânico.
   - `Especialidade`: Especialidade do mecânico.

5. **Ordem de Serviço (OS)**
   - `idOrdem de Serviço`: Identificador único da ordem de serviço.
   - `Data de Emissão`: Data em que a ordem foi emitida.
   - `Valor Total`: Valor total da ordem de serviço.
   - `Status`: Status atual da ordem (ex.: em andamento, concluída).
   - `Data de Conclusão`: Data de conclusão da ordem.
   - **Relacionamentos**:
     - Relacionada a um único veículo.
     - Associada a uma equipe responsável.

6. **Detalhes de Serviços**
   - `idServiço`: Identificador único do serviço detalhado.
   - **Relacionamento**: Detalhes vinculados a uma ordem de serviço específica.

7. **Serviço**
   - `idServiço`: Identificador único do serviço.
   - `Descrição`: Descrição detalhada do serviço.
   - `Preço Base`: Preço base do serviço.

8. **Peça**
   - `idPeça`: Identificador único da peça.
   - `Descrição`: Descrição da peça.
   - `Preço Unitário`: Valor unitário da peça.

9. **Detalhe de Peças**
   - `idPeça`: Chave estrangeira vinculada à tabela `Peça`.
   - **Relacionamento**: Detalhe vinculado a uma ordem de serviço específica.

---

## Relacionamentos entre Tabelas

- Um **cliente** pode ter múltiplos **veículos**.
- Cada **veículo** pode estar associado a várias **ordens de serviço**.
- Cada **ordem de serviço** é atribuída a uma única **equipe** e pode incluir múltiplos **serviços** e **peças**.
- Cada **equipe** é composta por um ou mais **mecânicos**.
- Um **serviço** pode ser detalhado dentro de uma **ordem de serviço**.
- Uma **peça** pode ser usada em múltiplas **ordens de serviço**.

---

## Uso do Sistema

Este modelo de banco de dados foi desenvolvido para fornecer suporte à gestão das operações em uma oficina mecânica. Ele permite:
- Gerenciar clientes e veículos.
- Registrar e acompanhar ordens de serviço.
- Atribuir equipes responsáveis.
- Detalhar serviços executados e peças utilizadas.
- Calcular automaticamente o custo total da ordem de serviço.

---

## Autor e Créditos

Este modelo foi desenvolvido com base no contexto da Oficina da DIO, utilizando boas práticas de modelagem de banco de dados. Para dúvidas ou sugestões, entre em contato.

## License

[MIT](https://choosealicense.com/licenses/mit/)

