---
title: Planes de mantenimiento de bases de datos reemplazados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- suspended database maintenance plans
- database maintenance plans [SQL Server Agent]
- maintenance plans [SQL Server Agent]
ms.assetid: efac127c-6c81-4c7a-a6c4-9aae5d15545d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3aea75cc4ecc94ccbaeb1f35cecd0b18ff3a65ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662508"
---
# <a name="database-maintenance-plans-superseded"></a><span data-ttu-id="bf630-102">Se han reemplazado los planes de mantenimiento de bases de datos</span><span class="sxs-lookup"><span data-stu-id="bf630-102">Database maintenance plans superseded</span></span>
    
## <a name="component"></a><span data-ttu-id="bf630-103">Componente</span><span class="sxs-lookup"><span data-stu-id="bf630-103">Component</span></span>  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="bf630-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agente de</span><span class="sxs-lookup"><span data-stu-id="bf630-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="bf630-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf630-105">Description</span></span>  
 <span data-ttu-id="bf630-106">Los planes de mantenimiento de bases de datos existentes se actualizarán y continuarán funcionando.</span><span class="sxs-lookup"><span data-stu-id="bf630-106">Existing database maintenance plans are upgraded and continue to work.</span></span> <span data-ttu-id="bf630-107">Sin embargo, no podrá crear nuevos planes de mantenimiento de bases de datos utilizando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf630-107">However, you will not be able to create new database maintenance plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="bf630-108">Para ver los planes de mantenimiento en el Explorador de objetos, expanda Administración y, a continuación, expanda Heredado.</span><span class="sxs-lookup"><span data-stu-id="bf630-108">To view the maintenance plans in Object Explorer, expand Management, and then expand Legacy.</span></span> <span data-ttu-id="bf630-109">Puede migrar los planes de mantenimiento de bases de datos existentes al nuevo formato seleccionando **migrar** en el menú contextual de cualquier plan de mantenimiento de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="bf630-109">You can migrate existing database maintenance plans to the new format by selecting **Migrate** from the context menu for any database maintenance plan.</span></span> <span data-ttu-id="bf630-110">Dado que la nueva característica de plan de mantenimiento no sustituye directamente a los planes de mantenimiento de bases de datos, es posible que se pierda alguna funcionalidad tras la migración.</span><span class="sxs-lookup"><span data-stu-id="bf630-110">Because the new maintenance plan feature is not a direct replacement of database maintenance plans, some functionality might be lost after migration.</span></span> <span data-ttu-id="bf630-111">Al migrar un plan de mantenimiento de bases de datos no se elimina el plan anterior, por lo que puede probar su funcionalidad como plan de mantenimiento antes de quitar el plan anterior.</span><span class="sxs-lookup"><span data-stu-id="bf630-111">Migrating a database maintenance plan does not delete the old plan, so you can test its functionality as a maintenance plan before removing the old plan.</span></span>  
  
 <span data-ttu-id="bf630-112">Las características siguientes ya no se admiten dentro de los planes de mantenimiento de bases de datos:</span><span class="sxs-lookup"><span data-stu-id="bf630-112">The following features are no longer supported within database maintenance plans:</span></span>  
  
-   <span data-ttu-id="bf630-113">Trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="bf630-113">Log shipping</span></span>  
  
-   <span data-ttu-id="bf630-114">La opción **intentar reparar los problemas secundarios** de la tarea de comprobación de integridad de la **base de datos**</span><span class="sxs-lookup"><span data-stu-id="bf630-114">The **Attempt to repair any minor problems** option of the **Database Integrity Check** task</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="bf630-115">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="bf630-115">Corrective Action</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bf630-116">evita que el trasvase de registros se incluya en un plan de mantenimiento de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="bf630-116">prevents log shipping from being included in a database maintenance plan.</span></span> <span data-ttu-id="bf630-117">Para obtener más información, vea "Trasvase de registros" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf630-117">For more information, see "Log Shipping" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
  
