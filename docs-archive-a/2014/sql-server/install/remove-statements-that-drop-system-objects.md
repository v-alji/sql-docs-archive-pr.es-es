---
title: Quitar instrucciones que quitan objetos del sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- drop system objects [SQL Server]
ms.assetid: cdfc3c50-c801-4039-a4bf-b35f876f1c61
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d9e8fbfd4a436e87cee413d95468ccf5dd36b9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662506"
---
# <a name="remove-statements-that-drop-system-objects"></a><span data-ttu-id="6ef68-102">Quitar instrucciones que quiten objetos del sistema</span><span class="sxs-lookup"><span data-stu-id="6ef68-102">Remove statements that drop system objects</span></span>
  <span data-ttu-id="6ef68-103">El Asesor de actualizaciones ha detectado instrucciones que quitan objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="6ef68-103">Upgrade Advisor detected statements that drop system objects.</span></span> <span data-ttu-id="6ef68-104">Los objetos del sistema, incluidos los procedimientos almacenados extendidos, se implementan en la base de datos de **recursos** de solo lectura (mssqlsystemresource) y no se pueden quitar.</span><span class="sxs-lookup"><span data-stu-id="6ef68-104">System objects, including extended stored procedures, are deployed in the read-only **resource** database (mssqlsystemresource) and cannot be dropped.</span></span> <span data-ttu-id="6ef68-105">Modifique las aplicaciones para revocar o denegar el permiso EXECUTE en los objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="6ef68-105">Modify your applications to either revoke or deny EXECUTE permission on system objects.</span></span>  
  
## <a name="component"></a><span data-ttu-id="6ef68-106">Componente</span><span class="sxs-lookup"><span data-stu-id="6ef68-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="6ef68-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ef68-107">Description</span></span>  
 <span data-ttu-id="6ef68-108">Las instrucciones como DROP TABLE, DROP PROCEDURE y **sp_dropextendedproc** no se pueden utilizar para quitar objetos del sistema, porque estos objetos se implementan en la base de datos de solo lectura **resource** .</span><span class="sxs-lookup"><span data-stu-id="6ef68-108">Statements such as DROP TABLE, DROP PROCEDURE, and **sp_dropextendedproc** cannot be used to remove system objects, because these objects are deployed in the read-only **resource** database.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="6ef68-109">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="6ef68-109">Corrective Action</span></span>  
 <span data-ttu-id="6ef68-110">Quite  de las aplicaciones todas las instrucciones que intenten quitar objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="6ef68-110">Remove all statements that try to drop system objects from your applications.</span></span> <span data-ttu-id="6ef68-111">Modifique las aplicaciones para revocar o denegar el permiso EXECUTE en los objetos del sistema.</span><span class="sxs-lookup"><span data-stu-id="6ef68-111">Modify your applications to either revoke or deny EXECUTE permission on system objects.</span></span> <span data-ttu-id="6ef68-112">También puede utilizar la herramienta de configuración de área expuesta (SAC) para deshabilitar algunos de estos objetos.</span><span class="sxs-lookup"><span data-stu-id="6ef68-112">Alternatively, you can use the Surface Area Configuration (SAC) tool to disable some of these objects.</span></span> <span data-ttu-id="6ef68-113">Por ejemplo, el procedimiento almacenado extendido **xp_cmdshell** se puede habilitar o deshabilitar utilizando la herramienta SAC.</span><span class="sxs-lookup"><span data-stu-id="6ef68-113">For example, the **xp_cmdshell** extended stored procedure can be disabled or enabled using the SAC tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef68-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ef68-114">See Also</span></span>  
 <span data-ttu-id="6ef68-115">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="6ef68-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="6ef68-116">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="6ef68-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
