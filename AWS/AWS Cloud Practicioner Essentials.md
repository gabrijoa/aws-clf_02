
## 1.1 Modelo Cliente‑Servidor

>_O modelo cliente-servidor é um tipo de arquitetura de software em que um cliente faz um pedido de dados ou serviço e um servidor processa esse pedido, retornando a resposta adequada. Por exemplo, em uma biblioteca, o visitante (cliente) solicita um livro e o bibliotecário (servidor) entrega o livro requisitado. No ambiente virtual, ao buscar um livro em um site, o servidor recebe sua consulta e devolve o conteúdo solicitado para leitura._

![[client-server.png]]
*Figura 1: Na computação, um cliente pode ser um browser ou uma aplicação desktop; o servidor pode ser um serviço como AWS Lambda, um computador on‑premises ou uma instância EC2.*


## 1.2 Cloud Computing

>Computação em nuvem é o modelo de fornecimento on-demand de recursos de TI (compute, storage, rede etc.) pela internet, com cobrança pay-as-you-go. Você solicita o que precisa e a AWS provisiona instantaneamente, sem infraestrutura física sua.
#### características do Cloud Computing
- **Serviço On-demand**
	Provisão ou desprovimento de recursos virtuais de forma instantânea, você apenas paga pelo o que você usa no momento que esta utilizando.
-  **"Undifferentiated heavy lifting"**
	 infraestrutura comum (backup, patching, scaling) são gerenciadas pelo provedor, você não precisa focar na estrutura e sim no seu objetivo.
- **Modos de acesso**
	Você pode acessar via console pela web ou de forma programática, por APIS ou SDKS, sem necessidade de contrato ou vendas necessárias
- **"Pay-as-you-go"**
	Cobrança baseada no consumo real de recursos, eliminando gastos com capacidade ociosa.


#### Tipos de Deploy
- **Cloud-Based* (Cloud Pública)**
	Todos os recursos são provisionados pela Cloud, ou seja, nenhum tipo de infraestrutura é físico por parte do cliente, apenas da AWS. Você pode migrar aplicações já criadas ou criar novas e apenas utilizar serviços da AWS para provisionar.
	
	*Exemplo: rodando uma aplicação utilizando servidores virtuais (EC2), utilizando banco de dados (RDS) e conexão de Redes (ELB), todos serviços provisionados pela AWS.*
	
- **On-Premise** (Cloud privada)**
	Todos os recursos são provisionados pela sua própria infraestrutura, utilizando virtualização e ferramentas de gerenciamento de recursos.
	Toda a função de infraestrutura é sua como Orquestração, backup, troca de equipamento obsoleto, etc.
	
	*Exemplo: Normalmente utilizado em processos onde as informações necessitam de maior controle sobre segurança, conformidade e privacidade, muito utilizado para empresas que trabalham com dados sensíveis ou governos.*
	
- **Hybrid-based (Cloud Híbrida)**
	Integra nuvem pública e on-premises conforme necessidade; conecta workloads legados e serviços em nuvem.
	*Exemplo: processamento de dados em lote (AWS Batch) em cloud pública, transações principais sendo feitas on-premise.*

| Modelo      | Descrição                                                                                                          | Exemplo                                                                                                                 |
| ----------- | ------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| Cloud-based | toda a provisão de recursos e infraestrutura são providas pela Cloud, sem uso de infraestrutura física do cliente. | uma aplicação web utilizando (EC2, RDS e ELB)                                                                           |
| privada     | toda a provisão de recursos e infraestrutura são providas por um data center físico próprio.                       | Aplicações on-premises, sistemas que precisam de conformidade, sigilo de dados e segurança avançada.                    |
| hibrida     | utilização dos dois modelos.                                                                                       | Processamento de dados em lote (AWS BATCH) em cloud pública, transações principais da aplicação sendo feitas on-premise |

#### Benefícios da computação em nuvem
- **gasto variável ao invés de fixo**
	*você não precisa de investimento de capital inicial, apenas pague o que você consuma na nuvem.*
 - **economia em escala**
	*infraestrutura compartilhada faz o seu preço por unidade diminuir.*
- **elimine a incerteza**
	*escalonamento vertical (positivo ou negativo) em minutos para a atual necessidade.*
- **aumente a velocidade e agilidade**
	*Provisione novos recursos em minutos, acelerando desenvolvimento e testes*
- **sem necessidade de manutenção de infraestrutura**
	*Foque apenas na projeção de projetos ao invés de focar em infraestrutura do servidor.*
- **Alcance global em minutos**
	*Dimensione a sua aplicação em múltiplas regiões do mundo com apenas alguns cliques, focando em baixa latencia e melhor experiência de usuário.*

| Benefício                      | Descrição                                                                               |
| ------------------------------ | --------------------------------------------------------------------------------------- |
| **Despesa variável vs. fixa**  | Sem grande CAPEX inicial; paga apenas pelo consumo de recursos.                         |
| Economias de escala            | Infraestrutura compartilhada reduz o custo por unidade                                  |
| eliminação de incerteza        | Escala para cima ou para baixo em minutos, ajustando-se à demanda real                  |
| Velocidade e agilidade         | Provisionamento em minutos acelera desenvolvimento, testes e exeperimentação            |
| Sem manutenção de data centers | Provedor cuida de Hardware e infraestrutura.                                            |
| alcance global em minutos      | Deploy em múltiplas regiões com poucos cliques, reduzindo latência para usuários finais |

## 2.1 EC2 (Elastic Compute Cloud)

>_Amazon Elastic Compute Cloud (EC2) fornece capacidade de computação de forma segura e redimensionável, visando substituir servidores físicos, você pode criar instâncias de forma manual ou programática, pagando apenas pelo tempo de execução._

#### benefícios do EC2

| Benefícios     | Explicação                                                                                     |
| -------------- | ---------------------------------------------------------------------------------------------- |
| Flexibilidade  | Você pode iniciar, destruir e redimensionar instâncias conforme necessário.                    |
| Custo-efetivo  | Pague apenas pelas instâncias que está utilizando.                                             |
| Agilidade      | Você pode lançar uma instância EC2 em minutos, comparando a semanas com servidores físicos.    |
| Controle total | Controle sobre sistema operacional, software instalado, redes e especificações computacionais. |
| Segurança      | instâncias isoladas por virtualização (multitenancy + hypervisor gerenciado pela AWS.)         |

#### Comparação: On-premises vs EC2


| Critério                 | On-premises               | Amazon EC2             |
| ------------------------ | ------------------------- | ---------------------- |
| Tempo de provisionamento | semanas/Meses             | Minutos                |
| Investimento inicial     | Alto (compra de hardware) | Nenhum (pay-as-you-go) |
| Escalabilidade           | Limitada ao hardware      | Sob demanda            |
| Flexibilidade            | Baixa                     | Alta                   |
| Custo de Manutenção      | Alto                      | AWS gerencia por você  |

#### Casos de uso 
- Execute aplicações empresariais e nativas de nuvem
	A AWS fornece infraestrura segura, confiável e de alta performance para atender as necessidades do cliente
- workloads;
	A AWS fornece computação para os mais variados tipos de implementações para atividades como ML, processamento em batch, testes, desenvolvimento e etc.
- Desenvolver para plataformas Apple
	Para desenvolver aplicações para Infraestrutura Apple, você precisa desenvolver em Ambientes macOS, com o EC2, você pode gerencias instâncias Apple para desenvolver, testar, executar e assinar sobre a sua demanda.

#### Como funciona o EC2
1. Launch
	   Você faz a configuração de hardware (OS, memoria RAM ou HD, Processador), configura formas de acesso (SSH, API, SDKS), e seu tráfego de rede (define se irá ser publico ou privado, com configurações de blocos de IP).
2. Connect
	Você se conecta com a aplicação da forma que foi configurada.
3. Use
	Você disponibiliza como sua aplicação irá ser fornecida para o determinado uso da sua aplicação/Workload.

![[ec2-diagram.png]]

>*a configuração da EC2 pode ser feita junto com outros serviços da nuvem AWS, desde a implementação programática, escalabilidade, definição de custos e conexão com serviços de banco de dados, teste, escalabilidade, análise de dados, criptografia e etc.*
#### Tipos de instâncias EC2

- **General purpose (uso geral)**
	Equilíbrio entre CPU, memória e rede. Bom para workloads variados e simplificados (pequenos banco de dados e aplicações de uso geral)
- **Compute optimized (computação otimizada)**
	Instâncias com CPU de alta performance, ideais para workloads intensivos em processamento, como servidores web de alta carga, batch processing e servidores de jogos dedicados.
- **Memory optimized** (memória RAM otimizada)
	Possui bastante memória ram; ideal para grandes conjuntos de dados na memória (bancos in-memory, processamento em tempo real).
	Ideal para aplicações que exigem dados pré-carregados na memória, garantindo baixa latência e alta performance.”
	
 - **Accelerated computing** (computação acelerada)
	 Utiliza aceleração de hardware com GPUs e FPGA para performar atividades específicas, accelerated computing é utilizada para renderização 3D, machine learning e processamento de vidoeos.
- **Storage optimized** (armazenamento otimizado)
	Alta performance de I/O de disco (IOPS elevado); indicado para data warehouses, OLTP de alta frequência, sistema de arquivos distribuídos
	em computação IOPS significa **input output operations per second**.
	pode se assimilar a entrada e saida de dados em grande escala em uma aplicação como necessidade de uso do Storage optimized.

##### Casos de uso de tipo de EC2

| **Tipo de instncia (EC2)** | Foco      | casos de uso                                                                                                                                                                                                                                                                                                                                           |
| -------------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **General purpose**        | uso geral | hospedar servidores web e APIs de uso geral, onde CPU, memória e rede têm demandas equilibradas;**<br><br>**Executar aplicações de back-end para microserviços ou ambientes de desenvolvimento/teste;**<br><br>**Bancos de dados de pequeno a médio porte, como MySQL ou PostgreSQL de uso moderado**<br>                                              |
| **Compute optimized**      | CPU       | Processamento de grandes volumes de transações em batch, como cobrança de cartões ou geração de relatórios financeiros noturnos;<br><br>Servidores de jogos online que exigem alta velocidade (CPU) para física e lógica do jogo;<br><br>Simulações científicas e de engenharia (HPC), como modelagem de fluidos ou análises genômicas.                |
| **Memory optimized**       | RAM       | Bancos de dados in-memory, como Redis ou SAP HANA, que carregam todo o dataset na RAM para latência muito baixa;<br><br>Processamento em tempo real de streams de dados grandes, por exemplo análise em memória de logs, telemetria ou dados de IoT;<br><br>Caches de alta capacidade para acelerar aplicações web de grande escal;                    |
| **Accelerated computing**  | GPU       | Treinamento e inferência de modelos de machine learning usando GPU (TensorFlow, PyTorch);<br><br>Renderização de gráficos 3D, edição e transcodificação de vídeo em tempo real;<br><br>Workloads de computação científica que se beneficiam de cálculos em ponto flutuante acelerados por FPGA;                                                        |
| **Storage Optimized**      | HD (I/O)  | Data warehouses como amazon Redshift ou sistemas de BI que executam consultas analíticas intensivas em I/O;<br><br>Sistemas de arquivos distribuídos e Big Data(Hadoop, Spark) que fazem leitura e escrita intensiva em disco local;<br><br>Aplicações OLTP de alta frequência, como plataformas de e-commerce com milhares de transações por segundo; |

#### Amazon EC2 Pricing

>o serviço Amazon EC2 oferece várias opções de preços para diferentes casos de uso. A cobrança é feita apenas pelo tempo de computação utilizado. 

#### Modelos de precificação

| Tipo de Instância               | Descrição                                                       | Contrato / Compromisso                                         | Economia (%)        | Casos de Uso Recomendados                                        | Peculiaridades / Observações                                                                                               |
| ------------------------------- | --------------------------------------------------------------- | -------------------------------------------------------------- | ------------------- | ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **On-Demand**                   | Pague por hora ou segundo de uso.                               | Nenhum. Uso sob demanda.                                       | Nenhuma             | Workloads imprevisíveis, desenvolvimento, testes rápidos.        | Sem custos antecipados. Ideal para começar. Sem reserva de capacidade.                                                     |
| **Reserved (Standard)**         | Desconto por uso contínuo de instâncias específicas.            | 1 ou 3 anos. Escolha exata de tipo, tamanho, OS, tenancy.      | Até 75%             | Aplicações com carga estável e previsível por longo prazo.       | Pode reservar capacidade em uma AZ. Desconto maior que Savings Plan.                                                       |
| **Reserved (Convertible)**      | Igual ao Standard, mas com flexibilidade para trocar tipo e AZ. | 1 ou 3 anos. Compromisso de uso, mas com mais flexibilidade.   | Menor que Standard  | Workloads estáveis, mas com incertezas quanto a instância.       | Permite trocar tipo de instância, OS, AZ. Menor economia devido à flexibilidade.                                           |
| **Savings Plan (EC2 Instance)** | Compromisso com gasto por hora em uma família de instância.     | 1 ou 3 anos. Valor ($/h) fixo em família e região.             | Até 72%             | Quando há flexibilidade em tipo/tamanho/OS da instância.         | Não reserva capacidade. Não precisa escolher instância exata. Aplica-se à família, região. Também cobre Fargate e Lambda.  |
| **Spot**                        | Usa capacidade ociosa da AWS com grande desconto.               | Nenhum. Instâncias podem ser interrompidas a qualquer momento. | Até 90%             | Processamento em lote, jobs paralelizáveis, testes não críticos. | Pode ser interrompida com 2 min de aviso. Lançamento depende da disponibilidade. Ideal para workloads tolerantes a falhas. |
| **Dedicated Hosts**             | Servidor físico reservado só para seu uso.                      | Pode ser On-Demand ou reserva.                                 | Nenhuma ou variável | Requisitos de conformidade/licenciamento (por socket/core).      | Mais caro. Permite usar licenças existentes. Total isolamento de hardware.                                                 |

#### Escalabilidade Amazon EC2

>Escalabilidade permite aumentar ou diminuir recursos computacionais conforme a demanda da aplicação.
>

	Problema do Data Center On-Premises:
	Comprar hardware baseado na média de uso = problema nos picos
	Comprar baseado no pico de uso = recursos ociosos
	utilização média < 10% em muitos data centers por medo de indisponibilidade

Com a AWS você provisiona os recursos necessários em tempo real e conforme a demanda.

- Clientes satisfeitos (serviço disponível).
- Equipe financeira satisfeita (uso otimizado de recursos).

#### EC2 Auto Scaling  

Serviço que ajusta automaticamente a quantidade de instâncias EC2 com base em métricas de uso.
Você cria Grupos baseados na necessidade da aplicação, desenhando um mínimo, desejável e máximo

| Tipo de Escalonamento | Descrição                                                          |
| --------------------- | ------------------------------------------------------------------ |
| Dyanmic Scaling       | Adiciona ou remove instâncias em resposta à demanda em tempo real. |
| Predictive Scaling    | Ajusta instâncias com base em previsões de demanda futuras.        |



##### Configurações de um Auto Scaling Group

| Configuração     | Descrição                                                                      |
| ---------------- | ------------------------------------------------------------------------------ |
| Minimum Capacity | Número mínimo de instâncias que sempre estarão ativas.                         |
| Desired Capacity | Número ideal de instâncias que você quer manter (pode ser maior que o mínimo). |
| Maxium Capacity  | Número máximo de instâncias que o grupo pode escalar.                          |
 **Exemplo**:
- Mínimo: 1 instância    
- Desejado: 2 instâncias
- Máximo: 4 instâncias  
    Resultado: sempre pelo menos 1, tenta manter 2, nunca passa de 4.
    
![[ec2-Auto-Scaling-Group.png]]
***O EC2 AUTO SCALING APENAS ESCALA DE FORMA HORIZONTAL***
Benefícios do EC2 Auto Scaling
- Escalonamento automático sob demanda
- Paga somente pelas instâncias em uso
- Alta disponibilidade por redundância
- Redução de custos com instâncias ociosas
- Baseado em métricas (CPU, uso de memória, requisições, etc.)

#### Elastic Load Balacing (ELB)

>**Elastic Load Balancing (ELB)** é um serviço gerenciado da AWS que **distribui automaticamente o tráfego de entrada entre múltiplos recursos**, como instâncias EC2. Ele atua como **ponto único de entrada** para aplicações que utilizam Auto Scaling, garantindo **alta disponibilidade, desempenho e escalabilidade automática**.

![[ELB.png]]
### Como funciona com Auto Scaling
- Quando novas instâncias EC2 entram em operação, o Auto Scaling as registra no ELB.
- Quando instâncias são removidas:    
    - O ELB primeiro **"drena"** as conexões ativas (espera as requisições atuais finalizarem).
    - Só depois a instância é terminada → sem interrupção para o cliente.
### Benefícios do ELB
- Alta disponibilidade automática.
- Distribuição eficiente de carga.
- Escalabilidade automática.
- Integração com Auto Scaling.
- Suporte a arquitetura desacoplada.


##### Messaging and Queueing (Mensageria e Fila)

##### **TIGHLY COUPLE ARCHITECTURE VS LOOSELY COUPLED ARCHITECTURE**

| Componentes se comunicam diretamente.          | Comunicação via intermediários (ex: filas).           |
| ---------------------------------------------- | ----------------------------------------------------- |
| Se um falha, afeta outros → falhas em cascata. | Se um componente falha, os demais continuam operando. |
|                                                |                                                       |
com Loosely coupled architecture a Resiliência e escalabilidade são aumentadas.
#### Amazon SQS (Simple Queue Service)

- **Modelo**: fila (queue).    
- Aplicações enviam mensagens para a fila e processam depois.
- **Payload**: conteúdo da mensagem (ex: nome, pedido, horário).
- **Vantagens**:
    - Desacoplamento.
    - Alta escalabilidade automática.
    - Alta disponibilidade.
    - AWS gerencia a infraestrutura da fila.
- **Útil para**: Processamento assíncrono, buffers entre sistemas.
#### Amazon SNS (Simple Notification Service)

- **Modelo**: publish/subscribe (pub/sub).
- Mensagens são publicadas em **tópicos**.
- Os tópicos entregam mensagens para múltiplos **assinantes**:
    - SQS, Lambda, Webhooks, SMS, email, push mobile etc.
- **Fan-out**: uma mensagem → múltiplos destinos.

#### AWS Compute Options


- #### 1. EC2
- #### 2. Serverless Computing
	Execução de código sem se preocupar com provisionamento de infraestrutura de servidores.

| característica            | Server-based (EC2)    | Serverless ex:lambda   |
| ------------------------- | --------------------- | ---------------------- |
| Provisionamento           | Manual                | Automático             |
| Gerenciamento de Servidor | Necessário            | Não Necessário         |
| Escalabilidade            | Deve ser configurada  | Automática             |
| Pagamento                 | uptime das instâncias | tempo real de execução |
- Benefícios
1. Foco em desenvolver produtos e features.
2. Escala automática
3. Pagamento baseado apenas no tempo de execução do código.

#### 3. AWS Lambda
>Serviço serverless para execução de código sem gerenciar servidores.

![[lambda.png]]


- Exemplo de uso :
1. Redimensionar automaticamente imagens enviadas para o S3.
- Limitação:
1. Cada execução deve durar até no máximo 15 minutos.

#### 3. Containers

> Forma padronizada de empacotar código, dependências e configurações em um único objeto.

- Benefícios:
1. Consistência entre ambientes (dev/test/prod)
2. Facilita segurança, confiabilidade e escalabilidade

- Exemplo:
1. O desenvolvedor usa um container para garantir que seu app rode extamente igual no laptop dele e no ambiente de produção

##### 3.1 Conatiner Orchestration Services

| Serviço                                 | Descrição                                                                                   |
| --------------------------------------- | ------------------------------------------------------------------------------------------- |
| Amazon ECS (Elastic Container Service)  | Gerenciamento de containers Docker, altamente escalável e com integração nativa à AWS.      |
| Amazon EKS (Elastic Kubernetes Service) | Execução de aplicações containerizadas usando kubernetes, com gestão automatizada pela AWS. |


#### 3.2 AWS Fargate
- O que é:
 1. Um motor serverless para containers, compatível com ECS e EKS.
 - Vantagens
 1. Sem provisionamento de instâncias EC2.
 2. Infraestrutura gerenciada pela AWS.
 3. Pagamento apenas pelos recursos consumidos.


#### 4. Quando usar cada?


| Necessidade                                                        | Melhor serviço |
| ------------------------------------------------------------------ | -------------- |
| Acesso total ao SO                                                 | EC2            |
| Executar funções pequenas/event-driven, sem se preocupar com infra | Lambda         |
| Rodar containers Docker                                            | ECS ou EKS     |
| Rodar containers sem gerenciar EC2                                 | Fargate        |
# Resumo

- Se precisa **gerenciar servidores**, use **EC2**.
- Se quer apenas rodar **funções sob demanda**, use **Lambda**.
- Se usa **Docker** e precisa de orquestração, escolha **ECS** (mais simples) ou **EKS** (Kubernetes).
- Se quer containers sem se preocupar com EC2, vá de **Fargate**.

## 

**Additional resources**

To learn more about the concepts that were explored in Module 2, review these resources.

- [Compute on AWS](https://aws.amazon.com/products/compute)
- [AWS Compute Blog](https://aws.amazon.com/blogs/compute/)
- [AWS Compute Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/compute-services.html)
[Hands-On Tutorials: Compute](https://aws.amazon.com/getting-started/hands-on/?awsf.getting-started-category=category%23compute&awsf.getting-started-content-type=content-type%23hands-on)
- [Category Deep Dive: Serverless](https://aws.amazon.com/getting-started/deep-dive-serverless/)
- [AWS Customer Stories: Serverless](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc%7Cproduct%23api-gateway%7Cproduct%23cloudfront%7Cproduct%23route53%7Cproduct%23directconnect%7Cproduct%23elb&awsf.customer-references-category=category%23serverless)
- [Amazon EC2 Reserved Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-reserved-instances.html)
- [How Savings Plans apply to usage](https://docs.aws.amazon.com/savingsplans/latest/userguide/sp-applying.html)

# 3. AWS Global Infrastructure: Regions and Availability Zones

#### 3.1 Introdução 
> Antes da AWS, empresas precisavam operar suas aplicações em data centers próprios. Home, a AWS oferece a possibilidade de hospedar aplicações em data centers que elas não precisam construir ou manter.


Tradicionalmente, empresas teriam que:
- Construir um segundo data center (muito caro)
- Ou apenas armazenar backups e esperar que o desastre nunca aconteça (o que não é um bom plano de negócios).

AWS resolve isso com o conceito de Regiões e Zonas de Disponibilidade (Availability Zones).

#### 3.2 O que é uma Região AWS?
Região é um conjunto de múltiplos data centers físicos em uma mesma área geográfica.
- Cada região é:
1. Isolada das outras.
2. Conectada através de uma rede de fibra de alta velocidade controlada pela AWS.

Nenhum dado sai de uma região sem autorização explícita, o **compliance local** é respeitado, como por exemplo os dados em Frankfurt não saem da Alemanha ao menos que seja autorizado.

Exemplos de região:
- Paris
- Tóquio
- São Paulo
- Dublin
- Ohio

#### 3.3 como escolher uma Região
Existe **quatro fatores principais** para escolher em qual Região rodar seus serviços:

| Fator                       | Explicação                                                                   | Exemplo                                                                                 |
| --------------------------- | ---------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Compliance                  | Restrições legais que exigem que os dados fiquem dentro de certas fronteiras | Se precisa manter dados no Reino Unido, escolha a região de Londres.                    |
| Proximidade                 | Quanto mais próxima a Região dos seus usuários, menor a latência             | Se seus usuários estão em Singapura, prefira a Região de Singapura.                     |
| Disponibilidade de Serviços | Nem todas as Regiões têm todos os serviços AWS disponíveis.                  | Ex: Amazon Braket (computação quântica) só é disponível em algumas Regiões.             |
| Preço                       | custo de operar varia entre Regiões                                          | São Paulo é mais caro (~50% a mais) que Oregon devido à estrutura tributária do Brasil. |

#### 3.4 Availability Zone - AZ (Zona de Disponibilidade) 
AZ são uma unidade ou grupos de data centers em uma Região, suas características são:
- Energia elétrica redundante
- Rede e conectividade redundantes
- Cada Região AWS é composta de múltiplas AZs
##### Design de Resiliência
- AZs são separadas por dezenas de quilômetros, o suficiente para:
- reduzir risco de falhas simultâneas.
-  Garantir baixa latência (milissegundos) entre AZs.
##### **A AWS RECOMENDA RODAR SUA APLICAÇÃO EM PELO MENOS DUAS AZS.**

![[AZ.png]]

## 3.5 Exemplo prático: EC2 em múltiplas AZs

### Cenário 1: Instância em uma única AZ

- Você lança uma instância EC2 em `us-west-1a` (Norte da Califórnia).
    
- Se `us-west-1a` falhar → **perda da instância**.
    

### Cenário 2: Instâncias em múltiplas AZs

- Você lança instâncias EC2 em `us-west-1a` **e** `us-west-1b`.
- Se uma AZ falhar, a outra mantém a aplicação funcionando.
- Com o **Auto Scaling**, é possível **substituir rapidamente** as instâncias perdidas.

#### Serviços Regionais X Serviços Locais
- muitos serviços AWS são regionais por padrão:
	Ex: Elastic Load Balancer (ELB) funciona automaticamente em múltiplas AZs sem necessidade de configuração adicional
- Serviços regionais são altamente disponiveis por design.


#### RECAP 


| conceito                     | definição                                                 |
| ---------------------------- | --------------------------------------------------------- |
| Região                       | Conjunto de AZs em uma área geográfica                    |
| AZ (Availability Zone)       | Um ou mais data center fisicamente separados mas próximos |
| Fatores para escolher região | Compliance, Proximidade, Serviços disponíveis, preço      |
| Melhor prática               | Executar aplicações em pelo menos duas AZs                |

#### Caso de uso real
Empresa multinacional de e-commerce:
- Sede em Washington D.C
- Muitos clientes em singapura
- solução:
	- Servidores administrativos na Região Norte de Virgínia.
	- Aplicações para clientes rodando na Região de Singapura para reduzir a latência.


![[az step.png]]![[az step 2.png]]![[az step 3.png]]

- [AWS global infrastructure](https://aws.amazon.com/about-aws/global-infrastructure)
- [Regions and Availability Zones](https://aws.amazon.com/about-aws/global-infrastructure/regions_az)

#### Edge Locations


##### Content Delivery Networks (CDNs)
> CDN é uma rede de entrega de conteúdo, é uma rede de servidores interconectados que aceleram o carregamento de uma pagina da Web para plicações com dados pesados. 
> seu propósito principal é reduzir a latência ou o atraso na comunicação criados por um projeto de rede. O trafego de comunicação entre servidores e clientes precisam viajar entre longas distâncias físicas.

| Conceito | Explicação                                                                                         |
| -------- | -------------------------------------------------------------------------------------------------- |
| CDN      | Rede de entrega de conteudo que copia dados mais próximos dos clientes                             |
| AWS CDN  | Amazon CloudFront                                                                                  |
| Função   | Entrega de dados, vídeos, aplicações e APIs com baixa latência e alta velocidade de transferência. |

![[cdn map.png]]

#### Edge Locations
- Edge locations: Sites que armazenam cópias em cache dos seus conteúdos próximos dos usuários.
- separados das Regiões AWS.
- além do CloudFront, Edge Locations também executam:
- Amazon Route 53: Serviço de DNS para redirecionar clientes de forma rápida e configurável.

#### AWS dentro do seu Data Center: AWS Outposts
> O AWS Outposts é uma familia de soluções totalmente gerenciadas que fornecem infraestrutura e serviços da AWS para praticamente qualquer local da borda ou on-premises para uma experiência híbrida verdadeiramente consistente. As soluções do Outposts permitem que os clientes estendam e executem serviços da AWS nativos on-premises.
> você pode executar alguns produtos da AWS localmente e se conectar a uma ampla gama de serviços disponíveis na região local da AWS

| Serviço      | Descrição                                                                            |
| ------------ | ------------------------------------------------------------------------------------ |
| AWS Outposts | instalação de uma "mini-Região AWS" dentro da sua própria infraestrutura.            |
| Operação     | Propriedade e gerenciamento pela AWS, mas localizada fisicamente no seu prédio.      |
| Uso          | Casos onde regulamentos ou necessidades específicas impedem uso de Regiões públicas. |
- **Regions**: Áreas geográficas isoladas, com todos os serviços necessários.
- **Availability Zones (AZs)**: Permitem alta disponibilidade e recuperação de desastres através de edifícios fisicamente separados (vários quilômetros de distância).
- **Edge Locations**: Posições distribuídas mundialmente para cache e aceleração de conteúdos com Amazon CloudFront.


#### PROVISIONAMENTO DE RECURSOS NA AWS

> Tudo na AWS é baseado em chamadas de api. Isso significa que qualquer ação é feita por meio de requisições pré-definidas a APIs da AWS


| Ferramenta             | Descrição                                                           | Características                                                                                                                                                                                                                                                                                                                                                 |
| ---------------------- | ------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AWS Management Console | Interface web visual para acessar e gerenciar serviços AWS.         | Interface gráfica web;<br>ótima para iniciantes e ambientes de teste;<br>Inclui assistentes e fluxos automáticos;<br>Também está disponível via aplicativo mobile(visualizar alarmes, billing);<br><br>**NÃO RECOMENDADO EM AMBIENTES DE PRODUÇÃO, POIS É MANUAL E SUJEITO A ERROS HUMANOS.**                                                                   |
| AWS CLI                | interface de linha de comando para executar scripts e comandos AWS. | permite automatizar tarefas via comandos de terminal;<br>Disponível para Windows, macOS e Linux;<br>Ideal para scriptar e repetir ações com consistência;<br><br>exemplo de uso:<br>`aws ec2 run-instances --image-id ami-123456 --count 1 --instance-type t2.micro`<br><br>**Vantagens:** Reduz erros manuais, permite agendamentos, integração com pipelines. |
| SDKs                   | APIs específicas por linguagem de programação                       | APIs específicas para linguagem como: Python, Java, C++, .NET e outras;<br>Útil para integrar serviços AWS em aplicações existentes;<br>permite evitar chamadas de API de baixo nível;<br><br>***AWS oferece documentação e exemplos de códigos para cada SDK.***                                                                                               |
| AWS CloudFormation     | infraestrutura como código (IaC), em JSON/YAML.                     |                                                                                                                                                                                                                                                                                                                                                                 |
| AWS Elastic Beanstalk  | Gerenciamento simplificado de ambientes baseados em EC2.            | Plataforma que orquestra recursos EC2 automaticamente;<br>Você fornece o código e as configurações - a AWS cuida do resto;<br>tarefas como: Ajuste de capacidade, Load balacing, Auto scaling, monitoramento de saúde;<br><br>***Menos foco na infraestrutura, mais foco no código e negócio***                                                                 |

