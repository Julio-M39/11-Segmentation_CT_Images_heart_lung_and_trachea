# U-Net para Segmentação de Imagens de Tomografia Computadorizada (Coração, Pulmão e Traqueia)

OBS: Caso o Github não renderize o arquivo .ipynb use os links abaixo:

- <a href="https://nbviewer.org/github/Julio-M39/11-Segmentation_CT_Images_heart_lung_and_trachea/blob/main/U-Net%20Convolutional%20Networks%20Para%20Segmenta%C3%A7%C3%A3o%20de%20Imagens%20de%20Tomografia%20Computadorizada.ipynb">Clique aqui!</a> 

### Definição do Projeto

Neste Projeto vamos usar um modelo pré-treinado de arquitetura U-Net disponível com o framework PyTorch e construir uma solução de segmentação de imagens de tomografia 
computadorizada para segmentar o coração, o pulmão e a traqueia. Ao final, vamos gerar as previsões em vídeo. Esse modelo de IA sendo capaz de realizar a segmentação pode ser usado como suporte clínico ao especialista médico a fim de detectar possíveis anomalias.

**Base de Imagens**

Para este projeto usaremos as imagens e máscaras disponíveis no link abaixo:

https://www.kaggle.com/sandorkonya/ct-lung-heart-trachea-segmentation

Este conjunto de dados foi modificado a partir do conjunto de dados de segmentação pulmonar por Kónya et al., 2020 no link: 

https://www.kaggle.com/sandorkonya/ct-lung-heart-trachea-segmentation

Os  arquivos  nrrd  originais  foram  salvos no  formato  de  tensor  único  com  máscaras correspondentes  aos  rótulos:  (pulmões,  coração,  traqueia)  como  matrizes  numpy  usando pickle. Cada tensor tem a seguinte forma: número de fatias (slices), largura, altura e número de classes, onde largura, altura e número de fatias são parâmetros individuais de cada id de tensor e número de classes = 3.

Além disso, os dados foram salvos como imagens RGB, onde cada imagem corresponde a  um ID  de slice,  e  suas  imagens-máscara  possuem  canais  correspondentes  a  três  classes: (pulmão, coração, traqueia).

### Etapas do Projeto

- Carregando e Compreendendo os Dados
- Processo de Treinamento
- Funções Para os Cálculos das Métricas
- Função de Perda
- Métricas Por Classe
- Treinamento do Modelo
- Avaliação do Modelo
- Funções Para Geração de Vídeo
- Geração de Vídeo das Previsões do Modelo

### Resultados

| CLASSES  | DICE   | JACCARD | 
| -------- | ------ | ------- | 
| Pulmão   | 97,9 % | 96,8 %  |
| Coração  | 97,9 % | 97,0 %  |
| Traqueia | 95,5 % | 93,5 %  |

**Resultados Visuais**

Na imagem abaixo podemos ver os resultados visuais para a segmentação do pulmão em azul, coração em vermelho e traqueia em amarelo.

<div>
<img src="https://user-images.githubusercontent.com/54995990/189792403-48d44949-f824-46f9-b796-9f59db527940.png" width="800px" />
</div>
