---
title: Cambios en el comportamiento de syslockinfo y sp_lock | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- syslockinfo
- sp_lock
ms.assetid: b9892ae3-ac15-48be-8b52-78dbed6467ed
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 65ace190004cab911dd8996642720620eba94935
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672515"
---
# <a name="changes-to-behavior-in-syslockinfo-and-sp_lock"></a><span data-ttu-id="f9129-102">Cambios del comportamiento de syslockinfo y sp_lock</span><span class="sxs-lookup"><span data-stu-id="f9129-102">Changes to behavior in syslockinfo and sp_lock</span></span>
  <span data-ttu-id="f9129-103">**syslockinfo** y **sp_lock** devolver valores inesperados.</span><span class="sxs-lookup"><span data-stu-id="f9129-103">**syslockinfo** and **sp_lock** may return unexpected values.</span></span> <span data-ttu-id="f9129-104">También pueden devolver filas adicionales, mientras que las versiones anteriores de **syslockinfo** y **sp_lock** devolvían un máximo de dos filas por recurso de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f9129-104">They may also return additional rows, whereas previous versions of **syslockinfo** and **sp_lock** returned a maximum of two rows per lock resource.</span></span>  
  
 <span data-ttu-id="f9129-105">Para obtener acceso a la información de **syslockinfo** o para ejecutar **sp_lock** es necesario contar con el permiso VIEW SERVER STATE en el servidor.</span><span class="sxs-lookup"><span data-stu-id="f9129-105">To access information from **syslockinfo** or execute **sp_lock** requires VIEW SERVER STATE permission on the server.</span></span>  
  
## <a name="component"></a><span data-ttu-id="f9129-106">Componente</span><span class="sxs-lookup"><span data-stu-id="f9129-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="f9129-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9129-107">Description</span></span>  
 <span data-ttu-id="f9129-108">En [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], las columnas **rsc_objid** y **rsc_indid** en **syslockinfo** y las columnas **objid** e **indid** en **sp_lock** devuelven sistemáticamente el Id. de objeto y el Id. de índice.</span><span class="sxs-lookup"><span data-stu-id="f9129-108">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], the **rsc_objid** and **rsc_indid** columns in **syslockinfo** and the **objid** and **indid** columns in **sp_lock** consistently return the object ID and index ID.</span></span> <span data-ttu-id="f9129-109">En [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], es posible que se devuelva un valor de 0.</span><span class="sxs-lookup"><span data-stu-id="f9129-109">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a value of 0 may be returned.</span></span>  
  
 <span data-ttu-id="f9129-110">En [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], **syslockinfo** y **sp_lock** devuelven un máximo de dos filas para un recurso de bloqueo dado en una transacción única.</span><span class="sxs-lookup"><span data-stu-id="f9129-110">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], **syslockinfo** and **sp_lock** return a maximum of two rows for any given lock resource in a single transaction.</span></span> <span data-ttu-id="f9129-111">A partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], cuando está habilitada la partición del bloqueo, pueden devolverse varias filas del mismo recurso que se ejecuta en una sola transacción.</span><span class="sxs-lookup"><span data-stu-id="f9129-111">Starting with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], when lock partitioning is enabled, multiple rows for the same resource running under one transaction may be returned.</span></span> <span data-ttu-id="f9129-112">Puede haber hasta N + 1 filas devueltas, donde N es el número de CPU.</span><span class="sxs-lookup"><span data-stu-id="f9129-112">There may be up to N + 1 rows returned, where N is the number of CPUs.</span></span> <span data-ttu-id="f9129-113">Asimismo, ahora es posible que se muestren solicitudes GRANTED y WAITING para el mismo recurso, lo cual no era posible en [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9129-113">Also, it is now possible to have GRANTED and WAITING requests displayed for the same resource, which was not possible in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="f9129-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="f9129-114">Permissions</span></span>  
 <span data-ttu-id="f9129-115">es necesario contar con el permiso VIEW SERVER STATE en el servidor.</span><span class="sxs-lookup"><span data-stu-id="f9129-115">Requires VIEW SERVER STATE permission on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9129-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f9129-116">See Also</span></span>  
 <span data-ttu-id="f9129-117">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="f9129-117">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="f9129-118">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="f9129-118">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
