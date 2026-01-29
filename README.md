# Sistema de Agendamento de Consultas Médicas

## Descrição

Sistema web desenvolvido para automatizar o processo de agendamento de consultas em clínicas médicas. A aplicação permite o controle completo de agendas, gerenciamento de pacientes, médicos e oferece diferentes níveis de acesso para administradores, médicos e recepcionistas.

## Objetivo

Substituir processos manuais de agendamento por uma solução informatizada que elimine conflitos de horário, centralize informações de pacientes e facilite o gerenciamento de consultas médicas.

## Funcionalidades Principais

### Gestão de Usuários
- Cadastro e manutenção de médicos, recepcionistas e administradores
- Controle de acesso baseado em perfis de usuário
- Sistema de autenticação com matrícula e senha
- Recuperação de senha via email

### Agendamento de Consultas
- Cadastro de consultas com validação automática de disponibilidade
- Verificação de conflitos de horário
- Controle de horários de funcionamento da clínica
- Cancelamento e reagendamento de consultas
- Restrição de cancelamento com antecedência mínima de 24 horas

### Gestão de Pacientes
- Cadastro completo de pacientes pela recepcionista
- Histórico de consultas por paciente
- Busca de pacientes por nome, matrícula ou CPF
- Desativação automática de cadastros inativos

### Controle de Agenda
- Visualização de agenda diária, semanal e mensal
- Identificação de horários disponíveis e ocupados
- Confirmação de presença pelo médico
- Registro automático de faltas de pacientes

### Especialidades Médicas
- Cadastro de especialidades
- Associação de médicos a especialidades
- Busca de médicos por especialidade

### Relatórios
- Consultas realizadas por período
- Estatísticas de cancelamentos e faltas
- Relatórios individuais por médico

### Auditoria
- Registro de todas as ações críticas do sistema
- Logs com data, hora e usuário responsável
- Rastreabilidade completa de operações

## Perfis de Usuário

### Administrador
Responsável pela gestão completa do sistema. Pode cadastrar e gerenciar médicos, recepcionistas e outros administradores. Possui acesso a relatórios gerenciais e logs de auditoria.

### Médico
Visualiza suas próprias consultas agendadas, confirma presença de pacientes, registra faltas e acessa histórico de pacientes atendidos. Pode alterar seus próprios dados cadastrais.

### Recepcionista
Realiza o atendimento ao público, gerencia cadastro de pacientes, agenda consultas, efetua cancelamentos e reagendamentos. Visualiza a agenda dos médicos para facilitar o agendamento.

### Paciente
Não possui acesso direto ao sistema. Todas as operações relacionadas ao paciente são realizadas pela recepcionista.

## Regras de Negócio

### Horários e Agendamento
- Cada consulta tem duração padrão de 30 minutos
- Horário de funcionamento: Segunda a sexta, das 8h às 18h
- Um médico pode atender no máximo 16 pacientes por dia
- Não é permitido agendar consultas em datas passadas
- Um médico não pode ter duas consultas no mesmo horário

### Pacientes
- Cada paciente pode ter no máximo 3 consultas agendadas simultaneamente
- Consultas canceladas permanecem no histórico do paciente
- Cadastros inativos por 12 meses são automaticamente desativados

### Cancelamento
- Consultas só podem ser canceladas com 24 horas de antecedência
- Todas as consultas canceladas são registradas no histórico

### Confirmação
- Consultas não confirmadas até 1 hora após o horário agendado são marcadas automaticamente como falta do paciente

## Requisitos Técnicos

### Segurança
- Senhas armazenadas com criptografia hash
- Bloqueio temporário após 3 tentativas incorretas de login
- Sessões expiram após 30 minutos de inatividade
- Matrícula única para cada usuário
- Registro de logs para todas as ações críticas

### Performance
- Tempo de resposta máximo de 3 segundos para consultas
- Suporte para até 100 usuários simultâneos

### Disponibilidade
- Disponibilidade mínima de 99% durante horário comercial
- Backup automático diário do banco de dados

### Compatibilidade
- Funciona em navegadores Chrome, Firefox e Edge
- Interface responsiva para desktop, tablets e smartphones
- Aplicação web acessível via navegador

### Usabilidade
- Interface intuitiva e de fácil navegação
- Mensagens de erro em português claro
- Formulários com validação de dados

## Fluxo Básico de Uso

### 1. Configuração Inicial
O administrador acessa o sistema e cadastra as especialidades médicas, médicos e recepcionistas que utilizarão o sistema.

### 2. Cadastro de Pacientes
A recepcionista cadastra novos pacientes conforme chegam à clínica, incluindo dados pessoais e informações de contato.

### 3. Agendamento
A recepcionista busca o paciente, seleciona a especialidade desejada, escolhe o médico e visualiza os horários disponíveis na agenda. Ao selecionar data e horário, o sistema valida se não há conflitos e confirma o agendamento.

### 4. Confirmação de Consulta
No dia da consulta, o médico acessa o sistema, visualiza sua agenda do dia e confirma a presença do paciente após o atendimento. Caso o paciente não compareça, o médico registra a falta.

### 5. Cancelamento ou Reagendamento
Se necessário, a recepcionista pode cancelar ou reagendar consultas, respeitando o prazo mínimo de 24 horas de antecedência.

### 6. Consulta de Histórico
Médicos e recepcionistas podem consultar o histórico completo de consultas de um paciente, incluindo consultas realizadas, canceladas e faltas.

### 7. Geração de Relatórios
Administradores e médicos podem gerar relatórios de consultas por período, visualizar estatísticas e acompanhar indicadores de atendimento.

## Estrutura de Dados

### Principais Entidades
- Usuários: Administradores, Médicos e Recepcionistas
- Pacientes
- Especialidades Médicas
- Consultas
- Logs de Auditoria

### Relacionamentos
- Médicos possuem uma ou mais especialidades
- Consultas relacionam pacientes e médicos
- Todos os usuários possuem matrícula única
- Logs registram ações de usuários no sistema

## Validações do Sistema

### Validações de Agendamento
- Verifica se o horário está dentro do expediente da clínica
- Valida se o médico está disponível no horário solicitado
- Confirma se a data não é passada
- Verifica se o paciente não excedeu o limite de consultas agendadas

### Validações de Cadastro
- Garante unicidade de matrícula
- Valida formato de email
- Verifica campos obrigatórios
- Impede exclusão de administradores se restarem menos de 3 ativos

### Validações de Cancelamento
- Verifica se a consulta existe e está agendada
- Confirma se o prazo de 24 horas está sendo respeitado
- Registra motivo do cancelamento

## Benefícios do Sistema

- Eliminação de conflitos de horário
- Redução de erros no agendamento
- Histórico completo e organizado de pacientes
- Agilidade no atendimento da recepção
- Melhor aproveitamento da agenda médica
- Controle estatístico de consultas
- Rastreabilidade de todas as operações
- Acesso rápido a informações de pacientes
- Automatização de processos administrativos

## Documentação Adicional

Para informações detalhadas sobre requisitos, regras de negócio e especificações técnicas, consulte o documento [Levantamento de Requisitos](Levantamento-Requisitos/LR-versao3.pdf).
Os próximos passos são:
1) Fazer a Modelagem lógica na UML para fazer que os dados vejam claros, para ficar mais fácil de desenvolver a Modelagem Relacional.
2) Realizar o Detalhamento de Caso de Uso, para quando for fazer o projeto back-end ou front-end, definindo de maneira clara, quais são os atores que vão relacionar com o dados do sistema e quais são as respostas que o sistema deve dar para ter mais clareza, definindo responsabilidades, respeitando as regras de négocios, fluxo principal, fluxo de exeção. E, o que pode acontecer dentro do sistema ou o que não pode acontecer dentro do limite do sistema.
3) Escolher uma arquitetura de desenvolvimento, como um estudante de sistema de informação isso é muito importante.
4) Desenvolver algoritmo do front-end definindo quais são as linguagens.
5) Desenvolver algoritmo do back-end definindo as suas linguagens.

## Autor

Daniel Nazário
Sistemas de Informação - Universidade do Estado do Amazonas

## Versão

Versão 4.0 - Janeiro de 2026
