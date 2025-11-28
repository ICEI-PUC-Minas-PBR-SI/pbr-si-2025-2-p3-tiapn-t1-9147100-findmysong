# 7. Conclusão

<span style="color:red">Pré-requisitos: <a href="6-Interface-Sistema.md"> Projeto da Solução</a></span>

O desenvolvimento do **FindMySong** representou uma jornada significativa de aprendizado e aplicação prática de conceitos de Engenharia de Software e Sistemas de Informação. O projeto, que nasceu da necessidade de identificar músicas a partir de trechos de letras, evoluiu para uma aplicação web funcional, moderna e integrada.

---

## Resultados Obtidos

A solução final atendeu plenamente aos objetivos definidos inicialmente. Entregamos uma plataforma que não apenas realiza buscas de forma eficiente, mas também oferece uma experiência enriquecida ao usuário.

### Integração Real  
A conexão com a API do Spotify e o redirecionamento para o Genius transformaram a aplicação em um hub centralizador de informações musicais. Essa integração respeita direitos autorais e garante acesso legal ao conteúdo, conforme planejado nas restrições iniciais.

### Experiência de Usuário (UX)  
A implementação como **Single Page Application (SPA)** em **React** proporcionou uma navegação fluida e responsiva. Elementos como o player global de preview e a persistência de preferências (tema visual, estado da sidebar) elevaram o nível da usabilidade além do previsto.

### Arquitetura Robusta  
A divisão clara em **Frontend (Vercel)**, **Backend (Render)** e **Banco de Dados (PostgreSQL)** mostrou domínio técnico da equipe na construção de uma arquitetura distribuída, escalável e compatível com tecnologias amplamente utilizadas, como Node.js e TypeScript.

---

## Limitações da Solução

Mesmo com os resultados positivos, algumas limitações foram identificadas no escopo atual do projeto.

### Dependência de Terceiros  
O preview de áudio depende da disponibilidade do recurso fornecido pela API do Spotify. Em casos onde o preview_url não é liberado devido a licenciamento regional, a experiência do usuário é reduzida, exigindo redirecionamento externo.

### Gestão de Conteúdo  
As letras das músicas não são armazenadas internamente. O uso do Genius simplifica questões relacionadas a direitos autorais, porém desloca o usuário para fora da plataforma para visualizar a letra completa.

### Recursos Sociais Limitados  
Playlists e curtidas são estritamente pessoais. A plataforma não oferece ainda compartilhamento de playlists ou recursos de interação social entre usuários.

---

## Sugestões para Trabalhos Futuros

Com foco em evolução contínua, são propostas as seguintes melhorias para versões futuras do FindMySong:

### Implementação de OAuth Completo  
Permitir login social (Google, Spotify, Facebook) para reduzir barreiras de entrada e facilitar o acesso.

### Integração com Web Playback SDK  
Possibilitar a reprodução de músicas completas (para usuários Spotify Premium), substituindo os previews de 30 segundos.

### Gamificação e Comunidade  
Adicionar funcionalidades sociais, como compartilhamento de playlists, comentários públicos e recomendações colaborativas baseadas no gosto musical.

### Expansão da API de Letras  
Integrar APIs que permitam exibir letras sincronizadas dentro da aplicação, oferecendo experiências como acompanhamento em tempo real ou karaokê.

---

Em síntese, o **FindMySong** cumpriu seu propósito acadêmico e prático, apresentando uma solução útil, tecnicamente sólida e apoiada em uma stack moderna capaz de resolver um problema real de negócio.
