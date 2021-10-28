# AMI

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