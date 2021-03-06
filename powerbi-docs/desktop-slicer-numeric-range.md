---
title: Usar a segmentação de intervalo numérico no Power BI Desktop
description: Saiba como usar uma segmentação para restringir a intervalos numéricos no Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 135e6ff76a0972bdedbff3eaf7ab1222f82a94ab
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2018
ms.locfileid: "39331156"
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Usar a segmentação de intervalo numérico no Power BI Desktop
Com a **segmentação de intervalo numérico**, você pode aplicar todos os tipos de filtros a qualquer coluna numérica no modelo de dados. Você pode optar por filtrar como **entre** números, **menor ou igual** a um número ou **maior ou igual** a um número. Embora possa parecer simples, essa é uma maneira muito eficiente de filtrar os dados.

![Visual com segmentação de intervalo numérico](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## <a name="using-the-numeric-range-slicer"></a>Usando a segmentação de intervalo numérico
Você pode usar a segmentação de intervalo numérico como qualquer outra segmentação de dados. Basta criar um visual de **segmentação** para o relatório e, em seguida, selecionar um valor numérico para o valor **Campo**. Na imagem a seguir, o campo *LineTotal* está selecionado.

![Criar uma segmentação de intervalo numérico](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

Selecione o link de seta para baixo no canto superior direito da **segmentação de intervalo numérico** e um menu será exibido.

![Menu de segmentação de intervalo numérico](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-2-between.png)

Para o intervalo numérico, você pode selecionar uma das três seleções a seguir:

* Entre
* Menor ou igual a
* Maior ou igual a

Ao selecionar **Entre** no menu, um controle deslizante será exibido e você poderá filtrar os valores numéricos que estão entre os números. Além de usar a barra de controle deslizante, você pode clicar em qualquer caixa e digitar os valores. Isso é prático quando você deseja segmentar em números inteiros específicos e a granularidade de movimentação da barra de segmentação dificulta encontrar exatamente esse número.

Na imagem a seguir, a página do relatório é filtrada por valores de *LineTotal* que variam entre 2500,00 e 6000,00.

![Segmentação de intervalo numérico com Entre](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-3-between-range.png)

Quando selecionamos **menor ou igual a**, a alça esquerda (valor mais baixo) da barra de controle deslizante desaparece e somente podemos ajustar o limite superior da barra de controle deslizante. Na imagem a seguir, definimos o máximo da barra deslizante como 5928,19.

![Segmentação de intervalo numérico com Menor que](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-4-less-than.png)

Por fim, se selecionarmos **maior ou igual a**, a alça da barra de controle deslizante direita (valor mais alto) desaparecerá e poderemos ajustar o valor menor, conforme é mostrado na imagem a seguir. Agora apenas os itens com *LineTotal* maior ou igual a 4902,99 serão exibidos nos visuais na página do relatório.

![Segmentação de intervalo numérico com Maior que](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-5-greater-than.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer"></a>Ajustar para números inteiros com a segmentação de intervalo numérico

Uma segmentação de intervalo numérico será ajustada para números inteiros se o tipo de dados do campo subjacente for um **Número Inteiro**. Isso permite que a segmentação se alinhe corretamente com números inteiros. Os campos de tipo **Número Decimal** permitem que você insira ou selecione frações de um número. A formatação aplicada na caixa de texto corresponde ao conjunto de formatação no campo, mesmo que seja possível digitar ou selecionar números mais precisos.


## <a name="limitations-and-considerations"></a>Limitações e considerações
No momento, as seguintes considerações e limitações aplicam-se à **segmentação de intervalo numérico**:

* No momento, a **segmentação de intervalo numérico** filtra todas as linhas subjacentes nos dados, não qualquer valor agregado. Por exemplo, se o campo *Valor de Vendas* for usado, cada transação com base em *Valor de Vendas* será filtrada, não a soma de *Valor de Vendas* de cada ponto de dados de um visual.
* No momento, isso não funciona com Medidas.
* Você pode digitar qualquer número de caixas de texto em uma segmentação de numérica, mesmo que ela esteja fora do intervalo de valores da coluna subjacente. Isso permite que você defina os filtros quando souber que os dados poderão mudar no futuro.
