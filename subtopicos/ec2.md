# IAM

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