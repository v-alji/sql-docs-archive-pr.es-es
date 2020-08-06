---
title: Contenido de FORE_COLOR y BACK_COLOR (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- FORE_COLOR contents
- backgrounds [MDX]
- cells [MDX]
- colors [MDX]
- storing cell color information
- cell backgrounds
- BACK_COLOR contents
ms.assetid: ff8f40cb-2ac4-4fc2-9761-7f1b14c17c8c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 748754ec3c90bb44392d7acb7de8f815be24086e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748344"
---
# <a name="fore_color-and-back_color-contents-mdx"></a><span data-ttu-id="25f9f-102">Contenido de FORE_COLOR y BACK_COLOR (MDX)</span><span class="sxs-lookup"><span data-stu-id="25f9f-102">FORE_COLOR and BACK_COLOR Contents (MDX)</span></span>
  <span data-ttu-id="25f9f-103">Las propiedades de celda `FORE_COLOR` y `BACK_COLOR` se utilizan para almacenar información de color del texto y el fondo de una celda, respectivamente, en el formato rojo-verde-azul (RGB) del sistema operativo Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="25f9f-103">The `FORE_COLOR` and `BACK_COLOR` cell properties store color information for the text and the background of a cell, respectively, in the Microsoft Windows operating system red-green-blue (RGB) format.</span></span>  
  
 <span data-ttu-id="25f9f-104">El intervalo válido de un color RGB normal es de cero (0) a 16,777,215 (&H00FFFFFF).</span><span class="sxs-lookup"><span data-stu-id="25f9f-104">The valid range for an ordinary RGB color is zero (0) to 16,777,215 (&H00FFFFFF).</span></span> <span data-ttu-id="25f9f-105">El byte alto de un número de este intervalo es siempre igual a 0; los 3 bytes más bajos, del byte menos significativo al más significativo, determinan la cantidad de rojo, verde y azul, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="25f9f-105">The high byte of a number in this range always equals 0; the lower 3 bytes, from least to most significant byte, determine the amount of red, green, and blue, respectively.</span></span> <span data-ttu-id="25f9f-106">Los componentes rojo, verde y azul se representan mediante un número comprendido entre 0 y 255 (&HFF).</span><span class="sxs-lookup"><span data-stu-id="25f9f-106">The red, green, and blue components are each represented by a number between 0 and 255 (&HFF).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25f9f-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25f9f-107">See Also</span></span>  
 [<span data-ttu-id="25f9f-108">Usar las propiedades de celda &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="25f9f-108">Using Cell Properties &#40;MDX&#41;</span></span>](mdx-cell-properties-using-cell-properties.md)  
  
  
