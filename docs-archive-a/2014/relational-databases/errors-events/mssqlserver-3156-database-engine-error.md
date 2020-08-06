---
title: MSSQLSERVER_3156 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3156 (Database Engine error)
ms.assetid: 345d8ed4-177e-4ec3-bab3-25d30000e323
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 25b5a037012a6d6b47b91e763a49cfb67b89f43c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673019"
---
# <a name="mssqlserver_3156"></a><span data-ttu-id="caa0f-102">MSSQLSERVER_3156</span><span class="sxs-lookup"><span data-stu-id="caa0f-102">MSSQLSERVER_3156</span></span>
    
## <a name="details"></a><span data-ttu-id="caa0f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="caa0f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="caa0f-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="caa0f-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="caa0f-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="caa0f-105">Event ID</span></span>|<span data-ttu-id="caa0f-106">3156</span><span class="sxs-lookup"><span data-stu-id="caa0f-106">3156</span></span>|  
|<span data-ttu-id="caa0f-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="caa0f-107">Event Source</span></span>|<span data-ttu-id="caa0f-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="caa0f-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="caa0f-109">Componente</span><span class="sxs-lookup"><span data-stu-id="caa0f-109">Component</span></span>|<span data-ttu-id="caa0f-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="caa0f-110">SQLEngine</span></span>|  
|<span data-ttu-id="caa0f-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="caa0f-111">Symbolic Name</span></span>|<span data-ttu-id="caa0f-112">LDDB_CANT_WRITE</span><span class="sxs-lookup"><span data-stu-id="caa0f-112">LDDB_CANT_WRITE</span></span>|  
|<span data-ttu-id="caa0f-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="caa0f-113">Message Text</span></span>|<span data-ttu-id="caa0f-114">El archivo '%ls' no se puede restaurar en '%ls'.</span><span class="sxs-lookup"><span data-stu-id="caa0f-114">File '%ls' cannot be restored to '%ls'.</span></span> <span data-ttu-id="caa0f-115">Utilice WITH MOVE para identificar una ubicación válida para el archivo.</span><span class="sxs-lookup"><span data-stu-id="caa0f-115">Use WITH MOVE to identify a valid location for the file.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="caa0f-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="caa0f-116">Explanation</span></span>  
 <span data-ttu-id="caa0f-117">Este mensaje general identifica los nombres lógicos o físicos de los archivos que no se pudieron restaurar debido a un problema con la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="caa0f-117">This general message identifies the logical or physical file names of files that could not be restored because of a problem with the specified location.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="caa0f-118">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="caa0f-118">Possible Causes</span></span>  
 <span data-ttu-id="caa0f-119">Entre las posibles causas figuran las siguientes:</span><span class="sxs-lookup"><span data-stu-id="caa0f-119">The possible causes include the following:</span></span>  
  
-   <span data-ttu-id="caa0f-120">Es posible que necesite acceso al directorio de Windows especificado.</span><span class="sxs-lookup"><span data-stu-id="caa0f-120">You might need access to the specified Windows directory.</span></span>  
  
-   <span data-ttu-id="caa0f-121">Es posible que haya escrito incorrectamente la ruta de acceso o que haya especificado una que no existe.</span><span class="sxs-lookup"><span data-stu-id="caa0f-121">You might have mistyped the path or specified a path that does not exist.</span></span>  
  
-   <span data-ttu-id="caa0f-122">Es posible que un archivo que no se puede sobrescribir esté utilizando el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="caa0f-122">The file name might be being used by a file that cannot be overwritten.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="caa0f-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="caa0f-123">User Action</span></span>  
 <span data-ttu-id="caa0f-124">Compruebe si en los registros de errores existen otros mensajes que proporcionen más información.</span><span class="sxs-lookup"><span data-stu-id="caa0f-124">Look at the error logs for other messages that provide more details.</span></span>  
  
 <span data-ttu-id="caa0f-125">Corrija el problema relacionado con la ubicación especificada. Por ejemplo, conceda acceso o utilice la opción WITH MOVE en la instrucción RESTORE para colocar el archivo en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="caa0f-125">Correct the problem with the specified location, for example, by granting access, or use the WITH MOVE option in your RESTORE statement to relocate the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa0f-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="caa0f-126">See Also</span></span>  
 <span data-ttu-id="caa0f-127">[Restaurar una base de datos a una nueva ubicación &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="caa0f-127">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="caa0f-128">[Restaurar archivos en una nueva ubicación &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="caa0f-128">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 [<span data-ttu-id="caa0f-129">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="caa0f-129">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
