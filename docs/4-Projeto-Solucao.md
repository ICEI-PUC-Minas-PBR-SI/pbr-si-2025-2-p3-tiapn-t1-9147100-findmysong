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


# 4.3. Modelo de dados

## 4.3.1 Modelo ER (Descrição)

Entidades:  
- usuarios  
- playlists  
- playlist_musicas  
- curtidas  
- biblioteca  
- feedbacks  
- configuracoes  

### Relacionamentos 1:N

- Um usuario pode ter muitas playlists.  
- Um usuario pode ter muitas curtidas.  
- Um usuario pode ter muitos registros em biblioteca.  
- Uma playlist pode ter muitas playlist_musicas.

### Entidades Independentes

- feedbacks (não referencia usuarios — anônimo)  
- configuracoes (tabela única)

---

## 4.3.2 Esquema Relacional (Conceitual)

usuarios (id, nome, email, senha, avatar_url, data_cadastro)
configuracoes (id, site_name, theme, items_per_page, language, updated_at)
feedbacks (id, query, nota, comentario, data_envio)
curtidas (id, usuario_id, spotify_id, titulo, artista, imagem, url)
biblioteca (id, usuario_id, spotify_id, titulo, artista, imagem, url)
playlists (id, usuario_id, nome, descricao, data_criacao)
playlist_musicas (id, playlist_id, spotify_id, titulo, artista, imagem, url, adicionada_em)


---

## 4.3.3 Modelo Físico (Script SQL)

```sql
-- 1. Tabela usuarios
CREATE TABLE usuarios (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(100) NOT NULL,
  email VARCHAR(100) NOT NULL UNIQUE,
  senha VARCHAR(255) NOT NULL,
  avatar_url TEXT,
  data_cadastro TIMESTAMP DEFAULT NOW()
);

-- 2. Tabela configuracoes
CREATE TABLE configuracoes (
  id SERIAL PRIMARY KEY DEFAULT 1,
  site_name VARCHAR(100),
  theme VARCHAR(50) DEFAULT 'light',
  items_per_page INTEGER DEFAULT 20,
  language VARCHAR(10) DEFAULT 'pt-BR',
  updated_at TIMESTAMP DEFAULT NOW()
);

-- 3. Tabela feedbacks
CREATE TABLE feedbacks (
  id SERIAL PRIMARY KEY,
  query TEXT NOT NULL,
  nota INTEGER NOT NULL CHECK (nota BETWEEN 1 AND 5),
  comentario TEXT,
  data_envio TIMESTAMP DEFAULT NOW()
);

-- 4. Tabela curtidas
CREATE TABLE curtidas (
  id SERIAL PRIMARY KEY,
  usuario_id INTEGER REFERENCES usuarios(id) ON DELETE CASCADE,
  spotify_id VARCHAR(255) NOT NULL,
  titulo TEXT,
  artista TEXT,
  imagem TEXT,
  url TEXT,
  UNIQUE(usuario_id, spotify_id)
);

-- 5. Tabela biblioteca
CREATE TABLE biblioteca (
  id SERIAL PRIMARY KEY,
  usuario_id INTEGER REFERENCES usuarios(id) ON DELETE CASCADE,
  spotify_id VARCHAR(255) NOT NULL,
  titulo TEXT,
  artista TEXT,
  imagem TEXT,
  url TEXT,
  UNIQUE(usuario_id, spotify_id)
);

-- 6. Tabela playlists
CREATE TABLE playlists (
  id SERIAL PRIMARY KEY,
  usuario_id INTEGER REFERENCES usuarios(id) ON DELETE CASCADE,
  nome VARCHAR(100) NOT NULL,
  descricao TEXT,
  data_criacao TIMESTAMP DEFAULT NOW()
);

-- 7. Tabela playlist_musicas
CREATE TABLE playlist_musicas (
  id SERIAL PRIMARY KEY,
  playlist_id INTEGER REFERENCES playlists(id) ON DELETE CASCADE,
  spotify_id VARCHAR(255) NOT NULL,
  titulo TEXT,
  artista TEXT,
  imagem TEXT,
  url TEXT,
  adicionada_em TIMESTAMP DEFAULT NOW(),
  UNIQUE(playlist_id, spotify_id)
);
```




### 4.4. Tecnologias

_Descreva qual(is) tecnologias você vai usar para resolver o seu problema, ou seja, implementar a sua solução. Liste todas as tecnologias envolvidas, linguagens a serem utilizadas, serviços web, frameworks, bibliotecas, IDEs de desenvolvimento, e ferramentas._

Apresente também uma figura explicando como as tecnologias estão relacionadas ou como uma interação do usuário com o sistema vai ser conduzida, por onde ela passa até retornar uma resposta ao usuário.


| **Dimensão**   | **Tecnologia**  |
| ---            | ---             |
| SGBD           | MySQL           |
| Front end      | HTML+CSS+JS     |
| Back end       | Java SpringBoot |
| Deploy         | Github Pages    |

