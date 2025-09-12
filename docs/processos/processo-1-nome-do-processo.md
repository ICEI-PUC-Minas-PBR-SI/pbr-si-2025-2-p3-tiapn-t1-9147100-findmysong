### 3.3.1 Processo 1 – Busca e Exibição de Músicas por Trecho da Letra  

**Oportunidades de melhoria:** Automatizar a busca para que o usuário obtenha resultados de forma rápida, precisa e integrada a plataformas oficiais.  

<img width="954" height="590" alt="image" src="https://github.com/user-attachments/assets/a939cde7-1f65-447d-8a08-93a33961844d" />


**Fluxo BPMN (descrição):**  
1. Usuário acessa a aplicação.  
2. Digita o trecho lembrado da música.  
3. Sistema pesquisa na API/base de dados.  
4. Resultados são exibidos (título, artista e link para streaming).  
5. Usuário seleciona a música desejada.  

**Detalhamento das atividades:**  

| **Campo**      | **Tipo**        | **Restrições**        | **Valor default** |
|----------------|-----------------|-----------------------|-------------------|
| trecho_musica  | Caixa de Texto  | mínimo 3 caracteres   | vazio             |
| resultados     | Tabela          | gerado automaticamente| null              |

| **Comando** | **Destino**               | **Tipo**   |
|-------------|---------------------------|------------|
| buscar      | Exibir lista de resultados| default    |
| selecionar  | Abrir link em streaming   | default    |

---

