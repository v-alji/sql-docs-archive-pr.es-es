---
title: Análisis rápido | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- fast parse [Integration Services]
ms.assetid: 6688707d-3c5b-404e-aa2f-e13092ac8d95
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 343b8b8b74338512dbf29b3d2efd436df1ffa8ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747696"
---
# <a name="fast-parse"></a><span data-ttu-id="c695e-102">Fast Parse</span><span class="sxs-lookup"><span data-stu-id="c695e-102">Fast Parse</span></span>
  <span data-ttu-id="c695e-103">El análisis rápido ofrece un conjunto rápido y simple de rutinas para analizar datos.</span><span class="sxs-lookup"><span data-stu-id="c695e-103">Fast parse provides a fast, simple set of routines for parsing data.</span></span> <span data-ttu-id="c695e-104">Estas rutinas no son dependientes de la configuración regional y solo admiten un subconjunto de formatos de fecha, hora y número entero.</span><span class="sxs-lookup"><span data-stu-id="c695e-104">These routines are not locale-sensitive and they support only a subset of date, time, and integer formats.</span></span>  
  
## <a name="requirements-and-limitations"></a><span data-ttu-id="c695e-105">Requisitos y limitaciones</span><span class="sxs-lookup"><span data-stu-id="c695e-105">Requirements and Limitations</span></span>  
 <span data-ttu-id="c695e-106">Al implementar el análisis rápido, un paquete arriesga su capacidad de interpretar los datos numéricos y de fecha y hora en formatos específicos de configuración regional, así como varios formatos ISO 8601 básicos y extendidos utilizados con frecuencia, pero el paquete mejora su rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c695e-106">By implementing fast parse, a package forfeits its ability to interpret date, time, and numeric data in locale-specific formats and many frequently used ISO 8601 basic and extended formats, but the package enhances its performance.</span></span> <span data-ttu-id="c695e-107">Por ejemplo, el análisis rápido admite únicamente las representaciones de formato de fecha usadas con más frecuencia, como DDMMYYYY y DD-MM-YYYY, no realiza ningún análisis específico de una configuración regional, no reconoce caracteres especiales en los datos de moneda y no puede convertir una representación hexadecimal o científica de números enteros.</span><span class="sxs-lookup"><span data-stu-id="c695e-107">For example, fast parse supports only the most commonly used date format representations such as YYYYMMDD and YYYY-MM-DD, does not perform locale-specific parsing, does not recognize special characters in currency data, and cannot convert hexadecimal or scientific representation of integers.</span></span>  
  
 <span data-ttu-id="c695e-108">El análisis rápido solamente está disponible cuando se utiliza el origen de archivo plano o la transformación Conversión de datos.</span><span class="sxs-lookup"><span data-stu-id="c695e-108">Fast parse is available only when you use the Flat File source or the Data Conversion transformation.</span></span> <span data-ttu-id="c695e-109">El aumento del rendimiento puede ser considerable, por lo que debería tener en cuenta la posibilidad de utilizar el análisis rápido en estos componentes de flujo de datos, si es posible.</span><span class="sxs-lookup"><span data-stu-id="c695e-109">The increase in performance can be significant, and you should consider using fast parse in these data flow components if you can.</span></span>  
  
 <span data-ttu-id="c695e-110">Si el flujo de datos en el paquete exige un análisis sensible a la configuración regional, se recomienda el análisis estándar en lugar del rápido.</span><span class="sxs-lookup"><span data-stu-id="c695e-110">If the data flow in the package requires locale-sensitive parsing, standard parse is recommended instead of fast parse.</span></span> <span data-ttu-id="c695e-111">Por ejemplo el análisis rápido no reconoce los datos relacionados con la configuración regional que incluyen símbolos decimales como la coma, formatos de fecha que no sean los formatos año-mes-fecha y símbolos de moneda.</span><span class="sxs-lookup"><span data-stu-id="c695e-111">For example, fast parse does not recognize locale-sensitive data that includes decimal symbols such as the comma, date formats other than year-month-date formats, and currency symbols.</span></span>  
  
 <span data-ttu-id="c695e-112">Las representaciones truncadas que implican una o más partes de una fecha, como el siglo, año o mes, no son reconocidas por el análisis rápido.</span><span class="sxs-lookup"><span data-stu-id="c695e-112">Truncated representations that imply one or more date parts, such as a century, a year, or a month, are not recognized by fast parse.</span></span> <span data-ttu-id="c695e-113">Por ejemplo, el análisis rápido no reconoce el formato "**-YYMM**", que especifica un año y mes en un siglo específico, ni "**--MM**", que especifica un mes en un año implícito.</span><span class="sxs-lookup"><span data-stu-id="c695e-113">For example, fast parse recognizes neither the '**-YYMM**' format, which specifies a year and month in an implied century, nor '**--MM**', which specifies a month in an implied year.</span></span> <span data-ttu-id="c695e-114">Sin embargo, se reconocen algunas representaciones con precisión reducida.</span><span class="sxs-lookup"><span data-stu-id="c695e-114">However, some representations with reduced precision are recognized.</span></span> <span data-ttu-id="c695e-115">Por ejemplo, el análisis rápido reconoce el formato 'hhmm;', que indica solamente horas y minutos, y '**YYYY**', que indica el año solamente.</span><span class="sxs-lookup"><span data-stu-id="c695e-115">For example, fast parse recognizes the 'hhmm;' format, which indicates hour and minute only, and '**YYYY**', which indicates year only.</span></span>  
  
 <span data-ttu-id="c695e-116">El análisis rápido se especifica en el nivel de columna.</span><span class="sxs-lookup"><span data-stu-id="c695e-116">Fast parse is specified at the column level.</span></span> <span data-ttu-id="c695e-117">En el origen de archivo plano y en la transformación Conversión de datos, puede especificarse el análisis rápido en las columnas de salida.</span><span class="sxs-lookup"><span data-stu-id="c695e-117">In the Flat File source and the Data Conversion transformation, you can specify Fast parse on output columns.</span></span> <span data-ttu-id="c695e-118">Las entradas y salidas pueden incluir columnas sensibles y no sensibles a la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="c695e-118">Inputs and outputs can include both locale-sensitive and locale-insensitive columns.</span></span>  
  
 <span data-ttu-id="c695e-119">Para obtener más información sobre los formatos de datos que admiten el análisis rápido, vea [Numeric Data Formats](../../2014/integration-services/numeric-data-formats.md) y [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span><span class="sxs-lookup"><span data-stu-id="c695e-119">For more information about the data formats that Fast parse supports, see [Numeric Data Formats](../../2014/integration-services/numeric-data-formats.md) and [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="c695e-120">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c695e-120">Related Tasks</span></span>  
 [<span data-ttu-id="c695e-121">Configurar el análisis rápido</span><span class="sxs-lookup"><span data-stu-id="c695e-121">Set Fast Parse</span></span>](../../2014/integration-services/set-fast-parse.md)  
  
  
