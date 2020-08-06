---
title: SQL Server tipos de datos en el .NET Framework | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- System.Data library
- System.Data.SqlTypes namespace
- data types [CLR integration]
- SqlTypes library
- database objects [CLR integration], data types
- common language runtime [SQL Server], data types
- building database objects [CLR integration], data types
- mapping data types [CLR integration]
ms.assetid: c70d3ffe-2c32-45a5-849b-ef113dda09b9
author: rothja
ms.author: jroth
ms.openlocfilehash: fe0ed680e7050c58738301256575e4138f21276f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751169"
---
# <a name="sql-server-data-types-in-the-net-framework"></a><span data-ttu-id="9436c-102">Tipos de datos de SQL Server en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9436c-102">SQL Server Data Types in the .NET Framework</span></span>
  <span data-ttu-id="9436c-103">La biblioteca `SqlTypes` forma parte de la biblioteca de clase base de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9436c-103">The `SqlTypes` library is part of the base class library of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="9436c-104">Está diseñado para proporcionar a los tipos de datos la misma semántica y precisión que las encontradas en la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9436c-104">It is designed to provide data types with the same semantics and precision as those found in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="9436c-105">En este tema se describe la nueva semántica para los programadores de .NET Framework y se muestran los tipos implementados en el espacio de nombres `System.Data.SqlTypes` incluido en la biblioteca `System.Data`.</span><span class="sxs-lookup"><span data-stu-id="9436c-105">This topic describes the new semantics to .NET Framework programmers, and introduces the types implemented in the `System.Data.SqlTypes` namespace that is included in the `System.Data` library.</span></span>  
  
 <span data-ttu-id="9436c-106">En la siguiente tabla se muestran los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="9436c-106">This following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="9436c-107">Nulabilidad y comparaciones lógicas de tres valores</span><span class="sxs-lookup"><span data-stu-id="9436c-107">Nullability and Three-Value Logic Comparisons</span></span>](nullability-and-three-value-logic-comparisons.md)  
 <span data-ttu-id="9436c-108">Describe cómo controlar los valores NULL con tipos de datos de integración de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9436c-108">Discusses how NULL values are handled with common language runtime (CLR) integration data types.</span></span>  
  
 [<span data-ttu-id="9436c-109">Intercalación y tipos de datos de integración CLR</span><span class="sxs-lookup"><span data-stu-id="9436c-109">Collation and CLR Integration Data Types</span></span>](collation-and-clr-integration-data-types.md)  
 <span data-ttu-id="9436c-110">Describe la manera en la que se administran las intercalaciones con la integración CLR.</span><span class="sxs-lookup"><span data-stu-id="9436c-110">Describes how collations are handled with CLR integration.</span></span>  
  
 [<span data-ttu-id="9436c-111">Administrar los parámetros de objetos grandes &#40;LOB&#41; en CLR</span><span class="sxs-lookup"><span data-stu-id="9436c-111">Handling Large Object &#40;LOB&#41; Parameters in the CLR</span></span>](handling-large-object-lob-parameters-in-the-clr.md)  
 <span data-ttu-id="9436c-112">Describe la manera de pasar los tipos LOB entre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el CLR.</span><span class="sxs-lookup"><span data-stu-id="9436c-112">Describes how to pass LOB types between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the CLR.</span></span>  
  
 [<span data-ttu-id="9436c-113">Asignar datos de parámetros CLR</span><span class="sxs-lookup"><span data-stu-id="9436c-113">Mapping CLR Parameter Data</span></span>](mapping-clr-parameter-data.md)  
 <span data-ttu-id="9436c-114">Muestra las asignaciones de tipo de datos entre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la integración CLR y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9436c-114">Shows data type mappings between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], CLR integration, and the .NET Framework.</span></span>  
  
  
