---
title: INFORMATION_SCHEMA. Esquemas devuelve los nombres de esquema en una base de datos, no en las bases de datos de una instancia | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- INFORMATION_SCHEMA.SCHEMATA view
ms.assetid: 4337b643-910d-47d7-bea8-f4052066b9a2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cb2a34a59bf6257c188210fc7bf2aeacb70f6b7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676823"
---
# <a name="information_schemaschemata-returns-schema-names-in-a-database-not-databases-in-an-instance"></a><span data-ttu-id="c23bb-102">INFORMATION_SCHEMA.SCHEMATA devuelve los nombres de esquema en una base de datos, no las bases de datos en una instancia</span><span class="sxs-lookup"><span data-stu-id="c23bb-102">INFORMATION_SCHEMA.SCHEMATA returns schema names in a database, not databases in an instance</span></span>
  <span data-ttu-id="c23bb-103">El Asesor de actualizaciones ha detectado instrucciones que hacen referencia a la vista INFORMATION_SCHEMA.SCHEMATA.</span><span class="sxs-lookup"><span data-stu-id="c23bb-103">Upgrade Advisor detected statements that reference the INFORMATION_SCHEMA.SCHEMATA view.</span></span> <span data-ttu-id="c23bb-104">En versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], esta vista devolvía todas las bases de datos de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c23bb-104">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this view returned all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c23bb-105">En [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y en versiones posteriores, la vista devuelve todos los esquemas de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="c23bb-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later, the view returns all schemas in a database.</span></span>  
  
## <a name="component"></a><span data-ttu-id="c23bb-106">Componente</span><span class="sxs-lookup"><span data-stu-id="c23bb-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="c23bb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c23bb-107">Description</span></span>  
 <span data-ttu-id="c23bb-108">En versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la vista INFORMATION_SCHEMA.SCHEMATA devolvía todas las bases de datos de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c23bb-108">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the INFORMATION_SCHEMA.SCHEMATA view returned all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c23bb-109">Ahora, la vista devuelve todos los esquemas en una base de datos, lo cual cumple el estándar SQL.</span><span class="sxs-lookup"><span data-stu-id="c23bb-109">Now, the view returns all schemas in a database, which complies with the SQL Standard.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c23bb-110">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="c23bb-110">Corrective Action</span></span>  
 <span data-ttu-id="c23bb-111">Modifique la aplicación para que haga referencia a la vista de catálogo **Sys. Databases** para devolver todas las bases de datos de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c23bb-111">Modify your application to reference the **sys.databases** catalog view to return all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c23bb-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c23bb-112">See Also</span></span>  
 <span data-ttu-id="c23bb-113">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="c23bb-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="c23bb-114">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="c23bb-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
