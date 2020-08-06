---
title: Generar elementos para valores NULL mediante el parámetro XSINIL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, null values
- null values [SQL Server], XML
- ELEMENTS directive
- XSINIL parameter
ms.assetid: 2dbc4e48-1cae-4d83-b371-3265da9687cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 602de12b5aa9be8997fbd49a2f23e0b73444aac0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751961"
---
# <a name="generate-elements-for-null-values-with-the-xsinil-parameter"></a><span data-ttu-id="d734f-102">Generar elementos para valores NULL mediante el parámetro XSINIL</span><span class="sxs-lookup"><span data-stu-id="d734f-102">Generate Elements for NULL Values with the XSINIL Parameter</span></span>
  <span data-ttu-id="d734f-103">La directiva **ELEMENTS** genera XML en el cual cada valor de columna se asigna a un elemento del XML.</span><span class="sxs-lookup"><span data-stu-id="d734f-103">The **ELEMENTS** directive constructs XML in which each column value maps to an element in the XML.</span></span> <span data-ttu-id="d734f-104">Si el valor de la columna es NULL, no se agrega ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="d734f-104">If the column value is NULL, no element is added.</span></span> <span data-ttu-id="d734f-105">Al especificar el parámetro **XSINIL** opcional en la directiva ELEMENTS, se puede solicitar que también se cree un elemento para el valor NULL.</span><span class="sxs-lookup"><span data-stu-id="d734f-105">By specifying the optional **XSINIL** parameter on the ELEMENTS directive, you can request that an element also be created for the NULL value.</span></span> <span data-ttu-id="d734f-106">En este caso, se devuelve un elemento que tiene el atributo **xsi:nil** establecido en TRUE para cada valor de columna NULL.</span><span class="sxs-lookup"><span data-stu-id="d734f-106">In this case, an element that has the **xsi:nil** attribute set to TRUE is returned for each NULL column value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d734f-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d734f-107">See Also</span></span>  
 [<span data-ttu-id="d734f-108">Usar el modo RAW con FOR XML</span><span class="sxs-lookup"><span data-stu-id="d734f-108">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
