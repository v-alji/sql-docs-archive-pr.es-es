---
title: Análisis estándar | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- standard parse [Integration Services]
- locales [Integration Services]
ms.assetid: dfe835b1-ea52-4e18-a23a-5188c5b6f013
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7cacff710870d372d6bbf8345e05397857c13a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747111"
---
# <a name="standard-parse"></a><span data-ttu-id="bbb96-102">Standard Parse</span><span class="sxs-lookup"><span data-stu-id="bbb96-102">Standard Parse</span></span>
  <span data-ttu-id="bbb96-103">El análisis estándar es un conjunto de rutinas de análisis dependientes de la configuración regional y que admiten todas las conversiones de tipo de datos proporcionadas por las API de conversión de tipo de datos de Automation disponibles en Oleaut32.dll y Ole2dsip.dll.</span><span class="sxs-lookup"><span data-stu-id="bbb96-103">Standard parse is a locale-sensitive set of parsing routines that support all the data type conversions provided by the Automation data type conversion APIs that are available in Oleaut32.dll and Ole2dsip.dll.</span></span> <span data-ttu-id="bbb96-104">El análisis estándar es equivalente a las API de análisis de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="bbb96-104">Standard parse is equivalent to the OLE DB parsing APIs.</span></span>  
  
 <span data-ttu-id="bbb96-105">El análisis estándar proporciona conversión de tipo de datos internacionales y se debe usar si el análisis rápido no admite el formato de datos.</span><span class="sxs-lookup"><span data-stu-id="bbb96-105">Standard parse provides support for data type conversion of international data, and it should be used if the data format is not supported by Fast parse.</span></span> <span data-ttu-id="bbb96-106">Para obtener más información sobre la conversión API de los tipos de automatización de datos, vea "Los tipos de conversión de datos API" en la [biblioteca MSDN](https://go.microsoft.com/fwlink/?LinkId=79427).</span><span class="sxs-lookup"><span data-stu-id="bbb96-106">For more information about the Automation data type conversion API, see "Data Type Conversion APIs" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=79427).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb96-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bbb96-107">See Also</span></span>  
 [<span data-ttu-id="bbb96-108">Fast Parse</span><span class="sxs-lookup"><span data-stu-id="bbb96-108">Fast Parse</span></span>](../../2014/integration-services/fast-parse.md)  
  
  