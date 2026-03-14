💻 Samsung Galaxy Book Technical Guide: Boot & Disk Recovery

Este repositório documenta soluções técnicas definitivas para problemas de boot e permissões de disco em notebooks da linha Samsung Galaxy Book (incluindo modelos como NP750XFG e a série Book 4)

https://github.com/adrianosalves/samsung-galaxy-book-recovery-guide/blob/main/samsung-galaxy-book-recovery-guide.png

.
🛠️ Problemas Comuns Resolvidos
1. Pen drive de boot não é reconhecido: O notebook não mostra o dispositivo USB nas opções de boot.

2. Disco C Bloqueado (Acesso Negado): Após atualizações, o Windows bloqueia o acesso à unidade principal, impedindo o funcionamento de apps como Calculadora e Gerenciador de Tarefas.

--------------------------------------------------------------------------------
🚀 1. Configuração do Pen Drive de Boot (O Segredo)

Para que a BIOS dos modelos Samsung mais recentes reconheça o dispositivo USB, o "segredo" está na configuração do software Rufus:

- Esquema de Partição: Deve ser obrigatoriamente GPT.
- Sistema de Destino: UEFI (não CSM).
- Ferramenta recomendada: Sergei Strelec (WinPE) para reparos de permissão ou a ISO oficial do Windows 11 para instalação limpa.

--------------------------------------------------------------------------------
🔐 2. Recuperação de Disco C: Acesso Negado (Sem Formatar)

Se o seu disco principal exibir "Acesso Negado", o problema é a corrupção das permissões de segurança.

Passo a Passo:

Inicie o notebook pelo pen drive com o sistema Sergei Strelec.

Acesse as Propriedades do Disco Local C: > Segurança > Avançado.

Adicione manualmente os seguintes grupos que costumam sumir após atualizações críticas:

- SYSTEM (Controle Total).
- Administradores (Controle Total).
- Usuários Autenticados (Controle Total).
- Usuários (Leitura e Execução).
  
Aplique as alterações e reinicie o sistema normalmente.

--------------------------------------------------------------------------------
⌨️ 3. Comandos e Teclas de Atalho Essenciais

F2: Acessar a configuração da BIOS.

F10: Acessar o Menu de Boot temporário (em alguns modelos Samsung).

Shift + Reiniciar: Acessar as opções avançadas de inicialização do Windows.

Alt + D: Atalho para excluir partições durante a instalação do Windows via teclado.

--------------------------------------------------------------------------------
🌐 4. Drivers e BIOS (Modelos Recentes)

Para garantir a instalação correta em modelos como o NP750XFG:

- BIOS: Em casos de bloqueio de boot, pode ser necessário entrar na BIOS (F2), ir em Security > Secure Boot Control, mudar para Custom e apagar as chaves de Secure Boot (Delete all Secure Boot variables).

- Drivers de Rede: Utilize o aplicativo Samsung Update em outro computador para baixar o driver de Wireless LAN específico para o modelo do seu notebook e copie-o para o pen drive de instalação.

--------------------------------------------------------------------------------
🤝 Créditos e Referências

Solução de esquema de partição GPT: Siron Digital.
Guia de recuperação de permissões via WinPE: Baseado em procedimentos técnicos para Galaxy Book 4.

--------------------------------------------------------------------------------
Como usar este guia?

Este README serve como uma base de conhecimento para técnicos de TI. Sinta-se à vontade para abrir uma Issue caso encontre uma variação nestes procedimentos para outros modelos Samsung.

--------------------------------------------------------------------------------
Dica: Você pode copiar e colar esse conteúdo diretamente em um arquivo chamado README.md no seu perfil do GitHub. Ele usa a formatação padrão Markdown suportada pela plataforma.
