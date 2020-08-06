---
title: Habilitar la integración con CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- clr enabled option
- common language runtime [SQL Server], enabling
ms.assetid: eb3e9c64-7486-42e7-baf6-c956fb311a2c
author: rothja
ms.author: jroth
ms.openlocfilehash: d7187906f1376deb81ca7ff4770af7b12b63c022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747616"
---
# <a name="enabling-clr-integration"></a><span data-ttu-id="dcf2d-102">Habilitar la integración con CLR</span><span class="sxs-lookup"><span data-stu-id="dcf2d-102">Enabling CLR Integration</span></span>
  <span data-ttu-id="dcf2d-103">La característica de integración de Common Language Runtime (CLR) está desactivada de forma predeterminada y se debe habilitar para utilizar objetos que se implementan utilizando la integración CLR.</span><span class="sxs-lookup"><span data-stu-id="dcf2d-103">The common language runtime (CLR) integration feature is off by default, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="dcf2d-104">Para habilitar la integración con CLR, utilice la opción **clr enabled** del **sp_configure** procedimiento almacenado:</span><span class="sxs-lookup"><span data-stu-id="dcf2d-104">To enable CLR integration, use the **clr enabled** option of the **sp_configure** stored procedure:</span></span>  
  
```  
  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'clr enabled', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="dcf2d-105">Puede deshabilitar la integración de CLR estableciendo la opción **clr enabled** en 0.</span><span class="sxs-lookup"><span data-stu-id="dcf2d-105">You can disable CLR integration by setting the **clr enabled** option to 0.</span></span> <span data-ttu-id="dcf2d-106">Al deshabilitar la integración CLR, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] deja de ejecutar todas las rutinas CLR y descarga todos los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="dcf2d-106">When you disable CLR integration, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stops executing all CLR routines and unloads all application domains.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dcf2d-107">Para habilitar la integración con CLR, debe tener el permiso de nivel de servidor ALTER SETTINGs, que se mantiene implícitamente por parte de los miembros de los roles fijos de servidor **sysadmin** y **ServerAdmin** .</span><span class="sxs-lookup"><span data-stu-id="dcf2d-107">To enable CLR integration, you must have ALTER SETTINGS server level permission, which is implicitly held by members of the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dcf2d-108">Es posible que los equipos configurados con grandes cantidades de memoria y un gran número de procesadores no puedan cargar la característica de integración CLR de SQL Server al iniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="dcf2d-108">Computers configured with large amounts of memory and a large number of processors may fail to load the CLR integration feature of SQL Server when starting the server.</span></span> <span data-ttu-id="dcf2d-109">Para solucionar este problema, inicie el servidor con la opción de inicio del servicio **-gmemory_to_reserve** [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y especifique un valor de memoria suficientemente grande.</span><span class="sxs-lookup"><span data-stu-id="dcf2d-109">To address this issue, start the server by using the **-gmemory_to_reserve**[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service startup option, and specify a memory value large enough.</span></span> <span data-ttu-id="dcf2d-110">Para más información, consulte [Opciones de inicio del servicio de motor de base de datos](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="dcf2d-110">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dcf2d-111">No se admite la ejecución de Common Language Runtime (CLR) con "agrupación ligera".</span><span class="sxs-lookup"><span data-stu-id="dcf2d-111">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="dcf2d-112">Antes de habilitar la integración CLR, debe deshabilitar la agrupación ligera.</span><span class="sxs-lookup"><span data-stu-id="dcf2d-112">Before enabling CLR integration, you must disable lightweight pooling.</span></span> <span data-ttu-id="dcf2d-113">Para obtener más información, consulte [lightweight pooling (opción de configuración del servidor)](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="dcf2d-113">For more information, see [lightweight pooling Server Configuration Option](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf2d-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dcf2d-114">See Also</span></span>  
 <span data-ttu-id="dcf2d-115">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcf2d-115">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="dcf2d-116">[clr enabled (opción de configuración del servidor)](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="dcf2d-116">[clr enabled Server Configuration Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) </span></span>  
 <span data-ttu-id="dcf2d-117">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcf2d-117">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="dcf2d-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dcf2d-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 [<span data-ttu-id="dcf2d-119">Roles de nivel de servidor</span><span class="sxs-lookup"><span data-stu-id="dcf2d-119">Server-Level Roles</span></span>](../security/authentication-access/server-level-roles.md)  
  
  
