# DecisoesBaseadasDados2
Entrega de Trabalho Aplicado de Decisões Baseadas em Dados 2

# O Projeto

Objetivo:
Modelo de previsão da inflação de bens industriais brasileira utilizando métodos de machine learning e redes neurais artificiais a partir de outros indicadores de mercado.
Futuro desenvolvimento de um nowcasting da inflação de bens industriais

Saídas do modelo:
Previsão da inflação de bens industriais;
Tempo de repasse de um choque nos custos de produção;
Indiretamente: avaliação da pressão na cadeia produtiva.

Importância:
Adoção ou ajustes de políticas monetárias por Bancos Centrais para controlar a inflação, visando a estabilidade econômica;
Ajuste e negociação de contratos por empresas, assim como para avaliação de investimento em aumento da capacidade produtiva e/ou instalação de novas tecnologias;
Avaliação de aplicações financeiras por investidores, que podem antecipar suas ações de compra e venda a partir da previsão de inflação para determinado setor.

# Entendimento dos Dados

Carregamento dos Dados no Python por:
Arquivos em csv ou xlsx;
Através de API (Sidra IBGE);

Análise dos Dados:
Conversão de dados de string para float e datetime;
Análise de comportamento das séries temporais – identificação de possíveis erros de dados;
Remoção de linhas com dados faltantes;
Teste de Estacionariedade;
Decomposição das séries em tendência, sazonalidade e resíduos;
Análise dos gráficos de autocorrelação e autocorrelação parcial;
Algumas séries não apresentavam estacionariedade por se tratarem de números índices ou números brutos. Neste caso, foram incluídos os dados de variação (primeiras diferenças)

Desenvolvimento dos Códigos:
Para cada um dos indicadores, exceto para ICI, NUCI e Nível de Estoques, foi criado um código separadamente chamado “Code_GetData_’nomedoindicador’”. Neste código são desenvolvidas as etapas (1) e (2) acima;
Essa estratégia foi necessária devido à grande diversidade dos dados, do formato de disponibilização destes e fontes;
Após todo o processo de tratamento dos dados, é gerado um arquivo csv;
Finalmente, todos esses arquivos csv’s são compilados através de código num único arquivo csv para ser utilizado para o desenvolvimento dos modelos de previsão.

# Preparação dos Dados

Seleção e inclusão de dados das variáveis de interesse no mesmo dataframe – tarefa realizada no final da etapa anterior;
Definição de data de início das séries a serem utilizadas;

Criação de Dummies:
Período de Regime de Exceção – período de março/2020 a dezembro/2022 contemplando pandemia e 1º ano da Guerra da Rússia / Ucrânia;
Dummies para cada mês do ano -  necessárias para Modelos de Machine Learning, como o Random Forest, que não "enxergam" a sazonalidade apenas pelo índice de data.

Criação de 4 defasagens para todas as variáveis explicativas e da variável target (modelo deve considerar a endogeneidade da série);

Análises exploratórias;

Análise de Componentes Principais: redução de dimensionalidade da base de dados (análise de dados exploratória, visualização e pré-processamento de dados) – base de dados mais refinada para modelagem econométrica e modelos de machine learning / redes neurais;

Separação da base de dados de treinamento e da de teste (80% para treinamento);

Normalização de dados para ficarem no mesmo intervalo [0,1].

