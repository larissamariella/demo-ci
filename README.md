# Atividade de Integração Contínua

Neste repositório, fiz a atividade prática de Integração Contínua usando o GitHub Actions, seguindo o [roteiro disponibilizado pela UFMG](https://github.com/aserg-ufmg/demo-ci).

Primeiro, criei um fork do projeto e configurei o arquivo `.github/workflows/actions.yaml` para compilar o código Java e executar os testes automaticamente a cada push na `main` ou pull request para ela. Usei Java 8 e Maven, como no exemplo da atividade.

Depois de salvar a configuração, acompanhei a execução pela aba Actions. Nessa primeira etapa, o build e os dois testes passaram.

Para a segunda parte, criei a branch `bug` e alterei a função `soma` da calculadora: no lugar de retornar `x + y`, ela passou a retornar `x + y + 1`. A ideia era colocar um erro de propósito para ver se os testes conseguiam identificar o problema.

Abri um pull request dessa branch para a `main`, e o GitHub Actions executou tudo novamente. O código compilou, mas os dois testes falharam: a soma de 2 + 3 retornou 6 em vez de 5, e a de 4 + 6 retornou 11 em vez de 10. Deixei o PR aberto, sem fazer o merge, para manter o registro desse resultado.

Com esse exemplo, consegui ver na prática como a integração contínua ajuda a identificar um erro antes de juntar a alteração ao código principal.

Os resultados podem ser conferidos aqui:

- [Execução inicial, com os testes passando](https://github.com/larissamariella/demo-ci/actions/runs/42539344992)
- [Pull request com o bug proposital](https://github.com/larissamariella/demo-ci/pull/1)
- [Execução do PR, com os testes falhando](https://github.com/larissamariella/demo-ci/actions/runs/42539438576)

O projeto e o roteiro originais são do repositório [aserg-ufmg/demo-ci](https://github.com/aserg-ufmg/demo-ci).
