
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
	
	*Exemplo: Normalmente utilizado em processos a onde as informações necessitam de maior controle sobre segurança, conformidade e privacidade, muito utilizado para empresas que trabalham com dados sensíveis ou governos.*
	
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
