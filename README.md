# Análise Exploratória de Dados Logística da Loggi


![alt text](https://github.com/kedimo-cd/Analise_Logistica_da_loggi/blob/main/img/Loggi.png)
*******
# 1. O que é a Loggi

A Loggi é uma startup unicórnio brasileira de tecnologia focada em logística. A Loggi começou entregando apenas documentos entre 2013 e 2014. Dois anos depois, entrou no segmento de e-commerce. E, desde 2017, tem atuado nas entregas de alimentos também.


# 2. O Problema de negócio

 A Loggi afim de trazer melhorias na qualidade de entrega do serviço oferecido na região de Brasília – Distrito Federal, busca por soluções para que as entregas sejam feitas de maneiras mais rápidas e agis, além disso, garantir que o serviço esteja distribuído de forma uniforme pelas regiões estabelecidas, evitando assim, sobrecarga e consequentemente melhorando o fluxo de trabalho.
 
# 3. Estratégia de Solução
 Como estratégia, adotei a prática do método CRISP-DM.Embora iremos usar somente as primeiras etapas, este método é voltado para a resolução rápida pro problema, onde nos primeiros ciclos já é possível gerar valor para o time de negócio. 
 A imagem abaixo ilustra como funciona:
![alt text](https://github.com/kedimo-cd/Analise_Logistica_da_loggi/blob/main/img/CRISP-DM.png)

# 4. Coleta de Dados

O Loggi Benchmark for Urban Deliveries (BUD) é um repositório do GitHub ([link](https://github.com/loggi/loggibud)) com dados e códigos para problemas típicos que empresas de logística enfrentam: otimização das rotas de entrega, alocação de entregas nos veículos da frota com capacidade limitada, etc. Os dados são sintetizados de fontes públicas (IBGE, IPEA, etc.) e são representativos dos desafios que a startup enfrenta no dia a dia, especialmente com relação a sua escala.
Os dados foram disponibilizados em um formato json com uma lista de instâncias de entregas. Cada instância representa um conjunto de entregas que devem ser realizadas pelos veículos do hub (centro de distribuição). OS dados foram transformados e processados em um formato DataFrame 
 
| Atributos | Descrição |
| ------ | ------- |
| name | Identificador do hub |
| region | Região onde o hub esta situado |
| lng | Valor coordenadas geograficas de localização|
| lat | Valor coordenadas geograficas de localização |
| Vehicle_capacity | Capacitade total de armazenamento de carga |
| Deliveries | Id de entregas dos hubs |

# 5. Data  Wrangling

Seguindo a metodologia do CRIP-DM, a etapa a seguir é a limpeza e transformação dos dados. Nesta etapa foi realizado o seguinte:

-**_Tratamento dos dados nested_**: Os dados foram normalizados com uma operação conhecida como explode ou explosão. Onde cada elemento da lista é transformado em uma linha.
-**_Operação flatten_**: Conhecida também como achatamento, esta operação consiste em transformar cada chave do json em uma nova coluna.
-**_Feature Engeneering_**: Foi criado algumas features para posterior análise e geração de insights 
-**_Geocodificação_**: É o processo que transforma uma localização descrita por um texto (endereço, nome do local, etc.) em sua respectiva coordenada geográfica (latitude e longitude).

