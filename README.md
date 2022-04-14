# Cancioneiro das múltiplas Fortalezas: retratos da capital cearense em composições

Este repositório refere-se à análise e apuração realizadas para a reportagem reportagem [Cancioneiro das múltiplas Fortalezas](https://mais.opovo.com.br/reportagens-especiais/2022/04/12/as-multiplas-fortalezas-expressas-em-cancoes.html), publicada no O POVO+ no dia 12 de abril de 2022 em alusão aos 296 anos da Cidade. A data é comemorada no dia 13 de abril.

![Nuvem de palavras](https://user-images.githubusercontent.com/43644247/163463584-cac74999-3d82-430c-91b4-9bcab9df6952.png)

A partir de dados do projeto [Fortaleza em Música](https://play.google.com/store/apps/details?id=com.ufc.fortalezaemmusica&gl=US), da Universidade Federal do Ceará (UFC), a Central de Jornalismo de Dados do O POVO (DATADOC) buscou entender que cidade é retratada pelos artistas nas letras das composições.

Este repositório é uma forma garantir o compromisso com a transparência, integridade e confiabilidade das análises e materiais da DATADOC. Os dados originais pertencem ao Grupo de Imagem, Consumo e Experiência Urbana (ICA/UFC) e foram concedidos apenas para análise da equipe de reportagem.

Por isso, excepcionalmente, a base de dados original não será disponibilizada pela DATADOC e os trechos de código que mostram detalhes das informações concedidas pelos pesquisadores foram suprimidos do notebook `reportagem_fortaleza_296_anos`. Este repositório contém os códigos utilizados na análise e os arquivos gerados para elaboração de nuvens de palavras e demais gráficos. A análise é feita em Python.

--------------------------------------

### Fonte e coleta de dados:

- [Arquivos do aplicativo Fortaleza em Música](https://play.google.com/store/apps/details?id=com.ufc.fortalezaemmusica&gl=US)
- [Fortaleza em Mapas](https://mapas.fortaleza.ce.gov.br/)
- [YouTube DATA API](https://developers.google.com/youtube/v3/)

### Metodologia

Para chegarmos às evidências da reportagem [Cancioneiro das múltiplas Fortalezas](https://mais.opovo.com.br/reportagens-especiais/2022/04/12/as-multiplas-fortalezas-expressas-em-cancoes.html), que revelou os bairros de fortaleza mais citados em canções de artistas locais, foi adotada a técnica computacional “text  mining”.

Para esse processo, foi utilizada a [biblioteca Natural Language Toolkit (NLTK)](https://www.nltk.org/). Primeiramente consolidamos a amostra de 79 letras musicais em um corpus único. Em seguida , iniciamos a limpeza textual, com a exclusão das stopwords, carácteres especiais e pontuação,  e em seguida foi feita tokenização do corpus. 

Em seguida, foi construída a nuvem de palavras obtida por meio das 79 letras unificadas em um único corpus de análise , verificando-se que as cinco palavras mais evocadas foram: mar (60), sol (57), tempo (42), dia (41) e vida (37), mostrando que nas composições está presente a referência à paisagem litorânea da Capital.

O corpus geral foi constituído por 79 textos , dos quais emergiram 2812 ocorrências (palavras, formas ou vocábulos) sendo 1197 palavras que se repetem ao longo do texto e 1615 com uma única ocorrência.

Já o corpus referente às falas sobre a inspiração dos artistas era composto por 73 textos, dos quais emergiram 2008 ocorrências. Destas, eram 736 que se repetiam e 1272 de ocorrência única.

Em ambos os casos, buscou-se preservar palavras compostas e nomes de pessoas por meio da definição das funções `processingTxt` e `processingTxtInspiracao`. Também foram acrescentados mais termos à lista de stopwords em português disponível na biblioteca NLTK com expressões encontradas no corpus analisado.

### Arquivos gerados:

**_Dataframes_**
 - `df_nuvem_palavras_geral.csv`: palavras mais recorrentes nas letras das músicas;
 - `df_nuvem_inspiracao.csv`: palavras mais recorrentes nas falas dos artistas sobre inspiração para a música;
 - `arquivo_bairros_fortaleza`: quantidade de músicas referente a cada bairro de Fortaleza
 - `10mais.csv`: ranking das métricas de cada vídeo no YouTube
 
 **_Visualizações_**
- Nuvem de palavras com [termos mais recorrentes nas letras de música](https://public.flourish.studio/visualisation/9331125/)
- Nuvem de palavras dos [termos mais recorrentes nas falas dos artistas sobre inspiração](https://public.flourish.studio/visualisation/9331396/)
- Mapa de Fortaleza: [músicas catalogadas no App Fortaleza em Música](https://observablehq.com/embed/8acc04c8196c4c61?cells=chart%2Cfonte%2Cviewof+selected_artista%2Cviewof+selected_bairro)
- [Bairros mais cantados nas músicas sobre Fortaleza](https://public.flourish.studio/visualisation/9333060/)
- [Músicas mais assistidas no YouTube](https://public.flourish.studio/visualisation/9385338/)

--------------------------------------

#### Como utilizar:

Para executar o notebook com a coleta e processamento dos dados, é necessário um ambiente com *Python3* e dependências que podem ser instaladas via [Pip](https://pypi.org/project/pip/): 
```{python}
!pip install pandas
!pip install geopandas
!pip install nltk
```

### A central DATADOC

A Central de Jornalismo de Dados do O POVO (DATADOC) alia tecnologia e técnicas diversas de análises de dados para produzir um jornalismo de precisão para que você forme sua opinião com segurança. Nosso objetivo é fazer com que todos tenham acesso aos dados utilizados nas notícias que produzimos.

A DATADOC é composta por uma equipe de três jornalistas (sendo uma infografista), uma desenvolvedora front-end e um cientista da computação que coletam, enriquecem e disponibilizam as bases e códigos de cada reportagem para um jornalismo transparente e baseado em evidências.

 --------------------------------------
#### 🔥📰👩🏻‍💻 Se você gostou do nosso material, apoie assinando o OP+ e acompanhando o nosso trabalho.

#### 📝📨 Para feedback, dúvidas ou sugestões: datadoc@opovodigital.com

--------------------------------------
 
🗓️🕵🏻 Confira também outras produções recentes da central DATADOC: O especial ***#CredosDeFortaleza*** revelou benefícios fiscais indevidos, templos fantasmas e os principais devedores do fisco e está [disponível no O POVO+](https://bit.ly/3gkGPyF).