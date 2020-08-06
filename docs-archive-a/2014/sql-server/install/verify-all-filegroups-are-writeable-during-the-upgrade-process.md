---
title: Comprobar que se pueden escribir todos los grupos de archivos durante el proceso de actualización | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filegroups [SQL Server], writeable
- writeable filegroups [SQL Server]
ms.assetid: 2985efc1-4b14-46c3-abbd-a656b159f23c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8146efb876bf97c36c549a2b58d104592df611e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751646"
---
# <a name="verify-all-filegroups-are-writeable-during-the-upgrade-process"></a><span data-ttu-id="90eac-102">Comprobar que es posible escribir en todos los grupos de archivos durante el proceso de actualización</span><span class="sxs-lookup"><span data-stu-id="90eac-102">Verify all filegroups are writeable during the upgrade process</span></span>
  <span data-ttu-id="90eac-103">El Asesor de actualizaciones ha detectado una base de datos que tiene uno o más grupos de archivos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="90eac-103">Upgrade Advisor detected a database that has one or more read-only filegroups.</span></span> <span data-ttu-id="90eac-104">Todas las bases de datos de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deben tener los grupos de archivos establecidos en READ_WRITE antes de llevar a cabo la actualización.</span><span class="sxs-lookup"><span data-stu-id="90eac-104">All databases in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must have filegroups set to READ_WRITE before upgrading.</span></span>  
  
## <a name="component"></a><span data-ttu-id="90eac-105">Componente</span><span class="sxs-lookup"><span data-stu-id="90eac-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="90eac-106">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="90eac-106">Corrective Action</span></span>  
 <span data-ttu-id="90eac-107">Utilice ALTER DATABASE para establecer el grupo de archivos en READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="90eac-107">Use ALTER DATABASE to set the filegroup to READ_WRITE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90eac-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90eac-108">See Also</span></span>  
 <span data-ttu-id="90eac-109">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="90eac-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="90eac-110">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="90eac-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
