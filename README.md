# Dados-Vendas_Produtos
!pip install plotly
!pip install numpy


import os
import pandas as pd
import seaborn as sns
from matplotlib import pyplot as plt
import numpy as np
import plotly.express as px

sns.set_theme(style="white", context="talk")
rs = np.random.RandomState(8)

lista_arquivo = os.listdir("C:/ caminho do seu arquivo")
display(lista_arquivo)

'Devolucoes - Belo Horizonte.csv',
 'Devolucoes - Curitiba.csv',
 'Devolucoes - Fortaleza.csv',
 'Devolucoes - Goiás.csv',
 'Devolucoes - Porto Alegre.csv',
 'Devolucoes - Recife.csv',
 'Devolucoes - Rio de Janeiro.csv',
 'Devolucoes - Salvador.csv',
 'Devolucoes - São Paulo.csv',
 'Vendas - Belo Horizonte.csv',
 'Vendas - Curitiba.csv',
 'Vendas - Fortaleza.csv',
 'Vendas - Goiás.csv',
 'Vendas - Porto Alegre.csv',
 'Vendas - Recife.csv',
 'Vendas - Rio de Janeiro.csv',
 'Vendas - Salvador.csv',
 'Vendas - São Paulo.csv']
if "Vendas" in arquivo:
    tabela= pd.read_csv(f"C:/Users/sergio\Downloads/}")
    tabela_total = tabela_total.append(tabela)
    display(tabela_total)
​
C:\Users\sergio\AppData\Local\Temp\ipykernel_6692\233733135.py:3: FutureWarning: The frame.append method is deprecated and will be removed from pandas in a future version. Use pandas.concat instead.
  tabela_total = tabela_total.append(tabela)
Unnamed: 0	SKU	Produto	Quantidade Vendida	Primeiro Nome	Sobrenome	Data	Loja	Preco Unitario	Unnamed: 8	Faturamento
0	17	HL4379	Televisão	2	Carolina	Alfradique	2/25/2018	Belo Horizonte	2500	NaN	5000.0
1	25	HL4379	Televisão	1	Danilo	Rubim	2/20/2018	Belo Horizonte	2500	NaN	2500.0
2	27	HL1918	iPhone	5	Bernard	Pedrosa	7/7/2018	Belo Horizonte	5300	NaN	26500.0
3	54	HL1918	iPhone	5	Lucas	Lemos	12/26/2018	Belo Horizonte	5300	NaN	26500.0
4	67	HL8851	Notebook	5	Bernardo	Botelho	6/8/2018	Belo Horizonte	3500	NaN	17500.0
...	...	...	...	...	...	...	...	...	...	...	...
2221	9981	HL7348	SmartWatch	4	João	Junior	4/14/2018	São Paulo	1400	NaN	NaN
2222	9984	HL1918	iPhone	4	Itai	Puntel	5/2/2018	São Paulo	5300	NaN	NaN
2223	9985	HL1918	iPhone	1	Guilherme	Vianna	3/18/2018	São Paulo	5300	NaN	NaN
2224	9991	HL7348	SmartWatch	5	Antônio	Soares	11/21/2018	São Paulo	1400	NaN	NaN
2225	9996	HL4379	Televisão	5	Caio	Moraes	1/22/2018	São Paulo	2500	NaN	NaN
12225 rows × 11 columns

tabela
tabela.info()
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 2226 entries, 0 to 2225
Data columns (total 10 columns):
 #   Column              Non-Null Count  Dtype  
---  ------              --------------  -----  
 0   Unnamed: 0          2226 non-null   int64  
 1   SKU                 2226 non-null   object 
 2   Produto             2226 non-null   object 
 3   Quantidade Vendida  2226 non-null   int64  
 4   Primeiro Nome       2226 non-null   object 
 5   Sobrenome           2226 non-null   object 
 6   Data                2226 non-null   object 
 7   Loja                2226 non-null   object 
 8   Preco Unitario      2226 non-null   int64  
 9   Unnamed: 8          0 non-null      float64
dtypes: float64(1), int64(3), object(6)
memory usage: 174.0+ KB
des Vendidas
#Unindades Vendidas
tabela_produtos = tabela_total.groupby('Produto').sum()
tabela_produtos = tabela_produtos[["Quantidade Vendida"]].sort_values(by="Quantidade Vendida", ascending=False)
display(tabela_produtos)
Quantidade Vendida
Produto	
iPhone	8974
Televisão	5931
Notebook	3249
Android	3183
SmartWatch	2980
Tablet	2921
Câmera	2805
#Produto campeão de vendas
#Produto campeão de vendas
plt.figure(figsize=(15,5))
sns.countplot(tabela['Produto'])
plt.show()
![download](https://user-images.githubusercontent.com/106316788/194774928-ef4efb0f-9a0d-41c8-aa03-e5f61fb1ea6d.png)

![image](https://user-images.githubusercontent.com/106316788/194774955-d90f7dc8-b0e9-4afd-914d-10cfa1522643.png)

tario
tabela['Preco Unitario'].describe().round(2)
display(tabela)
Unnamed: 0	SKU	Produto	Quantidade Vendida	Primeiro Nome	Sobrenome	Data	Loja	Preco Unitario	Unnamed: 8
0	5	HL1918	iPhone	4	Sarah	Souza	2/14/2018	São Paulo	5300	NaN
1	6	HL7348	SmartWatch	3	Alexandre	Rodriguez	5/20/2018	São Paulo	1400	NaN
2	9	HL1148	Câmera	3	Camille	Silva	3/26/2018	São Paulo	2100	NaN
3	10	HL1918	iPhone	3	Alon	Palmeira	11/6/2018	São Paulo	5300	NaN
4	18	HL8851	Notebook	4	Leandro	Rodrigues	8/6/2018	São Paulo	3500	NaN
...	...	...	...	...	...	...	...	...	...	...
2221	9981	HL7348	SmartWatch	4	João	Junior	4/14/2018	São Paulo	1400	NaN
2222	9984	HL1918	iPhone	4	Itai	Puntel	5/2/2018	São Paulo	5300	NaN
2223	9985	HL1918	iPhone	1	Guilherme	Vianna	3/18/2018	São Paulo	5300	NaN
2224	9991	HL7348	SmartWatch	5	Antônio	Soares	11/21/2018	São Paulo	1400	NaN
2225	9996	HL4379	Televisão	5	Caio	Moraes	1/22/2018	São Paulo	2500	NaN
2226 rows × 10 columns

Agrupamento por produtos x preço
#Agrupamento por produtos x preço
tabela.groupby('Produto')['Preco Unitario'].median()
Produto
Android       3400.0
Câmera        2100.0
Notebook      3500.0
SmartWatch    1400.0
Tablet        1600.0
Televisão     2500.0
iPhone        5300.0
Name: Preco Unitario, dtype: float64
Fatuarmeto geral
#Fatuarmeto geral
tabela_total['Faturamento'] = tabela_total['Quantidade Vendida'] * tabela_total['Preco Unitario']
​
tabela_faturamento = tabela_total.groupby('Produto').sum()
tabela_faturamento = tabela_faturamento[["Faturamento"]].sort_values(by="Faturamento", ascending=False)
display(tabela_faturamento)
Faturamento
Produto	
iPhone	47562200
Televisão	14827500
Notebook	11371500
Android	10822200
Câmera	5890500
Tablet	4673600
SmartWatch	4172000
Faturamento
#Faturamento
tabela_lojas = tabela_total.groupby('Loja').sum()
tabela_lojas = tabela_lojas[['Faturamento']]
display(tabela_lojas)
Faturamento
Loja	
Belo Horizonte	6480300
Curitiba	7060500
Fortaleza	14087900
Goiás	7441800
Porto Alegre	6868600
Recife	7303000
Rio de Janeiro	14867800
Salvador	13111300
São Paulo	22098300
 Faturamento por Loja em Cidades
## Faturamento por Loja em Cidades
tabela = px.data.tips()
dados_a = ['São Paulo', 'Belo Horionte', 'Curitiba', 'Salvador','Goiás', 'Porto Alegre','Recife']
dados_b = ['22098300','6480300','7060500','13111300','7441800','6868600', '7303000']
fig = px.pie(names =dados_a, values= dados_b , width = 430 , height = 400
            )
fig.show()

![newplot](https://user-images.githubusercontent.com/106316788/194774985-e2830846-273f-433d-af2b-5bd701e3ce26.png)
