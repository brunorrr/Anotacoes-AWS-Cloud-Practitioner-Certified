# EBS

## [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) Overview

A [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) é um volume de disco que você consegue conectar à sua instância [EC2](https://aws.amazon.com/pt/ec2/) A [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) se conecta à instância [EC2](https://aws.amazon.com/pt/ec2/) via rede, portanto possui latência.Pode ser conectada e desconectada facilmente como um pendriveSó pode estar conectada a uma AZ.Você paga pelo tamanho ALOCADOvocê pode aumentar o tamanho alocado com o tempo.

Você pode criar uma [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) e deixa-la desalocada de uma instância [EC2](https://aws.amazon.com/pt/ec2/).Se você quiser colocar o conteúdo de um volume [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) de uma AZ para outra, você pode criar uma snapshot dele e copia-la para a outra AZVocê pode marcar um volume [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) para ser excluído quando a instância [EC2](https://aws.amazon.com/pt/ec2/) vinculada a ele for eliminada.

## [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) Snapshots Overview

Snapshots podem ser utilizadas também para copiar volumes [EBS](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/UserGuide/AmazonEBS.html) para outras Regions