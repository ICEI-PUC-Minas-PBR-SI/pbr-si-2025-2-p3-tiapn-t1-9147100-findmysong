## 4. Projeto da Solução

<span style="color:red">Pré-requisitos: <a href="03-Modelagem do Processo de Negocio.md"> Modelagem do Processo de Negocio</a></span>

## 4.1. Arquitetura da solução


......  COLOQUE AQUI O SEU TEXTO E O DIAGRAMA DE ARQUITETURA .......

 Inclua um diagrama da solução e descreva os módulos e as tecnologias
 que fazem parte da solução. Discorra sobre o diagrama.
 
 **Exemplo do diagrama de Arquitetura**:
 
 ![Exemplo de Arquitetura](./images/arquitetura-exemplo.png)
 
---

# 4.2. Protótipos de telas

A aplicação é composta por 5 processos principais que definem a experiência do usuário, baseados nos protótipos de tela.

---

## 1. Processo de Cadastro/Login

**Tela:** AuthPage.tsx  
**Protótipo:** image_a6a42b.jpg  

**Descrição:**  
Substitui as telas separadas de Login e Cadastro. Apresenta um card centralizado com duas abas: "Sign In" (Entrar) e "Sign Up" (Criar Conta).

**Componentes:**  
- Card  
- Tabs  
- Input  
- Button (shadcn/ui)

**Fluxo:**  
- O usuário preenche o formulário.  
- O AuthPage usa axios para enviar os dados ao backend:  
  - `/api/usuarios/login`  
  - `/api/usuarios/register`  
- Exibe mensagens (toast).  
- Redireciona para `/home`.

![TELA DE LOGIN E CADASTRO](./images/login.png "TELA DE LOGIN E CADASTRO")


---

## 2. Processo de Home e Busca

**Tela:** Home.tsx  
**Protótipo:** image_a6a17f.jpg  

**Descrição:**  
Interface principal do app com duas colunas: Sidebar (esquerda) e conteúdo (direita). Player aparece ao tocar algo.

**Fluxo:**  
- Busca com barra de pesquisa.  
- Cards exibem:  
  - Play  
  - Link do Genius  
  - Link Spotify  
  - Menu “3 pontinhos”  
- Sidebar retrátil salva estado no `localStorage`.

![TELA HOME](./images/home.png "TELA PRINCIPAL COM BUSCA")


---

## 3. Processo do Painel de Admin

**Tela:** AdminPanel.tsx  
**Protótipo:** image_a6a87f.png  

**Descrição:**  
Página protegida para o email admin. Usa abas (Tabs).

**Fluxo:**  
- Alterna entre abas.  
- Pode trocar tema (Padrão, Halloween, Natal).  

![TELA DO PAINEL DO ADMINISTRADOR](./images/paineladmin.png "TELA PAINEL ADMIN")


---

## 4. Processo de Opinar sobre a Busca

**Tela:** FeedbackForm.tsx  
**Protótipo:** image_a6a7e8.png  

**Descrição:**  
Formulário exibido após uma busca válida.

**Fluxo:**  
- Usuário seleciona 1–5 estrelas.  
- Pode escrever comentário.  
- Envia para `/api/feedbacks`.

![TELA DE AVALIAÇÃO](./images/avaliacao.png "TELA DE AVALIAÇÃO")


---

## 5. Processo de Gerar Relatório de Opiniões

**Tela:** AdminPanel.tsx – Aba "Feedback"  

**Descrição:**  
Tabela com todos os feedbacks obtidos da rota `/api/feedbacks`.

**Fluxo:**  
- Exibe notas, comentários e data.  
- Botão “Exportar CSV”.

![TELA DE RELATÓRIOS](./images/relatorios.png "TELA DE RESGATE DAS AVALIAÇÕES")


---

## Diagrama de Classes

O diagrama de classes ilustra graficamente como será a estrutura do software, e como cada uma das classes da sua estrutura estarão interligadas. Essas classes servem de modelo para materializar os objetos que executarão na memória.

As referências abaixo irão auxiliá-lo na geração do artefato “Diagrama de Classes”.

> - [Diagramas de Classes - Documentação da IBM](https://www.ibm.com/docs/pt-br/rational-soft-arch/9.6.1?topic=diagrams-class)
> - [O que é um diagrama de classe UML? | Lucidchart](https://www.lucidchart.com/pages/pt/o-que-e-diagrama-de-classe-uml)

## Modelo ER

O Modelo ER representa através de um diagrama como as entidades (coisas, objetos) se relacionam entre si na aplicação interativa.]

As referências abaixo irão auxiliá-lo na geração do artefato “Modelo ER”.

> - [Como fazer um diagrama entidade relacionamento | Lucidchart](https://www.lucidchart.com/pages/pt/como-fazer-um-diagrama-entidade-relacionamento)


### 4.3. Modelo de dados

O desenvolvimento da solução proposta requer a existência de bases de dados que permitam efetuar os cadastros de dados e controles associados aos processos identificados, assim como recuperações.
Utilizando a notação do DER (Diagrama Entidade e Relacionamento), elaborem um modelo, na ferramenta visual indicada na disciplina, que contemple todas as entidades e atributos associados às atividades dos processos identificados. Deve ser gerado um único DER que suporte todos os processos escolhidos, visando, assim, uma base de dados integrada. O modelo deve contemplar, também, o controle de acesso de usuários (partes interessadas dos processos) de acordo com os papéis definidos nos modelos do processo de negócio.
_Apresente o modelo de dados por meio de um modelo relacional que contemple todos os conceitos e atributos apresentados na modelagem dos processos._

#### 4.3.1 Modelo ER

O Modelo ER representa através de um diagrama como as entidades (coisas, objetos) se relacionam entre si na aplicação interativa.]

As referências abaixo irão auxiliá-lo na geração do artefato “Modelo ER”.

> - [Como fazer um diagrama entidade relacionamento | Lucidchart](https://www.lucidchart.com/pages/pt/como-fazer-um-diagrama-entidade-relacionamento)

#### 4.3.2 Esquema Relacional

O Esquema Relacional corresponde à representação dos dados em tabelas juntamente com as restrições de integridade e chave primária.
 
As referências abaixo irão auxiliá-lo na geração do artefato “Esquema Relacional”.

> - [Criando um modelo relacional - Documentação da IBM](https://www.ibm.com/docs/pt-br/cognos-analytics/10.2.2?topic=designer-creating-relational-model)

![Exemplo de um modelo relacional](images/modeloRelacional.png "Exemplo de Modelo Relacional.")
---


#### 4.3.3 Modelo Físico

Insira aqui o script de criação das tabelas do banco de dados.

Veja um exemplo:

<code>

 -- Criação da tabela Médico
CREATE TABLE Medico (
    MedCodigo INTEGER PRIMARY KEY,
    MedNome VARCHAR(100)
);


-- Criação da tabela Paciente
CREATE TABLE Paciente (
    PacCodigo INTEGER PRIMARY KEY,
    PacNome VARCHAR(100)
);

-- Criação da tabela Consulta
CREATE TABLE Consulta (
    ConCodigo INTEGER PRIMARY KEY,
    MedCodigo INTEGER,
    PacCodigo INTEGER,
    Data DATE,
    FOREIGN KEY (MedCodigo) REFERENCES Medico(MedCodigo),
    FOREIGN KEY (PacCodigo) REFERENCES Paciente(PacCodigo)
);

-- Criação da tabela Medicamento
CREATE TABLE Medicamento (
    MdcCodigo INTEGER PRIMARY KEY,
    MdcNome VARCHAR(100)
);

-- Criação da tabela Prescricao
CREATE TABLE Prescricao (
    ConCodigo INTEGER,
    MdcCodigo INTEGER,
    Posologia VARCHAR(200),
    PRIMARY KEY (ConCodigo, MdcCodigo),
    FOREIGN KEY (ConCodigo) REFERENCES Consulta(ConCodigo),
    FOREIGN KEY (MdcCodigo) REFERENCES Medicamento(MdcCodigo)
);

</code>

Este script deverá ser incluído em um arquivo .sql na pasta src\bd.




### 4.4. Tecnologias

_Descreva qual(is) tecnologias você vai usar para resolver o seu problema, ou seja, implementar a sua solução. Liste todas as tecnologias envolvidas, linguagens a serem utilizadas, serviços web, frameworks, bibliotecas, IDEs de desenvolvimento, e ferramentas._

Apresente também uma figura explicando como as tecnologias estão relacionadas ou como uma interação do usuário com o sistema vai ser conduzida, por onde ela passa até retornar uma resposta ao usuário.


| **Dimensão**   | **Tecnologia**  |
| ---            | ---             |
| SGBD           | MySQL           |
| Front end      | HTML+CSS+JS     |
| Back end       | Java SpringBoot |
| Deploy         | Github Pages    |

