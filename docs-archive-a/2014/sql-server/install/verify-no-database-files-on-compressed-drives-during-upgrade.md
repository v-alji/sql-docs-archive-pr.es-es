---
title: Comprobar que no hay ningún archivo de base de datos en unidades comprimidas durante el proceso de actualización | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- compressed drives [SQL Server]
ms.assetid: 63be6853-c54a-42b2-ae1a-db2175f1d28e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9c04f7890ba8d8efe64afaf11b922af156c5de46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663283"
---
# <a name="verify-that-no-database-files-are-on-compressed-drives-during-the-upgrade-process"></a><span data-ttu-id="987f7-102">Comprobar que ningún archivo de base de datos se encuentre en unidades comprimidas durante el proceso de actualización</span><span class="sxs-lookup"><span data-stu-id="987f7-102">Verify that no database files are on compressed drives during the upgrade process</span></span>
  <span data-ttu-id="987f7-103">El Asesor de actualizaciones ha detectado archivos de base de datos en una unidad comprimida.</span><span class="sxs-lookup"><span data-stu-id="987f7-103">Upgrade Advisor detected database files on a compressed drive.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="987f7-104">no puede crear o actualizar las bases de datos en unidades comprimidas.</span><span class="sxs-lookup"><span data-stu-id="987f7-104">cannot create or upgrade databases on compressed drives.</span></span>  
  
## <a name="component"></a><span data-ttu-id="987f7-105">Componente</span><span class="sxs-lookup"><span data-stu-id="987f7-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="987f7-106">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="987f7-106">Corrective Action</span></span>  
 <span data-ttu-id="987f7-107">Al instalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], seleccione una unidad sin comprimir para las bases de datos del sistema y compruebe que las bases de datos que va a actualizar no están en unidades comprimidas.</span><span class="sxs-lookup"><span data-stu-id="987f7-107">When you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], select an uncompressed drive for system databases and verify that databases to be upgraded are not on compressed drives.</span></span> <span data-ttu-id="987f7-108">No obstante, tenga en cuenta que una vez actualizada la base de datos, puede colocar bases de datos de solo lectura y grupos de archivos secundarios de solo lectura en un sistema de archivos comprimidos NTFS.</span><span class="sxs-lookup"><span data-stu-id="987f7-108">However, note that after the database has been upgraded, you can put read-only databases and read-only secondary filegroups on an NTFS compressed file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987f7-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="987f7-109">See Also</span></span>  
 <span data-ttu-id="987f7-110">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="987f7-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="987f7-111">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="987f7-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
