# Segmentação de Instâncias em Imagens Médicas - Abordagem Clássica

Este repositório contém a implementação de um pipeline de Processamento Digital de Imagens (PDI) para a segmentação de instâncias em células/lesões de melanoma, utilizando estritamente algoritmos fundamentais de PDI e de maneira deterministica, tais 
algoritmos estão descritos na literatura de **Gonzalez & Woods**.

**Objetivo:** Realizar a segmentação sem o uso de redes neurais (Deep Learning) ou funções de alto nível ("caixa preta"), demonstrando a compreensão matemática dos operadores morfológicos e estatísticos.

## Metodologia

O pipeline foi construído "do zero" utilizando `NumPy` para operações matriciais. As etapas incluem:

1.  **Pré-processamento:** Conversão para escala de cinza, usando a conversão para tons de cinza (Y = 0.299R + 0.587G + 0.114B) - Cap. 6 G&W, que foca na intensidade percebida, e se valendo disso para ter uma melhor representação em GS
    e Suavização com Filtro Gaussiano (Convolução manual).
3.  **Segmentação Global:** Implementação manual do algoritmo de **Otsu** para binarização automática baseada em histograma, para maximixação de variância entre classes.
4.  **Morfologia Matemática:**
    * **Fechamento (Closing):** Para correção de ruídos internos.
    * **Dilatação:** Para ajuste de bordas.
5.  **Geometria Computacional:** Implementação do algoritmo **Monotone Chain** para obtenção do Fecho Convexo (Convex Hull), onde antes é feito a escolha do maior componente conexo para que ruídos possam ser descartados.
6.  **Visualização:** Algoritmo de *Scanline Fill* para criação de máscaras e sobreposição (overlay).

## Tecnologias Utilizadas

* Python 3
* NumPy (Operações matriciais)
* Matplotlib (Visualização)
* Scikit-Image (Apenas para I/O de arquivos)

## Como Executar

1. Clone o repositório:
   ```bash
   git clone [https://github.com/ArturDeLima/Classic-IP-Instance-Segmentation-Melanoma-.git](https://github.com/ArturDeLima/Classic-IP-Instance-Segmentation-Melanoma-.git)
2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
3. Abra o Jupyter Notebook:
   ```bash
    jupyter notebook trabalho_pdi.ipynb


## Demonstração de funcionamento

<img width="1000" height="607" alt="image" src="https://github.com/user-attachments/assets/32ca8d56-c968-44e3-8abe-7ea117874bc3" />


Autor: [Artur Lima]
Disciplina: Processamento de Imagens





