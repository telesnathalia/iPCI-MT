**Produto 1**

**PLANO DE TRABALHO \- Instituto PCI x Lapig / UFG**

**Mapeamento e Monitoramento das Pastagens no estado do Mato Grosso**

Atualização do mapeamento das áreas e da condição (vigor) das pastagens do Mato Grosso (2015–2026) e do mapeamento experimental de florestas plantadas (2022–2026), em suporte às metas da Estratégia PCI.

---

## **1\. Identificação das Partes**

**Contratante –** Instituto Produzir, Conservar e Incluir (iPCI)

**Contratada –** Fundação de Apoio à Pesquisa (FUNAPE), com execução técnica pelo Lapig / UFG

**Instrumento –** Contrato de Prestação de Serviços nº 19/2026

---

## **2\. Objeto**

Entre 2022 e 2023, o Lapig / UFG produziu para o Instituto PCI a série anual de mapas de pastagem e de vigor das pastagens de Mato Grosso para 2015–2022, com acurácia global média de **94,3%** nos mapas de pastagem (71.929 amostras de treinamento e 3.644 pontos de validação). Em 2024, fora do escopo daquele projeto, a série foi estendida até 2023\. Esses produtos são hoje a principal referência para o acompanhamento da meta do eixo PRODUZIR de recuperar **2,5 milhões de hectares** de pastagens de baixa produtividade até 2030\.

O presente plano tem por objeto a atualização dessa base e a criação de um novo produto, organizados em quatro frentes:

1. **Série de continuação** dos mapas de pastagem e de vigor para os anos posteriores a 2023, com a mesma metodologia de 2022 e sem alterar os anos já entregues.

2. **Versão aprimorada** dos mapas de pastagem e de vigor para 2015–2026, reprocessada com base amostral ampliada e ajustes metodológicos.

3. **Mapeamento experimental de florestas plantadas** (eucalipto e teca, sem diferenciação entre espécies) para 2022–2026.

4. **Análises de transição, conversão e balanço de metas**, nos recortes estadual, municipal e dos Pactos PCI Regionais.

Complementarmente, o Lapig irá incorporar informações derivadas de outros produtos que já desenvolve (produtividade primária bruta, biomassa, tendência do NDVI e densidade animal), com o objetivo de ampliar o uso dos dados no monitoramento das pastagens.

## ---

**3\. Objetivos**

### **3.1 Objetivo Geral**

Atualizar e aprimorar a base de monitoramento das pastagens de Mato Grosso, mantendo a consistência da série iniciada em 2015, e desenvolver o mapeamento experimental de florestas plantadas, gerando informações espacialmente explícitas para o acompanhamento das metas da Estratégia PCI.

### **3.2 Objetivos Específicos**

* Atualizar e ampliar a base amostral de treinamento e validação, atualmente com cerca de 72 mil pontos (Produto 2).

* Gerar a série de continuação dos mapas anuais de pastagem até 2025, sem alterar os anos já entregues (Produto 2).

* Gerar a versão aprimorada dos mapas anuais de pastagem 2015–2025, com acurácia global igual ou superior a **90%** (Produto 2).

* Gerar a série de continuação dos mapas de vigor até 2025, comparável à série 2015–2023 (Produto 3).

* Gerar a versão aprimorada dos mapas de vigor 2015–2025 (Alto, Médio e Baixo), com acurácia global igual ou superior a **80%** (Produto 3).

* Desenvolver a primeira versão do mapeamento experimental de florestas plantadas 2022–2025 (Produto 3).

* Avaliar a tendência do NDVI para identificar pastagens que estão perdendo produtividade (Produto 3).

* Analisar as transições entre classes de vigor e as conversões de pastagem para outros usos, inclusive para silvicultura, e calcular o balanço anual de metas (Produto 4).

* Analisar os dados de produtividade primária bruta (GPP) e biomassa das pastagens (Produto 4).

* Levantar a densidade animal (cabeças/ha) por município (Produto 4).

* Atualizar todos os mapeamentos para 2026 e consolidar os resultados em relatório técnico e bases de uso livre pelo iPCI (Produto 5).

---

## **4\. Metodologia e Estratégias de Execução**

Os mapas de pastagem e de vigor serão produzidos em duas linhas. A **série de continuação** usa a metodologia, os parâmetros e os mesmos pontos amostrais de 2015–2022 e gera os mapas para os anos seguintes, preservando os valores já utilizados pelo iPCI. A **versão aprimorada** reprocessa toda a série 2015–2026 com a base amostral expandida e os ajustes descritos na Seção 4.5; é a nova versão prevista no Termo de Referência e está sujeita às metas de acurácia. As duas linhas compartilham as mesmas imagens e o mesmo fluxo de processamento, executado no Google Earth Engine (GEE) e em Python.

### **4.1 Área de Estudo e Bases de Dados**

* Área: todo o estado de Mato Grosso (52 cenas Landsat WRS-2), nos biomas Amazônia, Cerrado e Pantanal; resultados agregados por estado, bioma, município e Pactos PCI Regionais.

* Imagens: Landsat 8 e 9 Collection 2 Tier 1 (30 m) para pastagem e vigor; Sentinel-2 (10 m) e Google Satellite Embeddings para apoio à inspeção, à expansão da base amostral e ao mapeamento de florestas plantadas.

* Bases auxiliares: SRTM/NASADEM, MapBiomas Coleção 11, malha municipal e biomas (IBGE), limites dos Pactos PCI Regionais (iPCI), Malha Fundiária Ambiental do Lapig, densidade de bovinos do Global Pasture Watch e levantamento de silvicultura do IMEA (2015–2021).

* Referência espacial: SIRGAS 2000, com cálculo de área em projeção equivalente (Albers).

### **4.2 Base Amostral**

A base atual reúne 71.929 pontos inspecionados visualmente, ano a ano, para toda a série 2015–2022. Ela será trabalhada em duas etapas:

* **Etapa 1 – série de continuação:** os mesmos pontos serão inspecionados ano a ano para 2023–2026, seguindo o protocolo de interpretação da fase anterior. Indicadores de mudança (similaridade entre os *embeddings* anuais e séries Sentinel-2) serão usados para priorizar os pontos com provável alteração de uso, sem dispensar a inspeção dos demais.

* **Etapa 2 – versão aprimorada:** a base será expandida com uma rede neural não supervisionada do tipo *Self-Organizing Map* (SOM), treinada sobre séries temporais e *embeddings* de pontos já inspecionados e de novos pontos candidatos. Os neurônios são rotulados a partir dos pontos inspecionados; candidatos associados a neurônios dominados por uma única classe são incorporados, com inspeção visual de uma subamostra para controle de qualidade.

* **Diagnóstico:** distribuição dos pontos por cena, bioma, ano, classe e municípios do Pacto, e identificação das zonas de confusão recorrente (pastagem × agricultura, pastagem × vegetação campestre natural, pastagem × silvicultura), que orientam o reforço amostral.

* **Validação independente:** os pontos de validação permanecem separados dos de treinamento em ambas as etapas.

### **4.3 Mapeamento das Áreas de Pastagem**

Mantém-se o fluxo consolidado em 2022 (Parente et al., 2019):

1. Imagens Landsat TOA de cada ano, acrescidas de janela de seis meses antes e depois, com remoção de nuvens e sombras pela banda de qualidade.

2. *Feature space* de 76 métricas: estatísticas temporais (mínimo, mediana, máximo, desvio-padrão, amplitude e percentis 10, 25, 75 e 90\) de bandas espectrais e índices (NDVI, NDWI e CAI), além de elevação, declividade, latitude e longitude.

3. Classificação por Random Forest por cena (200 árvores), treinado com amostras da cena e das cenas vizinhas, com saída probabilística de 0 a 100%.

4. Filtro espaço-temporal de mediana (3 × 3 pixels × 5 anos) e discretização em pastagem para probabilidade igual ou superior a 51%.

Na série de continuação, apenas os anos novos são classificados, e o filtro temporal usa as probabilidades já publicadas dos anos anteriores, sem recalculá-las. A validação usa pontos independentes, com matriz de confusão, acurácia global e taxas de omissão e comissão por ano, e os resultados são comparados ao MapBiomas Coleção 11 (área total, área por município e mapa de concordância).

### **4.4 Monitoramento do Vigor das Pastagens (Série de Continuação)**

O vigor expressa a tendência da produtividade e da cobertura vegetal das pastagens em cada ano. O procedimento segue Santos et al. (2022), tal como aplicado em 2015–2022:

1. **Séries de EVI:** medianas mensais do *Enhanced Vegetation Index* (EVI), calculadas a partir de dados Landsat Collection 2 Surface Reflectance sobre as áreas mapeadas como pastagem. O EVI é menos sensível a ruídos atmosféricos e satura menos em áreas de alta biomassa do que o NDVI.

2. **Preenchimento de falhas:** lacunas causadas por nuvens são preenchidas com o filtro de mediana em janela temporal móvel (*Temporal Moving Window Median*, TMWM).

3. **Decomposição da série:** separação dos componentes de sazonalidade, tendência e resíduo; a sazonalidade é removida e a tendência (EVI dessazonalizado) é mantida, isolando a variação de longo prazo das oscilações climáticas intra-anuais.

4. **Agregação anual e filtragem:** cálculo da média anual da tendência por pixel, seguida de filtro de temporal de mediana de 5 anos para reduzir ruídos e oscilações agressivas entre anos.

5. **Normalização por bioma:** os valores são reescalados entre 0 e 1 em cada bioma (Amazônia, Cerrado e Pantanal), usando a média do 1% inferior e do 1% superior da distribuição.

6. **Classificação:** Alto vigor (≥ 0,6), Médio vigor (0,4 a 0,6) e Baixo vigor (\< 0,4). Valores altos indicam boa cobertura do solo por vegetação (sem diferenciar forrageiras de espécies invasoras e arbustivas) e alta biomassa; médios, início de degradação; baixos, perda de biomassa e exposição do solo.

7. **Saídas:** mapas anuais de vigor e tabelas de área por classe, ano, estado e município.

### **4.5 Aprimoramento dos Mapas**

A versão aprimorada busca reduzir os erros identificados na série de 2022, em especial a confusão com agricultura nos mapas de pastagem e a baixa detecção da degradação agrícola (59,7%) nos mapas de vigor. Cada ajuste será testado contra a série de continuação, e só será incorporado se melhorar a acurácia; as diferenças entre as duas linhas serão documentadas.

**Mapas de pastagem:**

* Retreinamento do classificador com a base amostral expandida por SOM, com reforço nas zonas de confusão e nas cenas sub-representadas.

* Avaliação de variáveis adicionais derivadas de Sentinel-2 e dos *embeddings* anuais.

* Tratamento específico dos anos de borda da série (2025–2026), em que o filtro temporal dispõe de menos anos vizinhos, e revisão do limiar de probabilidade por região, se a validação indicar ganho.

**Mapas de vigor:**

* Recalibração dos limiares das classes com os pontos de campo, em lugar dos cortes fixos de 0,4 e 0,6.

* Normalização em unidades regionais mais homogêneas que o bioma (por exemplo, ecorregiões), para reduzir o efeito das diferenças de clima e solo dentro de cada bioma.

* Inclusão de variáveis auxiliares — tendência e amplitude sazonal do NDVI e produtividade primária bruta (GPP) — para melhorar a separação da degradação agrícola, em que as plantas invasoras mantêm o índice de vegetação elevado.

* Teste de um produto de vigor com Sentinel-2 (10 m) em área-piloto, para diagnóstico em escala de propriedade.

### **4.6 Mapeamento Experimental de Florestas Plantadas**

O produto identifica anualmente, de 2022 a 2026, as áreas de silvicultura (eucalipto e teca, sem distinção de espécie) e quantifica a conversão de pastagens para esse uso. Por ser experimental, não tem meta de acurácia e sua qualidade depende das amostras de referência, que serão viabilizadas pelo iPCI junto a seus associados (AREFLORESTA).

* **Método principal:** Rede Neural Convolucional Temporal (TempCNN; Pelletier et al., 2019), que aprende em conjunto padrões espectrais e temporais e reconhece a trajetória típica dos plantios: crescimento após o plantio, corte raso e rebrota.

* **Sistemas integrados com floresta (IPF):** variam pouco no tempo e se distinguem pelo arranjo espacial das árvores, o que a TempCNN não captura. Serão tratados como classe à parte e, havendo amostras suficientes, avaliados em caráter exploratório com U-Net (Ronneberger et al., 2015), rede de segmentação que considera o contexto espacial.

* **Amostras de referência:** planilha-matriz elaborada pelo Lapig, com informações imprescindíveis (localização do talhão, espécie, sistema de cultivo, ano de plantio, fonte) e desejáveis (datas de corte, uso anterior, espaçamento, fotografias georreferenciadas); documentação dos mapeamentos do IMEA (2015–2021) e amostras de referência fornecidas pelo iPCI. As amostras devem ser recebidas até janeiro de 2027 para compor o Produto 3\.

* **Processamento:** análise exploratória das assinaturas espectro-temporais por sistema; séries Landsat 8/9 e Sentinel-2 harmonizadas a 30 m, com preenchimento de lacunas e janela plurianual; treinamento com amostras positivas e negativas (floresta nativa, cerrado, pastagem, agricultura e água).

* **Avaliação e pós-processamento:** validação cruzada espacial e amostras retidas (acurácia global, acurácias do usuário e do produtor, F1); filtro espacial, consistência temporal e área mínima mapeável; comparação com o MapBiomas e com o levantamento do IMEA.

### **4.7 Transições, Conversões e Balanço de Metas**

* Transições anuais entre as classes Alto, Médio e Baixo Vigor e Outros usos, e entre os anos extremos da série.

* Balanço de metas do eixo PRODUZIR: hectares recuperados por ano, áreas melhoradas ou convertidas versus áreas que perderam vigor, e saldo acumulado frente à meta de 2,5 Mha até 2030, com as regras de contagem de 2022\. O balanço oficial é calculado sobre a série de continuação; a versão aprimorada é apresentada em paralelo.

* Balanço entre novas pastagens e pastagens convertidas, com o destino das conversões identificado pelo MapBiomas Coleção 11 e pelo produto de florestas plantadas.

* Resultados para o estado, biomas e, em destaque, os municípios dos Pactos PCI Regionais.

### **4.8 Informações Complementares**

* **Tendência do NDVI:** regressão da tendência de longo prazo das séries de NDVI por pixel, para identificar pastagens com perda persistente de produtividade, separando-a das oscilações climáticas.

* **GPP e biomassa:** séries anuais de produtividade primária bruta e de biomassa das pastagens, a partir dos produtos Landsat do Global Pasture Watch e do MapBiomas, sintetizadas por município e classe de vigor.

* **Densidade animal:** estimativa de cabeças por hectare de pastagem por município, a partir das camadas de densidade de bovinos do Global Pasture Watch (Parente et al., 2025).

* **Condição por tamanho de imóvel:** atualização da análise de 2022 com a Malha Fundiária do Lapig, apresentada apenas de forma agregada, sem identificação de imóveis.

### **4.9 Documentação**

* Código (GEE e Python), parâmetros, limiares e versões de dados mantidos em repositório Git do projeto, com registro das decisões metodológicas.

* Cada produto acompanhado de nota metodológica e dicionário de dados, em nível de detalhe que permita a reprodutibilidade e a auditoria técnica.

* Revisão interna de todos os produtos antes da entrega.

---

## **5\. Cronograma e Marcos**

| Fase / Marco | Prazo estimado | Entregas parciais / objetivos |
| :---- | :---- | :---- |
| Plano de trabalho e diagnóstico da base amostral | Mês 1 | Produto 1: plano de trabalho, diagnóstico da base amostral e requisitos das amostras de florestas plantadas |
| Inspeção dos pontos para 2023–2026 (continuação) | Meses 1–3 | Base amostral atualizada para a série de continuação |
| Expansão da base amostral (SOM) | Meses 2–4 | Base amostral ampliada para a versão aprimorada |
| Mapas de pastagem (continuação e aprimorada) | Meses 2–4 | Produto 2: mapas de pastagem, estatísticas municipais, relatório de acurácia e comparação com o MapBiomas |
| Mapas de vigor e tendência do NDVI | Meses 3–6 | Produto 3 (parte): mapas de vigor atualizados |
| Florestas plantadas (experimental) | Meses 2–6 | Amostras recebidas até o mês 4; Produto 3 (parte): primeira versão e nota técnica |
| Transições, balanço de metas e informações complementares | Meses 5–7 | Produto 4: relatório parcial e planilhas consolidadas |
| Ano de 2026 e relatório final | Meses 7–8 | Produto 5: atualização dos mapas para o ano de 2026, relatório técnico final e repositório organizado |
| Reserva de prazo da vigência | Meses 9–12 | Consolidação do ano de 2026, se necessário, e ajustes solicitados |

*O contrato foi assinado em 22/10/2026, com vigência de 12 meses; os meses contam a partir da assinatura. Como o método usa imagens de até seis meses do ano seguinte, os mapas de 2026 serão entregues no Produto 5 em versão preliminar, podendo ser consolidados na reserva de prazo.*

---

## **6\. Entregáveis**

* **Produto 1 – Plano de Trabalho e Diagnóstico da Base Amostral (mês 1):** este plano; diagnóstico da base amostral (planilha e mapa); requisitos das amostras de florestas plantadas (planilha-matriz).

* **Produto 2 – Base Amostral Ampliada e Mapeamento das Áreas de Pastagem (mês 4):** base amostral atualizada e ampliada; mapas anuais de pastagem da série de continuação e da versão aprimorada; área por município e ano; relatório de acurácia (acurácia global, omissão e comissão) e comparação com o MapBiomas Coleção 11\.

* **Produto 3 – Condição das Pastagens e Florestas Plantadas (mês 6):** mapas anuais de vigor das duas linhas, com tabelas por classe, ano, estado e município e relatório de validação; mapa de tendência do NDVI; primeira versão dos mapas de florestas plantadas 2022–2025, com estatísticas e nota técnica de limitações e incertezas.

* **Produto 4 – Relatório Parcial de Transições e Balanço de Metas (mês 7):** transições anuais, conversões por destino, hectares recuperados por ano, GPP, biomassa e densidade animal por município; planilhas por estado, município e Pacto.

* **Produto 5 – Relatório Técnico Final (mês 8):** mapas de 2026; relatório final com metodologia, resultados, limitações e recomendações; entrega organizada de todas as bases de dados em repositório digital, com dicionário de dados.

Formatos: rasters em GeoTIFF (30 m); vetores em GeoPackage ou shapefile; tabelas em .xlsx e .csv; relatórios em .docx e PDF; figuras em alta resolução. Todos os arquivos serão organizados por produto e por ano, em português.

---

## **7\. Equipe Técnica**

| Nome | Função | Atribuições |
| :---- | :---- | :---- |
| Laerte Guimarães Ferreira | Coordenação geral | Direção científica e aprovação interna dos produtos |
| Nathália Monteiro Teles | Coordenação técnico-institucional | Relação com o iPCI, cronograma, vigor e validação, relatórios, florestas plantadas |
| Vinícius Vieira Mesquita | Coordenação técnico-computacional | Processamento, mapas de pastagem, expansão da base amostral, repositório |
| Bolsistas e intérpretes | Apoio técnico | Inspeção visual de amostras, validação, tabelas e figuras |
| Pesquisadores do Lapig | Apoio metodológico | TempCNN e U-Net, GPP e biomassa |

---

## **8\. Obrigações e Responsabilidades das Partes**

### **8.1 Do Instituto PCI (Contratante)**

* Indicar ponto focal e participar das reuniões mensais de acompanhamento.

* Disponibilizar os limites dos Pactos PCI Regionais e a documentação dos mapeamentos de silvicultura do IMEA (2015–2021).

* Mobilizar, diretamente ou por meio de parceiros como a AREFLORESTA, as amostras de florestas plantadas até janeiro de 2027\.

* Analisar cada produto em até 10 dias úteis, aprovando-o ou solicitando ajustes.

### **8.2 Do Lapig / UFG (Contratada, via FUNAPE)**

* Executar as etapas conforme a metodologia descrita, mantendo a consistência da série histórica.

* Entregar os produtos nos formatos e prazos estabelecidos, com documentação que permita a reprodutibilidade.

* Comunicar tempestivamente ao iPCI riscos ou limitações que possam afetar prazos, escopo ou qualidade.

* Realizar os ajustes solicitados em até 10 dias úteis.

### **8.3 Critérios de Aceitação**

* Produto 2: acurácia global igual ou superior a 90% para a versão aprimorada dos mapas de pastagem.

* Produto 3: acurácia global igual ou superior a 80% para a versão aprimorada dos mapas de vigor; para florestas plantadas, o aceite está condicionado à execução das atividades e à entrega da documentação, e não a um patamar de acurácia.

* Caso as amostras de florestas plantadas não sejam disponibilizadas a tempo, a limitação será registrada formalmente e o escopo desse componente poderá ser repactuado.

### **8.4 Propriedade Intelectual e Divulgação**

* Os produtos desenvolvidos no âmbito do contrato são de titularidade do iPCI; as metodologias, ferramentas e algoritmos preexistentes do Lapig / UFG permanecem de titularidade de seus autores.

* A publicação científica dos resultados é admitida mediante comunicação prévia ao iPCI e menção à parceria.

### **8.5 Sigilo e Proteção de Dados**

* Dados do CAR e quaisquer informações que identifiquem imóveis ou titulares serão usados apenas para as finalidades do contrato, conforme a LGPD, e divulgados somente de forma agregada.

---

## **9\. Riscos e Medidas de Mitigação**

| Risco | Medida de mitigação |
| :---- | :---- |
| Volume de inspeção da série de continuação (cerca de 72 mil pontos × 4 anos) | Dimensionamento da equipe no diagnóstico, priorização por indicadores de mudança e acompanhamento semanal da produção |
| Atraso ou insuficiência das amostras de florestas plantadas | Prazo-limite em janeiro de 2027, uso auxiliar do MapBiomas e de interpretação visual, e registro formal da limitação |
| Vigor abaixo da meta de 80% | Ajustes testados antes do Produto 3 e relato das precisões por tipo de degradação |
| Diferença entre a série de continuação e a versão aprimorada | Série de continuação mantida como referência oficial e diferenças documentadas nos Produtos 2 e 3 |
| Ausência do ano de 2026 no MapBiomas Coleção 11 | Destino das conversões relatado até o último ano disponível e atualizado com nova coleção |

---

## **10\. Referências**

Isik MS, Parente L, Consoli D, Sloat L, Mesquita VV, Ferreira LG, Sabbatini S, Stanimirova R, Teles NM, Robinson N, Costa Junior C, Hengl T. 2025\. Light use efficiency (LUE) based bimonthly gross primary productivity (GPP) for global grasslands at 30 m spatial resolution (2000–2022) PeerJ 13:e19774 [https\://doi.org/10.7717/peerj.19774](https://doi.org/10.7717/peerj.19774)

Parente, L.; Mesquita, V.; Miziara, F.; Baumann, L.; Ferreira, L. Assessing the pasturelands and livestock dynamics in Brazil, from 1985 to 2017: a novel approach based on high spatial resolution imagery and Google Earth Engine cloud computing. Remote Sensing of Environment, v. 232, 111301, 2019\.

Parente, L. et al. Global distribution of cattle, horses, goats, sheep and buffaloes at 1-km resolution for 2000–2022, based on subnational census data and spatiotemporal machine learning. Research Square (preprint), 2025\.

Pelletier, C.; Webb, G. I.; Petitjean, F. Temporal Convolutional Neural Network for the classification of satellite image time series. Remote Sensing, v. 11, n. 5, 523, 2019\.

Ronneberger, O.; Fischer, P.; Brox, T. U-Net: Convolutional networks for biomedical image segmentation. In: MICCAI 2015, Lecture Notes in Computer Science, v. 9351, p. 234–241, 2015\.

Santos, C. O.; Mesquita, V. V.; Parente, L. L.; Pinto, A. S.; Ferreira, L. G. Assessing the wall-to-wall spatial and qualitative dynamics of the Brazilian pasturelands 2010–2018, based on the analysis of the Landsat data archive. Remote Sensing, v. 14, n. 4, 1024, 2022\.