# 🏥 Sistema de Agendamento de Consultas Médicas

> Sistema web para gerenciamento de consultas médicas, desenvolvido como projeto acadêmico do curso de Sistemas de Informação da Universidade do Estado do Amazonas.

## Sobre o Projeto

O **Sistema de Agendamento de Consultas Médicas** foi desenvolvido para solucionar problemas comuns em clínicas e consultórios médicos, como conflitos de horários, dificuldades no gerenciamento de pacientes e falta de controle sobre cancelamentos e remarcações.

### Problema de Negócio

Foi identificado que muitos estabelecimentos de saúde não possuem um sistema eficiente de agendamento, enfrentando dificuldades em:

-  **Criar** consultas para pacientes
-  **Ler/Recuperar** informações de agendamentos
-  **Atualizar** horários e remarcar consultas
-  **Deletar** dados de pacientes que cancelaram

Este sistema resolve esses problemas através de uma interface intuitiva e regras de negócio bem definidas.

---

## Funcionalidades

### Para Médicos
- Visualizar agenda pessoal de consultas
- Confirmar presença de pacientes
- Acessar informações dos pacientes agendados

### Para Recepcionistas
- Cadastrar novos pacientes
- Agendar, remarcar e cancelar consultas
- Gerenciar dados de pacientes
- Visualizar agenda dos médicos

### Para Administradores
- Cadastrar médicos e suas especialidades
- Cadastrar recepcionistas
- Gerenciar usuários do sistema
- Controle total sobre cadastros

---

## Atores do Sistema

| Ator | Responsabilidades |
|------|-------------------|
| **Administrador** | Gerencia cadastros de médicos e recepcionistas |
| **Médico** | Visualiza agenda e confirma consultas |
| **Recepcionista** | Gerencia agendamentos e cadastro de pacientes |
| **Paciente** | Recebe atendimento (não acessa o sistema) |

---

## Regras de Negócio

- **RN01**:	Um médico não pode ter duas consultas agendadas no mesmo dia e horário (choque de horário).
- **RN02**:	Não é possível agendar consultas para datas passadas.
- **RN03**:	O paciente só pode cancelar a consulta com até 24 horas de antecedência.
- **RN04**:	Matrícula dos usuários deve ser única.
- **RN05**:	O paciente não deve ter acesso ao sistema de cadastro.
- **RN06**:	A Recepcionista pode acessar somente o agendamento e consulta dos pacientes.
- **RN07**:	O Médico não tem permissão para alterar os dados da Recepcionista, Administrador ou Paciente.
- **RN08**:	Uma consulta deve ter duração máxima de até 30 minutos
- **RN09**:	Um paciente pode ter no máximo 3 consultas agendadas simultaneamente.
- **RN10**:	Consultas canceladas devem ficar registrados no histórico do paciente.
- **RN11**:	O horário de funcionamento da clínica é das 8 h às 18 h (segunda a sexta)
- **RN12**:	Um médico pode atender no máximo 16 pacientes por dia.


---

## Tecnologias Utilizadas

### Backend
- **Linguagem:** [A definir - PHP/Python/Java/Node.js]
- **Banco de Dados:** [A definir - MySQL/PostgreSQL/MongoDB]
- **Framework:** [A definir]

### Frontend
- **HTML5** - Estrutura
- **CSS3** - Estilização
- **JavaScript** - Interatividade

### Ferramentas
- **Git** - Controle de versão
- **GitHub** - Repositório remoto
- **[Editor]** - Desenvolvimento

---

## Instalação e Configuração

### Pré-requisitos

```bash
# Certifique-se de ter instalado:
- [Linguagem/Runtime necessário]
- [Banco de dados]
- Git
```

### Passo a Passo

1. **Clone o repositório**
```bash
git clone https://github.com/seu-usuario/sistema-agendamento-consultas.git
cd sistema-agendamento-consultas
```

2. **Configure o banco de dados**
```bash
# Crie o banco de dados
# Execute o script de criação das tabelas
```

3. **Configure as variáveis de ambiente**
```bash
# Copie o arquivo de exemplo
cp .env.example .env

# Edite com suas configurações
```

4. **Execute o projeto**
```bash
# Comando para iniciar o servidor
```

5. **Acesse no navegador**
```
http://localhost:porta
```

---

## Estrutura do Banco de Dados

### Principais Entidades

- **Pacientes** (id, nome, email, telefone)
- **Médicos** (id, nome, especialidade, matricula)
- **Recepcionistas** (id, nome, matricula)
- **Consultas** (id, paciente_id, medico_id, data, hora_inicio, hora_fim, status, descricao)
- **Usuários** (id, matricula, senha, tipo, ativo)

---

## Roadmap

### Versão 1.0 (Atual)
- [x] Levantamento de Requisitos
- [ ] Modelagem do Banco de Dados
- [ ] Desenvolvimento do Backend
- [ ] Desenvolvimento do Frontend
- [ ] Testes Unitários
- [ ] Implantação

### Futuras Melhorias
- [ ] Sistema de notificações por e-mail/SMS
- [ ] Aplicativo mobile para pacientes
- [ ] Relatórios e dashboards
- [ ] Integração com calendários externos
- [ ] Histórico médico dos pacientes
- [ ] Sistema de prontuário eletrônico

---

## Documentação

A documentação completa do projeto está disponível na pasta `/docs`:

- [Levantamento de Requisitos](docs/LR-versao1.pdf)
- [Diagrama de Casos de Uso](docs/casos-de-uso.md) *(em desenvolvimento)*
- [Modelo Entidade-Relacionamento](docs/mer.md) *(em desenvolvimento)*
- [Manual do Usuário](docs/manual-usuario.md) *(em desenvolvimento)*

---

## Testes

```bash
# Executar testes unitários
npm test

# Executar testes de integração
npm run test:integration

# Cobertura de código
npm run test:coverage
```

---

## 🤝 Como Contribuir

Contribuições são bem-vindas! Para contribuir:

1. Faça um **Fork** do projeto
2. Crie uma **branch** para sua feature (`git checkout -b feature/MinhaFeature`)
3. **Commit** suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. Faça **Push** para a branch (`git push origin feature/MinhaFeature`)
5. Abra um **Pull Request**

### Padrões de Código
- Siga as convenções de código da linguagem utilizada
- Documente funções e métodos complexos
- Escreva testes para novas funcionalidades
- Mantenha commits claros e descritivos

---

## Autor

**Daniel Nazário**

- Estudante de Sistemas de Informação - UEA
-  LinkedIn: [linkedin](https://www.linkedin.com/in/danielnazariopro/)
- Email: seu.email@exemplo.com
- GitHub: [@danielnazario](https://github.com/DanielNazarioPro)

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## Agradecimentos

- Universidade do Estado do Amazonas (UEA)
- Professor orientador Marcio Palheta
- Colegas de curso que contribuíram com ideias e feedback

---

## Suporte

Encontrou algum problema? Tem alguma sugestão?

- 🐛 Abra uma [Issue](https://github.com/seu-usuario/sistema-agendamento-consultas/issues)
- 💬 Entre em contato: dmalzinha0221@gmail.com

---

<div align="center">

### ⭐ Se este projeto foi útil para você, considere dar uma estrela!

**Desenvolvido com por Daniel Nazário**

</div>
