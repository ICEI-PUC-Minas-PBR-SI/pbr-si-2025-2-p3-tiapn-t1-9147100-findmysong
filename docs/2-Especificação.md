# Especificações do Projeto  

Esta seção apresenta as especificações do sistema de busca de músicas por trechos de letras, partindo da perspectiva do usuário. Para isso, utilizamos:  

- **Personas** para detalhar os perfis ideais de usuários.  
- **Histórias de Usuários (User Stories)** para descrever necessidades e valores.  
- **Requisitos Funcionais e Não Funcionais** que delimitam o escopo da aplicação.  
- **Restrições do Projeto** que estabelecem limitações e condições para o desenvolvimento.  

---

## Personas  

**Persona 1 – Maria (usuária comum)**  
- Idade: 22 anos  
- Estudante universitária, gosta de ouvir música diariamente.  
- Objetivo: encontrar músicas lembrando apenas de um trecho da letra.  
- Dor: não consegue localizar a canção em aplicativos de streaming tradicionais.  

**Persona 2 – João (estudante de idiomas)**  
- Idade: 18 anos  
- Faz curso de inglês e usa músicas como recurso de aprendizado.  
- Objetivo: buscar letras para praticar vocabulário e compreensão auditiva.  
- Dor: dificuldade em localizar músicas específicas para estudo.  

**Persona 3 – Ana (professora/pesquisadora)**  
- Idade: 35 anos  
- Professora de inglês, utiliza músicas como recurso pedagógico em sala de aula.  
- Objetivo: selecionar rapidamente músicas que se encaixem em atividades didáticas.  
- Dor: perde tempo procurando canções adequadas para suas aulas.  

**Persona 4 – Carlos (músico/compositor)**  
- Idade: 28 anos  
- Músico independente, utiliza músicas como inspiração para composições.  
- Objetivo: pesquisar letras e identificar referências musicais.  
- Dor: dificuldade em encontrar obras com base em versos específicos.  

---

## Histórias de Usuários  

| EU COMO... (Persona)      | QUERO/PRECISO ... (Funcionalidade)   | PARA ... (Motivo/Valor)                        |  
|----------------------------|--------------------------------------|------------------------------------------------|  
| Usuário comum (Maria)      | Buscar músicas por trecho da letra   | Descobrir rapidamente o nome da canção         |  
| Estudante (João)           | Acessar a letra completa             | Usar como recurso pedagógico no estudo de idiomas |  
| Professora (Ana)           | Salvar músicas encontradas           | Reutilizar em aulas futuras                    |  
| Músico (Carlos)            | Comparar letras pesquisadas          | Inspirar novas composições                     |  
| Administrador do sistema   | Atualizar a base de letras e artistas| Manter o sistema preciso e atualizado          |  
| Usuário comum              | Avaliar a busca realizada            | Ajudar a melhorar a precisão dos resultados    |  

---



## Requisitos

As tabelas que se seguem apresentam os requisitos funcionais e não funcionais que detalham o escopo do projeto. Para determinar a prioridade de requisitos, aplicar uma técnica de priorização de requisitos e detalhar como a técnica foi aplicada.

### Requisitos Funcionais

|ID    | Descrição do Requisito  | Prioridade |
|------|-----------------------------------------|----|
|RF-001| Permitir que o usuário cadastre tarefas | ALTA | 
|RF-002| Emitir um relatório de tarefas no mês   | MÉDIA |

### Requisitos não Funcionais

|ID     | Descrição do Requisito  |Prioridade |
|-------|-------------------------|----|
|RNF-001| O sistema deve ser responsivo para rodar em um dispositivos móvel | MÉDIA | 
|RNF-002| Deve processar requisições do usuário em no máximo 3s |  BAIXA | 

Com base nas Histórias de Usuário, enumere os requisitos da sua solução. Classifique esses requisitos em dois grupos:

- [Requisitos Funcionais
 (RF)](https://pt.wikipedia.org/wiki/Requisito_funcional):
 correspondem a uma funcionalidade que deve estar presente na
  plataforma (ex: cadastro de usuário).
- [Requisitos Não Funcionais
  (RNF)](https://pt.wikipedia.org/wiki/Requisito_n%C3%A3o_funcional):
  correspondem a uma característica técnica, seja de usabilidade,
  desempenho, confiabilidade, segurança ou outro (ex: suporte a
  dispositivos iOS e Android).
Lembre-se que cada requisito deve corresponder à uma e somente uma
característica alvo da sua solução. Além disso, certifique-se de que
todos os aspectos capturados nas Histórias de Usuário foram cobertos.

## Restrições

O projeto está restrito pelos itens apresentados na tabela a seguir.

|ID| Restrição                                             |
|--|-------------------------------------------------------|
|01| O projeto deverá ser entregue até o final do semestre |
|02| Não pode ser desenvolvido um módulo de backend        |

Enumere as restrições à sua solução. Lembre-se de que as restrições geralmente limitam a solução candidata.

> **Links Úteis**:
> - [O que são Requisitos Funcionais e Requisitos Não Funcionais?](https://codificar.com.br/requisitos-funcionais-nao-funcionais/)
> - [O que são requisitos funcionais e requisitos não funcionais?](https://analisederequisitos.com.br/requisitos-funcionais-e-requisitos-nao-funcionais-o-que-sao/)
