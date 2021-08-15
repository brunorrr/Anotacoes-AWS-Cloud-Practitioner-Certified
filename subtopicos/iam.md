# IAM

## IAM Introduction: Users, Groups, Policies

Cada conta AWS é, na verdade, um usuário root. Este usuário possui usuários [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) associados a ele que são utilizados para gerenciar os recursos da conta. Esses usuários [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) (sem ser o root) podem (sem obrigatoriedade) estar contidos em grupos [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html).

Um usuário [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) pode estar contido em vários grupos [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html).Um grupo [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) pode conter vários usuários [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html).Um grupo [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) NÃO pode conter outro grupo [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html).

Uma permissão é uma regra [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) que dá acesso a um recurso da AWS.Uma policy(política, traduzido) é um conjunto de permissão.Cada grupo [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) ou usuário [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) pode possuir de 0 a N policies.Quando você adiciona um usuário [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) a um grupo, você automaticamente associa todas as policies(e as permissões anexadas a elas) a este usuário).

## IAM MFA Overview

MFA(Autenticação Multifator) é uma forma complementar de autenticação que fortalece o perímetro de segurança da tua conta afastando eventuais invasores que, de alguma forma, tenham descoberto a senha da sua conta. É altamente recomendado que todos os acessos na AWS estejam coberto por MFA.

## AWS CloudShell

AWS **Cloudshell** é uma forma de acessar o terminal da instância pelo portal da AWS de forma já pré autenticada sem necessidade de selecionar a instância.

## IAM Roles for AWS Services

Roles(funções, traduzido) é uma forma de permissão temporária no qual você permite que um serviço possa acessar uma instância, lambda ou outro serviço no seu nome temporariamente.

## IAM Security Tools

**IAM Credentials report** é um relatório em formato Excel que mostra um relatório de acessos com todos os acessos de todos os usuários [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) da conta AWS.**IAM Access Advisor** mostra de uma forma simplificada os acessos dados a um usuário [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) e quais serviços este usuário [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) acessou.

## Boas práticas IAM

Boas práticas:

* Somente use a conta root para fazer as configurações base na AWS.
* Um usuário físico = Um usuário [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
* Pratique o princípio de menor privilégio(least privilege principle) dando aos usuários apenas as permissões que eles precisam.
* Adicione Usuários a grupos e Adicione permissões a grupos.
* Crie políticas de senhas fortes.
* Use e Endosse o uso de MFA
* Crie e use Roles para dar permissões para serviços AWS
* Use chaves de acesso(Veja chaves privada/chaves públicas) para acessar CLIs e SDKs
* Faça auditoria nas permissões da conta AWS com o relatório de credenciais IAM.
* Nunca compartilhe usuários [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) ou Chaves de acesso.

## Shared Responsibility Model for IAM

Responsabilidade compartilhada [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html):

AWS:

* Infra
* Configuração e Análise de vulnerabilidade
* Validação de compliance.

Você:

* Administração e monitoramento de Usuários [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html), Grupos, Roles e Policies.
* Gerenciamento de MFA nas contas.
* Manter um rotacionamento de chaves constante.
* Usar as ferramentos [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) para aplicar as permissões apropriadas.
* Analisar padrões de acesso e revisar permissões.