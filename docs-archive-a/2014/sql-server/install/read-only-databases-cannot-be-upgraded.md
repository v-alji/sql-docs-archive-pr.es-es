---
title: No se pueden actualizar las bases de datos de solo lectura | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- database cannot be upgraded
ms.assetid: 27964211-ea30-4390-b791-dcf225fb9ae7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ba48ed2bd80961a4949dc13f04fed0637ecc27ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675697"
---
# <a name="read-only-databases-cannot-be-upgraded"></a><span data-ttu-id="39852-102">No se pueden actualizar bases de datos de solo lectura</span><span class="sxs-lookup"><span data-stu-id="39852-102">Read-only databases cannot be upgraded</span></span>
  <span data-ttu-id="39852-103">El Asesor de actualizaciones ha determinado que no se pueden actualizar algunas bases de datos de esta instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39852-103">Upgrade Advisor has determined that some databases on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be upgraded.</span></span>  
  
## <a name="component"></a><span data-ttu-id="39852-104">Componente</span><span class="sxs-lookup"><span data-stu-id="39852-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="39852-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="39852-105">Description</span></span>  
 <span data-ttu-id="39852-106">Se ha detectado una base de datos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="39852-106">A read-only database has been detected.</span></span> <span data-ttu-id="39852-107">Para actualizarla, el programa de instalación debe poder escribir en ella.</span><span class="sxs-lookup"><span data-stu-id="39852-107">To upgrade the database, Setup must be able to write to the database.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="39852-108">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="39852-108">Corrective Action</span></span>  
 <span data-ttu-id="39852-109">Cuando nadie esté usando la base de datos, use el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Administrador corporativo, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] o la instrucción ALTER DATABASE para cambiar la base de datos a lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="39852-109">When no one is using the database, use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise Manager, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], or the ALTER DATABASE statement to change the database to read-write.</span></span> <span data-ttu-id="39852-110">La instrucción siguiente cambia la base de datos al modo de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="39852-110">The following statement changes the database to read-write.</span></span>  
  
```  
USE master;  
GO  
ALTER DATABASE <database name>  
SET READ_WRITE;  
GO  
```  
  
 <span data-ttu-id="39852-111">Para obtener más información acerca de la instrucción ALTER DATABASE, vea el tema "ALTER DATABASE ([!INCLUDE[tsql](../../includes/tsql-md.md)])" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39852-111">For more information about the ALTER DATABASE statement, see the "ALTER DATABASE ([!INCLUDE[tsql](../../includes/tsql-md.md)])" topic in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39852-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39852-112">See Also</span></span>  
 <span data-ttu-id="39852-113">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="39852-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="39852-114">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="39852-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
