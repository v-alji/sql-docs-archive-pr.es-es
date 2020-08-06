---
title: Las constantes grandes se escriben como tipos de valores grandes en los modos de compatibilidad 90 o posterior | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- binary constants
- CHARINDEX function
- constants
- character string constants
- PATINDEX function
ms.assetid: 6e309fa0-5fb9-45a1-9739-f13fae525bfe
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 58acde8aaebdcac629463edcfb565eed13355ad4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663285"
---
# <a name="large-constants-are-typed-as-large-value-types-in-90-or-later-compatibility-modes"></a><span data-ttu-id="ee26a-102">Las constantes de gran tamaño están tipificadas como tipos de valor grande en los modos de compatibilidad 90 o superiores</span><span class="sxs-lookup"><span data-stu-id="ee26a-102">Large constants are typed as large-value types in 90 or later compatibility modes</span></span>
  <span data-ttu-id="ee26a-103">El Asesor de actualizaciones ha detectado la presencia de constantes grandes.</span><span class="sxs-lookup"><span data-stu-id="ee26a-103">Upgrade Advisor detected the presence of large constants.</span></span> <span data-ttu-id="ee26a-104">Las constantes de cadena de caracteres y las constantes binarias cuyo tamaño sea superior a 8.000 bytes se tratan como tipos de datos de objetos grandes en [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee26a-104">Character string constants and binary constants that are more than 8,000 bytes in size are treated as large object data types in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="ee26a-105">En [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y en versiones posteriores, las constantes de cadena de caracteres de gran tamaño, Unicode y binarias están tipificadas como tipos de valor grande.</span><span class="sxs-lookup"><span data-stu-id="ee26a-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, large character, Unicode, and binary constants, are typed as large-value types.</span></span>  
  
## <a name="component"></a><span data-ttu-id="ee26a-106">Componente</span><span class="sxs-lookup"><span data-stu-id="ee26a-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="ee26a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee26a-107">Description</span></span>  
 <span data-ttu-id="ee26a-108">Cuando se utilizan las funciones de cadena, como CHARINDEX y PATINDEX, con cadenas o constantes binarias que superan los 8.000 bytes, [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] devuelve el número de error 8116, mientras que [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y las versiones posteriores devuelven el número de error 8152.</span><span class="sxs-lookup"><span data-stu-id="ee26a-108">When string functions, such as CHARINDEX and PATINDEX, are used with string or binary constants that exceed 8,000 bytes, [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] returns error number 8116, and [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions return error number 8152.</span></span>  
  
 <span data-ttu-id="ee26a-109">En [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], las funciones de cadena devuelven el error 8116 cuando se utilizan con los tipos de datos `text`, `ntext` e `image`.</span><span class="sxs-lookup"><span data-stu-id="ee26a-109">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], the string functions return error 8116 when they are used with the `text`, `ntext`, and `image` data types.</span></span>  
  
 <span data-ttu-id="ee26a-110">En [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y en versiones posteriores, las constantes grandes se tratan como tipos de datos `varchar(max)`, `nvarchar(max)` y `varbinary(max)`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ee26a-110">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, the large constants are treated as `varchar(max)`, `nvarchar(max)`, and `varbinary(max)` data types, respectively.</span></span> <span data-ttu-id="ee26a-111">Estos tipos de datos son compatibles con funciones de cadena.</span><span class="sxs-lookup"><span data-stu-id="ee26a-111">These data types are compatible with string functions.</span></span>  
  
 <span data-ttu-id="ee26a-112">En [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y en versiones posteriores, las funciones de cadena, como CHARINDEX y PATINDEX, asumen que la cadena que contiene la secuencia de caracteres a buscar tienen menos de 8.000 bytes.</span><span class="sxs-lookup"><span data-stu-id="ee26a-112">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later versions, string functions, such as CHARINDEX and PATINDEX, assume the string that contains the sequence of characters to be found is less than 8,000 bytes.</span></span> <span data-ttu-id="ee26a-113">Esta es la razón por la cual se produce el error 8152 con CHARINDEX y PATINDEX.</span><span class="sxs-lookup"><span data-stu-id="ee26a-113">This is why error 8152 is raised for CHARINDEX and PATINDEX.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee26a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee26a-114">See Also</span></span>  
 <span data-ttu-id="ee26a-115">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="ee26a-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="ee26a-116">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="ee26a-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
