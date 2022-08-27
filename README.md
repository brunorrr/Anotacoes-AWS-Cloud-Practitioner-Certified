# AWS Cloud Practitioner

Este repositório é uma compilação das anotações que eu fiz enquanto fazia um curso da Udemy para a prova de certificação **CLF-C01 Cloud Practitioner**.
Nele estão contempladas informações relacionadas a serviços, políticas e processos da AWS que provavelmente cairão na prova de certificação.
O objetivo deste repositório não é funcionar como um curso ou tutorial sobre AWS, mas apenas como guia adicional para quem estiver buscando obter uma certificação CLF-C01, utilize-o para buscar uma definição mais simples e rápida de termos que você já tenha aprendido e que esteja com dificuldades para lembrar.

O curso que eu fiz para criar estas anotações foi o [Ultimate AWS Certified Cloud Practitioner](https://www.udemy.com/course/aws-certified-cloud-practitioner-new/) criado pelo **Stephane Maarek**.

Para facilitar o cruzamento de dados e informações ao longo da leitura, cada nome de produto funcionará como um verbete que será um link para algum artigo(oficial ou não) que dará mais detalhes sobre aquele produto/serviço/política.

## 6 Vantagens do uso de Cloud Computing

1. Você Troca CAPEX(Capital Expense) por OPEX(Operational Expense) - Significa que você não se preocupa mais com o hardware, apenas com as questões operacionais da sua aplicação.
2. Benefícios de enormes economias de escala. - Significa que teu gasto está totalmente adaptado ao teu consumo, não existe ociosidade, nem sobrecarregamento.
3. Pare de adivinhar sua capacidade. - Significa que com a cloud você pode utilizar de ferramentas e métricas para saber com mais exatidão qual será seu gasto com infra.
4. Aumente a tua velocidade e agilidade. - Significa que com a cloud você terá vários impedimentos a menos para ter um desenvolvimento mais ágil, com entregas mais curtas rápidas e contínuas.
5. Pare de gastar dinheiro rodando e mantendo data centers. - Agora quem mantém os datacenters é a AWS, você cuida apenas do contexto do teu negócio.
6. Torne-se global em minutos. - A infra e as ferramentas da AWS permitem que em alguns minutos você publique uma aplicação completa disponível para clientes no mundo todo.

## Tipos de Serviços Cloud

* Infrastructure as a Service (IaaS) - Serviços que fornecem conexão de rede, SOs, armazenamento, alta flexibilidade de utilização. Costumam ser genéricos, podem ser utilizados para vários fins. Ex: [EC2](https://aws.amazon.com/pt/ec2/).
* Platform as a Service (PaaS) - Serviços que fornecem uma plataforma para deployment, restauração, manutenção de dados, mas não te dão acesso ao SO diretamente, Ex: **Elastic BeanStalk**, [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html).
* Software as a Service (SaaS) - Serviços que atuam como uma aplicação na nuvem gerenciada pela AWS que você chama da sua aplicação para algum fim, Ex: **Rekognition**, **Polly**, **Translate**.
* Code as a Service (Caas) ou Function as a Service (FaaS) - Serviços orientados a evento que executam uma função simples na núvem em um ambiente serverless, Ex: [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html).

## AWS Cloud Overview

Sobre **Regions**, **Availability Zones** e **Data Centers**.
Uma Region é uma área no mundo na qual a Amazon disponibiliza um pacote de serviços da AWS.
Cada Region é composta de 2 a 6(geralmente 3) AZs(Availability Zones) ou Zonas de Disponibilidade, as AZs ficam separadas entre si de forma que haja uma redundância e seus serviços não sejam afetados em caso de desastres que afetem parcialmente a region.
Cada AZ é composta de N datacenters, sendo N >= 1 e N um número conhecido apenas pela Amazon, nestes datacenters são armazenados e processados os serviços contratados pelos clientes.

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

## IAM Best Practices

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
AWS

* Infra
* Configuração e Análise de vulnerabilidade
* Validação de compliance.

Você

* Administração e monitoramento de Usuários [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html), Grupos, Roles e Policies.
* Gerenciamento de MFA nas contas.
* Manter um rotacionamento de chaves constante.
* Usar as ferramentos [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) para aplicar as permissões apropriadas.
* Analisar padrões de acesso e revisar permissões.

## EC2 Instance Types Basics

O tipo da instância [EC2](https://aws.amazon.com/pt/ec2/) representa as características dela. Dado o formato classegeração.porte sendo o porte representando o tamanho de memória RAM que ela possa possuir ou a capacidade de processamento.Exemplo: t2.nano, m5.2xlarge
Na seguinte página é possível obter o portfólio de instâncias [EC2](https://aws.amazon.com/pt/ec2/) da AWS <https://aws.amazon.com/pt/ec2/instance-types/>

## EC2 Instance Launch Types

4 Tipos de opções de compra de instâncias [EC2](https://aws.amazon.com/pt/ec2/):

1. On-Demand - Modo mais caro, comprado a qualquer momento, sem compromisso de permanência.
2. Reservado - Mais barato que On-Demand, permanência mínima de 1 ano. Pode ser comprado no modo 24/7, no modo 24/7 com instância flexível ou em apenas algumas horas por semana.
3. Spot Instances - Modo mais barato - Uso de instâncias ociosas para execução de trabalhos, risco de perder o trabalho caso a instância seja solicitada por algum cliente(ver analogia do hotel).
4. Host Dedicado - Uso de datacenter físico dedicado para alocação de instâncias.

Reserva de instâncias [EC2](https://aws.amazon.com/pt/ec2/) podem ter um desconto de até 75% se comparada com a On-Demand.Período de reserva pode ser de 1 ano OU de 3 anos.

Spot instances são instâncias [EC2](https://aws.amazon.com/pt/ec2/) no qual o cliente usa um espaço de processamento ocioso para executar uma tarefa específica, desta forma a Amazon não deixa o hardware parado, pode-se comparar isso à aquelas passagens aéreas vendidas a funcionários de Cias aéreas nos aeroportos por um preço bem menos. Apesar de ser bem mais barato (até 90% a menos que On-Demand), neste modo, se algum cliente solicitar uma reserva de instância por algum outro modo que não seja spot e a Amazon seja obrigada a utilizar o espaço de processamento utilizado pela instância Spot, a instância é eliminada.Devido a esta característica contratual instável, instâncias Spot são recomendadas para tarefas com início, meio e fim definidos, tarefas batch e que não possuam interação com clientes externos.

Copiando conteúdo do PDF:

* On demand: coming and staying in resort whenever we like, we pay the full price
* Reserved: like planning ahead and if we plan to stay for a long time, we may get a good discount.
* Spot instances: the hotel allows people to bid for the empty rooms and the highest bidder keeps the rooms. You can get kicked out at any time.
* Dedicated Hosts: We book an entire building of the resort.

## [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) Overview

A [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) é um volume de disco que você consegue conectar à sua instância [EC2](https://aws.amazon.com/pt/ec2/) A [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) se conecta à instância [EC2](https://aws.amazon.com/pt/ec2/) via rede, portanto possui latência.Pode ser conectada e desconectada facilmente como um pendriveSó pode estar conectada a uma AZ.Você paga pelo tamanho ALOCADOvocê pode aumentar o tamanho alocado com o tempo.

Você pode criar uma [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) e deixa-la desalocada de uma instância [EC2](https://aws.amazon.com/pt/ec2/).Se você quiser colocar o conteúdo de um volume [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) de uma AZ para outra, você pode criar uma snapshot dele e copia-la para a outra AZVocê pode marcar um volume [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) para ser excluído quando a instância [EC2](https://aws.amazon.com/pt/ec2/) vinculada a ele for eliminada.

## [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) Snapshots Overview

Snapshots podem ser utilizadas também para copiar volumes [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) para outras Regions

## AMI Overview

**AMI** são imagens customizadas de instâncias [EC2](https://aws.amazon.com/pt/ec2/), estas imagens podem possuis softwares pré configurados.**AMIs** podem ser construidas para regiões específicas e copiadas de uma região para outra.**AMIs** são disponibizadas de 3 formas:

* Públicas gratuitas - disponibilizadas pela AWS e pela comunidade
* Privadas - criadas por usuários e de uso privado
* Comerciais - criadas por pessoas ou corporações e vendidas em marketplaces.

O processo de criar uma **AMI** consiste em:

1. Criar uma instância [EC2](https://aws.amazon.com/pt/ec2/)
2. Customizar a instância
3. Parar a instância
4. Construir a **AMI**, o que também irá criar uma Snapshot do volume [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html)

## EC2 Image Builder Overview

EC2 Image Builder é um processo de criação de instâncias EC2 que cria AMIs de maneira automatizada, com esse processo, você cria instâncias EC2, cria AMI e testa de forma automatizada.

## EC2 Instance Store

Comparando a performance de armazenamento do drive da instância EC2 com o [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html):

* Volumes [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) são drives de rede, por isso são mais lentos.
* Volumes [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) são mais práticos, podem ser montados e desmontados a qualquer momento.
* Drives de instância, por estarem diretamente conectados com a aplicação, têm uma latência bem menor.
* Drives de instância estão presos à execução desta, se a instância falhar, os dados contidos nela são perdidos.
O ideal é usar o drive da instância como buffer/cache e após determinado tempo, passar esta informação para o volume [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) de persistência mais longa.

## EFS Overview

EFS é um tipo de armazenamento de arquivo no qual instâncias diferentes podem acessar o mesmo volume de arquivos, mesmo que estas instâncias estejam em AZs diferentes. Diferente do [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) em que para levar dados de uma AZ para outra, é necessário criar uma snapshot do volume, no EFS, as instâncias de AZs dinstintas acessam os mesmos arquivos.Em termos de custo o EFS é bem mais caro que outras modalidades de armazenamento de arquivo, contudo, neste caso, você paga apenas pela quantidade de dados que usou, não pela que contratou.

EFS-IA(Infrequent Access): se ativado, move arquivos pouco utilizados de um lugar para o outro afim de economizar espaço, isso pode criar uma economia de até 92% se comparado ao EFS padrão.Esse processo é totalmente transparente para as aplicações.

## Shared Responsibility Model for EC2 Storage

Das responsabilidades da AWS:

* Infra
* Replicação de dados de [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) e EFS
* Privacidade física

Das suas responsabilidades:

* Configurar procedimentos de backups e snapshots
* Configurar processos de criptografia
* Todo dado dos drives
* compreender os riscos envolvidos em manter dados em drives de instâncias EC2 que podem ser encerradas.

## Amazon FSx Overview

Amazon FSx para Windows:Uma conexão da AWS com o sistema de arquivos NTFS do Windows, nesta conexão, instâncias EC2 podem acessar arquivos no formato NTFS que podem ser acessados por sistemas OnPremisse.Amazon FSx for Lustre:Um sistema de computação de alta performance para diversos fins, entre eles: Machine Learning, Analytics, Processamento de Video, Modelagem Financeira, entre outras. São sistemas que existem um tráfego de dados altíssimo e uma latência baixíssima.

## High Availability, Scalability, Elasticity

Escalabilidade vertical significa escalar uma aplicação aumentando a capacidade de uma instância(scale up/scale down), ou trocar esta instância por uma instância superior, por exemplo, trocar uma instância t2.micro por uma t2.large, isso aumenta os recursos da máquina como memória, CPU, etc... É recomendado fazer escalabilidade vertical em sistemas não distribuídos, como banco de dados. Escalabilidade vertical está limitada à capacidade do hardware que a AWS oferece, ainda que este limite seja alto.

Escalabilidade horizontal significa escalar uma aplicação aumentando a quantidade de instâncias/sistemas da aplicação(scale out/scale in). Escala horizontal é aplicada em sistemas distribuídos e é mais utilizada em aplicações web e aplicações modernas, é mais fácil de ser operada devido às facilidades que a AWS EC2 oferece para isso uma vez que para escalar uma aplicação horizontalmente basta criar mais instâncias para ela, para desescalar-la, basta eliminar estas instâncias. A escala pode ser automática ou manual. Para que as instâncias funcionem de maneira coordenada é necessário que haja um LoadBalancer que distribua as tarefas entre elas de maneira igualitária.

Alta disponibilidade(High Availability) é a prática de manter uma aplicação disponível em 2 ou mais AZs, de forma que esta aplicação esteja protegida contra desastres ou cortes de comunicação.

Escalabilidade vs Elasticidade vs Agilidade - IMPORTANTE PARA O EXAME

* Escalabilidade: Capacidade de acomodar uma carga maior obtendo um hardware mais robusto(scale up) ou obtendo mais nós(nodes)(scale out).
* Elasticidade: Uma vez que você atingiu o status escalável, a elasticidade é a capacidade de escalar de maneira automatizada com sistemas de auto-scaling, load-balancers inteligentes, etc...
* Agilidade: Agility é um distrator(distractor), não têm nada a ver com o conteúdo do curso, poderá aparecer no exame para confundir, agilidade é a capacidade de obter determinado objeto/recurso no menor tempo possível após a solicitação.

## Elastic Load Balancing (ELB) Overview

Utilidades de um Load Balancer:

* Distribuição de cargas através das instâncias.
* Cobertura das instâncias embaixo de um único nome DNS.
* Capacidade de lidar com instâncias problemáticas.
* Fazer Health Checks nas instâncias.
* Disponibilizar teu website/aplicação sob protocolo HTTPS.
* Alta disponibilidade entre múltiplas AZs.

ELB(Elastic Load Balancer) é um tipo de balanceador de carga gerenciável fornecido pela AWS. Pode ser configurado em alguns passos mas custa mais caro que um balanceador criado por você. Você também pode usar um balanceador personalizado que custa menos mas é mais difícil de configurar.Existem 3 tipos de Load Balancers fornecidos pela AWS:

* Load Balancer de Aplicação - Opera na camada de protocolo de aplicação(7)(HTTP/HTTPS)
* Load Balancer de Transporte/Network - Opera na camada de protocolo de (TCP/UDP) - Sistemas de alta performance.
* Load Balancer clássico - depreciado - trabalha tanto na camada 4(transporte) quanto 7(aplicação) - não vai cair no exame.

## Auto Scaling Groups (ASG) Overview

Auto Scaling Groups(Grupos Auto Escaláveis) são, talvez, o principal produto da computação na nuvem. A ideia é:

* Aumentar a quantidade de instâncias(Scale out) quando a carga de trabalho aumentar.
* Diminuir a quantidade de instâncias(Scale in) quando a carga de trabalho diminuir.
* Certificar que haja uma quantidade mínima e máxima de máquinas trabalhando de acordo com as questões financeiras, contratuais e operacionais pré definidas.
* Registrar novas instâncias no Load Balancer automaticamente.
* Detectar e substituir instâncias defeituosas automaticamente.
Desta forma, o processo de auto scaling é um dos principais recursos na otimização da utilização dos recursos(um dos princípios da nuvem).

## Auto Scaling Groups (ASG) Strategies

Exemplos de estratégias de Escalabilidade:Escalabilidade manual: Alterar o tamanho dos Auto Scaling Groups manualmente.Escalabilidade Dinâmica(Dynamic):Escala Simples:

* Quando o alarme da CloudWatch for disparado por carga alta(ex: CPU > 70%), então add 2 unidades.
* Quando o alarme da CloudWatch for disparado por carga baixa(ex: CPU < 30%), então remove 1 unidade.
Escala por alvo de uso de recurso(Target):
* Manter o uso de CPU de todas as instâncias em 40%, então se CPU > 40%, add instância, se CPU < 40%, remove instância, mantendo uma certa margem de manobra.
Escala agendada(Schedule):
* Sabe-se que o horário de pico de acesso no sistema é das 11:00 às 13:00 e das 17:00 às 19:00, então, nesse horário já se programa para adicionar mais instâncias.

Escalabilidade inteligente:

* Utiliza machine learning para estudar os padrões de volumetria do sistema ao longo das horas, dias e semanas para entender qual é a melhor estratégia de reserva de instâncias e escalabilidade com o ASG(Auto Scaling Group).
Claro que é possível combinar essas estratégias para otimizar recursos.

## ELB & ASG Summary

ASG:

* Implementa elasticidade para a aplicação, trabalha em múltiplas AZs
* Escala instâncias EC2 baseado na demanda, substitui instâncias problemáticas
* integrado com ELB

Resumo ELB e ASG:ELB = Elastic Load BalancingASG = Auto Scaling GroupHigh Availability = Prática de manter uma aplicação disponível em 2 AZs ou mais para que esteja protegida contra desastres e falhas de comunicação.Scalability = Prática de aumentar a capacidade dos recursos de uma aplicação(aumento vertical scale up/down) ou a quantidade destes recursos(aumento horizontal scale out/in)Elasticity = Automatização do processo de Escalabilidade com o uso de ELBs e ASGsAgility = Ganho obtido com a melhoria dos processos utilização da computação na nuvem.ELB:

* Balanceamento entre múltiplas instâncias EC2, pode ser configurado entre múltiplas AZs.
* Oferece suporte para Health Check.
* 4 Tipos: LB de Aplicação(HTTP - Camada 7), LB de transporte(TCP - Camada 4),LB de Gateway(NOVO)(IP - Camada 3), LB clássico (DEPRECIADO - camada 4 e 7).

## [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Overview

S3 é o serviço de armazenamento de objetos da AWS, pode ser usado para várias coisas, dentre elas:

* Backup e armazenamento.
* Recuperação de desastres
* Arquivos mortos
* Armazenamento em modelo de nuvem híbrido
* Hosting de aplicações
* Hosting de arquivos de media
* Repositórios de dados brutos(data lakes) e dados para BigData Analytics
* Entrega de Softwares
* Arquivos estáticos

Os objetos trabalhados no [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) são armazenados em diretórios chamados de buckets, esses buckets são armazenados dentro de uma region, contudo, seu nome é uma chave única global, ou seja, transcende todas as regions **E TODOS OS USUÁRIOS E CLIENTES DA AMAZON**, de forma que um bucket em São Paulo não pode ter o mesmo nome de um bucket em Ohio. Sobre a nomeação dos buckets, estas seguem uma convenção, que é a seguinte:

* Sem letra maiúscula
* Sem Underline
* Tamanho entre 3 e 63 caracteres
* Não ser um IP
* Deve iniciar com letra minúscula ou número

## [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Security: Bucket Policy

Sobre a segurança do [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html):Segurança baseada no IAM:Políticas do IAM podem ser usadas para determinar quais serviços do [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) podem ser acessados por quais usuários.Segurança baseada em recursos:

* Bucket policies - Políticas do bucket controladas pelo console [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html)
* Object Access Control List(ACL) - Ajuste fino de acesso
* Bucket Access Control List(ACL) - Ajuste grosseiro, menos comum
Um usuário IAM consegue acessar o [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) **SE**: ( Uma política IAM autoriza-o **OU** Uma política de recurso autoriza-o) **E** NÃO existe uma recusa explícita

Um exemplo de boa prática para acessos em buckets [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) é, ao invés de dar acessos a usuários, utilizar roles(funções) em instâncias EC2 para que elas possam ter acesso a esses buckets.

## [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Website Hands On

S3 pode ser bem útil para fazer websites.

## [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Versioning Overview

Versionamento de arquivos no [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) é possível e muito recomendado. Isso é feito a nível de objeto, criando um hash para cada versão do objeto.É recomendado versionar os buckets pois desta forma você protege o conteúdo já existe de exclusões desnecessárias. Isso também torna mais fácil um eventual roll back.Caso um arquivo não esteja versionado, ele ficará sob a versão ull\. Dar rollback ou suspender uma versão não apaga ela, uma vez que uma versão é criada, ela ficará lá para sempre.

## [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Server Access Logging

Todos os acessos feitos no [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) são salvos em logs, nesses logs constam solicitações feitas por quaisquer contas, autorizadas ou não, esses dados podem ser analisados por ferramentas de analytics. Esse tipo de informação é útil para auditoria e para achar a causa raiz de algum problema, encontrar padrões suspeitos, etc..

## [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Replication Overview

S3 Replication é o ato de Replicar um bucket [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), seguem algumas características:

* O bucket deve estar versionado, na origem e no destino.
* Cross Region Replication (CRR) replica entre 2 regions diferentes
* Same Region Replication (SRR) replica entre 2 AZs na mesma region
* Os buckets podem estar em contas roots diferentes
* A cópia é assíncrona
* Devem ser dadas as permissões IAM devidas para o [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html)
Casos de uso para CRR: Compliance, redução da latência de acesso, replicação entre contas root.Casos de uso para SRR: Agregação de log, Replicação entre ambiente de produção e testes.

## [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Replication Hands On

Sobre a replicação do [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Objetos criados antes da réplica **NÃO SÃO REPLICADOS**

## [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Storage Classes Overview

Classes de armazenamento [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html):

* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Standard - Uso geral(o que vimos até aqui)
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Infrequent Access(IA) - para arquivos pouco utilizados
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) One Zone Infrequent Access - para arquivos pouco utilizados que podem ser recriados ou que não são críticos, pois existe risco de perda.
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Intelligent Tiering - Sistema inteligente que determina para qual tipo de classe seus buckets devem ir.
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Glacier - Para armazenamento de arquivos mortos e backups.
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Glacier Deep Archive - Para armazenamento de arquivos mortos e backups que você entende que ficarão muito tempo sem serem lidos(estilo aqueles que acumularão poeira e teia de aranha no porão).
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Reduced Redudancy Storage(RRS) - **Depreciado** - Sistema legado que não será solicitado no exame.

Conceitos e Garantias da AWS:

* Durabilidade:
* A AWS garante que o [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) manterá 99,999999999% (11 9s) dos objetosentreas AZs. Isso significa que em média existe o risco de você perder um objetoacada 10000 anos. Esta regra é válida para todas as classes.
* Disponibilidade
* A medida de o quão disponível o [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) é.
* A AWS garante que o [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) estará disponível em 99,99% do tempo, o quesignifica que ela assume uma indisponibilidade de até 53 minutos por ano.Essagarantia varia de acordo com a classe [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html).

Para [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Standard:

* Disponibilidade de 99,99%
* Usado para dados acessados frequentemente.
* Baixa latência e alta taxa de transferência.
* Suporta falha de até 2 instalações(facilities) simultaneamente.

Usado para: Big Data Analytics, mobile, gaming, distribuição de conteúdos, etc...

S3 Standard - Infrequent Access (IA)

* Para arquivos pouco acessados mas que precisam de uma latência rápida, quando acessados.
* Disponibilidade de 99,9%
* Custo menor, se comparado com [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Standard, porém, há um custo maior por acesso.
* Suporta falha de até 2 instalações(facilities) simultaneamente.
Usado para: Data store para recuperação de desastres, backups, etc...

S3 Intelligent-Tiering

* Disponibilidade de 99,9%
* Mesma baixa latência e alta performance de taxa de transferência do [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) standard.
* Otimizado para custar menos pois automaticamente move objetos entre as outras 2 classes [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html)(acesso frequênte/infrequênte) baseado em padrões de acesso.

Usado para: Resiliência de eventos que impactem diretamente a AZ. Sistemas que exijam comprovantes, como compras que são muito acessados nas primeiras semanas após serem gerados e cada vez menos ao longo do tempo.

S3 One Zone - Infrequent Access (IA)

* Igual ao IA, contudo, desta vez, armazenado em uma única AZ.
* 99,5% de disponibilidade.
* Baixa latência e alta performance de taxa de transferência.
* Baixo custo se comparado com [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html)-IA (cerca de 20%)
Usado para: Armazenamento de backups secundários de dados on-premisse, dados que podem ser recriados, thumbs, etc...

S3 Glacier e Glacier Deep Archive

* Armazenamento de backups para períodos longos.
* Custo alto para obter esses dados, uma vez armazenados.
* Custo baixo para armazenar os dados.
* Amazon Glacier - barato:
* Consulta expedited - 1 a 5 minutos
* Consulta standard - 3 a 5 horas
* Consulta Bulk - 5 a 12 horas
* Amazon Glacier Deep Archive - O mais barato:
* Consulta Standard - 12 horas
* Consulta Bulk - 48 horas

## [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Glacier Vault Lock & [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Object Lock

S3 Object Lock

* Adota modelo WORM (Write Once Read Many)
* Bloqueia um objeto de ser alterado ou excluido. Uma vez criado, ficará com o mesmo conteúdo para sempre.

S3 Glacier Vault Lock

* Adota o modelo WORM (Write Once Read Many)
* Bloqueia a política para futuras edições, uma vez definido, não pode ser alterado.
* Ideal para Compliance, auditoria e garantia de Integridade de dados.

## Shared Responsibility Model for [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html)

Responsabilidade compartilhada do [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html):

AWS:

* Infra (os dados se manterão em pelo menos uma AZ)
* configuração e análise de vulnerabilidade
* validação de compliance

Você:

* Versionamento do [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html)
* Setup das políticas dos buckets
* Setup das replicações dos buckets
* Logging e monitoramento
* Escolha das classes de [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html)
* Criptografia de dados armazenados e em tráfego.

## AWS Snow Family Overview

AWS **Snow Family** é um serviço offline fornecido pela AWS em que você envia os dados da sua empresa para eles através de drives físicos, é indicado quando a quantidade de dados que você precisa enviar é muito alta e isso torna inviável utilizar a banda de internet. Ao contratar o serviço, a AWS enviará para você um drive no qual você passará os dados a serem transferidos para esses dispositivos, você então envia esses drives de volta para a AWS que passa esses dados para os servidores das AZs.

O primeiro tipo de serviço **Snow Family** é o **Snowball Edge**. Neste caso a AWS envia um drive de alguns kgs com alguns TBs ou PBs de capacidade no qual você passa os dados do teu servidor.Existem 2 sabores de **Snowball Edge** disponíveis

* **Snowball Edge** Storage Optimized
* 80TB de capacidade de HDD por bloco
* **Snowball Edge** Compute Optimized
* 42TB de capacidade de HDD por bloco

Caso de uso: Migração de dados para a nuvem, descomissionamento de Datacenter, recuperação de desastre.

**AWS Snowcone** é um dispositivo portátil de 2,1kg(4,5 libras), resistente, pode ser levado para qualquer lugar, útil para ser levado a lugares remotos e de condições extremas e sem acesso a internet.Possui capacidade de 8TB, não vêm com bateria ou cabos.Possui 2 interfaces de rede que podem ser conectadas na internet de qualquer terminal para que os dados sejam enviados diretamente para a AWS via **AWS DataSync**, ou os dados podem ser enviados via delivery, como os outros serviços da **Snow Family**.

AWS **Snowmobile** é um serviço da **Snow Family** no qual a AWS envia um caminhão para a empresa, neste caminhão são armazenados os HDDs que são levados de volta para a AWS para serem armazenados.Cada caminhão tem a capacidade de armazenar 100PB(1PB = 1000TB).Possui controle de temperatura, GPS, câmera de segurança 24/7Melhor que **SnowBall** se você for transferir mais de 10PB

**Edge Computing** é um conceito no qual o AWS **Snow Family** se faz útil no qual, quando você envia um dado para um dos dispositivos da AWS, quando o dado entra no dispositivo, a AWS já começa a pré processar esse dado baseada em alguma programação já feita. Este processamento pode ser algo relacionado a transformação de dado, machine learning, etc...

Sobre as características de cada dispositivo:**Snowcone**:

* 2 CPUs, 4GB RAM, conexão com/sem fio, acesso via USB-C
**Snowball Edge** - Compute Optimized
* 52 vCPUs, 208 GiB RAM, GPU opcional para processamento de vídeo ou machine learning, 42 TB de armazenamento
**Snowball Edge** - Storage Optimized
* 40 vCPUs, 80 GiB RAM, Clusterização de objeto disponível.
Todos podem rodar instâncias [EC2](https://aws.amazon.com/pt/ec2/) ou Funções **AWS Lambda**s (Usando **AWS IoT Greenglass**)Opção de deploy a longo prazo: desconto para aluguel a longo prazo de 1 OU 3 anos.

**AWS OpsHub** é um software que você pode baixar e que funciona de forma offline em que você conecta nos dispositivos da **Snow Family**. Com este software você pode transferir arquivos, criar e eliminar instâncias EC2 nos devices, monitorar os devices e sincronizar os devices com a cloud.

## Storage Gateway Overview

Na AWS, pelo que foi estudado até aqui, vimos 3 responsáveis agindo de 3 formas para armazenar dados.

* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) - Volumes
* [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) - Arquivos
* **Glacier** - Fitas
Se você não sabe onde armazenar cada dado, o **AWS Storage Gateway** consegue trabalhar como um mediador entre servidores on-premisse e esses 3 produtos, desta forma, o **Storage Gateway** é útil para trabalhar com recuperação de desastre, backup e restauração e armazenamento em camadas.

## [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Summary

Resumo [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html):

* Buckets vs Objetos: Buckets possuem um nome único para todos os usuários mas são anexados em uma única region.
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Security: O acesso a um bucket pode ser controlado via IAM ou via políticas do bucket(para acessos externos).
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) websites: Os buckets podem ser usados para hospedar websites estáticos.
* Versionamento [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html): É possível habilitar um versionamento de arquivo no [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) no qual é possível fazer rollback, inclusive, de exclusões.
* Logs de acesso [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html): É possível fazer um bucket [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) escrever logs de acesso em outro bucket para você saber quantas vezes cada arquivo do bucket foi acessado.
* Replicação [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html): É possível replicar um bucket para a mesma region ou para outra, mas apenas alteração após a criação da replicação serão copiadas, deve habilitar versionamento.
* Classes [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html): Standard, Standard IA, Standard IA-OZ, Intelligent, Glacier, Glacier Deep Archive.
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Lifecycle: regras para evoluir um arquivo de uma classe [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) para outra automaticamente após um tempo.

* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) glacier Vault Lock / [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Object Lock: Utilizam WORM(Write Once Read Many) sistema de backup \somente leitura\.
* Snow family: Serviço de devices físicos que podem ser utilizados para transferir e armazenar grandes quantidades de dados da empresa para a AWS de maneira offline, também permitem fazer edge computing.
* OpsHub: Aplicação Desktop utilizada para gerenciar os dispositivos Snow Family.
* Storage Gateway: Solução Híbrida que permite criar uma conexão entre armazenamento on-premisse com armazenamento na AWS(especialmente [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html), [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) e Glacier).

## Databases Introduction

AWS oferece suporte para base de dados relacionais e não-relacionais, nas quais você pode definir estruturas, índices e relacionamentos.

Base de dados NoSQL podem oferecer uma performance melhor na AWS pelos seguintes motivos:

* Flexibilidade: São fáceis de se desenvolver a partir de um modelo de dados.
* Escalabilidade: São desenhados para escalar horizontalmente(scale-out) com facilidade usando clusters distribuidos.
* Alta performance: otimizado para um modelo de dados específico.
* Altamento funcional: tipagem otimizada para o modelo de dados.
Exemplo: Key-value, documentos, gráficos, in-memory, search databases.

A AWS oferece gerenciadores para vários tipos de bancos de dados, os benefícios de se utilizar esses gerenciadores incluem:

* Provisionamento rápido, Alta disponibilidade, escalabilidade vertical e horizontal.
* Backups/Restaurações automatizados, operações, upgrades.
* Patches para os SOs gerenciados pela AWS.
* Monitoramento e alertas.
Contudo, várias tecnologias de bases de dados podem ser rodadas em instâncias [EC2](https://aws.amazon.com/pt/ec2/). Se por motivos estratégicos/financeiros você decidir adotar essas instâncias para lidar com suas bases de dados, entenda que todo processo de resiliência, backup, patching, alta disponibilidade, tolerância a falha e escalabilidade estarão sob sua responsabilidade.

## RDS & Aurora Overview

**RDS**, ou **Relational Database Service** é o serviço de banco de dados relacional da AWS, utiliza SQL como linguagem de query, pode ser usado como plataforma para os seguintes SGBD:

* Postgree
* MySQL
* MariaDB
* Oracle
* Microsoft SQL Server
* **Aurora** (SGBD da AWS)

**RDS** oferece os seguintes serviços:

* SO com patching automatizado.
* Backup e restauração para um ponto de restauração específico(um ponto na linha do tempo).
* Dashboards de monitoramento.
* Replicas de leitura para melhorar a performance de leitura.
* Alta disponibilidade utilizando mais de uma AZ.
* janelas de manutenção para upgrades.
* Capacidade de escalabilidade(horizontal e vertical).
* Armazenamento feito por volumes [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) (GP2 ou IO I)
Não é possível acessar as instâncias via SSH.

Amazon Aurora:

* Aurora é uma tecnologia proprietária da AWS (não é opensource)
* Dá suporte para PostgreSQL e MySQL.
* É otimizada para Cloud oferecendo um aumento de performance de 5x em cima do MySQL no RDS e de 3x em cima do PostGres.
* Aurora automaticamente incrementa seu tamanho de 10GB para até 64TB.
* Aurora custa mais que RDS(20%), mas é mais eficiente).
* Não possui versão disponível para free tier(gratuidade).

## RDS Deployments Options

Read Replicas:

* Bases de dados de somente leitura que são espelhos da base de dados **RDS** principal.
* Utilizadas para diminuir a carga de trabalho da base de dados principal.
* Os dados são escritos apenas na base de dados principal.
* Cada base de dados **RDS** pode ter até 5 réplicas
Multi-AZ FailOver:
* Bases de dados espelhos da base **RDS** instalada em outra AZ usada quando a AZ da base principal cai.
* Fica em stand-by enquanto o sistema opera normalmente.
* Cada base **RDS** pode ter 1 base FailOver em outra AZ.

**RDS** Deployment Multi-Region:Implementa o conceito de Réplica com base de dados **RDS** em regions diferentes. Desta forma você tem uma unidade **RDS** em uma region usada para escrita e leitura e outras réplicas em outras regions usadas apenas para leitura, os pontos a observar são:

* Isso pode ser usado para recuperação de desastre, uma vez que cada réplica é um backup.
* Melhora de performance com uma redução significativa da latência.
* A replicação entre distâncias grandes gera um custo.

## ElastiCache Overview

AWS **ElastiCache** é um sistema base de dados relacional in-memory, é utilizado para trabalhar em uma faixa de latência menor que o **RDS**, desta forma, melhorando a performance do sistema e reduzindo a carga de trabalho do **RDS**, especialmente para a leitura. Tal como no RDS, no **ElastiCache**, a AWS cuida da manutenção do SO, patching, otimização, setup, configuração, monitoramento, recuperação de falhas e backups.

## DynamoDB Overview

**DynamoDB** é um banco de dados NoSQL para AWS, seguem os conceitos:

* Totalmente gerenciável com alta disponibilidade replicável entre 3 AZs.
* Escala para atender a carga de trabalho alta com conceito de base de dados \serverless\ distribuida.
* Milhões de requisições por segundo, trilhões de linhas, centenas de TBs de espaço de armazenamento.
* Alta performance e consistência.
* Latência < 10ms.
* Integrado com [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) para autorização e administração.
* Baixo custo e capacidade para auto escalabilidade.

**DynamoDB Accelerator - DAX** é um banco de dados in-memory para o **DynamoDB**. Provê um aumento de performance de 10x, reduz o tempo de latência para alguns microssegundos. É seguro, altamente escalável e com alta disponibilidade. Difere do **ElastiCache** no sentido que o **DAX** é usado para o **DynamoDB** enquanto que o **ElastiCache** é usado para outros BDs

## Redshift Overview

**Redshift** é um banco de dados NoSQL baseado no PostGreSQL usado para OLAP(Online Analytical Processing), seguem as informações:

* Carrega os dados a cada hora, não a cada segundo.
* Performance 10x melhor que em outras warehouse, escala para até PBs de dados.
* Dados armazenados no formato de colunas e não no formato de linhas.
* Massively Parallel Query Execution(MPP) com alta disponibilidade.
* Instâncias no formato Pay as you go.
* Possui uma interface SQL para realizar as queries.
* Integrável com ferramentas BI como **AWS Quicksight** ou **Tableau**.

## EMR Overview

**Amazon EMR(Elastic MapReduce)** é uma ferramenta que auxilia na criação de clusters Hadoop (Big Data) para analisar e processar uma quantidade grande de dados, seguem as características:

* Os clusters são feitos de centenas de instâncias [EC2](https://aws.amazon.com/pt/ec2/).
* Também dá suporte para Apache Spark, HBase, Presto, Flink, etc...
* **EMR** cuida de todo provisionamento e configuração.
* Auto-scaling e integração com instâncias Spot.

Casos de uso: Data Processing, Machine Learning, web indexing, big data, etc...

## Athena Overview

**Amazon Athena** é um Banco de dados Serverless usado apenas para fazer consultas nos buckets [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), é usado para consultar dados armazenados no [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) e fazer análises de logs, seguem as informações:

* Você não paga pelo banco de dados, mas sim por cada consulta que faz.
* Output vem do [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html).
* Segurança através do [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html).

Caso de uso: Queries feitas no [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html).

## QuickSight Overview

**Amazon QuickSight** é um serviço de machine learning serverless para inteligência de negócio com objetivo de criar dashboards interativos. É rápido, automaticamente escalável, embedável e pago por sessão. É totalmente integrável com **RDS**, **Aurora**, **Athena**, **Redshift**, [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), etc...Caso de uso: Business Analytics, Visualização de construções, análises ad-hoc, fazer insights de negócios usando dados.

## DocumentDB Overview

**DocumentDB** é um banco de dados NoSQL baseado em documento no estilo do MongoDB. Totalmente gerenciável e disponível, replicável por 3 AZs.Pode incrementar seu tamanho de 10GB para até 64TB, automaticamente escala de acordo com a carga de trabalho com milhões de requisições por segundo.

## Neptune Overview

**Amazon Neptune** é um banco de dados gráfico.Adota Alta disponibilidade através de 3 AZs com até 15 réplicas de leituras, contrúa e rode aplicações funcionando e altamente conectadas, otimizadas para rodar queries complexas.basicamente, no exame, sempre que pensar em um banco de dados que lidam com os dados de forma gráfica, como os verbetes da Wikipedia, ou a relação de perfis de uma rede social, pense no **Amazon Neptune**.

## QLDB Overview

**Amazon QLDB(Quantum Ledger Database)** é um banco de dados especializado em registros de transações financeiras. Seguem as informações:

* Imutável, todos os dados registrados não podem ser editados ou removidos, apenas adicionados.
* os dados são criptografados e têm um hash gerado que pode ser usado para validar a criptografia.
* Tende a ser 2-3x mais rápido que frameworks para ledgers-blockchains
* Pode ser manipulado usando SQL.
A diferença principal entre o **QLDB** e o Blockchain está na distribuição, o blockchain trabalha com o conceito de dados descentralizados, no **QLDB** esses dados ficam registrados em um local apenas, isso pode ser útil por questões de regulação.

## Managed Blockchain Overview

**Amazon Blockchain** permite um armazenamento de dados descentralizado. Permite que você conecte em redes de blockchain públicas ou crie sua rede privada. É compatível com Hyperledger Fabric e Ethereum.

## DMS Overview

**DMS(Database Migration Service)** É o serviço que faz a migração de banco de dados, seguem as informações:

* Pode migrar bancos de dados do mesmo tipo(ex: De Oracle para Oracle), ou de tipos diferentes(ex: de Oracle para **Aurora**).
* O banco de dados de origem fica disponível durante toda a migração.

## Glue Overview

**AWS Glue** é um serviço de extração, transformação e carregamento de dados(ELT).Pode ser usado para, por exemplo, extrair dados de uma base de dados **RDS** ou [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), transforma-la e carrega-la em um sistema **Redshift**.O **Glue Data Catalog** é um serviço que fornece um catálogo de datasets que descobre a melhor forma de organizar as colunas para enviar para o **Redshift**.

## Databases & Analytics Summary

Resumo:

* Banco de dados relacionais - OLTP: **RDS** e **Aurora**.
* Read Replica: Réplicas de leitura que ficam em outras AZs.
* Multi-regions: Réplicas de leituras que ficam em outras regions para cache.
* In-memory Database: **ElastiCache**
* Key/Value Database: **DynamoDB**(Serverless) e **DAX**(Versão in-memory para **DynamoDB**)
* Warehouse - OLAP: **Redshift**(SQL)
* Clusters Hadoop: **EMR**
* Athena: Queries para Amazon [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html)(Servers e SQL)
* QuickSight: Dashboards dos dados(serverless).
* DocumentDB: \Aurora para MongoDB\ Banco de dados NOSQL.
* Amazon QLDB: Banco de dados Imutável Ledger da Amazon.
* Amazon Managed Blockchain: Gerenciamento de Hyperledger Fabri e Ethereum blockchain.
* Glue: ELT(Extract Transform Load) e serviço de catálogo de dados.
* DMS: Serviço de migração de BD
* Neptune: Banco de dados gráfico

## ECS, Fargate & ECR Overview

**ECS (Elastic Container Service)** é o serviço de containers da AWS, roda containers do Docker dentro de instâncias [EC2](https://aws.amazon.com/pt/ec2/), a AWS inicia e para os containers, possui integração com o **Application Load Balancer(ELB)**.

**Fargate** é outro serviço de gerenciamento de containers Docker dentro da AWS, diferente do **ECS**, o **Fargate** não exige qualquer tipo de infraestrutura(sem instâncias [EC2](https://aws.amazon.com/pt/ec2/)), ou seja, é um serviço serverless. A AWS apenas rodará os containers baseada na CPU e memória RAM que você precisa.

**ECR(Elastic Container Registry)** é um serviço que armazena imagens de containers para serem utilizados pelo **ECS** ou pelo **Fargate**.

## Serverless Introduction

O conceito de Serverless dentro da AWS é um serviço em que para ser executado, não há necessidade de prover/gerenciar instâncias ou servidores, ou seja, isso é feito de forma automática pela AWS.Alguns exemplos de Serviços Serverless da AWS são:

* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html)
* **DynamoDB**
* **Fargate**
* [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
* etc...

## Lambda Overview

[Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) é um serviço voltado para execuções simples, nele você executa funções/rotinas simples em que não há necessidade de criar qualquer tipo de instâncias. Funções [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) são limitadas por tempo de execução e funcionam de forma on-demand. A escalabilidade é automatizada(elástica).

Benefícios da utilização da [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html):

* Precificação fácil: Você paga por requisição E por tempo de computação.
* O modo Free Tier permite 1 milhão de requisições E 400 mil GBs detempode computação.
* Integração com todos os serviços da AWS.
* Event-Driven, ou seja, é reativa, as funções são executadas apenas caso chamadas por algum evento.
* Integrada com várias linguagens de programação.
* Podem ser facilmente monitoradas com AWS **CloudWatch**.
* Fácil de se obter mais recursos por função (até 10GB de RAM).
* Aumentar a memória RAM também aumenta a CPU e banda de conexão.
* O tempo de execução de uma função [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) é de 15 minutos.

Preço da AWS [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html):Pagando por chamada:

* Primeiro milhão de requisições são gratuitos.
* $0,20 dólares por milhão de requisições após. ($0,0000002 por requisição)
Pagando por duração: (in incremento de 1ms)
* SE RAM = 1GB então primeiros 400 mil segundos gratuitos.
* SE RAM = 128MB então primeiros 3,2 milhões segundos gratuitos.
* Após isso: $1,00 para cada 600000 GB-segundos
Devido ao preço baixo, é bem comum se utilizar bastante AWS [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html).

## API Gateway Overview

**AWS API Gateway** é o serviço que permite mediar e encapsular a comunicação entre APIs cadastradas na AWS(seja em **Lambdas** ou em instâncias [EC2](https://aws.amazon.com/pt/ec2/)) e o cliente. Seguem as informações:

* Os API Gateways permitem facilmente criar, publicar, gerenciar, monitorar e assegurar APIs.
* O serviço é totalmente Serverless.
* Da suporte para APIs RESTful e APIs com WebSocket
* Da suporte para serviços de autenticação, API Throttling, API key, monitoring, etc...

## Batch Overview

**AWS Batch** é um serviço que executa batches programados por você.

* Todos os processos de batch são totalmente gerenciáveis e escaláveis.
* Você pode rodar tranquilamente centenas de milhares de jobs na AWS.
* A ideia do batch é ter um início e fim pré determinados.
* O batch irá de forma dinâmica criar instâncias [EC2](https://aws.amazon.com/pt/ec2/) ou Instâncias **Spot**.
* **AWS Batch** irá prover a quantidade correta de CPU e memória.
* você envia e agenda o job e a **AWS Batch** faz o restante.
* Os jobs são definidos como Imagens Docker e rodam dentro do **ECS**.
* Útil para otimização de custo e redução do foco na infraestrutura.

**Batch** vs [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
[Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html):

* Tempo limitado a 15 minutos.
* Limitação de runtimes.
* Limitação de espaço de disco.
* Serverless.
**Batch**:
* Sem tempo limite.
* Sem limite de execução uma vez que é empacotado em uma imagem docker.
* É montado em um volume [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html).
* É executado em uma instância [EC2](https://aws.amazon.com/pt/ec2/).

## Lightsail Overview

**Amazon Lightsail** é uma alternativa da AWS para quem não tem experiência com cloud computing e provê:

* Servidores virtuais, armazenamento, banco de dados e rede.
* É mais barato.
* Uma alternativa mais simples do que usar [EC2](https://aws.amazon.com/pt/ec2/), **RDS**, **ELB**, [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html), **Route 53**, etc...
* Melhor para pessoas sem experiência com Cloud.
* Você pode configurar notificações e monitorar seus recursos do **Lightsail**.
* Alta disponibilidade mas sem auto-escalabilidade, possui certa limitação com a AWS.
Caso de uso: Aplicações web simples(alguns templates para LAMP, Nginx, MEAN, Node.js), Websites (WordPress, Magento, Plesk, Joomla), Ambiente de Dev/Teste.

## Other Compute - Summary

Resumo Other Compute Parte 1:

* **Docker**: Tenologia para rodar aplicações em containers.
* **ECS**: Serviço para rodar containers Docker em instâncias [EC2](https://aws.amazon.com/pt/ec2/).
* **Fargate**: Roda containers Docker de forma serverless, sem usar instâncias [EC2](https://aws.amazon.com/pt/ec2/).
* **ECR**: Repositório privado de imagens Docker.
* **Batch**: Roda jobs batch na AWS através de instâncias [EC2](https://aws.amazon.com/pt/ec2/).
* **Lightsail**: Serviço simples para rodar aplicações de baixo custo na AWS.

Resumo Other Compute Parte 2:

* [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html): Serviço Serverless no formato FaaS(Function as a Service), escalável e reativo que executa funções programáveis.
* Preço do [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html): Pode ser cobrado por tempo de execução x memória RAM OU pela quantidade de invocações.
* Linguagens de programação e [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html): Lambda da suporte para várias linguagens, porém, não permite criação de imagens Docker.
* Limite de tempo de execução de funções [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html): 15 minutos.
* Casos de Uso para [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html): Alterações Simples em objetos [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), rodar rotinas simples no formato cron job.
* **API Gateway**: Serviço usado para encapsular APIs, pode ser usado para encapsular funções lambda expostas via HTTP também.

## CloudFormation Overview

**AWS CloudFormation** é uma forma de criar templates para toda a estrutura de recursos a serem utilizados na AWS. Você cria um script que será responsável por criar recursos como: Buckets [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), Security Group, Instâncias [EC2](https://aws.amazon.com/pt/ec2/), etc... Você define a ordem em que serão criados e quais as definições de cada um.

Benefícios de usar AWS **CloudFormation** como Infrastructure as code em relação ao custo:

* Cada recurso vem taggeado com um identificador que permite que você veja quanto que ele está custando para você.
* Você consegue estimar os custos dos recursos usando os templates do **CloudFormation**.
* Você pode criar estratégias de economia, ex: criar um ambiente em um momento do dia e apagar este ambiente em outro.

Benefícios de usar AWS **CloudFormation** como Infrastructure as code em relação à produtividade:

* Você pode criar e destruir recursos automaticamente na nuvem sem necessidade de parar o ambiente para manutenção.
* Você pode criar diagramas automatizados para seus templates.
* Programação declarativa, sem necessidade de descobrir a ordem e orquestração.
Existem vários templates na web que podem ser usados com CloudFormation e ele pode ser utilizado com quase todos os recursos da AWS.

## CDK Overview

AWS **CDK**(**Cloud Development Kit**) é uma forma de substituir a linguagem padrão do **CloudFormation**(JSON/YAML) por alguma linguagem de sua preferência, ex: Javascript, Typescript, Python, Java ou .NET.Além disso, você pode deployar infra e aplicações ao mesmo tempo, o que é útil para funções [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)ou containers Docker no **ECS**/**EKS**

## Beanstalk Overview

**BeanStalk** É uma forma simples de deployar código usando uma arquitetura conhecida até o estado produtivo, exemplo de arquitetura conhecida: **ASG**+ **ELB**+ [EC2](https://aws.amazon.com/pt/ec2/).**Beanstalk** é considerado um PaaS(Platform as a Service).O serviço do **BeanStalk** é gratuito mas você paga pelos componentes que o **Beanstalk** está visualizando.

Serviços gerenciados pelo **Beanstalk**:

* Instâncias [EC2](https://aws.amazon.com/pt/ec2/), incluindo SO.
* Estratégia de deploy é configurável, mas é executava pelo Elastic **Beanstalk**.
* Provicionamento de capacity.
* Load Balancing e auto-scaling.
* monitoramento da aplicação.
Você ficaria responsável apenas pelo código da aplicação.

Existem 3 modelos de arquitetura para **Beanstalk**:

* Single Instance deployment: uma instância apenas, bom para desenvolvimento.
* Load Balancing + **ASG**: bom para produção ou pré-produção em aplicações web.
* **ASG** apenas: bom para aplicações indoor em produção

## CodeDeploy Overview

AWS **CodeDeploy** é um serviço que permite que você faça deploys de forma automatizada na AWS, ele permite que as instâncias [EC2](https://aws.amazon.com/pt/ec2/) sofram upgrades.Também funciona em servidores on-premisse ou em serviços híbridos através de um agente integrado.

## CodeCommit Overview

AWS **CodeCommit** é o serviço de versionamento de código fonte Git da AWS.Escalável e com alta disponibilidade.Permite espelhamento de algum outro repositório externo.

## CodeBuild Overview

AWS **CodeBuild** é o serviço de build da AWS.Compila, testa, empacota e constrói o componente.A estrutura é **CodeCommit** => **CodeBuild** => Deployar.Vantagens:Totalmente gerenciável.

* Serverless.
* Escalável.
* Alta disponibilidade.
* Seguro.
* Sistema de Pay-as-you-go, você paga pelo tempo de build.

## CodePipeline Overview

AWS **CodePipeline** é o serviço de esteira que orquestra de forma visual e totalmente gerenciável o **CodeCommit**, **CodeBuild**, **CodeDeploy** e **Elastic Beanstalk**.Permite criar um sistema de Continuous Delivery completo e de fácil visualização.

## CodeArtifact Overview

AWS **CodeArtifact** é o serviço de repositório de artefatos da AWS.Seguro, escalável e serverless.Suporte para integração com Maven, Gradle, npm, yarn, twine, pip e NuGet.Integração completa com **CodeBuild**.

## CodeStar Overview

AWS **CodeStar** permite que você gerencie todo processo de DevOps de forma simples e intuitiva, vendo os códigos, builds e aplicações.Totalmente integrável com **CodePipeline**, **CodeBuild**, **CodeDeploy**, **Elastic Beanstalk**, [EC2](https://aws.amazon.com/pt/ec2/), etc...

## Cloud9 Overview

AWS **Cloud9** é uma IDE online da AWS que permite edição de código online com debug e Pair Programming dinâmico em tempo real.

## Systems Manager (SSM) Overview

AWS **SSM** (**System Manager**) é um serviço que permite gerenciar instâncias [EC2](https://aws.amazon.com/pt/ec2/) e servidores on-premisse de maneira mais avançada. Consiste em um serviço para soluções híbridas que permite que você crie insights da sua infra com mais facilidade.O **SSM** vem com mais de 10 produtos, dentre eles:

* Um sistema de automação de patching para compliance.
* Um sistema de execução de comandos em múltiplos servidores.
* Um sistema de gerenciamento de parametrização.
Funciona tanto com Windows quanto com Linux.

O **SSM** se assemelha ao Puppet.Você cria uma instância que roda o **SSM** como master e em cada instância [EC2](https://aws.amazon.com/pt/ec2/) e nas máquinas on-premisse, você roda um agent que está conectado com este master, então os agents se reportam para o master de acordo com a necessidade e executam os comandos que o master ordena.

## OpsWorks Overview

Tal como o **SSM** e como sua alternativa, o AWS **OpsWorks** se assemelha ao Puppet e ao Chef, executando comandos nas instâncias [EC2](https://aws.amazon.com/pt/ec2/) e em VMs on-premisse.

## Deployment Summary

Resumo Deployment:

* **CloudFormation**(AWS apenas): Serviço de Infra as Code que permite executar código para a criação de recursos na AWS, funciona com quase todos os recursos da AWS e se repete através de regions e contas.
* **Beanstalk**(AWS apenas): Serviço PaaS limitado a certas linguagens ou Docker que permite deployar código em arquiteturas conhecidas, ex: **ELB**+[EC2](https://aws.amazon.com/pt/ec2/)+**RDS**.
* **CodeDeploy**(híbrido): sistema de deploy e upgrade de aplicações em servidores.
* **System Manager**(híbrido): Sistema de patch, configuração e execução de comando dentro das instâncias e servidores.
* **OpsWorks** (híbrido): Chef e Puppet gerenciado na AWS.

Resumo Serviços desenvolvedor:

* **CodeCommit**: Repositório Código Fonte Git da AWS.
* **CodeBuild**: Sistema de built e teste da AWS.
* **CodeDeploy**: Sistema de Deploy da AWS.
* **CodePipeline**: Sistema de orquestração e esteira da AWS.
* **CodeArtifact**: Sistema de repositório de artefatos da AWS.
* **CodeStar**: Visão unificada de todo processo de codificação e CI/CD da AWS.
* **Cloud9**: IDE online da AWS que permite collab.
* AWS **CDK**: Unifica **CloudFormation** com linguagem de programação e permite que você automatize a criação de uma infra enquanto já programa as aplicações.

## Why Global Applications?

Dizer que uma aplicação está disponível globalmente é dizer que ela está alocada em mais de uma region. Dentre as vantagens de se disponibilizar uma aplicação globalmente, podemos citar:

* Diminuição da latência: Permitir que clientes do mundo todo possam acessar a aplicação com uma baixa latência.
* Recuperação de desastre: Uma proteção maior a desastre, uma vez que os dados estarão disponíveis em mais de uma region,
* Proteção contra ataques: A infraestrutura estará distribuída globalmente, dificultando ataques.

Serviços que auxiliam no processo de globalização de aplicações:

* **Route 53**: Sistema DNS que direciona o cliente para o servidor AWS mais próximo para reduzir ao máximo a latência.
* **CloudFront**: Serviço CDN da AWS que replica parte da aplicação para as Edge locations da AWS diminuindo a latência e trabalha com caches de estáticos.
* **S3 Transfer Acceleration**: Acelera uploads e downloads globais na Amazon [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html).
* AWS **Global Accelerator**: Melhora a disponibilidade e performance usando a rede da AWS.

## Route 53 Overview

Amazon **Route 53** é o serviço de DNS gerenciável da AWS.Nele você consegue fazer registros de:

* Domínio para IPv4: www.google.com => 12.34.56.78
* Domínio para IPv6: www.google.com => 2001:4860:4860::8888
* Domínio para domínio: search.google.com => google.com
* Domínio para recurso AWS: example.com => Alias(ex: **ELB**, **CloudFront**, [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), **RDS**, etc...)

A sequência de funcionamento do **Route 53** é:

1. Cliente chama **Route 53** enviando domínio.
2. **Route 53** devolve IP correspondente ao domínio.
3. Cliente chama IP.

Existem 4 tipos de roteamento no **Route 53** para se entender:

### 1. Simple Routing Policy

1. Cliente Chama **Route 53** pedindo IP de um domínio
2. **Route 53** devolve IP
3. Cliente chama IP

Não possui Health Check

#### 2. Weighted Routing Policy

O **Route 53** faz uma espécie de Load Balancing por DNS em que distribui em certos IPs, ex: 50% no IP X, 50% no IP Y.Possui Health Check.

#### 3. Latency Routing Policy

O **Route 53** obtém a localização do cliente e direciona ele para a instância mais próxima para que tenha a menor latência possível.Possui Health Check.

#### 4. Failover Routing Policy

O **Route 53** o health check em uma instância determinada como primária e caso o healthcheck falhe, automaticamente passa a direcionar os clientes para uma instância de Failover. Ideal para recuperação de desastres.Possui Healthcheck.

## CloudFront Overview

**CloudFront** é o serviço de CDN da AWS.Trabalha primariamente com buckets [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) distribuindo arquivos e cacheando eles nos edges, definindo políticas avançadas de segurança com **OAI (Origin Access Identity)**. **CloudFront** também pode ser utilizado como porta de entrada para uploads de arquivos no [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html).**CloudFront** também pode trabalhar como mediador de outros back-ends como:

* Load Balancers.
* Instâncias [EC2](https://aws.amazon.com/pt/ec2/).
* Websites [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) (habilitando o bucket como um website [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) estático).
* Qualquer outro backend HTTP que você queira.

**CloudFront** vs [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Cross Region Replication **CloudFront**:

* Distribui os arquivos globalmente através da edge network.
* Os arquivos são cacheados por um tempo limitado(ex: 1 dia)
* Bom para arquivos estáticos que precisam estar disponíveis em todos os lugares do mundo.
[S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Cross Region Replication:
* Precisa ser configurado para cada region que você quer que esteja disponível.
* Os arquivos são atualizados quase em tempo real.
* As replicas são de apenas leitura.
* É bom para arquivos dinâmicos que precisam estar disponíveis com baixa latência em algumas regions.

## [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Transfer Acceleration

**S3 Transfer Acceleration** é uma técnica para diminuir o tempo de transferência de um pacote de uma region/AZ para outra. Exemplo: o arquivo está na region 1 e precisa ir para a region 2, ele é levado para a edge location da region 1 que fica mais próxima da region 2 e de lá é levado para a region 2.

## AWS Global Accelerator

**AWS Global Accelerator** é uma técnica da AWS usada para melhorar a conexão do cliente com os servidores da AWS, o objetivo é conectar o cliente com a edge location mais próxima possível, desta forma o cliente se conecta com a edge location e esta se conecta com o servidor final com uma conexão mais robusta para obter as informações necessárias.

**Global Accelerator** vs **CloudFront**
**CloudFront**:

* Além de usar Edge locations faz cacheamento de arquivos nelas.
* A maioria dos arquivos são obtidos ainda nas edge locations.
**Global Accelerator**:
* Sem cache.
* Melhora a performance de conexão deixando parte do percurso de conexão com a própria AWS.
* Bom para casos de uso com HTTP que usam IPs estáticos ou que usam failovers determinísticos de regions.

## AWS Outposts

**AWS Outposts** é um serviço da AWS para empresas que usam modelo de cloud híbrida. Nele a AWS disponibiliza um raque físico para a empresa no qual pode ser anexado ao datacenter, este raque fornece todos os serviços da AWS e praticamente transforma o datacenter on-premisse da empresa em um anexo da AWS mas dedicado à empresa. A diferença é que neste caso o cliente é responsável também pela segurança física do servidor.

Alguns benefícios do **AWS Outposts**:

* Baixa latência no uso de serviços on-premisse.
* Processamento de dados local.
* Data residency.
* Migração fácil de dados dos servidores on-premisse para a cloud.
* Serviço totalmente gerenciável.
Alguns serviços que funcionam com **Outposts**: [EC2](https://aws.amazon.com/pt/ec2/), [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html), [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), **EKS**, **ECS**, **RDS**, **EMR**.

## AWS WaveLength

**AWS WaveLength** é um serviço da AWS que fornece infra para instâncias e deploys em edges de redes 5G, útil para provedoras de internet móvel porque fornece uma latência baixa para os clientes dessas provedoras na área próxima.Caso de uso: Smart Cities, Smart Vehicles, Video Streams interativos, AR/VR, Real-time gaming, etc...

## Leveraging the AWS Global Infrastructure Summary

Resumo Aplicações globalizadas na AWS:

* **Route 53**: Serviço DNS da AWS, possui estratégias para latência e recuperação de desastre.
* **CloudFront**: Serviço de CDN da AWS, faz cache de arquivos nas edge locations diminuindo a latência.
* **S3 Transfer Acceleration**: Acelera upload e download na Amazon [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) usando edge locations.
* **Global Accelerator**: Melhora a conexão global usando a edge location mais próxima do cliente como proxy.
* **Outposts**: Raques físicos da AWS anexados aos datacenters on-premisse da empresa para disponibilizar os serviços da AWS.
* **WaveLength**: Disponibiliza infra para subir serviços AWS nas edges de redes 5G para redes de latência super baixas.

## Cloud Integrations Overview

O maior problema em tentar estabelecer uma comunicação entre 2 aplicações na AWS é o aumento da demanda de um lado seguido de uma rápida escalada que não é acompanhada do outro lado na mesma velocidade, com isso pode haver lentidão ou queda de serviços.Para resolver esse problema a AWS oferece serviços de queues para desacoplar aplicações do ponto de vista de sincronicidade. Os serviços disponíveis são:

* **SQS**: Modelo de Fila.
* **SNS**: Modelo de Listening/Publishing.
* **Kinesis**: Modelo de data streaming em tempo real. (Fora do escopo do exame)
Desta forma as aplicações e serviços podem escalar de forma independente.

## SQS Overview

**Amazon Standard Queue (SQS)** é o serviço de fila mais antigo da AWS(10 anos de idade).É um serviço totalmente gerenciável, serverless, usado para desacoplar aplicações, seguem as características:

* Pode escalar de 1 para 10000s de mensagens por segundo. O **SQS** estabelece o tempo de vida máximo da mensagem de 4 dias, mas você pode estender este tempo para até 14 dias.
* Não há um limite de quantas mensagens você pode inserir na fila.
* As mensagens são excluídas da fila quando são lidas pelos consumidores.
* O serviço possui uma latência muito baixa, inferior a 10ms entre publicar e receber.
* Consumidores compartilham o trabalho de ler a mensagem e escalam horizontalmente.

## SNS Overview

**Amazon Simple Notification Service (SNS)** têm por premissa fazer um publicador enviar uma mensagem para vários observadores.É cadastrado um publicador, este publicador envia a mensagem a apenas um tópico **SNS**. O tópico envia a mensagem a todos os subscribers cadastrados. Cada tópico pode ter até 10 milhões de inscrições. O limite de tópicos é de 10000.Os Subscribers de tópicos do **SNS** podem ser:

* Serviços HTTP/HTTPS
* Email, SMS, Notificadores Mobile.
* Queues **SQS**
* Funções [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html).

## Kinesis Overview

Amazon **Kinesis** é um serviço de streaming de bigdata em tempo real. Feito para coletar, processar e analisar streaming de dados em qualquer escala em tempo real. ISSO É TUDO QUE É PEDIDO NO EXAME PARA PRACTITIONER.Mais informações:

* **Kinesis** Data Streams: sistema de streaming em baixa latência para trazer dados de centenas de milhares de fontes.
* **Kinesis** Data Firehose: carrega streams em buckets [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), Redshift, ElasticSearch, etc...
* **Kinesis** Data Analytics: Realisa analytics em tempo real nos streams usando SQL.
* **Kinesis** Video Streams: Monitora video streams em tempo real para análise.

## Amazon MQ Overview

**Amazon MQ** é um serviço de fila da AWS feito para haver uma convivência entre a estrutura de fila da Amazon e serviços legado. Usado por empresas que estão migrando seus sistemas de ambientes on-premisse para a cloud e deixaram de usar tecnologias de fila on-premisse para usar as tecnologias da Amazon.O **Amazon MQ** é basicamente um Apache ActiveMQ gerenciável, NÃO é serverless, é necessário criar uma instância e dar manutenção a ela para gerenciá-lo, não é tão escalável quanto **SQS** ou **SNS** mas possui as mesmas features que os outros dois serviços.

## Cloud Integrations Summary

Resumo Integração:

* **SQS**: Serviço de Fila com múltiplos produtores, t de vida das mensagem < 14 dias, múltiplos consumidores compartilham a leitura, quando a mensagem é lida, ela é deletada, usado para desacoplar as aplicações.
* **SNS**: Serviço de notificação, usado para Emails, Lambda, **SQS**, HTTP, Mobile, etc... Multíplos Observadores, a mensagem vai em formato de broadcast e é volátil, uma vez enviada, é destruída.
* **Kinesis**: Serviço de streaming em tempo real, persistência e análise.
* **Amazon MQ**: Apache ActiveMQ gerenciável da AWS, usado para adaptar sistemas de fila on-premisse para a cloud (ex: MQTT, AMQP, etc...)

## CloudWatch Metrics & CloudWatch Alarms Overview

AWS **CloudWatch** é o serviço de métricas da Amazon, usado para fazer a análise gráfica da utilização dos serviços da AWS afim de se obter informações de forma simplificada para a tomada de decisão com relação a utilização dos serviços na nuvem, pode se gerar gráficos com dados relacionados a:

* [EC2](https://aws.amazon.com/pt/ec2/): Utilização da CPU, Checagem de status, Network. Alimentação padrão a cada 5 min, pode se diminuir o intervalo para 1 minuto pagando mais.
* [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html): Taxa de Leitura/Escrita dos volumes.
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html): BucketSizeBytes, NumbersOfObjects, AllRequests.
* **Billing**: Custo total estimado(apenas na region us-east-1)
* Service Limits: O quanto você tem utilizado a API de um serviço.
* Métricas customizadas: você pode criar sua própria métrica.

**AWS CloudWatch Alarms** é um sistema de alarmes associada a métrica.Os alarmes possuem as seguintes ações:

* Auto Scaling: Incrementar ou decrementar quantidade de instâncias [EC2](https://aws.amazon.com/pt/ec2/).
* Recuperar, reiniciar, finalizar ou parar instâncias [EC2](https://aws.amazon.com/pt/ec2/).
* Notificações **SNS**: Enviar notificações para um tópico **SNS**.
É possível definir os triggers com base em várias condicionantes como: Sampling, %, max, min, etc... Você também pode controlar qual período em que o alarme irá monitorar.Exemplo de alarme:Alarme **Billing** na métrica **Billing** da **CloudWatch** que monitora os custos.Status possíveis:
* OK - para status satisfatório
* INSUFICIENT_DATA - para dados não conclusivos
* ALARM - para status que disparam o alarme

## CloudWatch Logs Overview

Amazon **CloudWatch** Logs são logs coletados de:

* **Elastic Beanstalk**: coleção de logs coletadas das aplicações
* **ECS**: Coleção de logs dos containers.
* [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html): Coleção de logs das funções.
* **CloudTrail**: Logs baseados nos filtros.
* **CloudWatch** Log Agent: Log de máquinas [EC2](https://aws.amazon.com/pt/ec2/) em servidores on-premisses.
* **Route53**: Logs de queries DNS.
Esses logs são coletados e permites monitoramento em tempo real, a retenção dos logs pode ser ajustada em tempo real na **CloudWatch**.

**CloudWatch** Logs podem ser utilizados em instâncias [EC2](https://aws.amazon.com/pt/ec2/) na AWS em on-premisse, para isso as instâncias precisam estar configuradas com roles [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html), um log agent será instalado nessas instâncias ou no servidor on-premisse que enviarão os logs para a **CloudWatch**.

## CloudWatch Events / EventBridge Overview

**Amazon EventBridge** é a evolução do **CloudWatch Events**.A ideia é ter um barramento que possa receber eventos dos serviços da AWS ou de serviços terceiros, bem como enviar esses eventos para outras aplicações, utiliza modelos esquemáticos.

**Amazon CloudWatch Events** são eventos disparados baseados em regras criadas dentro do **CloudWatch**, ex: executar funções [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html), disparar tópicos **SNS**, etc..

## CloudTrail Overview

AWS **CloudTrail** é um serviço que registra todos os eventos executados em todos os serviços da AWS para fins de governança, compliance, segurança ou auditoria. Você consegue obter um histórico de eventos, chamadas de APIs feitos na conta da AWS, como consoles, SDKs, CLI, serviços da AWS e você você colocar logs da **CloutTrail** na **CloudWatch** Logs ou [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html). Os Trails podem ser aplicados em todas as regions(default) ou em uma única region.Então se algo der errado na AWS, se algo de suspeito acontecer na conta, se algum recursos for excluído inesperadamente, o primeiro lugar a ser investiado e o **CloudTrail**.**CloudTrail** vem habilitado por padrão na sua conta.

Tipos de eventos do **CloudTrail**:Management Events:Eventos de relacionados a manutenção de recursos da conta da AWS, ex:

* Configuração de segurança
* Configuração de roteamento
* Configuração de logging
* Alteração em instâncias, buckets, volumes.
Por padrão esse tipo de log vem ativado.Você pode separar esses logs em leitura(usuários que apenas acessam as telas) e escritas(usuários que tentam modificar recursos).Data Events:Eventos relacionados a dados, por padrão o log vem desligado, ex:
* Buckets [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html): GetObject, DeleteObject, PutObject.
* Funções [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html): Execuções da função(invoke)
Também podem ser separados em leitura e escrita.continua...

**CloudTrail** Insights:Este tipo de serviço tem por objetivo tentar buscar por atividade suspeita na conta como: provisionamento suspeito de recursos, limite de recursos constantemente atingidos, supostas tentativas de fraldes dentro do contexto [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html).Para que o Insight funcione, ele precisa analisar os logs regulares para ter uma ideia do que seria um comportamento normal da conta, e então passará a analisar continuamente. Qualquer anomalia encontrada aparecerá no console do **CloudTrail** e eventos serão enviados para o Amazon [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), também poderão ser gerados eventos no **EventBridge**.

**CloudTrail** armazena dados por até 90 dias, para armazenar dados por mais tempo, você pode replicar esses dados dentro de buckets [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) e acessa-los usando **Athena**.

## X-Ray Overview

AWS **X-Ray** é um serviço de Debugging em produção que analisa a interação entre módulos da aplicação e exibe essas interações de forma visual mostrando a taxa de sucessos, permitindo que se obtenha o perfil das requisições que obtiveram erros e quais e como os usuários estão sendo impactados.

## CodeGuru Overview

Amazon **CodeGuru** é um serviço que usa Machine Learning para fazer Code Review automatizado e recomendações de melhoria de performance da aplicação.É dividido em 2 funcionalidades:

* **CodeGuru** Reviewer: Sistema de codeReview para análise de códigos estáticos.
* **CodeGuru** Profiler: Recomendações para melhoria da performance da aplicação em runtime.
Dá suporte para Java e Python, pode ser integrado com Github, Bitbucket e AWS **CodeCommit**.Pode funcionar tanto na AWS quanto On-Premisse.

## Service Health Dashboard

**AWS Status - Service Health** é um serviço público da AWS que informa o status de cada serviço fornecido pela Amazon em cada region. Também informa o histórico de status.Você pode assinar um feed RSS para obter informações em tempo real.Pode ser acessado na URL: <https://status.aws.amazon.com>

## Personal Health Dashboard

**AWS Personal Health Dashboard (PHD)** é um serviço da AWS que te alerta sobre eventos anormais nos serviços da AWS que possam te impactar. Diferente do **Service Health Dashboard**, o **Personal Health Dashboard** fornece informações personalizadas baseado nos serviços que você utiliza, também fornece informações relevantes e provativas de tempos em tempos para te ajudar a organizar os eventos em progresso.Pode ser acessado pela URL: <https://phd.aws.amazon.com>

## Cloud Monitoring Summary

Resumo Monitoramento pt 1:

* **CloudWatch**:
* metrics: Monitora a performance dos serviços da **AWS** e **billing** com métricas
* Alarms: Automatiza notificações, realiza ações no [EC2](https://aws.amazon.com/pt/ec2/), notificações **SNS** com métrica.
* Logs: coleta logs de [EC2](https://aws.amazon.com/pt/ec2/), Servers, [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html).
* **Events**: Reação a event na AWS ou dispara a evento baseado emagendamento.
* **EventBridge**: Mesmo que Events
* **CloudTrail**: Audita chamadas de APIs de recursos da AWS feitas na sua conta.
* **CloudTrail Insight**: Serviço de análise automatizada de eventos da CloudTrail,

Resumo Monitoramento pt 2:

* **X-Ray**: Serviço de debugging em produção para aplicações distribuídas.
* **Service Health Dashboard**: Status de todos os serviços da AWS em todas as regions.
* **Personal Health Dashboard(PHD)**: Mostra eventos da AWS que possam impactar sua infra.
* Amazon **CodeGuru**: Serviço de CodeReview automatizado e recomendações de performance da aplicação.

## VPC Overview

Conteúdo relacionado a **VPC** e networking pedido no exame de Practitioner:

* **VCP**, Subnets, Internet Gateways e NAT Gateways.
* **Security Groups**, Network ACL(NACL), **VPC** Flow Logs.
* **VPC** Peering, **VPC** Endpoints.
* Site to Site VPN e Direct Connect
* Transit Gateway.

## VPC, Subnet, Internet Gateway & NAT Gateways

**Virtual Private Cloud (VPC)** é uma rede privada que permite que você realize a comunicação entre seus componentes de forma privada como uma rede local(similar a uma VPN), cada **VPC** está limitada a uma region.Subnet é uma partição de uma **VPC**, permitindo que você isole alguns de seus componentes dos outros, cada subnet está limitada a uma AZ.Uma subnet pública é uma subnet acessível da internet.Uma subnet privada é uma subnet não acessível da internet.Para definir os perfis de comunicação de cada subnet, você pode utilizar um serviço chamado Route Tables.

**Internet Gateway** é um componente que se conecta com a **VPC** para mediar a comunicação entre ela e a internet, é utilizada tanto para download quanto para upload de dados.**NAT Gateway**(AWS-managed) e **Instâncias NAT**(self-managed) são componentes que permitem que subnets privadas acessem a internet sem se exporem, usada apenas para download de dados. Utilizam tradução NAT.

## Security Groups & Network Access Control List (NACL)

**Network Access Control List (NACL)** é um firewall que utiliza um conjunto de regras para definir que tipo de tráfego é PERMITIDO e que tipo de tráfego é PROIBIDO. São anexadas à subnets, as regras trabalham apenas com IPs.**Security groups**, como podem ser utilizados juntamente com **NACL**, porém, **Security Groups** estão anexados a Instâncias [EC2](https://aws.amazon.com/pt/ec2/)/ **Elastic Network Interface (ENI)**, as regras de **Security Groups** trabalham apenas com gráficos PERMITIDOS, regras de **Security Groups** podem incluir IPs ou outros **Security Groups**.

Mais diferenças entre **NACL** e **Security Groups**, as comparações estão de forma respectiva. **Security Groups**:

1. Funciona a nível de instância.
2. Suporta apenas regras de PERMISSÃO.
3. É stateful, o tráfego de retorno é automaticamente permitido, a não ser que haja uma regra negando.
4. Só é associado à instância se na criação da instância o **Security Group** for ligado a ela.

**NACL**:

1. Funciona a nível de subnet.
2. Suporta regras de PERMISSÃO e NEGAÇÃO.
3. É stateless, a autorização do tráfego de retorno deve ser explicitada pelas regras.
4. É automaticamente aplicado a todas as instâncias da subnet.

## VPC Flow Logs & VPC Peering

**VPC Flow Logs** é um serviço que cria logs relacionados a **VPC**, Subnets e **ENIs**. Ajudam a monitorar problemas e realizar troubleshooting relacionados à conexões: subnet-internet, subnet-subnet, internet-subnet.Captura informações da interface de outros serviços da AWS também como: **ELBs**, **ElastiCache**, **RDS**, **Aurora**, etc...Os dados do **VPC Flow Logs** podem ser enviados para o [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) e **CloudWatch Logs**.

**VPC Peering** permite que duas **VPCs** se comuniquem de forma privada como se estivessem na mesma rede. Para que este procedimento seja feito é necessário que a configuração de IPs das **VPCs** não permita overlapping(conflito de range de IPS da máscara de rede). A conexão **VPC Peering** não é transitiva, o que significa que se você tiver 3 **VPCs** e quiser que as 3 se comuniquem entre si, precisará de 3 peerings, cada peering criando ponte entre 2 **VPCs**, cada peering será criado para DUAS **VPCs** e não poderá ser reconfigurado para uma terceira.

## VPC Endpoints - Interface & Gateway (S3 & DynamoDB)

**VPC Endpoints** é um serviço que permitem que você se conecte com serviços da AWS usando uma rede privada, invés de uma rede pública. Isso melhora a segurança da conexão e diminui a latência.**VCP Endpoint Gateway** é usado para acessar o [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) e o **DynamoDB**.**VPC Endpoint Interface** é usado para o restante dos serviços.

## Direct Connect & Site-to-Site VPN

**Site to Site VPN** é o serviço de VPN da AWS que permite conexão de datacenter on-premisse com a AWS pela internet via VPN.**Direct Connect (DX)** é um serviço que permite conexão do datacenter on-premisse com a AWS por meio de uma conexão física, direta e privada, é muito mais seguro, caro e leva no mínimo 1 mês para ser feito.

Para utilizar **site-to-site VPN** o cliente deve um **Customer Gateway (CGW)** no servidor on-premisse, a VPN fará a conexão na internet e a porta de entrada na AWS será um **Virtual Private Gateway(VGW)**

## Transit Gateway Overview

**Transit Gateway** é um mediador universal que é utilizado para conectar todas as formas de conexão da AWS: **VPC**, VPN, **Direct Connect Gateway**, on-premisse, etc... funcionando em um formato de estrela(hub-and-spoke).

## VPC & Networking Summary

Resumo Networking pt 1:

* **VPC**: Virtual Private Network, Rede privada na AWS, Limitada a Region
* Subnet: Partição dentro da **VPC** - Limitada à AZ.
* **Internet Gateway**: A nível de **VPC**, provê acesso à internet. Download e Upload.
* **NAT Gateway/Instance**: Dá acesso à internet para subnets privadas. Apenas download.
* **NACL**: Stateless, Regras de subnet para entrada e saída de dados.
* **Security Groups**: Stateful, regras de instâncias [EC2](https://aws.amazon.com/pt/ec2/) ou **ENI**.

Resumo Networking pt2:

* **VPC Peering**: Conexão entre DUAS(apenas) **VPCs** SE não houver overlapping.
* **VPC Endpoints**: Permite acesso privado à serviços AWS dentro da VPC.
* **VPC Flow Logs**: Logs de tráfego de rede.
* **Site to Site VPN**: VPN via internet para acesso de DC on-premisse na AWS.
* **Direct Connect**: Acesso direto entre DC on-premisse e AWS.
* **Transit Gateway**: Hub Estrela que conecta milhares de **VPCs** e redes on-premisses juntas.

## Shared Responsibility Model: Reminders & Examples

Modelo de responsabilidade compartilhada da AWS quanto à segurança:AWS:

* Proteção física da infra.
* Serviços gerenciados como: [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), **DynamoDB**, **RDS**, etc...
Cliente:
* Serviços não gerenciados como instâncias [EC2](https://aws.amazon.com/pt/ec2/)(atualização SO, patches, updates), firewalls, configuração de redes, [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html).
* Criptografia de dados.
Compartilhada:
* Gerenciamento de patches, gerenciamento de configurações, treinamento.

Exemplo de modelo de responsabilidade com **RDS**:AWS:

* Gerenciar instâncias [EC2](https://aws.amazon.com/pt/ec2/), desabilitar acesso SSH.
* DB patching automatizado.
* OS patching automatizado.
* Auditar instâncias subjacentes e discos e garantir que funcionem.
Cliente:
* Verificar portas, IP, regras inbound de Security Groups nos BDs.
* Gerenciamento de usuários e permissões in-database.
* criação de BD com/sem acesso público.
* assegurar que os grupos de parâmetros ou BDs estão configurados para permitir apenas conexões SSL/TLS.
* Configurações de criptografia de BD.

Exemplo de modelo de responsabilidade com [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html):AWS:

* Garantir armazenamento ilimitado para o cliente.
* Garantir criptografia para o cliente.
* Garantir separação de dados entre diferentes clientes.
* Garantir que funcionários não possam acessar os dados dos clientes.
Cliente:
* Configuração do bucket.
* Política do bucket(público/privado)
* Usuários e roles [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html).
* Habilitar criptografia.

## DDoS Protection: WAF & Shield

Proteções contra dDoS na AWS:

* **AWS Shield Standard**: proteção contra ataques dDoS para a aplicação e website para todos os clientes sem custos adicionais.
* **AWS Shield Advanced**: Proteção dDoS premium 24/7
* **AWS WAF**: Filtra requisições específicas baseado em certas regras.
* **Cloudfront e Route53**: Protege a rede usando a Global Edge Network, pode se combinar com AWS Shield.
Mesmo com essas proteções, você deve estar preparado para usar o Auto scaling para manter a aplicação no ar.Para mais informações veja: <https://aws.amazon.com/answers/networking/aws-ddos-attack-mitigation>

Mais detalhes do **AWS Shield**:**AWS Shield Standard**:

* Serviço gratuito disponível para todos os clientes.
* Provê proteção contra ataques como floods SYN/UDP, reflexão de ataques e outros ataques nas camadas 3 e 4.
**AWS Shield Advanced**:
* Serviço de mitigação de dDoS opcional.
* Custa $3000 por mês por organização.
* Protege contra atques mais sofisticados na Amazon [EC2](https://aws.amazon.com/pt/ec2/), **ELB**, **CloudFront**, **Global Accelerator** e **Route 53**.
* Acesso 24/7 ao **AWS dDoS response team (DRP)**.
* Proteção contra eventuais custos superiores de uso de recursos devido a ataques dDoS.

**AWS Web Application Firewall (WAF)**:Protege as aplicações contra exploits comuns na web. Trabalha na camada 7. Trabalha em serviços como **ELB**, **API Gateway** e **CloudFront**.Definição de Web Access Control List (Web ACL):

* Define regras para IPs, headers HTTP, body HTTP, strings de URI.
* Proteção contra ataques comuns, ex: SQL Injection, Cross-site scripting.
* Size Constraints, geo-match.
* rate-based rules, definição de um ataque baseado na frequência de envios de requisições(ex: > 10/segundo)

## Penetration Testing

Você, como cliente, pode realizar testes de penetração em serviços da AWS, dos serviços da AWS, estes 8 você pode fazer o teste SEM pedir permissão da AWS:

* [EC2](https://aws.amazon.com/pt/ec2/), **NAT Gateways**, **ELB**.
* **RDS**.
* **CloudFront**.
* **Aurora**.
* **API Gateway**.
* [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) e [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) Edge functions.
* **Lightsail** resources.
* **Elastic Beanstalk**
A lista pode aumentar com o tempo, mas isso não será exigido no exame.

Tipos de ataques proibidos à infra da AWS:

* DNS zone walking na **Route 53**.
* DOS ou DDoS, real ou simulado.
* Port flooding.
* Protocol flooding.
* Request flooding.
Para qualquer outro evento simulado, entre em contato com aws-security-simulated-event@amazon.comPara saber mais, acesse: <https://aws.amazon.com/security/penetration-testing>

## Encryption with KMS & CloudHSM

Na AWS a criptografia de dados ocorre em 2 momento, no momento em que o dado está armazenado(at rest) e no momento que está em trânsito(in motion).Em armazenamento é chamado quando o dado está arquivado em um dispositivo, ex: em um HD, em uma instância **RDS**, em um bucket **S3 Glacier Deep Archive**, etc...Em trânsito é quando o dado está se movendo de um lugar para outro, ex: dado sendo transferido de on-premisse para AWS, ou de [EC2](https://aws.amazon.com/pt/ec2/) para **DynamoDB**, etc...Ambos os dados precisam ser criptografados e essa criptografia é feita usando técnicas que utilizam encryption keys.

Um serviço da AWS usado para criptografia é o **Key Management Service (KMS)**, neste serviço a AWS gera e gerencia chaves de criptografia sem necessidade da sua interferência.O **KMS** atua nos serviços da seguinte forma:

* [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html): Criptografia de volumes.
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html): Criptografia Server-side dos objetos dentro dos buckets.
* **Redshift**: Criptografia dos dados dentro do BD.
* **RDS**: Criptografia dos dados dentro do BD.
* **EFS**: Criptografia dos arquivos e dados dentro do sistema de arquivos.
Os seguintes serviços vêm com o **KMS** habilitado por padrão:
* **CloudTrail Logs**
* **S3 Glacier**
* **Storage Gateway**

Outro serviço de criptografia que a AWS oferece é o **CloudHSM**. Neste serviço a AWS fornece um hardware dedicado para a criptografia dos seus dados, este hardware é protegido contra adultérios seguindo o compliance FIPS I 40-2. Neste serviço você gerencia as suas próprias chaves por inteiro.

Categorizando os Customer Master Keys (CMK):Customer Managed CMK:

* Criado, gerenciado e usado pelo cliente, podem ser habilitado e desabilitado.
* Possibilidade de política de rotatividade, ex: novas chaves geradas a cada ano, chaves antigas preservadas.
* Possibilidade de importar chaves de fora da AWS.
AWS Managed CMK:
* Criadas, gerenciadas e usadas pela AWS em benefício do cliente.
* Usadas nos serviços, ex: aws/s3, aws/ebs, aws/redshift
AWS owned CMK:
* Coleção de CMKs que a AWS usa e gerencia em mais de uma conta de clientes.
* A AWS usa essas CMKs para proteger recursos na sua conta, mas não permitem que você se quer veja a chave.
**CloudHSM** Key:
* Chaves geradas pelo seu próprio device de hardware **CloudHSM**.
* Operações criptográficas performadas dentro do cluster do **CloudHSM**.

## AWS Certificate Manager (ACM) Overview

**AWS Certificate Manager (ACM)** é o serviço de gerenciamento certificados SSL e TLS, pode ser usado para prover criptografia para protocolo HTTPS.Dá suporte tanto para certificado TLS público e privado, sendo que a versão público é gratuita. Também faz renovação automática do certificado TLS.Possui integração com:

* **ELB**
* **CloudFront**
* **API Gateway**

## Secrets Manager Overview

**AWS Secrets Manager** é o serviço de gerenciamento de senhas da AWS.É um serviço mais novo. Têm capacidade de forçar uma rotação de senhas a cada X dias com geração automática de senhas na rotação(usa [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) para isso).Possui integração com Amazon **RDS** (MySQL, PostGreSQL, Aurora) e as senhas são criptografadas com **KMS**.Geralmente utilizado com integração com **RDS**.

## Artifact Overview

**AWS Artifact** é um portal que te permite ter acesso à documentação de compliance da AWS bem como acordos, possui 2 serviços:

* **Artifact Reports**: Te permite baixar documentos relacionados a compliance e segurança emitidos por auditores externos como: Certificações ISO, Payment Card Industry (PCI) e System and Organization Control (SOC).
* **Artifact Agreements**: Te permite revisar, aceitar e acompanhar o status de acordos como Business Associate Addendum (BAA) ou Health Insurance Portability and Accountability Act (HIPAA) para uma conta individual na sua organização.
Esses documentos podem ser usados em eventuais auditorias internas e externas e compliances.

## GuardDuty Overview

**Amazon GuardDuty** é um serviço inteligente de descoberta de eventuais ameaças a sua conta. Utiliza Machine Learning, detecção de anomalias e dados de terceiros. Você pode habilita-lo e obter um período de teste de 30 dias, sem necessidade de instalação de Software.O **GuardDuty** irá usar como input o **CloudTrail Logs** para procurar chamadas estranhas apra APIs e deploys não autorizados, **VPC Flow Logs** para detectar tráfego anormais ou IPs estranhos, **DNS Logs** para identificar instâncias [EC2](https://aws.amazon.com/pt/ec2/) comprometidas que estejam enviando dados não autorizados com queries DNS.Você pode configurar o **CloudWatch Event Rules** para notificar em caso de algum evento relevante seja encontrado.O **CloudWatch Event Rules** pode acionar um [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) ou **SNS**.

## Inspector Overview

**Amazon Inspector** é um serviço que analisa instâncias [EC2](https://aws.amazon.com/pt/ec2/) em busca de vulnerabilidades conhecidas nos SOs. Para funcionar precisa ser instalado no SO da instância [EC2](https://aws.amazon.com/pt/ec2/).Depois da verificação, você passará a receber um relatório com a lista de vulnerabilidades.

## Config Overview

**AWS Config** é um serviço que auxilia na auditoria e compliance registrando configurações e mudanças ao longo do tempo.Pode salvar esses dados dentro do [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), dados esses que podem depois serem analisados pela **Athena**.**AWS Config** pode auxiliar em questões como:

* Existem acessos SSH não autorizado nos meus **Security Groups**?
* Meus Buckets [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) estão com acesso público?
* Como minhas configurações **ALB** mudaram ao longo do tempo?
Você receberá alertas via notificações **SNS** por cada mudança.**AWS Config** está vinculado a uma region mas pode ser agregado a outras regions e outras contas.

## Macie Overview

**Amazon Macie** é um serviço totalmente gerenciado de segurança que utiliza machine learning para tentar identificar dados sensíveis na AWS. Quando habilitado, o **Macie** irá analisar seus componentes(ex: buckets [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html)) e procurar por possíveis dados sensíveis como Personaly Identifiable Information (PII).Essas informações podem ser enviadas via **CloudWatch Events**, [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) e/ou **SNS**.

## Security Hub Overview

**AWS Security Hub** é um serviço que centraliza vários serviços de segurança da AWS e em várias contas em um dashboard com sistemas de checagem de segurança automatizados.Possui dashboards integrados que mostram o estado atual de segurança e compliance das contas para auxiliar na tomada de decisão.Automaticamente agregam alertas em formatos pessoais ou pré-definidos de vários serviços da AWS como:

* **GuardDuty**
* **Inspector**
* **Macie**
* **IAM Access Analyzer**
* **AWS System Manager**
* **AWS Firewall Manager**
* **AWS Partner Network Solutions**.
Para funcionar é necessário que se habilite o serviço **AWS Config**.

## Amazon Detective Overview

**Amazon Detective** é um serviço usado para achar a causa raiz de uma eventual falha de segurança na sua conta, utiliza os relatórios do **GuardDuty**, **Macie** e **Security Hub** + Dados do **VPC Flow Logs**, **CloudTrail**, **GuardDuty** + Machine Learning e Gráficos para identificar a causa raiz de uma eventual fralde, então produz uma visão unificada de tudo.

## AWS Abuse

**AWS Abuse** é o canal de comunicação da AWS para denúncia de uso indevido dos serviços da AWS. É proibido utilizar os serviços da AWS para:

* Spam - enviar e-mails, posts, SMSs de forma automatizada e com fins indesejados
* Port Scanning - Enviar pacotes para suas portas para descobrir enventuais inseguranças.
* Dos ou DDoS - Ataque massivo de dados local ou distribuído a fim de derrubar um serviço.
* Intrusion attemps - Tentativa de invasão aos seus recursos.
* Hosting objectionable or copyrighted content - armazenar conteúdo ilegal ou sob copyright sem consentimento.
* Distribuição de Malwares - Utilizar recursos da AWS para distribuir Malwares e danificar computadores ou outros devices.
Para denunciar esse tipo de prática, preencha este formulário: <https://support.aws.amazon.com/#/contacts/report-abuseOu> envie um email para: abuse@amazonaws.com

## Root User Privileges

A conta root, por ter acesso total, não deve ser utilizada para atividades diárias, ainda que sejam administrativas, e devido a sua importância, sua senha e meios de proteção devem ser protegidos ao máximo, contudo, algumas ações só podem ser realizadas pela conta root, são elas:

* Mudança das configurações da conta(ex: nome da conta, email central, senha do root, root user acess keys)
* Ver certas taxas.
* Encerrar a conta AWS.
* Restaurar as permissões [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html).
* Mudar ou cancelar o plano de suporte AWS.
* Se registrar como um vendedor de instâncias reservadas no marketplace - quando você reserva instâncias mas se arrepende antes do fim do tempo e resolve vender o tempo restante no market place.
* Configurar Buckets [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) para habilitar MFA.
* Editar ou Excluir uma política de bucket [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) que inclua uma invalidVPC ID ou VPC endpoint ID.
* logar como GovCloud.

## Security & Compliance Summary

Resumo Security e Compliance pt 1:

* Responsabilidade compartilhada: Veja as anotações específicas.
* **Shield**: Serviço de proteção automática para DDoS com plano Standard + Plano advanced com suporte 24/7
* **WAF**: Firewall para filtrar requisições baseado em regras.
* **KMS**: Chaves de criptografia gerenciadas pela AWS.
* **CloudHSM**: Hardware dedicado para criptografia, cliente gerencia chaves de criptografia.
* **AWS Certificate Manager**: Gerenciamento de Certificados SSL/TLS, faz deploy, provisiona e renova automaticamente.
* **Artifact**: Portal com acesso a relatórios de compliance como PCI, ISO, etc...
* **GuardDuty**: Procura por comportamento malicioso na **VPC**, **DNS** e **CloudTrail Logs**.
* **Inspector**: Agente instalado na instância [EC2](https://aws.amazon.com/pt/ec2/) que procura por vulnerabilidade no SO.

Resumo Security e Compliance pt 2:

* **Config**: Rastreia mudanças de configuração para detectar quebra de regras de compliance.
* **Macie**: Busca por dados sensíveis(PII) nos Buckets [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html).
* **CloudTrail**: Rastreia chamadas de APIs de serviços da AWS feitas por usuários da conta.
* **AWS Security Hub**: Hub que centraliza a visão de vários serviços de segurança de várias contas.
* **Detective**: Busca a causa raiz de problemas de segurança e atividades suspeitas.
* **AWS Abuse**: Serviço de denúncia de atividades suspeitas ou ilegais com serviços da AWS.
* Privilégios do Usuário Root:
* Mudar configurações da conta.
* Fechar conta.
* Mudar o cancelar o plano de suporte da AWS.
* Se registrar como vendedor no Reserved Instance Marketplace.
* Entre outros.

## Rekognition Overview

**Amazon Rekognition** é o serviço que usa ML para fazer reconhecimento de objetos, pessoas, textos, cenas em imagens e vídeos.Também faz análise facial, busca facial e contagem de pessoas. Pode criar um BD com \rostos familiares\ ou comparar com rostos conhecidos(celebridades).Casos de uso:

* Dar nome as coisas(labeling)
* Moderação de conteúdo.
* Detecção de texto.
* Detecção de rostos e análise(géneros, idade, emoções)
* Busca de rostos e verificação.
* Reconhecimento de celebridades.
* Pathing(para análise de jogos esportivos)
Para conhecer melhor o serviço, acesse: <https://aws.amazon.com/rekognition/>

## Transcribe Overview

**Amazon Transcribe** é um serviço que transcreve áudios para texto de forma automática. Utiliza um processo de deep learning chamado Automatic Speech Recognition (ASR).Casos de uso:

* Transcrever chamadas com usuários.
* Closed caption automático.
* Geração de metadado automático para arquivos de mídia.

## Polly Overview

**Amazon Polly** é um serviço da Amazon feito para transformar texto em áudio usando deep learning permitindo que você crie aplicações que falem.

## Translate Overview

**Amazon Translate** é o serviço de tradução da AWS, útil para internacionalização de textos de grande volume.

## Lex + Connect Overview

**Amazon Lex** é um serviço parecido com a **Alexa** que faz transformação de palavras em ação, pode ser usado com chatbots.**Amazon Connect** é um serviço que recebe chamadas e cria fluxos de atendimento baseado em um Virtual Contact Center, pode se integrar com outros CRMs ou com a AWS e com o Lex afim de fazer um sistema integrado de recebimento de chamadas e emissão de ordens. Não exige pagamento antecipado e pode ser até 80% mais barato que soluções de contact centers tradicionais.O fluxo de comunicação entre esses serviços seria:Cliente via chamada telefônica -(chamada)- **Connect** -(stream)- **Lex** -(invocar)- [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) -(agendar)- CRM

## Comprehend Overview

**Amazon Comprehend** é um serviço totalmente gerenciado e serverless que usa Natural Language Processing (NLP) para fazer interpretação de texto e insights. Pode descobrir:

* Idioma do texto.
* Extrair frases/palavras chaves, lugares, pessoas, marcas e eventos.
* Entender o quão positivo ou negativo o texto é.
* Analisar o texto usando tokenização e parte do discurso.
* Organizar o texto por tópicos.
Casos de usos:
* Analisar interações por emails com cliente para entender experiência positiva ou negativa.
* Criar e agrupar artigos por tópico e compreender assuntos.

## SageMaker Overview

**Amazon SageMaker** é um serviço feito para desenvolvedores e cientistas de dados que auxilia a criar modelos de ML para cenários customizados para sua empresa. Ele auxilia em todo processo de obter os cenários de atuação de ML, gerenciamento e monitoramento. Se trata de um serviço mais complexo e voltado para quem tem mais experiência com ML.

## Forecast Overview

**Amazon Forecast** é um serviço que faz predições com base em dados que você envia para ele. Tende a ser até 50% mais preciso do que análises manuais de dados.Casos de uso: Análise econômica, planejamento financeiro, planejamento de recursos.Exemplo de fluxo:Dados obtidos -> [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) -> **Forecast** -> Forecasting model -> Resultado(ex: vendas aumentarão em 20%)

## Kendra Overview

**Amazon Kendra** é um serviço voltado para descoberta de informações em documentos baseado em perguntas. Ele faz busca em documentos como: Texto, PDFs, HTMLs, PowerPoints, Word, FAQs, Google Drive, OneDrive, ServiceNow, SalesForce, etc... Tem capacidade de interpretar linguagem natural.Ex de uso:Você pergunta para ele: \Onde é o bebedouro?\Ele procura na lista de documentos o mapa da empresa e descobre que o bebedouro fica no 1º andar e responde: \1º andar\

## Personalize Overview

**Amazon Personalize** é um serviço que utiliza dados para personalizar a experiência dos clientes da sua empresa. Ele recebe informações de APIs ou do [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) e após alguns dias cria um modelo que define quais seriam as melhores informações para aparecerem para cada um dos clientes quando eles acessassem determinada tela. Utiliza a mesma tecnologia da amazon.com

## Machine Learning Summary

Resumo Machine Learning:

* **Rekognition**: Sistema de reconhecimento facial e reconhecimento de celebridades.
* **Transcribe**: Transcrição de áudio em texto.
* **Polly**: Transformação de texto para áudio.
* **Translate**: Tradução.
* **Lex**: Constrói conversações com chatbots.
* **Connect**: Contact center na núvem.
* **Comprehend**: Processamento de linguagem natural.
* **SageMaker**: ML para criação de modelos para cientistas de dados e devs.
* **Forecast**: Usa ML para predições.
* **Kendra**: Sistema de busca que usa ML.
* **Personalize**: Sistema de recomendações personalizadas em tempo real.

## Organizations Overview

**Organizations** são estruturas globais da AWS em que você reúne várias contas root em uma organização. Uma das contas root fica sendo a conta master e as outras contas ficam como contas child. Os benefícios de se fazer uma organização são:

* **Billing** consolidado entre todas as contas com um único método de pagamento.
* Benefícios de preço agregados ao longo do uso, ex: desconto no uso de volumes de [EC2](https://aws.amazon.com/pt/ec2/) e [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html).
* Pooling de instâncias [EC2](https://aws.amazon.com/pt/ec2/) reservadas compartilhado para economizar.
Existem APIs disponíveis para automatizar a criação de contas.Existe um sistema de restrição de privilégio de contas chamado **Service Control Policies (SCP)**

É possível também dividir as contas em grupos chamados **Organization Units(OU)**, de forma que fique da seguinte forma:Uma master account contém de 0 a n **OUs**.Uma master account contém de 0 a n contas.Uma **OU** contém de 1 a n contas.Uma **OU** contém de 0 a n **OUs**.Uma conta não contém nada além dela mesma.Um exemplo de estrutura organizacional é:

* Master(master)
* Produção(**OU**)
* Sistema 1(conta)
* Sistema 2(conta)
* Homologação(**OU**)
* Sistema 1(conta)
* Sistema 2(conta)
* Dev(**OU**)
* Sistema 1(conta)
* Sistema 2(conta)

**Service Control Policies (SCP)** é o serviço que faz parte da **Organization** que restringe acesso das contas filhas aplicando whitelist e blacklist em ações [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html). Pode ser aplicado em **OUs** e contas mas não podem ser aplicados na master. **SCP** é aplicado a todos os usuários e roles de todas as contas [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) e root das **OUs** e contas filhas.**SCP** não afeta service-linked roles(roles que permitem que serviços AWS integrem com Organization e não podem ser restritos por **SCPs**).**SCP** devem ter um PERMITIR explícito para permitir qualquer coisa, ou seja, não permitem nada por padrão.Cada **OU** e conta herda as políticas **SCP** da **OU**/master mãe dentro da **organization**.Casos de uso:

* Restringir acesso a alguns serviços, ex: não pode usar **EMR**.
* Restringir certos servirços obedecendo compliance.

## AWS Control Tower Overview

**AWS Control Tower** é uma maneira de configurar e governar um ambiente de múltiplas contas de forma segura e aderente a compliance baseado nas melhores práticas.Benefícios:

* Automatizar a configuração do ambiente em alguns cliques.
* Automatizar as políticas usando guardrails.
* Detectar violações de políticas e remedia-las.
* Monitorar compliance através de dashboards interativos.
**AWS Control tower** roda sobre **AWS Organization** e automaticamente configura o **Organization** para organizar as contas e implementar **SCPs.** **AWS Control Tower** possui um painel em que você pode criar várias contas e **OUs** e administrar **SCPs** de forma fácil.

## Pricing Models of the Cloud

A AWS possui 4 modelos de preços:

* Pay as you go: Você paga pelo que você usa, forma prática, responsiva e escalável de usar, porém, mais cara.
* Save when you reserve: risco mitigados, orçamento previsível, você reserva a utilização de recursos e assim obtém descontos, você pode os seguintes recursos: [EC2](https://aws.amazon.com/pt/ec2/), **DynamoDB**, **ElastiCache**, **RDS**, **Redshift**.
* Pay less by using more: Quanto mais você usa um recurso, menos você paga por ele.
* Pay less as AWS grows: A medida em que a infra da AWS cresce, você vai pagando menos pelos recursos.

Sobre gratuidade na AWS:Os seguintes serviços da AWS são gratuitos: [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html), **VPC** e **Billing** consolidado.Os seguintes serviços da AWS são gratuitos mas interagem de forma automatizada com serviços pagos: **Elastic Beanstalk**, **CloudFormation** e **Auto Scaling Groups**.Free Tier: Grupo de serviços que podem ser usados por um tempo/quantidade de forma gratuita, para entender em detalhes, acesse: <https://aws.amazon.com/free/> são exemplos de elegíveis a free tier:

* Instância [EC2](https://aws.amazon.com/pt/ec2/) t2.micro por 1 ano
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html), **ELB** baseado em quantidade de dados transferidos.

Precificação do [EC2](https://aws.amazon.com/pt/ec2/) pt 1:Você só é cobrado pelo que você usa e esse custo é multiplicado pela quantidade de instâncias.Cada tipo de instância tem um preço que é baseado em:

* Capacidade física.
* Region.
* SO e software.
* Tipo instância.
* Tamanho instância.
O tempo e quantidade de dados processados pelo **ELB** também são cobrados.O sistema de monitoramento de instância também gera um custo, especialmente se você optar pela geração de dados a cada 1 minuto ao invés de a cada 5 minutos.

Precificação do [EC2](https://aws.amazon.com/pt/ec2/) pt 2:Tipos de cobrança para [EC2](https://aws.amazon.com/pt/ec2/):

* On-demand
* Cobrança inicial de 60 segundos.
* Após isso, SE for Linux ENTÃO cobra a cada segundo, SE for Windows,ENTÃOcobra a cada hora.
* Reserved instances
* Até 75% de desconto comparadas com on-demand proporcionalmente.
* Reserva de 1 OU 3 anos.
* Adiantamento de pagamento TOTAL, PARCIAL ou NENHUM.
* Spot instance
* Até 90% de desconto comparada com on-demand proporcionalmente.
* Utilização de recursos ociosos da AWS, sem garantia de continuidade.
* Dedicated Host
* On-demand
* Reserva de 1 OU 3 anos.
* Saving plans
* Formas de economizar e obter descontos na utilização de recursos.

Precificação de [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html), **ECS** e **Fargate**:

* [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
* Você pode pagar por chamada OU por tempo de duração da execução.
* **ECS**
* Você NÃO paga pelo armazenamento das imagens, mas paga cada vez que cadaimagemsubir em uma instância.
* **Fargate**
* Em **Fargate** você paga pelo CPU e memória alocada para a suaaplicação e containers.

Precificação [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html):[S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) possui as seguintes classes: [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Standard, [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Infrequent Access, [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) One-Zone IA, [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Intelligent Tiering, [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Glacier e [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Glacier Deep Archive nessa ordem de preço do maior para o menor em termos de volume de arquivos armazenados.O preço pode ser definido baseado no volume dos objetos (quantidade e tamanho).Também quanto mais requisições você obtiver, mais você paga.Você NÃO paga para colocar dados dentro do [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), mas paga para ler esses dados sendo que na lista acima, os primeiros você paga menos para fazer essa leitura.O serviço [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Transfer Acceleration também haverá uma taxa a ser paga.Toda vez que você usar o Lifecycle para levar dados de uma classe [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) para outra, você também terá que pagar uma taxa.**EFS** também têm características similares, você paga por uso, possui infrequent access e regras de lifecycle.

Precificação [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html):Você paga pelo tipo de volume(devido à performance) e pela quantidade de GBs ALOCADA(não usada) por mês.Cobrança por IOPS(IO per second):

* Gerenal purpose SSD: incluso
* Provisioned IOPS SSD: Quantidade IOPS alocada.
* Magnetic: Quantidade de requisições.
Snapshots: Você paga pela quantidade de GBs por mês.Transferência de dados: Você paga pela quantidade de dados lidas e quanto mais dados você ler, mais desconto você têm.Escrita de dados é gratuita.

Precificação **RDS**:Você paga por hora de utilização e pela quantidade de IOs por mês, sendo que esta quantidade varia da performance de IO do BD(Single AZ ou Multi AZ).Dados transferidos para fora do BD são pagos e você ganha desconto pelo volume e dados transferidos para dentro do BD são gratuitos.Características do BD: Engine, tamanho e Classe de memória.Tipos de compra:

* On-demand
* Reserved Instances de 1 OU 3 anos com pagamento adiantado OBRIGATÓRIO.
Armazenamento de backup: Não existe necessidade de pagamento por armazenamento de backup de 100% do seu BD por uma region se seu BD não estiver cheio.Você paga a mais por armazenamento adicionais(GB por mês).

Precificação **CloudFront**:No **CloudFront** você paga por volume de dados transferidos para fora do sistema e ganha desconto pelo volume, a contagem é feita pela quantidade de requisições HTTP/HTTPS.A precificação varia de acordo com a área geográfica das edges locations.

Precificação Networking:Considere o cenário:

* Region 1
* AZ 1
* Instância 1
* Instância 2
* AZ 2
* Instância 3
* Region 2
* AZ3
* Instância 4

Supondo que você queira fazer uma comunicação entre as instâncias 1 e 2(R1AZ1I1 - R1AZ1I2) utilizando um IP privado, você não paga nada.Supondo que você queira fazer uma comunicação entre as instâncias 1 e 3(R1AZ1I1 - R1AZ2I3) utilizando um IP público, você paga $0,02 por GB.Supondo que você queira fazer uma comunicação entre as instâncias 1 e 3(R1AZ1I1 - R1AZ2I3) utilizando um IP privado, você paga $0,01 por GB.Supondo que você queira fazer uma comunicação entre as instâncias 1 e 4(R1AZ1I1 - R2AZ3I4), você paga $0,02 por GB.Desta forma usar a mesma AZ te dá maior performance me menor preço mas sacrifica a alta-disponibilidade e utilizar AZs/regions diferentes te da menor performance e maior preço mas te da segurança e redundância devido à alta-disponibilidade.

## Savings Plan Overview

Savings Plan é uma forma de se obter desconto pela utilização de instâncias de computação na AWS. Com esse formato, ao invés de fazer reserva de instâncias, você determina que irá gastar uma certa quantidade de $ por hora pelos próximos 1 OU 3 anos. É um a forma mais fácil de ter uma infra de longo prazo na AWS. Existem 2 tipos de saving plan:

* EC2 Savings Plan
* Até 72% de desconto, se comparada com on-demand.
* Você pode selecionar a classe e geração das instâncias que você querutilizar,ex: C5 ou M5.
* Não pode escolher a AZ, nem tamanho(ex: m5.xl ou m5.4xl), SO ou arrendamento.
* Adiantamento de pagamento TOTAL, PARCIAL ou NENHUM.
* Compute Savings Plan
* Até 66% de desconto comparado com on-demand.
* Não pode escolher Família, Region, tamanho, SO, arrendamento, ou opções decomputação.
* Tipos de computação: EC2, Fargate e Lambda.

Você pode configurar todas as questões de custo no AWS Cost Explorer console.Mais em: <https://aws.amazon.com/savingsplans/pricing/>

## Compute Optimizer Overview

**AWS Compute Optimizer** é um serviço que usa ML para reduzir custos e melhorar a performance, faz isso analisando a utilização de instâncias [EC2](https://aws.amazon.com/pt/ec2/), volumes [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) e funções [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html), configurações e métricas da **CloudWatch** e então exporta relatórios para o [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) que mostram o que você pode fazer para reduzir seus custos na AWS.Tem uma efetividade de reduzir custos de até 25%.

## Billing & Costing Tools Overview

Ferramentas de custos de billing:

* Estimativa de custos na AWS
* TCO Calculator
* Simple Monthly Calculator
* Pricing Calculator
* Rastreando custos na AWS
* Billing Dashboard
* Cost Allocation Tags
* Cost and Usage Reports
* Cost Explorer
* Monitoramento e planejamento de custos
* Billing Alarms
* Budgets

## Estimating Costs in the Cloud - TCO Calculator & Pricing Calculator

**Simple Monthly Calculator** é um serviço em que você diz qual serviço da AWS você pretende usar e como você pretende usar e ele diz o quanto que isso irá te custar nos próximos 12 meses.Essa calculadora foi depreciada em 30 de Junho de 2020 e foi substituida pelo **AWS Pricing Calculator** que pode ser acessado em <https://calculator.aws/>

**AWS Total Cost of Ownership (TCO) Calculators** é usada para ajudar a reduzir custos fazendo cálculos no modelo pay-as-you-go.O **TCO Calculators** te permite estimar a economia de custos quando usando a AWS e provendo relatórios detalhados que podem ser usados em apresentações executivas.Compare custos de suas aplicações no formato on-premisse ou hosting tradicionais com AWS: Server, Storage, Network, etc..Para mais detalhes, acesse: <https://awstcocalculator.com/> OBS: o **TCO Calculator** já foi depreciado, contudo ainda pode ser cobrado no exame.

## Tracking Costs in the Cloud - Billing Dashboard, Cost Allocation Tags, Reports

Na visão do **Billing Dashboard** é possível ver os gastos no mês atual, você pode ver o gasto geral ou os gastos por produto.Também é possível, taggeando cada serviço(ex: instância, imagem, bucket, etc..) dividir os custos de cada produto pelo valor da tag, ex: colocar tags de centros de custos em instâncias permite que você veja quanto que cada centro de custo está gerando de gasto.Você pode editar essas tags usando o Tag Editor.

**AWS Cost and Usage Reports** é usado para relatórios detalhados. Contém o conjunto mais detalhado de custos e uso de dados incluindo metadados de serviços, pricins e reservas (Ex: [EC2](https://aws.amazon.com/pt/ec2/) reserved instances).**AWS Cost and Usage Report** consegue detalhar por dadods por categoria de serviços, por conta e por usuário [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) por hora e dia, da mesma forma que por tags que você tenha criado.Este relatório pode ser integrado e analisado por **Athena**, **Redshift** ou **QuickSight**.

**Cost Explorer** é um serviço que ajuda a visualizar, entender e gerenciar os custos da AWS ao longo do tempo. Cria relatórios personalizados para analisar custos e uso de dados, pode ser usado para fazer uma análise de custo total e através de todas as contas. Possui uma granularidade mensal e de hora. Você pode usar para escolher um Savings Plan melhor para diminuir seus custos.Pode também prever os custos nos próximos 12 meses baseado nos últimos usos.Também pode ter seus dados exportados para buckets [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html).

## Monitoring Costs in the Cloud - Billing Alarms & AWS Budgets

**Billings Alarms** disponíveis na **CloudWatch**, como já visto, são sistemas de métricas de billing que podem ser exportados para a **CloudWatch** e geram gráficos de custo.Só estão disponíveis na region us-east-1 mas contemplam os custos de todas as regions.

**AWS Budget** é um sistema de orçamento que te permite criar alarme para caso algum serviço(ou todos) que você esteja utilizando excedam o seu orçamento.Existem 3 tipos de orçamentos: Uso, Custo e reserva.Para Reserved Instances você pode fazer budget para track utilization. Suporta reservas para [EC2](https://aws.amazon.com/pt/ec2/), **ElastiCache**, **RDS** e **Redshift**.Suporta até 5 notificações SNS por budget.Pode filtrar por: Serviço, conta ligada, tag, opção de compra, tipo de instância, region, AZ, API, etc...Mesma opções do Cost Explorers.Os 2 primeiros Budgets são gratuitos, após isso você paga $0,02 por dia por budget.

## AWS Trusted Advisor

**Trusted Advisor** é um serviço que analisa a sua conta da AWS e faz recomendações relacionadas a: Otimização de custo, Performance, Segurança, Tolerância à Falha, Limites de Serviços.Existem 2 níveis de checagens:

* Disponível para todos os clientes - Checagem padrão com recomendações em que você pode receber emails semanalmente e notificações do console.
* Disponível apenas para clientes dos Planos de Suporte Business & Enterprise - Full **Trusted Advisor** - Habilita alarmes na **CloudWatch** quando chega nos limites, acesso programático utilizando APIs de suporte da AWS.

Exemplos de verificações do **Trusted Advisor**:

* Otimização de custos
* Instâncias [EC2](https://aws.amazon.com/pt/ec2/) subutilizadas, **ELBs** e**EBSs** ociosos.
* Otimização de Reserved instances e savings plans.
* Performance
* Otimização de instâncias [EC2](https://aws.amazon.com/pt/ec2/) muito utilizadas,**CloudFront**.
* Otimização de taxa de transferência de [EC2](https://aws.amazon.com/pt/ec2/) para[EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html), recomendações de registro de Alias.
* Segurança
* Verificação de utilização de MFA na conta root, rotação de chaves[IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html), Access Keys expostas.
* Verificação de buckets [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) expostos ao público,**SecurityGroups** com portas sem restrição.
* Tolerância à falha
* Idade de snapshots [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html), Balanceamento de AZs.
* **ASG** Multi-AZ, **RDS** Multi-AZ, configurações**ELB**, etc...
* Limites de Serviços

## Support Plans for AWS

A AWS possui 4 Planos de suporte:

* **AWS Basic Support Plan** - Gratuito
* **AWS Developer Support Plan** - Pago
* **AWS Business Support Plan** - Pago
* **AWS Enterprise Support Plan** - Pago

Recursos do plano de suporte **AWS Basic Support Plan**:**Customer Service and Communities**: Acesso 24/7 aos serviços do cliente, documentações, whitepappers e fóruns de suporte.**AWS Trusted Advisor**: Acesso às 7 verificações do **Trusted Advisor** padrões e guias para que você provisione seus recursos seguindo as melhores práticas e melhorar a sua performance e segurança.**AWS Personal Health Dashboard**: Uma visão personalizada da saúde dos serviços da AWS e alertas de quando seus recursos serão impactados.

Recursos do plano de suporte **AWS Developer Support Plan**:Todos os recursos do **Basic Support Plan** +Acesso direto ao suporte da AWS com possibilidade de abertura de ticket com a equipe de suporte.Contato direto com a equipe de suporte da AWS.Tempo de resposta Em caso de incidentes:

* Incidentes gerais: < 24 horas úteis
* Incidentes com impacto no sistema: < 12 horas úteis

Recursos do plano de suporte **AWS Business Support Plan**:Todos os recursos do **Basic Support Plan** +Útil para ser utilizado em trabalhos em ambiente produtivo.Trusted Advisor com acesso completo a todas as verificações + acesso à API.Telefone 24/7, email e acesso a chat com a equipe de Suporte da AWS.Tickets e contatos ilimitados.Acesso ao Infrastructure Event Management por um custo adicional.Tempo de resposta Em caso de incidentes:

* Incidente geral: < 24 horas úteis
* Sistema impactado: < 12 horas úteis
* Sistema PRODUTIVO impactado: < 4 horas
* Sistema PRODUTIVO fora do ar: < 1 hora

Recursos do plano de suporte **AWS Enterprise Support Plan** : Todos os recursos do **Business Support Plan** +Ideal para empresas grandes que possuem risco de grande impacto em ambiente produtivo.Acesso ao **Technical Account Manager (TAM)** Acesso ao **Concierge Support Team** - Para dar conselhos para utilização da conta e billing.Acesso ao Infrastrucutre Event management, Will-Architected and Operation Reviews.Tempo de resposta Em caso de incidentes:

* Incidente geral: < 24 horas úteis
* Sistema impactado: < 12 horas úteis
* Sistema PRODUTIVO impactado: < 4 horas
* Sistema PRODUTIVO fora do ar: < 1 hora
* Sistema PRODUTIVO CRÍTICO fora do ar: < 15 minutos

## Account Best Practices Summary

Resumo Boas práticas para conta pt 1:

* **Organizations**: Estrutura que junta várias contas root em uma organização com uma conta master.
* **SCP**: Serviço de controle de permissões usado em **Organizations** que restringe acesso das roots filhas.
* **AWS Control Tower**: Sistema que automatiza a criação de uma **Organization** criando múltiplas contas.
* **OU**: Grupo de contas dentro da **Organization**.
* Use Tag and Cost Allocation Tags: Sistema de tags para facilitar o controle de custo no **billing**.

Resumo Boas práticas para conta pt 2:

* **IAM Guideline**: Usar MFA, princípio do least-privilege, política e rotação de senha.
* **Config**: Para gravar todas as alterações de configurações e compliance ao longo do tiempo.
* **CloudFormation**: Para deployar stacks ao longo de contas e regions de forma automatizada.
* **Trusted Advisor**: Obter insights, e Suport Plans baseados na sua necessidade. Para isso envie logs para o [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) e **CloudWatch**.
* **CloudTrail**: API que grava logs de alterações feitas na conta.
Se a sua conta for comprometida de alguma forma: Mude a senha root, delete e rotacione todas as senhas e chaves, chame o suporte da AWS.

## Billing Summary

Resumo Billing e ferramentas de custo pt 1:

* Otimizador de computação: Recomenda configurações de recursos para reduzir custos.
* **TCO Calculator**: Calculadora DEPRECIADA para prever a economia de se migrar de on-premisse para AWS.
* **Simples Monthly Calculator/Pricing Calculator**: Custos dos serviços na AWS.(Simple Monthly DEPRECIADO)
* **Billing Dashboard**: Dashboard que mostra resumo de custos e resumo do free tier.
* **Cost Allocation Tags**: Taggeamento de recursos afim de criar relatórios de custos detalhados.

Resumo Billing e ferramentas de custo pt 2:

* **Cost and Usage Reports**: Relatório super detalhado de custos.
* **Cost Explorer**: Vê histórico de gastos com detalhe e faz previsão de 12 meses.
* **Billing Alarms**: Disponível apenas na us-east-1 gera gráfico de custo por serviço, analisa globalmente.
* **Budget**: Sistema de orçamento avançado que gera alerta baseado em limite de gastos.
* **Savings Plans**: Forma fácil de economizar baseado em uso de longo prazo dos recursos da AWS.

## Security Token Service (STS) Overview

**AWS Security Token Service (STS)** é o serviço de STS da AWS. Este serviço faz a autenticação e geração de token de short-term para o usuário.Casos de uso:

* Federação de identidade: Gerenciar as identidades dos usuários e prover tokens para que esses usuários possam acessar os recursos da AWS.
* Acesso para contas com [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) Roles.
* IAM Roles para [EC2](https://aws.amazon.com/pt/ec2/): Gerando credenciais temporárias para instâncias EC2 para acessarem recursos AWS.
Este recurso de STS funciona de forma transparente ao usuário e funciona como mais uma camada de segurança.

## Cognito Overview

**Amazon Cognito** é um serviço de gerenciamento de usuários, caso sua aplicação tenha acesso de usuários aos serviços, **Cognito** pode fazer o gerenciamento desses usuários quanto a acessos, autorização e autenticação.

## Directory Services Overview

**AWS Directory Services** é um serviço da AWS que se conecta com o Windows Active Directory, possui 3 modelos:

* AWS Managed Microsoft AD
* Você cria sua próprio AD na AWS e gerencia os usuário on-premisse,suporta MFA. Estabelece uma conexão de \trust\ entre on-premisse e AWS.
* AD Connector
* AD da AWS aciona o AD on-premmise como um proxy, usuários sãogerenciados on-premisse.
* Simple AD
* AD totalmente gerenciado na AWS, não pode ser conectado com on-premisse.

## Single Sign-On (SSO) Overview

**AWS Single Sign-On (SSO)** é o serviço que permite que um usuário [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) se logue em várias contas root ao mesmo tempo. O mesmo usuário [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) pode estar cadastrado em múltiplas contas root, e com SSO ele se loga uma vez que automaticamente estará autenticado em todas as contas em que ele têm acesso dentro da Organization. Suporta SAML 2.0 e pode ser integrado com Active Directory.

## Advanced Identity - Summary

Resumo Advanced Identity:

* [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html): Identity and Access Management, gerencia acessos e permissões de usuários da conta AWS.
* **Organizations**: Gerencia várias contas AWS.
* **Security Token Service (STS)**: Autentica e gera tokens temporários para acessos limitados a recursos da AWS.
* **Cognito**: Cria um BD de usuários para aplicações web e mobile.
* **Directory Services**: Integração de AD com Microsoft Active Directory na AWS.
* **Single Sign-On (SSO)**: Uma forma de um usuário [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) se logar uma vez para várias contas AWS em uma **Organization**.

## WorkSpaces Overview

**Amazon Workspaces** é um serviço de Desktop as a Service (DaaS) que cria desktops vituais de Windows e Linux. É uma ótima solução para eliminar a necessidade de gerenciar VDIs on-premisse.Facilmente escalável para milhares de usuários. Com dados seguros e integráveis com KMS. Serviço com modo pay-as-you-go com taxas mensais e por horas.

## AppStream 2.0 Overview

**Amazon AppStream 2.0** é um serviço de streaming de aplicações. Nele você disponibiliza um aplicativo na web, a AWS roda esse aplicativo em uma instância e você acessa esse aplicativo por um browser.A principal diferença entre **AppStream 2.0** e **Workspaces** é que **Workspaces** roda um SO inteiro com uma VDI, o **AppStream** roda apenas a aplicação que é acessada por um browser e você pode configurar a instância quanto a CPU, RAM e GPU.

## Sumerian Overview

**Amazon Sumerian** é um serviço que cria e roda aplicações VR, AR e 3D. Pode ser usado para criar animações e modelos 3D facilmente. Facilmente usável com templates e assets, sem necessidade de conhecimento em programação ou modelagem 3D, acessível de web-browsers ou em hardwares populares de AR/VR.Acesse para conhecer mais: <https://docs.aws.amazon.com/sumerian/latest/userguide/gettingstartedshowcase.html>

## IoT Core Overview

**AWS IoT Core** é um serviço que conecta devices IoT com a AWS, é um serviço serverless, seguro e escalável que suporta bilhões de devices e trilhões de mensagens. Suas aplicações podem se comunicar com os devices mesmo quando não estão conectadas.Pode se integrar com [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html), [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), **SageMaker**, etc...Você pode obter esses dados para analisar dados e tomar decisões.

## Elastic Transcoder Overview

**Amazon Elastic Transcoder** é um serviço de conversão de arquivos de mídia. Neste serviço você sobe arquivos de mídia para buckets no [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), adiciona esses arquivos no **Transcoder**, ele converterá o arquivo para o formato desejado e salvará o resultado em outro bucket no [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html).É um serviço fácil de usar, facilmente escalável, com bom custo-benefício, totalmente gerenciável, seguro e no formato pay-as-you-go.

## Device Farm Overview

**AWS Device Farm** é um serviço de device farm da AWS, nele você pode testar sua aplicação web ou mobile em devices REAIS(não emuladores) controlados pela AWS, esses devices ficam em locais remotods, os testes ocorrem em múltiplos devices e a execução é automatizada. Você pode interagir com os devices, eles geram relatórios, logs e screenshots dos testes feitos. Além disso é possível configurar features como GPS, idioma, wi-fi, bluetooth, etc...

## AWS Backup Overview

**AWS Backup** é o serviço de backup da AWS, nele você configura um período em que será feito um backup dos seus dados e ele automaticamente copia o conteúdo dos seus serviços(RDS, [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html), DynamoDB, EC2, EFS, FSx, Aurora) para dentro de um bucket no [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html).

## CloudEndure Overview

**Amazon CloudEndure** é um serviço de recuperação de desastre da AWS. Neste serviço os servidores on-premisse irão fazer replicações constantes e automáticas de dados(Oracle, MySQL, SQL Server, etc...) para a AWS em instâncias de baixo custo. Em um eventual desastre, o serviço será acionado e instâncias de alta performance da AWS serão acionadas no formato de failover assumindo o papel de produção em alguns minutos, ficando assim até que o ambiente on-premisse seja reestabelecido.

## AWS WhitePapers Well-Architected Framework

Well Architected Framework General Guiding PrinciplesPrincípios que são pontos chave para a importância da utilização de infra na nuvem.

* Parar de tentar adivinhar a capacidade da sua infra.
* Testar sistemas em escala produtiva.
* Automatizar para fazer a experimentação arquitetural mais fácil.
* Permitir uma arquitetura que possa evoluir, que não seja engessada.
* Guiar seu modelo de arquitetura baseado em DADOS.
* Melhorar através de testes(game days) - Fazer testes/simulações na sua infra afim de descobrir falhas e pontos de ruptura e corrigi-los.

Boas práticas de design na AWS:

* Escalabilidade - Usar escalabilidade vertical e horizontal.
* Recursos descartáveis: servidores devem ser descartáveis e facilmente configuráveis.
* Automação: Usar serviços servers, IaaS e Auto Scaling(elasticidade).
* Desacoplamento: Fugir de aplicações monolíticas pois são difíceis de manter e tendem a ser mais instáveis. Quebrar em aplicações menores faz com que erros se propagem menos.
* Pensar em SERVIÇOS, não em SERVIDORES: Não use apenas [EC2](https://aws.amazon.com/pt/ec2/), teoricamente quase tudo poderia ser resolvido em instâncias [EC2](https://aws.amazon.com/pt/ec2/), mas existem outros serviços que podem resolver a maior parte dos problemas de forma mais fácil, segura e barata, pense em usar: **RDS**, [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html), **EKS**, **ECS**, [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html), **DynamoDb**, **ElastiCache**, etc...

5 pilares do Well Achitected Framework:

1. Excelência Operacional
2. Segurança
3. Confiabilidade
4. Eficiência de performance
5. Otimização de custo

Esses pilares não são concorrentes e nem precisam ser balanceados, mas sim, trabalham em sinergia.

### 1º pilar: Operational Excellence

Pilares do Well Achitected Framework:1 - Excelência OperacionalA habilidade de rodar e monitorar sistemas para entregar valor de negócio e fazer melhoria continua em processos e procedimentos envolvidos.Princípios de Design:

* Peformar operações com código: Infrastructure as Code (IaC) - **CloudFormation**, Terraform são exemplo.
* Documentar: Automatizar a criação de documentos de cada construção.
* Fazer mudanças frequentes, pequenas e reversíveis: Em caso de falha, você poderá voltar ao estado anterior.
* Refinar procedimentos frequentemente: Fazer processo de PDCA em seus processo frequentemente e adequar equipe a isso.
* Antecipar falhas.
* Aprender com as falhas.

Pilares do Well Achitected F:1 - Excelência OperacionalOnde cada serviço se encaixa neste pilar? não cai no exam

* Preparação
* **AWS CloudFormation** - Criação de ambiente
* **AWS Config** - Validação de ambiente
* Operação
* **AWS CloudFormation** - Manutenção de ambiente
* **AWS Config** - Validação de ambiente
* **AWS CloudTrail** - Monitoramento de ambiente
* **Amazon CloudWatch** - Monitoramento de ambiente e dados
* **AWS X-Ray** - Debug de ambiente e dados
* Evolve
* **AWS CloudFormation** - Evolução de ambiente
* **AWS CodeBuild** - Criação de artefatos
* **AWS CodeCommit** - Versionamento de código
* **AWS CodeDeploy** - Evolução de instâncias
* **AWS CodePipeline** - Controle de esteira

### 2º pilar: Security

Pilares do Well Achitected Framework:2- Segurança pt 1A habilidade de proteger informações, sistemas e assets enquanto entrega valor ao negócios, faz isso através de estratégias de mitigação e gerenciamento de riscos.Princípios de design:

* Implementar um sistema de identidade forte: Centralizar o gerenciamento de privilégios e reduzir(ou mesmo eliminar) a existência de credenciais de longo prazo, seguindo princípio de least priviliege.
* Habilitar rastreabilidade: Integrar logs e métricas com sistemas que respondem automaticamente e realizam ações.
* Aplicar segurança em todas as camadas: Aplicar princípios de seguranças na rede, VPC, subnet, Load Balancer, instâncias, SOs e aplicações.

Pilares do Well Achitected Framework:2- Segurança pt 2

* Automatizar as boas práticas de segurança.
* Proteger dados em trânsito e em armazenamento: Utilizar criptografia, tokenização e controle de acesso.
* Manter pessoas longe dos dados: Reduzir ou eliminar a necessidade de contato direto ou manual com o processamento de dados.
* Se preparar para eventos de segurança: Realizar simulações de eventos de segurança com ferramentas que melhores a detecção de falhas, investigações e recuperação.

Pilares do Well Achitected Framewo:2- Segurança pt 1Onde cada serviço se encaixa neste pilar? não cai no exam

* Gerenciamento de Acessos e identidades
* [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) - Gerenciamento de usuários
* **AWS-STS** - Gerenciamento de credenciais limitadas etemporárias
* **MFA Tokens** - gerenciamento de tokens de MFA
* **AWS Organizations** - Agrupamento de contas
* Controles detetives
* **AWS Config** - Monitoramento do ambiente
* **AWS CloudTrail** - Rastreando ações
* **Amazon CloudWatch** - Rastreando ações e monitorando ambiente
* Proteção de infra
* **Amazon CloudFront** - Absorvendo impacto de ataques
* Amazon VPC - Segregando rede interna
* AWS Shield - Protegendo de ataques
* AWS WAF - Filtrando e protegendo aplicações
* Amazon Inspector - Buscando vulnerabilidades

Pilares do Well Achitected Framework:2- Segurança pt 2Onde cada serviço se encaixa neste pilar? não cai no exam

* Data Protection
* **KMS** - Gerenciamento de chaves
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) - Armazenamento de objetos
* **ELB** - Balanceamento
* [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) - Armazenamento de arquivos em bloco
* **RDS** - BD
* Resposta a incidentes
* [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) - Rotacionando credenciais
* **CloudFormation** - reformando ambiente
* **CloudWatch Events** - analisando causa rai

### 3º pilar: Reliability

Pilares do Well Achitected Framework:3- ConfiabilidadeHabilidade de um sistema se recuperar de uma interrupção na infra ou serviços, adquirir recursos computacionais para se adequar a demanda e as suas variações e mitigar problemas como falhas de configurações ou issues transientes na rede.Princípios de design:

* Testes para simular recuperações: Use simulações de diferentes falhas para recriar cenários de falhas que aconteceram antes.
* Se recupera automaticamente de uma falha: Antecipe e remedie falhas antes que elas ocorram.
* Escale horizontalmente e aumente a disponibilidade do ambiente: Aumente a quantida de recursos que seu sistema possui para que, caso haja uma falha, esta impacte pontos menores.
* Pare de tentar adivinhar sua capacidade: tenha um nível ótimo de uso da infra, sem sobrecarrega-la nem subutiliza-la. Use AutoScaling.
* Gerencie mudanças com automações: Use automações para fazer mudanças na infra.

Pilares do Well Achitected Fra:3- ConfiabilidadeOnde cada serviço se encaixa neste pilar? não cai no exam

* Fundações
* [IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) - Controle de acessos de usuários
* Amazon VPC - Limitando acessos da rede
* Service Limits - Definir limites para seus serviços
* AWS Trusted Advisor - Utilizar e seguir orientações do advisor
* Gerenciamento de Mudanças
* AWS Auto Scaling - automatizar mudanças na infra
* Amazon CloudWatch - monitorar mudanças na infra
* AWS CloudTrail - Monitorar alterações no estado do ambiente
* AWS Config - Verificar se o ambiente segue os compliances
* Gerenciamento de falhas
* Backups - faz backups dos ambientes
* AWS CloudFormation - manutenção do ambiente
* Amazon [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) - armazenamento de objetos de backup
* Amazon [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html) Glacier - arquivamento de objetos
* Amazon Route 53 - Redirecionamento de DNS em caso de falha em algumendpoint

### 4º pilar: Performance Efficiency

Pilares do Well Achitected Framework:4- Eficiência de PerformanceA habilidade de usar recursos computacionais de forma eficiente para atingir os requisitos de sistema, e manter essa eficiência a medida em que mudanças ocorram e a tecnologia evolua.Princípios de design:

* Democratizar tecnologias complicadas: Permitir que todas as pessoas possam ter conhecimento de tecnologias complexas como AWS.
* Estar disponível globalmente em minutos: Deploys fáceis em várias regions.
* Usar arquiteturas serverless: Evitar o trabalho de ter que gerenciar servidores.
* Experimentar coisas mais frequentemente: Testar e comparar coisas de forma mais fácil.
* Simpatia mecânica: Estar familiarizado com todos os serviços da AWS.

Pilares do Well Achitected Framework:4- Eficiência de PerformanceOnde cada serviço se encaixa neste pilar? não cai no exam

* Seleção
* **Auto Scaling**: Escalabilidade.
* [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html): Execução de procedimentos.
* [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html): Coleção de arquivos em bloco do ambiente.
* [S3](https://docs.aws.amazon.com/pt_br/AmazonS3/latest/userguide/Welcome.html): Coleção de objetos do ambiente.
* **RDS**: BD com dados do ambiente.
* Review
* **CloudFormation**: Manutenção do ambiente.
* Monitoring
* **CloudWatch**: Monitoramento do ambiente
* [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html): Execução de procedimentos caso necessário.
* Tradeoffs
* **RDS**: BDs
* **ElastiCache**: Cache de dados dentro das instâncias
* **Snowball**: Transferir dados para o dispositivo, processa-loseleva-los para a cloud após um tempo.
* **CloudFront**: Cache de dados nas edges

### 5º pilar: Cost Optimization

Pilares do Well Achitected Framework:5- Otimização de CustoPrincípios de design

* Adotar um modo de consumo: Pagar somente pelo que você usar.
* Medir a eficiência geral: Use **CloudWatch**
* Pare de gastar dinheiro em operações com data centers: AWS cuida da infra e te permite focar em projetos.
* Analise e atribua despesas: Faça uma identifica acurada do uso e custos de cada sistemas para que isso te ajude a medir o Return on Investiment (ROI), Para isso, use Tags
* Use serviços a níveis de aplicação e gerenciados afim de reduzir custos de propriedade: Desta forma você pode operar na nuvem com um custo menor por transação e mantendo a escalabilidade.

Pilares do Well Achitected Framework:5- Otimização de Custo pt 1Onde cada serviço se encaixa neste pilar? não cai no exam

* Conhecimento de gastos
* **Budgets** - Tenha conhecimento de como você está usandoseuorçamento.
* **Cost and Usage Reports** - Tenha relatórios detalhados dosgastos.
* **Cost Explorer** - Tenha relatórios de histórico de gastos
* **Reserved Instance Reporting** - Saiba se suas instânciasreservadas estão mesmo sendo usadas.
* Recustos com custo-beneficio
* **Spot Instance** - Use instâncias spot se possível
* **Reserved Instance** - Use instâncias reservadas, se possível
* **S3 Glacier** - faça o ciclo de arquivamento de dados noglacier

Pilares do Well Achitected Framework:5- Otimização de Custo pt 2Onde cada serviço se encaixa neste pilar? não cai no exam

* Pareando oferta e demanda
* **Auto scaling** - saiba escalar e desescalar de forma elásticacomASG
* [Lambda](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html) - Use Lambdas para facilitar a escalabilidade
* Otimizando ao longo do tempo
* **Trusted Advisor** - Use e siga as orientações do advisor
* **Cost and Usage Report** - Use os relatórios detalhados natomadade decisão
* **AWS News Blog** - Leia o blog da AWS para receberdicasde economia com a infra.

## AWS Well-Architected Tool

**AWS Well-Architected Tool** é uma ferramenta da AWS que te auxili a verificar se sua conta está alinhada com os 5 pilares do Well-Architected Framework.

1. Você seleciona o workload, responde as perguntas
2. Revê suas respostas em torno dos 5 pilares
3. Obtém dicas, vídeos, documentações, relatórios e vê os resultados em um dashboard
Para mais informações acesse: <https://console.aws.amazon.com/wellarchitected>

## AWS Ecosystem

Links úteis da AWS, todos gratuitos:

* AWS Blogs: <https://aws.amazon.com/blogs/aws/>
* AWS Forums (community): <https://forums.aws.amazon.com/index.jspa>
* AWS Whitepapers & Guides: <https://aws.amazon.com/whitepapers>
* AWS Quick Starts: <https://aws.amazon.com/quickstart/>
* AWS Solutions: <https://aws.amazon.com/solutions/>

**AWS Marketplace** é o local em que você pode comprar e vender objetos de/para vendedores independentes(terceiros), exemplo:

* **AMIs** customizadas(SO custom, firewall, solução técnica)
* Template CloudFormation
* Software as a Service
* Containers
Se você comprar algo no **Marketplace**, o lançamento da compra vai para o seu **billing**.Você também pode vender suas soluções no **Marketplace** para outras organizações.

**AWS Professional Services organization** é um time de experts pelo mundo que atuam junto com seu time e com alguém da **AWS Partner Network (APN)** para auxiliar a resolver problemas.**APN Technology Partners** são empresas que provêm hardware, conexão e softwares para a AWS e têm confiança desta.**APN Consulting Partners** são serviços de profissionais que auxiliam na construção da AWS e prestam consultoria para serviços.**APN Training Partners** são serviços de profissionais que te ajudam a aprender AWS.**AWS Competency Program**: **AWS Competencies** são "certificações" dadas a parceiros APNs que demonstraram conhecimento técnicos e auxiliaram clientes em resolver problemas em certas áreas.**AWS Navigate Program** é um programa que ajuda parceiros a se tornarem melhores parceiros.

Dos treinamentos OFICIAIS da AWS:**AWS Training**

* **AWS Digital (online)** e **Classroom Training** (em pessoa) - Pago e público
* **AWS Private Training** - Contratado para a organização
* **Training e Certification para o governo dos EUA**
* **Training e Certification para empresas**
* **AWS Academy** - Treinamento em universidades
Fora isso existem treinamentos não oficiais como os da Udemy(Stephane <3)

## State of Learning Checkpoint - AWS Certified Cloud Practitioner

Para informações sobre o exame acesse: <https://aws.amazon.com/pt/certification/certified-cloud-practitioner/Leia:https://d1.awsstatic.com/pt_BR/training-and-certification/docs-cloud-practitioner/AWS-Certified-Cloud-Practitioner_Exam-Guide.pdf>
Responda as perguntas de exemplo: <https://d1.awsstatic.com/training-and-certification/docs-cloud-practitioner/AWS-Certified-Cloud-Practitioner_Sample-Questions.pdf>
