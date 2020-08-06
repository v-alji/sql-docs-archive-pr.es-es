---
title: Intercalación y tipos de datos de integración CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- data types [CLR integration]
- parameter collation [CLR integration]
- collations [CLR integration]
ms.assetid: 6ebaed8e-2e2b-4f6d-bf4b-bc25452de441
author: rothja
ms.author: jroth
ms.openlocfilehash: 1a5b0367487aeb80355b8c5c976818e1b6c1ac04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751185"
---
# <a name="collation-and-clr-integration-data-types"></a><span data-ttu-id="72cd0-102">Intercalación y tipos de datos de integración CLR</span><span class="sxs-lookup"><span data-stu-id="72cd0-102">Collation and CLR Integration Data Types</span></span>
  <span data-ttu-id="72cd0-103">En [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], el objeto `CompareInfo` administra las intercalaciones.</span><span class="sxs-lookup"><span data-stu-id="72cd0-103">In the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], the `CompareInfo` object handles collations.</span></span> <span data-ttu-id="72cd0-104">Las interfaces de programación de aplicaciones (API) de cadenas de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] utilizan la propiedad `CompareInfo` asociada al objeto `CultureInfo` del subproceso actual para comparar las cadenas.</span><span class="sxs-lookup"><span data-stu-id="72cd0-104">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] string application programming interfaces (APIs) use the `CompareInfo` property associated with the `CultureInfo` object of the current thread to perform string comparisons.</span></span> <span data-ttu-id="72cd0-105">La configuración predeterminada del `CultureInfo` objeto se basa en la [!INCLUDE[msCoName](../../includes/msconame-md.md)] configuración regional de Windows del equipo en el que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="72cd0-105">The default setting of the `CultureInfo` object is based on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows locale setting for the computer on which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span> <span data-ttu-id="72cd0-106">Esto determina la semántica de comparación predeterminada para comparar valores de `CultureInfo` si no se ha especificado ningún `System.String` concreto.</span><span class="sxs-lookup"><span data-stu-id="72cd0-106">This determines the default comparison semantics, if no explicit `CultureInfo` is specified, for comparisons of `System.String` values.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="72cd0-107">no cambia de forma explícita la propiedad `CompareInfo` para la intercalación de base de datos o de servidor.</span><span class="sxs-lookup"><span data-stu-id="72cd0-107">does not explicitly change the `CompareInfo` property to the database or server collation.</span></span> <span data-ttu-id="72cd0-108">Si es necesario, los usuarios deben establecer la propiedad `CompareInfo` pertinente en sus rutinas.</span><span class="sxs-lookup"><span data-stu-id="72cd0-108">If required, users must set the appropriate `CompareInfo` property in their routines.</span></span>  
  
## <a name="parameter-collation"></a><span data-ttu-id="72cd0-109">Intercalación de parámetros</span><span class="sxs-lookup"><span data-stu-id="72cd0-109">Parameter Collation</span></span>  
 <span data-ttu-id="72cd0-110">Cuando se crea una rutina de Common Language Runtime (CLR) y enlazado a la rutina hay un parámetro de un método CLR del tipo `SQLString`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crea una instancia del parámetro con la intercalación predeterminada de la base de datos que contiene la rutina que hace la llamada.</span><span class="sxs-lookup"><span data-stu-id="72cd0-110">When you create a common language runtime (CLR) routine, and a parameter of a CLR method bound to the routine is of type `SQLString`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates an instance of the parameter with the default collation of the database containing the calling routine.</span></span> <span data-ttu-id="72cd0-111">Si un parámetro no es `SqlType` (por ejemplo, `String` en lugar de `SQLString`), la información de intercalación de la base de datos no se asocia al parámetro.</span><span class="sxs-lookup"><span data-stu-id="72cd0-111">If a parameter is not a `SqlType` (for example, `String` rather than `SQLString`), the collation information from the database is not associated with the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72cd0-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72cd0-112">See Also</span></span>  
 [<span data-ttu-id="72cd0-113">Tipos de datos de SQL Server en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="72cd0-113">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
