# GameKeyBlocker

Já perdeu uma disputa em algum jogo online ou qualquer outro tipo, por ter seu jogo minimizado devido o Windows achar que você estava pressionando algum atalho? Esse pequeno programa resolve esse estresse! Nunca mais tenha seu jogo minimizado em suas sessões.

O Bloqueador de Atalhos do WindowsUm é um utilitário desenvolvido em C# e Windows Forms focado em prevenir interrupções acidentais durante sessões de jogos ou momentos de foco intenso. O programa utiliza a API Win32 (Low-Level Keyboard Hooks) para interceptar e bloquear atalhos de sistema do Windows que normalmente tiram o usuário da tela ativa.

## Principais Funcionalidades

* **Bloqueio de Teclas de Sistema:** Intercepta e anula os comandos:
* Tecla Windows (Esquerda e Direita)
* `Alt` + `Tab`
* `Alt` + `Esc`
* `Ctrl` + `Esc`


* **Atalho Global de Alternância:** Ative ou desative o bloqueio a qualquer momento, independente da janela em foco, pressionando simultaneamente as teclas **O** e **P**.
* **Operação em Background (System Tray):** Ao fechar a janela principal, o aplicativo não é encerrado. Ele é minimizado para a bandeja do sistema, mantendo a interface limpa.
* **Feedback Visual e Sonoro:** Emite um alerta sonoro do sistema e altera a cor do botão na interface para indicar claramente se o bloqueio está ativo (Verde) ou inativo (Vermelho).

## Como Utilizar

1. **Execução:** Inicie o executável. A interface principal exibirá o status atual do bloqueio.
2. **Ativação manual:** Clique no botão central ou clique com o botão direito no ícone da bandeja do sistema e selecione "Ligar".
3. **Ativação rápida:** Com o programa rodando (mesmo minimizado), pressione `O` e `P` juntos para alternar o status instantaneamente.
4. **Encerramento:** Para fechar o programa definitivamente, clique com o botão direito no ícone da bandeja do sistema e selecione "Fechar programa". O botão "X" da janela apenas oculta a interface.

## Requisitos Técnicos

* **Linguagem:** C#
* **Framework:** .NET Framework (Windows Forms)
* **Integração:** P/Invoke para acesso nativo a bibliotecas do Windows (`user32.dll`, `kernel32.dll`) visando o gerenciamento de Hooks de teclado (`SetWindowsHookEx`).

## Estrutura do Código

O projeto baseia-se em interceptação de baixo nível (Low-Level Keyboard Hook). O tráfego do teclado é monitorado antes de chegar aos aplicativos. Se o bloqueio estiver ativo e uma tecla restrita for identificada, o código retorna um ponteiro ignorando a ação padrão do sistema operacional, efetivamente bloqueando o comando.
