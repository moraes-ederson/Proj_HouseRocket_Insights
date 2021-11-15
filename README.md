# Projeto House Rocket - Insights

Acesse ao código deste projeto aqui: https://github.com/moraes-ederson/Proj_HouseRocket_Insights/blob/944ca6238ed47270dd1158be6c6ca00e325b73b6/Proj_HouseRocket_Insights_v01.ipynb

## 1. Problema de Negócio

Trata-se de um problema fictício que visa encontrar as melhores oportunidades de compra e venda de imóveis disponíveis no portfólio da House Rocket, empresa também fictícia.  
E quais são as dores enfrentadas pelos tomadores de decisão?  
•	O time do negócio não consegue tomar boas decisões de compra sem analisar os dados.  
•	O portfólio é muito grande e leva muito tempo para fazer o trabalho manualmente.  

### 1.1 Objetivo

Gerar insights através da análise e manipulação dos dados para auxiliar na tomada de decisão pelo time de negócios.  

### 1.2 Questões de negócios a serem respondidas

1 - Quais são os imóveis que a House Rocket deveria comprar e por qual preço?  
2 - Uma vez o imóvel comprado, qual o melhor momento para vendê-lo e por qual preço?  

### 1.3 Insights

Visando descobrir e entregar mais insights para o time de negócios, vamos explorar e validar as seguintes hipóteses:  
•	H1: Imóveis que possuem vista para água são pelo menos 30% mais caros, na média.  
•	H2: Imóveis com ano de construção menor que 1955 são pelo menos 50% mais baratos, na média.  
•	H3: Imóveis sem porão possuem terrenos pelo menos 50% maiores do que com porão, na média.  
•	H4: O crescimento do preço dos imóveis YoY (Year over Year) é de pelo menos 10%.  
•	H5: Imóveis com 3 banheiros tem um crescimento de preço MoM (Month over Month) de pelo menos 15%.  

## 2. Premissas

•	Preços indicados em dólares americanos (US$).  
•	Dimensões de áreas indicadas em pés quadrados.  
•	Foram mantidos todos registros do conjunto de dados.  
•	Há “IDs” repetidos, porém com informações e atributos diferentes.  
•	Mantidos também os outliers para validação das hipóteses.  
•	Compra viável considerada apenas para imóveis avaliados com índice de condição sobre o estado do mesmo sendo maior ou igual a 3.  

## 3. Planejamento da Solução  

Para recomendação de compra:

•	Agrupar os imóveis por região (zipcode).  
•	Dentro de cada região, encontrar a mediana do preço do imóvel.  
•	Sugerir que os imóveis abaixo do preço mediano da região e que estejam em boas condições sejam comprados.  

Para recomendação de venda:

•	Agrupar os imóveis recomendados para compra por região (zipcode) e por sazonalidade (estações do ano).  
•	Dentro de cada região e sazonalidade, calcular a mediana do preço.  
•	Condições de venda:  
1 -	Se o preço da compra for maior que a mediana da região + sazonalidade: O preço da venda será igual ao preço da compra + 10%.  
2 -	Se o preço da compra for menor que a mediana da região + sazonalidade. O preço da venda será igual ao preço da compra + 30%.  

## 4. Principais Insights desta Análise

•	Imóveis com vista para água são na média 213% mais caros do que os demais.  
•	O ano de construção do imóvel não impacta no seu preço.  
•	O aumento de preço dos imóveis “YoY” (ano após ano) é de pouco mais de 0,5% apenas.  
•	Pouco mais da metade do portfólio não são boas recomendações de compra.  
•	Os imóveis anunciados na primavera são mais caros, enquanto os anunciados no inverno são os mais baratos, em média. Logo é mais recomendado anunciar a venda na primavera e comprar quando estiver no inverno.  

## 5. Resultados Financeiros para o Negócio

A empresa tem potencial para economizar cerca de US$ 1.055.901.488 (25.79%) adquirindo os imóveis recomendados considerando valor mediano de mercado.  

A empresa tem potencial para lucrar cerca de US$ 774.596.311 (529%) considerando a venda dos imóveis adquiridos nos valores recomendados.  

## 6. Conclusão

O objetivo inicial foi alcançado, onde conseguimos gerar os relatórios com as recomendações de preço de compra e venda, bem como o melhor momento para realizar a venda.  

## 7. Próximos Passos Possíveis para Melhorias do Projeto

•	Gerar um app de visualização com Streamlit ou outra ferramenta de “DataViz”.  
•	Detalhar e tratar outliers.  
•	Analisar mais variáveis e validar mais hipóteses buscando novos insights.  
•	Checar quais atributos mais impactam no preço dos imóveis.  
•	Coletar informações da localização dos imóveis através de uma API geográfica e adicioná-las ao conjunto de dados ou relatório de entrega.  
•	Adicionar um mapa interativo com os imóveis disponíveis no portfólio.  
•	Construir um modelo de machine learning para predizer os preços dos imóveis de determinada região.  
