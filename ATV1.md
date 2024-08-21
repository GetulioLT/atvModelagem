### Atividade Prática de Modelagem de Dados

Você foi contratado para desenvolver o modelo de dados para um **sistema de gestão de eventos** chamado **"Eventus"**. Este sistema permitirá que os organizadores de eventos criem e gerenciem eventos como conferências, workshops e seminários. Os eventos podem ter múltiplas sessões, cada uma com palestrantes e participantes. Os participantes podem se inscrever em diferentes sessões de um evento. Além disso, o sistema deve permitir que os organizadores acompanhem as inscrições, enviem convites e gerenciem a lista de presença.

1. **Modelo Conceitual:** Utilizando o BRModelo, crie um diagrama de entidade-relacionamento (DER) para o sistema "Eventus". O diagrama deve incluir:
   - Entidades principais, como **Evento**, **Sessão**, **Palestrante**, **Participante** e **Inscrição**.
   - Atributos para cada entidade, como nome do evento, data do evento (para Evento), título da sessão, horário (para Sessão), etc.
   - Relacionamentos entre as entidades, como **Evento-Sessão**, **Sessão-Palestrante**, **Participante-Inscrição**.
   - Identificação de chaves primárias e estrangeiras.
   - Definição dos tipos de relacionamentos (um para muitos, muitos para muitos, etc.).

2. **Modelo Lógico:** Após a criação do modelo conceitual, transforme o DER em um modelo lógico, criando as tabelas no BRModelo. As tabelas devem incluir:
   - Atributos com seus respectivos tipos de dados.
   - Chaves primárias e estrangeiras.
   - Restrições necessárias, como integridade referencial e unicidade.

3. **Entrega:** Envie os arquivos do BRModelo com o modelo conceitual e o modelo lógico, juntamente com um breve relatório explicando as principais decisões tomadas na modelagem, a justificativa para a estrutura das tabelas e como as entidades se relacionam no sistema.

#### Tabela de Testes

| Nome da Tabela | Atributos | Chave Primária | Chave Estrangeira |
|----------------|-----------|----------------|-------------------|
| **Evento** | id_evento (inteiro), nome_evento (texto), data_inicio (data), data_fim (data), local (texto) | id_evento | - |
| **Sessão** | id_sessao (inteiro), id_evento (inteiro), titulo (texto), horario_inicio (hora), horario_fim (hora) | id_sessao | id_evento (Evento) |
| **Palestrante** | id_palestrante (inteiro), nome (texto), biografia (texto) | id_palestrante | - |
| **Participante** | id_participante (inteiro), nome (texto), email (texto), telefone (texto) | id_participante | - |
| **Inscrição** | id_inscricao (inteiro), id_participante (inteiro), id_sessao (inteiro), data_inscricao (data) | id_inscricao | id_participante (Participante), id_sessao (Sessão) |

Esta tabela de testes lista todas as tabelas que devem ser criadas no modelo lógico e os principais aspectos que devem ser verificados (chaves primárias, estrangeiras e integridade referencial).
