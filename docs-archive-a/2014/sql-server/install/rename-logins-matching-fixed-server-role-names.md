---
title: Cambiar el nombre de inicios de sesión que coinciden con nombres de roles fijos de servidor | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- user-defined login names [SQL Server]
- fixed server roles [SQL Server]
- renamed logins [SQL Server]
- logins [SQL Server], names
ms.assetid: 10a1d77c-3153-474f-a6a0-969556794467
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 296ae4d4051e79e3c5d3bc158ef3e87c9164ecd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747892"
---
# <a name="rename-logins-matching-fixed-server-role-names"></a><span data-ttu-id="b00a6-102">Cambiar el nombre de los inicios de sesión que coinciden con nombres de roles fijos de servidor</span><span class="sxs-lookup"><span data-stu-id="b00a6-102">Rename logins matching fixed server role names</span></span>
  <span data-ttu-id="b00a6-103">El Asesor de actualizaciones ha detectado uno o más nombres de inicio de sesión definidos por el usuario que coinciden con los nombres de los roles fijos del servidor.</span><span class="sxs-lookup"><span data-stu-id="b00a6-103">Upgrade Advisor detected one or more user-defined login names that match the names of fixed server roles.</span></span> <span data-ttu-id="b00a6-104">Los nombres de roles fijos de servidor están reservados.</span><span class="sxs-lookup"><span data-stu-id="b00a6-104">Fixed server role names are reserved.</span></span> <span data-ttu-id="b00a6-105">Cambie el nombre del inicio de sesión antes de actualizar.</span><span class="sxs-lookup"><span data-stu-id="b00a6-105">Rename the login before you upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b00a6-106">Componente</span><span class="sxs-lookup"><span data-stu-id="b00a6-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b00a6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b00a6-107">Description</span></span>  
 <span data-ttu-id="b00a6-108">Los siguientes nombres de roles fijos de servidor están reservados y no se pueden usar como nombres de inicio de sesión definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="b00a6-108">The following fixed server role names are reserved and cannot be used as user-defined login names.</span></span>  
  
-   <span data-ttu-id="b00a6-109">**sysadmin**</span><span class="sxs-lookup"><span data-stu-id="b00a6-109">**sysadmin**</span></span>  
  
-   <span data-ttu-id="b00a6-110">**serveradmin**</span><span class="sxs-lookup"><span data-stu-id="b00a6-110">**serveradmin**</span></span>  
  
-   <span data-ttu-id="b00a6-111">**setupadmin**</span><span class="sxs-lookup"><span data-stu-id="b00a6-111">**setupadmin**</span></span>  
  
-   <span data-ttu-id="b00a6-112">**securityadmin**</span><span class="sxs-lookup"><span data-stu-id="b00a6-112">**securityadmin**</span></span>  
  
-   <span data-ttu-id="b00a6-113">**processadmin**</span><span class="sxs-lookup"><span data-stu-id="b00a6-113">**processadmin**</span></span>  
  
-   <span data-ttu-id="b00a6-114">**dbcreator**</span><span class="sxs-lookup"><span data-stu-id="b00a6-114">**dbcreator**</span></span>  
  
-   <span data-ttu-id="b00a6-115">**diskadmin**</span><span class="sxs-lookup"><span data-stu-id="b00a6-115">**diskadmin**</span></span>  
  
-   <span data-ttu-id="b00a6-116">**bulkadmin**</span><span class="sxs-lookup"><span data-stu-id="b00a6-116">**bulkadmin**</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b00a6-117">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="b00a6-117">Corrective Action</span></span>  
 <span data-ttu-id="b00a6-118">Antes de actualizar, siga los pasos que se detallan a continuación:</span><span class="sxs-lookup"><span data-stu-id="b00a6-118">Before upgrading, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="b00a6-119">Registre los identificadores de seguridad (SID) de los inicios de sesión ejecutando la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="b00a6-119">Record the security identifiers (SIDs) of the logins by executing the following statement.</span></span>  
  
    ```  
    SELECT name, sid   
    FROM master.dbo.syslogins   
    WHERE name IN('sysadmin', 'serveradmin','setupadmin', 'securityadmin','processadmin', 'dbcreator','diskadmin','bulkadmin')  
    ```  
  
2.  <span data-ttu-id="b00a6-120">Elimine los inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="b00a6-120">Drop the logins.</span></span>  
  
3.  <span data-ttu-id="b00a6-121">Utilice el procedimiento del sistema **sp_addlogin** para crear nuevos inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="b00a6-121">Use the **sp_addlogin** system procedure to create new logins.</span></span> <span data-ttu-id="b00a6-122">Especifique el SID devuelto en el paso 1 en el parámetro \*\* \@ SID\*\* para cada inicio de sesión correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b00a6-122">Specify the SID returned in step 1 in the **\@sid** parameter for each corresponding login.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b00a6-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b00a6-123">See Also</span></span>  
 <span data-ttu-id="b00a6-124">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b00a6-124">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b00a6-125">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="b00a6-125">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
