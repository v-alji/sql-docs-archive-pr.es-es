---
title: Quitar UDT&#39;s con nombre del tipo de datos ORDPATH reservado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 474e910a-6abb-4e28-acc2-055338c011d4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0528d19de17781d863e3a42fdef7db558fe5d190
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751701"
---
# <a name="remove-udt39s-named-after-the-reserved-ordpath-data-type"></a><span data-ttu-id="2ac54-102">Quitar UDT&#39;s con nombre del tipo de datos Reserved ORDPATH</span><span class="sxs-lookup"><span data-stu-id="2ac54-102">Remove UDT&#39;s named after the reserved ORDPATH data type</span></span>
  <span data-ttu-id="2ac54-103">El Asesor de actualizaciones detectó un tipo definido por el usuario (UDT) que se denomina con un término reservado para el tipo de datos `ORDPATH`.</span><span class="sxs-lookup"><span data-stu-id="2ac54-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for the `ORDPATH` data type.</span></span>  
  
## <a name="component"></a><span data-ttu-id="2ac54-104">Componente</span><span class="sxs-lookup"><span data-stu-id="2ac54-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="2ac54-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ac54-105">Description</span></span>  
 <span data-ttu-id="2ac54-106">Los términos utilizados para los tipos de datos integrados no se deberían usar como nombres para Common Language Runtime (CLR) o los UDT de alias.</span><span class="sxs-lookup"><span data-stu-id="2ac54-106">The terms used for built-in data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="2ac54-107">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="2ac54-107">Corrective Action</span></span>  
 <span data-ttu-id="2ac54-108">Elimine el UDT que se denomina con el tipo de datos y vuelva a crearlo con un nombre no reservado.</span><span class="sxs-lookup"><span data-stu-id="2ac54-108">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="2ac54-109">Recursos externos</span><span class="sxs-lookup"><span data-stu-id="2ac54-109">External Resources</span></span>  
 [<span data-ttu-id="2ac54-110">Crear un tipo definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="2ac54-110">Creating a User-Defined Type</span></span>](../../relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types.md)  
  
  
