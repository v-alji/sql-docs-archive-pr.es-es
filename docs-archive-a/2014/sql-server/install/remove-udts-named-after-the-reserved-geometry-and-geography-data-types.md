---
title: Quite los UDT con el nombre de los tipos de datos GEOMETRY y Geography reservados | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- geometry data type [SQL Server], UDTs
- geography data type [SQL Server], UDTs
ms.assetid: a167ce3a-50b4-4e77-a884-adb23b586c72
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4977d45d53e1114edc8e04ad504963bae0b9eb9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751698"
---
# <a name="remove-udts-named-after-the-reserved-geometry-and-geography-data-types"></a><span data-ttu-id="bbac7-102">Quitar UDT con nombre después de los tipos de datos GEOMETRY y GEOGRAPHY reservados</span><span class="sxs-lookup"><span data-stu-id="bbac7-102">Remove UDTs named after the reserved GEOMETRY and GEOGRAPHY data types</span></span>
  <span data-ttu-id="bbac7-103">El Asesor de actualizaciones detectó un tipo definido por el usuario (UDT) que se denomina después de un término reservado para los tipos de datos `geometry` o `geography`.</span><span class="sxs-lookup"><span data-stu-id="bbac7-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for either the `geometry` or the `geography` data types.</span></span> <span data-ttu-id="bbac7-104">Los tipos de datos `geometry` y `geography` son parte de la nueva característica de datos espaciales.</span><span class="sxs-lookup"><span data-stu-id="bbac7-104">The `geometry` and `geography` data types are part of the spatial data feature.</span></span>  
  
## <a name="component"></a><span data-ttu-id="bbac7-105">Componente</span><span class="sxs-lookup"><span data-stu-id="bbac7-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="bbac7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bbac7-106">Description</span></span>  
 <span data-ttu-id="bbac7-107">Las condiciones utilizadas para los tipos de datos espaciales no se deberían utilizar como nombres para Common Language Runtime (CLR) o UDT de alias.</span><span class="sxs-lookup"><span data-stu-id="bbac7-107">The terms used for spatial data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="bbac7-108">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="bbac7-108">Corrective Action</span></span>  
 <span data-ttu-id="bbac7-109">Elimine el UDT que se denomina con el tipo de datos y vuelva a crearlo con un nombre no reservado.</span><span class="sxs-lookup"><span data-stu-id="bbac7-109">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="bbac7-110">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="bbac7-110">External Resources</span></span>  
 [<span data-ttu-id="bbac7-111">Crear un tipo definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="bbac7-111">Creating a User-Defined Type</span></span>](../../relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types.md)  
  
 [<span data-ttu-id="bbac7-112">Información general de los tipos de datos espaciales</span><span class="sxs-lookup"><span data-stu-id="bbac7-112">Spatial Data Types Overview</span></span>](../../relational-databases/spatial/spatial-data-types-overview.md)  
  
  
