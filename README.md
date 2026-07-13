# Catálogo Central

## Base Oficial de Conhecimento

### Documentações

- Dicionário de Campos
- regras-sla.md
- fluxos-formulario.md
- matriz-aprovacoes.md
- faq.md
- WFM
- mop.md
- telecom.md
- relatorios.md

Fluxo e Regras de Navegação da Central de Solicitações
Objetivo
A Central de Solicitações utiliza uma estrutura de formulário ramificado. Isso significa que os campos apresentados ao usuário variam conforme o setor responsável e o tipo de solicitação selecionado.
A IA deve utilizar este fluxo para compreender:
•	Quais informações são obrigatórias em cada processo.
•	Quais aprovações são necessárias.
•	Quais anexos são exigidos.
•	Como identificar corretamente o contexto da solicitação.
•	Qual área deverá tratar a demanda. 
________________________________________
Fluxo Principal
Etapa 1 – Identificação
Todo chamado inicia obrigatoriamente com:
Sua Matrícula
Matrícula da pessoa que está abrindo a solicitação.
Matrícula do Colaborador Impactado
Matrícula do colaborador afetado pela solicitação.
Ambos os campos aceitam apenas números. 
________________________________________
Etapa 2 – Setor Responsável
O usuário seleciona o setor responsável pela demanda.
Opções:
Área	Destinação
Control Desk	Ajustes e liberações em tempo real
WFM	Escalas, horários e folgas
MOP	Atualizações cadastrais do Mapa Operacional
Planejamento	De acordos, estudos e liberações
Relatórios	Extrações, indicadores e análises
Telecom	Genesys, URA, filas e telefonia
A partir desta escolha o formulário segue para uma árvore completamente diferente. 
________________________________________
Fluxo WFM
Processo Inicial
O usuário escolhe:
Novo Colaborador
ou
Colaborador Existente
________________________________________
Novo Colaborador
O formulário solicita:
•	Tipo de inclusão 
o	Usuário Único
o	Múltiplos Usuários
•	Data de lançamento da escala
•	Planilha de usuários
A IA deve entender que esse fluxo está relacionado a criação inicial de escalas. 
________________________________________
Colaborador Existente
O usuário seleciona o tipo da solicitação.
Entre elas:
•	Alteração de Horário Solteira
•	Alteração de Horário Definitiva
•	Ajuda na Unidade
•	Folga BH
•	Folga BH por Exceção
•	Folga Prêmio
•	Treinamento
•	Empréstimo
•	Troca Casada
•	Campanhas
•	Reuniões
•	Defeito de Equipamento
•	Doação de Sangue
•	Processo Seletivo
•	Serviço Militar
•	Vestibular
•	Visita Área Técnica
•	Cenário Final de Semana
e outras. 
________________________________________
Fluxos que Exigem De Acordo
Diversas solicitações possuem uma etapa intermediária obrigatória de aprovação.
Aprovação do Planejamento
Necessária para:
•	Folga BH
•	Folga Prêmio
•	Treinamentos
•	Empréstimos
•	Alterações de Horário
•	Trocas
Nesses casos o formulário exige:
Número do chamado de "De Acordo"
Esse número é usado posteriormente pelo fluxo e fica armazenado no campo:
De_Acordo_Liberado
## Aprovação Gerencial
Necessária para:
### Folga BH por Exceção
O usuário deve anexar:
- E-mail de aprovação do gerente
- E-mail do gerente aprovador
A IA deve considerar a solicitação inválida se o anexo não existir. 
# Fluxo Telecom
## Tipos de Solicitação
### Criação de Usuário
Fluxo para criação de acessos Genesys.
Campos:
- Organização
- Tipo de acesso
- E-mail
- Nome operador
- Nome gestor
- Bandeira
ou
- Planilha de múltiplos usuários
## Alteração de Usuário
Fluxo semelhante ao de criação.
Inclui:
- Organização
- Perfil
- Usuário
- Gestor
- Bandeira
ou
- Upload de planilha para múltiplos usuário
## Filas de Atendimento
Uma das ramificações mais complexas do formulário.
O usuário escolhe:
### Modelo
- Fila Única
- Múltiplas Filas
### Operações Permitidas
- Criação de fila
- Alteração de prioridade
- Alteração de status
- Alteração de bandeira
- Alteração de categoria
- Alteração de subcategoria
- Alteração de nível de serviço
- Alteração de sussurro
### Dados Capturados
Dependendo da escolha:
- Nome da fila
- Prioridade
- Bandeira
- Categoria
- Subcategoria
- Nível de serviço
- Abandono
- Sussurro
- Data desejada
Além do anexo obrigatório de aprovação gerencial.
## Routing e Call Flows
Fluxo destinado a alterações de URA.
A IA deve considerar:
### URA
O usuário escolhe uma URA dentre dezenas de opções cadastradas.
Exemplos:
- O_URA FLEURY
- O_URA A MAIS
- O_URA CHECK UP
- O_URA CONCIERGE
- O_URA VITA
- O_URA WEINMANN
 
entre outras.
 
### Processos Permitidos
 - Inclusão/Alteração de Áudio
- Alteração de Opção
- Inclusão de Nova Opção
- Inclusão de Novo Menu
- Alteração de Horário
- Fechamento Pontual
### Evidências Obrigatórias
Para qualquer alteração em fluxo:
- Aprovação Gerencial
- Documento DE → PARA
Sem esses anexos a demanda não deve ser executada. 
# Fluxo MOP
## Inclusão de Novo Colaborador
O formulário coleta praticamente todo o cadastro operacional.
Dados exigidos: 
- Nome
- Nome Social
- Gestor
- Horário
- Jornada
- DSR
- Centro de Custo
- Posição
- Local
- Bandeira
- Cargo
- Login
- E-mail
- 3L3N
- Login LIS
- Sigla LIS
- Data de Nascimento
- Sexo
- RG
- CPF
- Endereço
- Telefone
- Celular
Esses campos alimentam exatamente os campos mapeados no dicionário de dados da Central de Solicitações
## Alterações MOP
Permite alterações de:
- Cargo
- Bandeira
- DSR
- Centro de Custo
- CPF
- RG
- E-mail
- Endereço
- Telefone
- Login
- Matrícula
- Hierarquia
- Tipo de Máquina
entre outras. 
Para essas alterações o formulário exige:
[DE] informação atual
[PARA] informação nova
220
# Fluxo Relatórios
## Tipos
- Estudos
- Extrações
- Inconsistências
- Sugestões
## Subtipos
A escolha do relatório é obrigatória.
Existem relatórios em:
### Qlik
 
- Indicadores
- TMO
- Qualidade
- Banco de Horas
- Painel Executivo
- Painel Bonificação
### Excel
- Conversão
- Produtividade
- Volumetria
- SMS
- Sumário Executivo
- Meta Retenção
### Wise
- Extração de Agendamento
### Novos Relatórios
Solicitação de criação de novos indicadores. 
# Fluxo Control Desk
Fluxo destinado a liberações em tempo real.
Tipos:
- Reunião
- Treinamento
- Saída Antecipada
Obrigatoriamente o solicitante deve informar qual foi o agente de Control Desk que autorizou a ação.
Sem essa aprovação o chamado é negado. 
# Regra Geral para Interpretação pela IA
Ao analisar um chamado a IA deve seguir a seguinte hierarquia:
1. Identificar o Setor Responsável.
2. Identificar o Tipo de Solicitação.
3. Verificar se existe fluxo de aprovação.
4. Verificar anexos obrigatórios.
5. Verificar datas solicitadas.
6. Verificar SLA da solicitação.
7. Identificar área tratadora.
8. Identificar Analista Responsável.
9. Validar se todos os campos obrigatórios da ramificação escolhida foram preenchidos.
10. Considerar inválidas solicitações que não possuam os anexos obrigatórios definidos no fluxo. 
Esse conteúdo já fica em um nível muito próximo de uma **documentação funcional completa do Forms**, permitindo que um agente de IA entenda não apenas os campos, mas todo o processo decisório e as regras de navegação do formulário.

