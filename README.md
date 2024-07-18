# Dados Sequenciais

Esta documentação detalha o processo de inserção de dados em sequência nas tabelas `PARCEIRONEGOCIO`, `PARCEIROBENEFICIO`, `Formulario` e `CONTRATO`. Os dados devem ser inseridos seguindo a ordem especificada para garantir a integridade referencial e o correto relacionamento entre as tabelas.

## 1. Inserção na Tabela PARCEIRONEGOCIO

**Colunas e Valores**

- `empresa_id`: 2 (fixo)
- `organizacao_id`: 154 (Hubbie), outros valores possíveis incluem 168 (SATH Seguros), 169 (AGEGOLD Seguros), 171 (RA Seguros)
- `grupoparceiro_id`: 1 (fixo)
- `categoriaparceiro_id`: 1 (fixo)
- `classificacaoparceiro_id`: 1 (fixo)
- `estadocivil_id`: 2 (Solteiro), outros valores incluem 3 (Casado), 4 (Divorciado), 5 (Viúvo)
- `sexo_id`: 1 (Feminino), 3 (Masculino)
- `nome`: "NUBIA OLIVEIRA DE SOUZA"
- `cpf`: "02815271800"
- `datanascimento`: "1963-09-19"
- `iscliente`: 1 (ativo)
- `isfuncionario`: 0 (não)

**Observações**

- `parceironegocio_id` é gerado automaticamente pelo sistema (auto increment).

## 2. Inserção na Tabela PARCEIROBENEFICIO

**Colunas e Valores**

- `empresa_id`: 2 (fixo)
- `organizacao_id`: 154 (como definido anteriormente)
- `parceironegocio_id`: Utilizar o ID gerado na inserção anterior na tabela `PARCEIRONEGOCIO`
- `convenio_id`: 1 (fixo)
- `numerobeneficio`: 2263876442
- `createdby`: 6974 (ID do usuário robô)
- `created`: Data atual
- `isactive`: 1 (ativo)
- `data_concessao`: "2024-04-12"

**Observações**

- `parceirobeneficio_id` é gerado automaticamente pelo sistema (auto increment).

## 3. Inserção na Tabela Formulario

**Colunas e Valores**

- `empresa_id`: 2 (fixo)
- `organizacao_id`: 154 (como definido anteriormente)
- `parceironegocio_id`: 701097 (ID obtido da tabela `PARCEIRONEGOCIO`)
- `created`: Data atual
- `createdby`: 6149
- `isactive`: 1 (ativo)
- `updated`: Data atual
- `updatedby`: 6974 (ID do usuário robô)
- `canalorigem_id`: 3 (Discador)

**Observações**

- `formulario_id` é gerado automaticamente pelo sistema (auto increment).

## 4. Inserção na Tabela CONTRATO

**Colunas e Valores**

- `empresa_id`: 2 (fixo)
- `organizacao_id`: 154 (como definido anteriormente)
- `formulario_id`: Utilizar o ID gerado na inserção anterior na tabela `Formulario`
- `coeficiente_id`: 1376523
- `produto_id`: 2561 (Seguro Verbin)
- `tabela_id`: 40059
- `banco_id`: 30
- `convenio_id`: 1 (fixo)
- `usuario_id`: 5575
- `workflow_id`: 2233
- `etapa_id`: 15776
- `created`: Data atual
- `createdby`: 5575
- `isactive`: 1 (ativo)
- `updated`: Data atual
- `updatedby`: 5340
- `prazo`: 84
- `numerobeneficio`: 2263876442
- `contratobanco`: "35435177 SAFRA CORBAN"
- `datastatusfinal`: "2024-07-16"
- `valorContratoLiquido`: 15373.51
- `formapagamento_id`: 1
- `data_atualizacao_etapa`: Data atual

**Observações**

- `contrato_id` é gerado automaticamente pelo sistema (auto increment).

## Notas Gerais

- As datas `created`, `updated`, e `data_atualizacao_etapa` devem ser ajustadas para a data atual no momento da inserção.
- É crucial seguir a ordem de inserção conforme documentado para manter a integridade dos dados entre as tabelas relacionadas.
- Os IDs gerados automaticamente devem ser capturados e utilizados nas inserções subsequentes para manter o relacionamento correto entre as tabelas.
