---
title: Administrar parámetros de objetos grandes (LOB) en CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- large data, CLR integration
- LOB data [SQL Server], CLR integration
- SqlBytes data type
- SqlChars data type
ms.assetid: d07956f6-9543-4476-9426-536f95991150
author: rothja
ms.author: jroth
ms.openlocfilehash: ee791c73a6610761c2086723f9e41c2351b37dd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751174"
---
# <a name="handling-large-object-lob-parameters-in-the-clr"></a><span data-ttu-id="5844e-102">Administrar parámetros de objetos grandes (LOB) en CLR</span><span class="sxs-lookup"><span data-stu-id="5844e-102">Handling Large Object (LOB) Parameters in the CLR</span></span>
  <span data-ttu-id="5844e-103">Use `SqlBytes` y `SqlChars` para pasar parámetros de tipo binario de objeto grande (LOB) (`varbinary(max)`) y de tipo de caracteres LOB (`nvarchar(max)`), respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5844e-103">Use `SqlBytes` and `SqlChars` to pass large object (LOB) binary type (`varbinary(max)`) and LOB character type (`nvarchar(max)`) parameters, respectively.</span></span> <span data-ttu-id="5844e-104">Estos tipos permiten la transmisión por secuencias de los valores LOB de la base de datos a la rutina de Common Language Runtime (CLR), en lugar de copiar el valor completo en el espacio administrado.</span><span class="sxs-lookup"><span data-stu-id="5844e-104">These types allow streaming the LOB values from the database to the common language runtime (CLR) routine, instead of copying the entire value into managed space.</span></span> <span data-ttu-id="5844e-105">`SqlBinary` y `SqlString` solo se deben usar para los valores de cadenas de caracteres y binarios pequeños.</span><span class="sxs-lookup"><span data-stu-id="5844e-105">`SqlBinary` and `SqlString` should be used only for small binary and character string values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5844e-106">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5844e-106">See Also</span></span>  
 [<span data-ttu-id="5844e-107">Tipos de datos de SQL Server en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5844e-107">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
