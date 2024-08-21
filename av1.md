### Atividade Prática de Modelagem de Dados

#### Contextualização
Você foi contratado por uma empresa especializada na **manutenção de elevadores** chamada **"Elevatec"**. A empresa presta serviços de manutenção preventiva e corretiva para diversos tipos de elevadores instalados em prédios residenciais, comerciais e industriais. Para gerenciar suas operações, a Elevatec precisa de um sistema que registre os clientes, os elevadores que possuem, os técnicos que realizam as manutenções, as ordens de serviço geradas, e os detalhes das manutenções realizadas. O sistema também deve acompanhar o histórico de manutenções para cada elevador.

1. **Modelo Conceitual:** Utilize o BRModelo para criar um diagrama de entidade-relacionamento (DER) que represente o sistema da Elevatec. O DER deve incluir:
   - Entidades principais, como **Cliente**, **Elevador**, **Técnico**, **Ordem de Serviço**, e **Manutenção**.
   - Atributos para cada entidade, como nome do cliente, endereço (para Cliente), número de série, fabricante (para Elevador), etc.
   - Relacionamentos entre as entidades, como **Cliente-Elevador**, **Elevador-Ordem de Serviço**, **Ordem de Serviço-Manutenção**.
   - Identificação de chaves primárias e estrangeiras.
   - Definição dos tipos de relacionamentos (um para muitos, muitos para muitos, etc.).

2. **Modelo Lógico:** Transforme o modelo conceitual em um modelo lógico, criando as tabelas no BRModelo. As tabelas devem incluir:
   - Atributos com seus respectivos tipos de dados.
   - Chaves primárias e estrangeiras.
   - Restrições necessárias, como integridade referencial e unicidade.

3. **Modelo Físico:** Gere o script SQL para a criação das tabelas no SQL Online a partir do modelo lógico. O script deve:
   - Criar todas as tabelas com seus respectivos atributos, chaves primárias, chaves estrangeiras e restrições.
   - Definir os tipos de dados adequados para cada atributo.

4. **Inserção de Dados:** Insira dados fictícios nas tabelas criadas usando SQL. Você deve:
   - Inserir ao menos 3 registros em cada tabela.
   - Garantir que os dados inseridos respeitem as relações definidas entre as tabelas (por exemplo, um elevador deve estar associado a um cliente).

5. **Consultas SQL:** Escreva consultas SQL para responder às seguintes perguntas:
   - Liste todos os elevadores de um cliente específico, incluindo o número de série e o fabricante.
   - Liste todas as manutenções realizadas por um técnico específico, incluindo a data e o tipo de manutenção.
   - Liste todas as ordens de serviço geradas para um elevador específico, incluindo a data da ordem e o status.

6. **Entrega:** Envie os arquivos do BRModelo (modelos conceitual e lógico), o script SQL gerado para o modelo físico, o script com as inserções de dados, e as consultas SQL realizadas.

#### Tabela de Testes

| Nome da Tabela | Atributos | Chave Primária | Chave Estrangeira |
|----------------|-----------|----------------|-------------------|
| **Cliente** | id_cliente (inteiro), nome_cliente (texto), endereco (texto), telefone (texto) | id_cliente | - |
| **Elevador** | id_elevador (inteiro), numero_serie (texto), fabricante (texto), id_cliente (inteiro) | id_elevador | id_cliente (Cliente) |
| **Técnico** | id_tecnico (inteiro), nome_tecnico (texto), especialidade (texto), telefone (texto) | id_tecnico | - |
| **Ordem de Serviço** | id_ordem_servico (inteiro), id_elevador (inteiro), data_ordem (data), status (texto) | id_ordem_servico | id_elevador (Elevador) |
| **Manutenção** | id_manutencao (inteiro), id_ordem_servico (inteiro), id_tecnico (inteiro), tipo_manutencao (texto), data_manutencao (data), descricao (texto) | id_manutencao | id_ordem_servico (Ordem de Serviço), id_tecnico (Técnico) |

Esta tabela de testes lista todas as tabelas que devem ser criadas no modelo lógico e físico, e os principais aspectos que devem ser verificados, como chaves primárias, estrangeiras e integridade referencial.
