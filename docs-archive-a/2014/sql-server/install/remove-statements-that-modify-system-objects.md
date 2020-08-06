---
title: Quitar instrucciones que modifican objetos del sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- direct system catalog updates [SQL Server]
- system catalogs [SQL Server]
ms.assetid: 221b46c2-c27e-4df8-bd8c-8b990d6d5e98
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 526181bc4bf7ab81df2eaa25f19e7627c9b7af10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751706"
---
# <a name="remove-statements-that-modify-system-objects"></a><span data-ttu-id="3ba76-102">Eliminar instrucciones que modifican objetos del sistema</span><span class="sxs-lookup"><span data-stu-id="3ba76-102">Remove statements that modify system objects</span></span>
  <span data-ttu-id="3ba76-103">El Asesor de actualizaciones ha detectado la existencia de instrucciones que actualizan el catálogo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3ba76-103">Upgrade Advisor detected statements that update the system catalog.</span></span> <span data-ttu-id="3ba76-104">No se permite realizar actualizaciones directas del catálogo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3ba76-104">Direct system catalog updates are not allowed.</span></span> <span data-ttu-id="3ba76-105">Modifique los scripts de SQL para que utilicen API documentadas y oficiales.</span><span class="sxs-lookup"><span data-stu-id="3ba76-105">Modify your SQL scripts to use official and documented APIs.</span></span>  
  
## <a name="component"></a><span data-ttu-id="3ba76-106">Componente</span><span class="sxs-lookup"><span data-stu-id="3ba76-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="3ba76-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ba76-107">Description</span></span>  
 <span data-ttu-id="3ba76-108">No se permite realizar actualizaciones directas del catálogo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3ba76-108">Direct system catalog updates are not allowed.</span></span> <span data-ttu-id="3ba76-109">Cualquier intento de hacerlo generará el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="3ba76-109">Any attempt to do so will generate the following error:</span></span>  
  
 `Server: Msg 259, Level 16, State 1, Line 1`  
  
 `Ad hoc updates to system catalogs are not allowed.`  
  
## <a name="corrective-action"></a><span data-ttu-id="3ba76-110">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="3ba76-110">Corrective Action</span></span>  
 <span data-ttu-id="3ba76-111">Modifique los scripts de SQL para que utilicen API documentadas y oficiales.</span><span class="sxs-lookup"><span data-stu-id="3ba76-111">Modify your SQL scripts to use official and documented APIs.</span></span> <span data-ttu-id="3ba76-112">Por ejemplo, utilice ALTER DATABASE *database_name* SET EMERGENCY en lugar de ejecutar una instrucción UPDATE en la tabla del sistema **sysdatabases** .</span><span class="sxs-lookup"><span data-stu-id="3ba76-112">For example, use ALTER DATABASE *database_name* SET EMERGENCY instead of running an UPDATE statement on the **sysdatabases** system table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ba76-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3ba76-113">See Also</span></span>  
 <span data-ttu-id="3ba76-114">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="3ba76-114">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="3ba76-115">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="3ba76-115">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](https://docs.microsoft.com/sql/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
