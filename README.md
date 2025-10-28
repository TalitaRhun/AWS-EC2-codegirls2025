# AWS-EC2-codegirls2025
Anotações e alguns insights que foi adquirido sobre Elastic Compute Cloud - EC2 

Escolher a Instância certa não se trata apenas de selecionar um tipo aleatório e sim entender quais são as necessidades da aplicação e utilizar os recursos da nuvem de forma inteligente alcançando eficiência operacial e economizando custos, sempre com muita atenção à segurança.

// Anotações sobre como criar uma instância

1. Lançamento (Criação da Instância)
Hands On: No Console AWS, vá para o serviço EC2 > Instances > Escolher o nome da Instância 

✍️ NOTE: "EC2 (Elastic Compute Cloud) é o serviço de servidores virtuais (VMs) da AWS. 'Lançar' (Launch) é o termo usado para 'criar' uma nova instância."
✍️ NOTE: "Usar 'Tags' é uma boa prática essencial para organizar recursos na AWS, facilitando a identificação e o gerenciamento de custos."

2. Hands On: Em "Application and OS Images", selecione Amazon Linux 2 AMI.
   Insight: Recomendo uma AMI Amazon Linux 2 ou Ubuntu, e o tipo t2.micro para se manter no Nível Gratuito da AWS.

✍️ NOTE: "AMI (Amazon Machine Image) é o 'molde' do servidor. Contém o Sistema Operacional (SO) e pode vir com softwares pré-instalados. Escolhi o Amazon Linux 2 por ser otimizado para AWS e estar no Nível Gratuito (Free Tier)."
  
3. Hands On: Em "Instance type", selecione t2.micro.

✍️ NOTE: "Tipo de Instância define o hardware (vCPU, RAM, Rede). A t2.micro é a principal opção do Nível Gratuito, ideal para testes e estudos."  

4. Hands On: Em "Key pair (login)", clique em Create new key pair.

Dê um nome (ex: minha-chave-aws)

Tipo: RSA

Formato: .pem (para usar com SSH no Mac/Linux)

Clique em "Create" e salve o arquivo .pem em um local seguro.

✍️ NOTE: "O Par de Chaves é o método de autenticação SSH. A AWS armazena a chave pública na instância, e eu fico com a chave privada (arquivo .pem). Sem essa chave, eu não consigo acessar o servidor. Ela é minha 'senha', portanto deve ser guardada em um local seguro"

5. Hands On: Em "Network settings", clique em Edit.

Em "Security group name", coloque um nome (ex: meu-sg-ssh)

Em "Inbound security groups rules", você verá uma regra:

Tipo: SSH

Porta: 22

Fonte: Anywhere (0.0.0.0/0)

MUDE A FONTE (Source): Troque Anywhere para My IP. O AWS preencherá com o seu IP atual.

✍️ NOTE: "Security Group (SG) é um Firewall Virtual que controla o tráfego de entrada e saída da instância. É stateful (respostas são permitidas automaticamente)."
✍️ NOTE: "Regra de Segurança: Liberei a porta 22 (padrão do SSH) apenas para a origem My IP (meu computador). 
Insight de Segurança: Nunca deixar a porta 22 aberta para Anywhere (0.0.0.0/0) em produção, pois isso permite que qualquer pessoa na internet tente forçar o acesso ao meu servidor."

6. Hands On: Clique em Launch instance.
