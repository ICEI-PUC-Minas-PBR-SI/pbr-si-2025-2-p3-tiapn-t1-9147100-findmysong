# 2. Especificações do Projeto  

Esta seção apresenta as especificações do sistema de busca de músicas por trechos de letras, partindo da perspectiva do usuário. Para isso, utilizamos:  

- **Personas** para detalhar os perfis ideais de usuários.  
- **Histórias de Usuários (User Stories)** para descrever necessidades e valores.  
- **Requisitos Funcionais e Não Funcionais** que delimitam o escopo da aplicação.  
- **Restrições do Projeto** que estabelecem limitações e condições para o desenvolvimento.  

---

## 2.1. Personas  

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

## 2.2. Histórias de Usuários  

| EU COMO... (Persona)      | QUERO/PRECISO ... (Funcionalidade)   | PARA ... (Motivo/Valor)                        |  
|----------------------------|--------------------------------------|------------------------------------------------|  
| Usuário comum (Maria)      | Buscar músicas por trecho da letra   | Descobrir rapidamente o nome da canção         |  
| Estudante (João)           | Acessar a letra completa             | Usar como recurso pedagógico no estudo de idiomas |  
| Professora (Ana)           | Salvar músicas encontradas           | Reutilizar em aulas futuras                    |  
| Músico (Carlos)            | Comparar letras pesquisadas          | Inspirar novas composições                     |  
| Administrador do sistema   | Atualizar a base de letras e artistas| Manter o sistema preciso e atualizado          |  
| Usuário comum              | Avaliar a busca realizada            | Ajudar a melhorar a precisão dos resultados    |  

---



## 2.3. Requisitos

### Requisitos Funcionais (RF)

| ID     | Descrição do Requisito                                                                                      | Prioridade |
|--------|--------------------------------------------------------------------------------------------------------------|------------|
| RF-001 | Permitir que o usuário realize buscas de músicas integradas à API do Spotify (por nome, artista ou trecho). | ALTA       |
| RF-002 | Exibir resultados detalhados em cards (capa, título, artista) com links diretos para o Spotify e para a letra no Genius. | ALTA       |
| RF-003 | Reproduzir um trecho (preview de 30s) da música em um player global persistente ao clicar no card.          | ALTA       |
| RF-004 | Permitir o cadastro e login de usuários (autenticação própria com JWT).                                     | ALTA       |
| RF-005 | Permitir que usuários logados criem playlists personalizadas e adicionem músicas a elas.                    | ALTA       |
| RF-006 | Permitir que usuários logados salvem músicas em sua biblioteca ("Liked Songs").                             | MÉDIA      |
| RF-007 | Oferecer um painel administrativo para gerenciamento de temas visuais (Halloween, Natal, Padrão).           | MÉDIA      |
| RF-008 | Coletar feedback dos usuários (avaliação de 1 a 5 estrelas) sobre a precisão da busca e exibir relatório para o administrador. | BAIXA      |

---

### Requisitos Não Funcionais (RNF)

| ID      | Descrição do Requisito                                                                                           | Prioridade |
|---------|-------------------------------------------------------------------------------------------------------------------|------------|
| RNF-001 | A interface deve ser responsiva e adaptável a dispositivos móveis (sidebar retrátil/menu hambúrguer).             | ALTA       |
| RNF-002 | A aplicação deve ser uma SPA (Single Page Application) desenvolvida em React, garantindo fluidez sem recarregamento. | ALTA       |
| RNF-003 | O sistema deve persistir as preferências do usuário (como estado da sidebar) localmente.                          | MÉDIA      |
| RNF-004 | O backend deve atuar como um gateway seguro para ocultar as chaves de API do Spotify.                             | ALTA       |
| RNF-005 | A comunicação entre frontend e backend deve ser segura (HTTPS) e protegida contra CORS indevido.                  | ALTA       |

---

## 2.4. Restrições

| ID   | Restrição                                                                                                      |
|------|-----------------------------------------------------------------------------------------------------------------|
| 01   | O projeto deverá ser entregue até o final do semestre letivo.                                                  |
| 02   | O sistema não armazenará arquivos de áudio (MP3) no banco de dados; apenas links e metadados.                   |
| 03   | O sistema dependerá da disponibilidade da API do Spotify para busca e reprodução dos previews.                  |
| 04   | O frontend deve utilizar a biblioteca de componentes shadcn/ui para a interface de autenticação.                |
| 05   | A hospedagem será dividida: Frontend na Vercel e Backend/Banco de Dados no Render.                              |
