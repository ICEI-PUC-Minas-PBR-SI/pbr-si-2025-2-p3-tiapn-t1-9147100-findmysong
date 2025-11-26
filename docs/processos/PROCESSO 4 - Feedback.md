# **3.3.4 Processo 4 – Feedback dos Usuários**

**Oportunidades de melhoria:** Estruturar um processo de coleta de opinião para refinar a busca.

### **Descrição das atividades do processo**

Este processo permite que o usuário forneça feedback sobre os resultados de uma pesquisa. Após realizar uma busca e analisar os resultados, o sistema oferece a opção de avaliação. Se o usuário aceitar, ele envia uma nota e um comentário, que são armazenados. Caso contrário, o processo encerra.

![GRÁFICO BPMN do PROCESSO 4](../images/BIZAGI33NEW2.png "GRÁFICO BPMN do Processo 4.")

### **Fluxo BPMN (descrição):**

1. Usuário realiza uma busca e recebe resultados.  
2. Usuário analisa os resultados (ouve preview, vê letra).  
3. Sistema exibe opção de avaliar precisão.  
4. Usuário envia feedback (nota + comentário opcional).  
5. Sistema armazena feedback para análise posterior.

---

## **Atividade 1: Realizar busca de música**

**Participante:** Usuário

**Descrição:** O usuário insere o nome da música, artista ou trecho da letra na barra de pesquisa principal para iniciar o processo.

### **Campos da tela:**

| **Campo**       | **Tipo**        | **Restrições**          | **Valor default** |
|-----------------|-----------------|--------------------------|-------------------|
| Barra de Busca  | Caixa de Texto  | Obrigatório preencher    | Vazio             |

### **Comandos principais:**

| **Comando** | **Destino**                           | **Tipo**   |
|-------------|----------------------------------------|------------|
| Buscar      | API do Spotify (/api/spotify/search)   | default    |

---

## **Atividade 2: Analisar resultados**

**Participante:** Usuário

**Descrição:** O usuário interage com os cards de música retornados (ouvindo o preview ou abrindo a letra) para verificar se a busca foi precisa.

### **Campos da tela:**

| **Campo**        | **Tipo**            | **Restrições**                       | **Valor default** |
|------------------|---------------------|---------------------------------------|-------------------|
| Player de Áudio  | Botão Interativo    | Apenas se houver preview disponível   | Pausado           |
| Link Spotify     | Hiperlink           | Abre em nova aba                      | N/A               |
| Link Letra       | Hiperlink           | Abre em nova aba (Genius)             | N/A               |

### **Comandos principais:**

| **Comando**     | **Destino**                  | **Tipo**   |
|-----------------|------------------------------|------------|
| Tocar Preview   | Inicia o player no rodapé     | default    |
| Ver Letra       | Redireciona para o Genius     | link       |

---

## **Atividade 3: Enviar avaliação e comentário**

**Participante:** Usuário

**Descrição:** Caso decida avaliar, o usuário seleciona uma nota (estrelas) e opcionalmente deixa um comentário sobre a precisão da busca.

### **Campos da tela:**

| **Campo**    | **Tipo**         | **Restrições**                            | **Valor default** |
|--------------|------------------|--------------------------------------------|-------------------|
| Avaliação    | Seleção (1-5)    | Obrigatório se for enviar feedback         | Vazio             |
| Comentário   | Caixa de Texto   | Máximo de 500 caracteres                   | Vazio             |

### **Comandos principais:**

| **Comando** | **Destino**                    | **Tipo**   |
|-------------|--------------------------------|------------|
| Enviar      | Armazena na base (/api/feedback) | default    |
| Cancelar    | Limpa o formulário              | cancel     |

---
