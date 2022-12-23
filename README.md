# Análise Exploratória de Dados Logística da Loggi


![alt text](https://github.com/kedimo-cd/Analise_Logistica_da_loggi/blob/main/img/Loggi.png)
*******
# 1. O que é a Loggi

A Loggi é uma startup unicórnio brasileira de tecnologia focada em logística. A Loggi começou entregando apenas documentos entre 2013 e 2014. Dois anos depois, entrou no segmento de e-commerce. E, desde 2017, tem atuado nas entregas de alimentos também.


# 2. O Problema de negócio

 Afim de trazer melhorias na qualidade de entrega do serviço oferecido na região de Brasília – Distrito Federal, a Loggi busca por soluções para que as entregas sejam feitas de maneiras mais rápidas e agis, além disso, garantir que o serviço esteja distribuído de forma uniforme pelas regiões estabelecidas, evitando assim, sobrecarga e consequentemente melhorando o fluxo de trabalho.
 
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

- **_Tratamento dos dados nested_**: Os dados foram normalizados com uma operação conhecida como explode ou explosão. Onde cada elemento da lista é transformado em uma linha.
- **_Operação flatten_**: Conhecida também como achatamento, esta operação consiste em transformar cada chave do json em uma nova coluna.
- **_Feature Engeneering_**: Foi criado algumas features para posterior análise e geração de insights 
- **_Geocodificação_**: É o processo que transforma uma localização descrita por um texto (endereço, nome do local, etc.) em sua respectiva coordenada geográfica (latitude e longitude).

# 6. Análise Exploratória dos dados

O Objetivo desta etapa foi analisar os dados para gerar insights. Para isso, foram utilizados os dados de forma visual para levantamento e validação de algumas hipóteses. Abaixo você poderá observar algumas dessas análises. 

### Entregas por região no DF
![alt text](https://github.com/kedimo-cd/Analise_Logistica_da_loggi/blob/main/img/mapa_hub_tabela.png)

- **Visualização**

![alt text](https://github.com/kedimo-cd/Analise_Logistica_da_loggi/blob/main/img/mapa_hub_df.png)


### Proporção de entregas por região

![alt text](https://github.com/kedimo-cd/Analise_Logistica_da_loggi/blob/main/img/Percentual%20_entregas_regiao.png)

- **Visualização**

![alt text](https://github.com/kedimo-cd/Analise_Logistica_da_loggi/blob/main/img/Entregas_por_regiao.png)

# 7. Insights gerados

1. As **entregas** estão corretamente alocadas aos seus respectivos **hubs**;
2. Os **hubs** das regiões 0 e 2 fazem **entregas** em locais distantes do centro e entre si, o que pode gerar um tempo e preço de entrega maior.
3. A distribuição das **entregas** está muito concentrada nos **hubs** das regiões 1 e 2, mas pouco no da região 0. Contudo a capacidade dos veículos é mesma para todos os **hubs**, logo os **veículos** poderiam ser deslocados para as regiões de maior tráfego.

# 8. Contato
Este projeto foi inteiramente desenvolvido por mim com base nos conceitos ensinados no curso Formação analista de Dados EBAC. Fique a vontade para entrar em contato comigo através do meu LinkedIN.
Conecte-se comigo no meu [Linkedin](https://www.linkedin.com/in/k%C3%A9dimo-alc%C3%A2ntara-4371ab234/).
