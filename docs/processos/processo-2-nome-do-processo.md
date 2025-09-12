### 3.3.2 Processo 2 – Cadastro e Atualização de Informações  

**Oportunidades de melhoria:**  
Permitir que administradores atualizem parâmetros do sistema de forma centralizada, sem necessidade de alterações manuais em código. Isso inclui ajustes na interface, registro de eventos e feriados, além de configurações de backend e frontend.  

<img width="958" height="594" alt="image" src="https://github.com/user-attachments/assets/2914d3ef-41a5-42ac-a913-865bd19310f7" />


**Fluxo BPMN (descrição):**  
1. Administrador acessa o painel administrativo.  
2. Seleciona a funcionalidade desejada (interface, eventos, feriados, backend ou frontend).  
3. Realiza cadastro ou atualização das informações.  
4. Sistema salva e aplica as alterações na base/configuração.  
5. Atualizações ficam disponíveis imediatamente para os usuários do sistema.  

**Detalhamento das atividades:**  

| **Campo**          | **Tipo**       | **Restrições**             | **Valor default** |
|--------------------|----------------|----------------------------|-------------------|
| evento_feriado     | Caixa de Texto | opcional                   | vazio             |
| data_evento        | Calendário     | formato DD/MM/AAAA         | vazio             |
| ajuste_interface   | Dropdown       | seleção de tema/opções     | padrão do sistema |
| config_backend     | Área de Texto  | parâmetros técnicos        | vazio             |
| config_frontend    | Área de Texto  | parâmetros técnicos        | vazio             |

**Comandos principais:**  

| **Comando** | **Destino**       | **Tipo**   |
|-------------|-------------------|------------|
| salvar      | Base/configuração | default    |
| editar      | Base/configuração | default    |
| publicar    | Sistema           | aplica em tempo real |

---
