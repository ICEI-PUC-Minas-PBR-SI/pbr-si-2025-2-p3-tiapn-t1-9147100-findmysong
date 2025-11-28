# FindMySong

`Sistemas da Informação `

`Trabalho Interdisciplinar: Aplicações para Processos de Negócios`

`3º Período - 2º Semestre de 2025`

O projeto consiste no desenvolvimento de um sistema inovador de busca de músicas que possibilita ao usuário encontrar canções a partir de pequenos trechos de suas letras. Diferente dos aplicativos convencionais, que exigem o nome da música ou do artista, a proposta é oferecer uma ferramenta prática e intuitiva, capaz de localizar a canção desejada mesmo quando a lembrança é limitada a uma única palavra ou frase da letra.

Além de facilitar o acesso às músicas, o sistema busca atender diferentes perfis de usuários, desde ouvintes ocasionais até músicos e estudantes. O projeto prevê ainda recursos de feedback, relatórios de uso e integração com plataformas credenciadas de streaming, garantindo não apenas a usabilidade, mas também a relevância técnica e a contribuição para o mercado em constante crescimento da música digital.

## Integrantes

* Abraao Lucas Fialho de Paula Villela
* Eduardo Porto Gonçalves
* Gustavo Henrique Chagas Ramos
* Heitor Carlos Rezende Junior
* Samuel Ribeiro Faleiro

## Orientador

* Cleia Marcia Gomes Amaral

## Instruções de Utilização

Esta seção descreve, de forma clara e direta, como qualquer usuário pode acessar e utilizar o sistema **FindMySong**.

### 1. Acesso ao Sistema

Para utilizar o FindMySong, acesse:

**https://find-my-song-frontend.vercel.app/login**

A partir dessa página, todas as funcionalidades principais ficam disponíveis após o login.

---

### 2. Criar Conta

- Na tela inicial, selecione a aba **Sign Up** (Criar conta).  
- Informe os dados solicitados:  
  - Nome Completo  
  - E-mail  
  - Senha  
  - Confirmação de Senha  
- Clique em **Create Account**.  
- Após o registro bem-sucedido, você será redirecionado automaticamente para a aba de login.

---

### 3. Realizar Login

- Na tela inicial, certifique-se de estar na aba **Sign In**.  
- Insira seu e-mail e senha cadastrados.  
- Clique em **Sign In** para acessar o sistema.

---

### 4. Pesquisar Músicas

A pesquisa é a principal funcionalidade do sistema.

- No campo de busca no topo da tela, digite qualquer palavra, frase, nome de artista ou trecho da letra.
- Os resultados aparecerão em **cards** contendo:
  - Capa do álbum  
  - Nome da música  
  - Artista  
- Clique no botão **Play** (verde) para ouvir um preview de 30 segundos no player fixo no rodapé.

---

### 5. Curtir Músicas

Caso goste de uma música encontrada:

- Clique no ícone **coração (♥)** no card.  
- A música será adicionada à sua lista de **Músicas Curtidas**.

---

### 6. Visualizar Biblioteca e Playlists

- Acesse o **menu lateral esquerdo**.  
- Clique em **Sua Biblioteca**.  
- Serão exibidas suas playlists e músicas salvas.  
- Clique em **Músicas Curtidas** para visualizar apenas seus likes.

---

### 7. Criar Playlists

- No menu lateral, clique em **Criar Playlist**.  
- Informe:
  - Nome da playlist  
  - Descrição  
- Após criar, adicione músicas clicando nos **três pontinhos** nos cards.

---

### 8. Visualizar Letras e Ouvir no Spotify

Em qualquer card de música:

- Clique em **Letra (Genius)** para abrir a letra completa.  
- Clique em **Spotify** para ouvir a música completa no aplicativo ou site.

---

### 9. Painel Administrativo (Apenas Administradores)

Usuários com permissão especial podem acessar o menu **Admin** para:

- Alterar o **tema** da plataforma (Padrão, Halloween, Natal).  
- Visualizar **feedbacks** enviados pelos usuários.  

---

### 10. Avaliar o Sistema

Após realizar uma busca, um formulário pode aparecer solicitando feedback:

- Escolha uma nota de **1 a 5 estrelas**.  
- Insira um comentário opcional.  
- Clique em **Enviar** para contribuir com a melhoria do sistema.

---

# Documentação

<ol>
<li><a href="docs/1-Contexto.md"> Documentação de Contexto</a></li>
<li><a href="docs/2-Especificação.md"> Especificação do Projeto</a></li>
<li><a href="docs/3-Modelagem-Processos-Negócio.md"> Modelagem dos Processos de Negocio</a></li>
<li><a href="docs/4-Projeto-Solucao.md"> Projeto da solução</a></li>
<li><a href="docs/5-Planejamento-Projeto.md"> Gerenciamento do Projeto</a></li>
<li><a href="docs/6-Interface-Sistema.md"> Interface do Sistema</a></li>
<li><a href="docs/7-Conclusão.md"> Conclusão</a></li>
<li><a href="docs/8-Referências.md"> Referências</a></li>
</ol>

# Código

<li><a [href="src/README.md](https://github.com/Duardo-Dudds/FindMySong-frontend.git)"> Código Frontend</a></li>
<li><a [href="src/README.md](https://github.com/Duardo-Dudds/FindMySong-backend.git)"> Código Backend</a></li>

# Apresentação

<li><a href="presentation/README.md"> Apresentação da solução</a></li>


## Histórico de versões

### 1.0.0 – Versão Final
- Implementação completa do Player de Música Global com Context API.  
- Correção de bugs de layout (sidebar e padding).  
- Integração final com Spotify (`market=BR`).  
- Finalização da documentação e diagramas.

### 0.4.0
- Adição do Painel Administrativo com gestão de temas e feedbacks.  
- Implementação da funcionalidade de criar e gerenciar Playlists.

### 0.3.0
- Refatoração da interface utilizando **shadcn/ui**.  
- Nova tela de Autenticação unificada (**AuthPage**).

### 0.2.0
- Integração com a API do Spotify para busca de músicas.  
- Integração com o Genius para exibição de letras externas.

### 0.1.0
- Configuração inicial do ambiente (React + Node.js).  
- Estruturação do Banco de Dados PostgreSQL.

### 0.0.1
- Definição do escopo e modelagem dos processos de negócio.

---
