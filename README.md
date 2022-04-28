# aws

# EC2 - Elastic Cloud Computing
## Recursos
- Cada máquina na AWS é conhecida como uma instância, e essa instância pode ter suas próprias imagens, conhecidas como AMIs (Amazon Machine Image) - como um Docker mesmo.
- Informações de logins são key-value typed - A AWS possui a chave pública e nós guardamos a chave privada em algum lugar seguro.

## Configuração básica
- Primeiro precisamos configurar os pares de chaves (key pairs). É um por região.
1. No painel do EC2, vá em key pairs
2. A chave deve ter um nome descritivo, de preferência o mesmo nome da instância EC2.
3. O tipo pode ser RSA ou ED25519 (pesquisar depois).
4. Use .pem para open source do OpenSSH
5. Salve em um lugar seguro.
6. Use ```chmod 400 my-key-pair.pem``` para dar permissão de leitura.

- Depois precisamos criar um grupo de segurança, que atua como um firewall para instâncias, controlando o tráfego de entrada e de saída. Esse grupo deve permitir que conectemos nosso IP usando SSH
1. Precisamos do endereço IPv4 do computador local.
2. No painel do EC2 vá para Security Group. Coloque um nome bacana e uma boa descrição.
3. Nas regras, coloque HTTP - 80 - Anywhere
4. HTTPS - 443 - Anywhere
5. SSH - 22 - My IP

## Tutorial EC2 AWS
- A instância é baseada no Amazon EBS - o que significa que o volume raiz é um volume do EBS.
- Cada EC2 pode estar em uma zona de disponibilidade, que é como um datacenter isolado.
- Ao iniciar uma intância, protegemo-as usando um par de chaves e criando um grupo de segurança, que atua como um firewall. Para se conectar à instância, devemos especificar a chave privada
### Executando uma instância
1. No painel da AWS selecione Launch Instance
2. Selecione o SO ou o AMI
2. Crie ou selecione uma key (uma instância sem chave é inconectável!!)
3. Selecione o security group
5. Selecione a VPC
Ao rodar, a instância recebe um nome DNS público (IPv4)
Para conectar na instância: ```ssh -i "nome.pem" ec2-user@ec2-ip-ip-region.compute.amazonaws.com```
Em sistemas já rodando, podemos adicionar as chaves através do Beanstalk
Podemos adicionar security groupd indo em actions > security > change security groups

## IAM - Identity and Access Manager
Com o IAM podemos controlar o acesso em toda a AWS. Podemos especificar quem consegue acessar qual serviço
