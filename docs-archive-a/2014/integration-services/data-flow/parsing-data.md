---
title: Analizar datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- parsing [Integration Services]
- data parsing [Integration Services]
ms.assetid: 8893ea9d-634c-4309-b52c-6337222dcb39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3bd34cd83351e31313ae96ff5709ec999a60f2f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670471"
---
# <a name="parsing-data"></a><span data-ttu-id="2acda-102">Analizar datos</span><span class="sxs-lookup"><span data-stu-id="2acda-102">Parsing Data</span></span>
  <span data-ttu-id="2acda-103">Los flujos de datos de paquetes extraen y cargan datos entre almacenes de datos heterogéneos, que pueden usar diversos tipos de datos estándar y personalizados.</span><span class="sxs-lookup"><span data-stu-id="2acda-103">Data flows in packages extract and load data between heterogeneous data stores, which may use a variety of standard and custom data types.</span></span> <span data-ttu-id="2acda-104">En un flujo de datos, los orígenes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] realizan el trabajo de extraer datos, analizar datos de cadenas y convertir datos en un tipo de datos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2acda-104">In a data flow, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sources do the work of extracting data, parsing string data, and converting data to an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type.</span></span> <span data-ttu-id="2acda-105">Las transformaciones posteriores pueden analizar datos para convertirlos en un tipo de datos diferentes, o bien crear copias de columnas con diferentes tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="2acda-105">Subsequent transformations may parse data to convert it to a different data type, or create column copies with different data types.</span></span> <span data-ttu-id="2acda-106">Las expresiones usadas en los componentes también pueden convertir argumentos y operandos en diferentes tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="2acda-106">Expressions used in components may also cast arguments and operands to different data types.</span></span> <span data-ttu-id="2acda-107">Finalmente, cuando se cargan los datos en un almacén de datos, el destino puede analizar los datos para convertirlos en un tipo de datos que usa el destino.</span><span class="sxs-lookup"><span data-stu-id="2acda-107">Finally, when the data is loaded into a data store, the destination may parse the data to convert it to a data type that the destination uses.</span></span> <span data-ttu-id="2acda-108">Para obtener más información, vea [Integration Services Data Types](integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="2acda-108">For more information, see [Integration Services Data Types](integration-services-data-types.md).</span></span>  
  
## <a name="types-of-parsing"></a><span data-ttu-id="2acda-109">Tipos de análisis</span><span class="sxs-lookup"><span data-stu-id="2acda-109">Types of Parsing</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="2acda-110">proporciona dos tipos de análisis para convertir los datos: el análisis rápido y el análisis estándar.</span><span class="sxs-lookup"><span data-stu-id="2acda-110">provides two types of parsing for converting data: Fast parse and Standard parse.</span></span>  
  
-   <span data-ttu-id="2acda-111">El análisis rápido es un conjunto rápido y simple de rutinas de análisis que no admite conversiones de tipos de datos específicos de la configuración regional sino solo los formatos de fecha y hora usados con mayor frecuencia.</span><span class="sxs-lookup"><span data-stu-id="2acda-111">Fast parse is a fast, simple set of parsing routines that does not support locale-specific data type conversions, and supports only the most frequently used date and time formats.</span></span> <span data-ttu-id="2acda-112">Para más información, consulte [Fast Parse](../fast-parse.md).</span><span class="sxs-lookup"><span data-stu-id="2acda-112">For more information, see [Fast Parse](../fast-parse.md).</span></span>  
  
-   <span data-ttu-id="2acda-113">El análisis estándar es un conjunto completo de rutinas de análisis que admite todas las conversiones de tipos de datos proporcionadas por las API de conversión de tipo de datos de automatización disponibles en Oleaut32.dll y Ole2dsip.dll.</span><span class="sxs-lookup"><span data-stu-id="2acda-113">Standard parse is a rich set of parsing routines that supports all the data type conversions that are provided by the Automation data type conversion APIs available in Oleaut32.dll and Ole2dsip.dll.</span></span> <span data-ttu-id="2acda-114">Para más información, consulte [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="2acda-114">For more information, see [Standard Parse](../standard-parse.md).</span></span>  
  
  
