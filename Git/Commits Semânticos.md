## O que é “semântica em commits”?

Quando você faz uma alteração em um projeto e “salva” essa mudança no Git, você escreve uma mensagem explicando o que foi feito.
**Semântica em commits** é uma forma de escrever essas mensagens de um jeito organizado e fácil de entender, usando um padrão.

Assim, todo mundo que trabalhar no projeto consegue entender rapidinho o que mudou só lendo as mensagens.

---

## Por que isso é importante?

* Para facilitar o entendimento das mudanças feitas no código.
* Para ajudar outras pessoas (e você mesmo) a revisar o que foi feito.
* Para gerar automaticamente um resumo das novidades e correções do projeto (chamado “changelog”).
* Para ajudar a controlar versões do projeto (tipo dizer se é uma atualização pequena ou grande).

## Tipos mais usados e quando usar cada um

| Tipo      | Para que serve                                                                                        | Exemplo de mensagem                               |
| ----------| ----------------------------------------------------------------------------------------------------- | ------------------------------------------------- |
| *feat*    | Quando você cria uma funcionalidade nova                                                              | feat(login): adiciona botão de “entrar com Google”|
| *fix*     | Quando corrige um erro no código                                                                      | fix(menu): corrige erro que travava o menu        |
| *docs*    | Quando muda ou adiciona alguma coisa na documentação (guias, manuais, README)                         | docs: atualiza instruções de instalação           |
| *style*   | Quando muda só o visual do código, como espaços, indentação ou formatação, sem mexer no funcionamento | style: ajusta espaçamento do código               |
| *refactor*| Quando reorganiza ou melhora o código sem mudar o que ele faz (sem bugs ou funcionalidades novas)     | refactor: melhora organização da função de login  |
| *test*    | Quando adiciona ou conserta testes (códigos que verificam se o programa funciona)                     | test(auth): cria teste para verificação de senha  |
| *chore*   | Para tarefas gerais que não mudam o código do programa em si, como atualizar ferramentas              | chore: atualiza pacotes do projeto                |

## Como escrever mensagens com semântica? (O padrão Conventional Commits)

As mensagens de commit seguem este formato básico:

```
<tipo>[opcional: parte do código]: descrição curta do que foi feito
```

### O que significa cada parte?

* **tipo**: Diz o que você fez na mudança, por exemplo, adicionou algo novo, corrigiu um erro, atualizou a documentação, etc.
* **\[parte do código]** (opcional): Indica qual parte do programa foi mexida (pode ser “login”, “menu”, “api”, etc.).
* **descrição curta**: Um resumo pequeno, simples, do que você fez nessa mudança.
