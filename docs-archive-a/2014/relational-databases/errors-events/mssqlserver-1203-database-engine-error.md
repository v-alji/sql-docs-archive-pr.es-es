---
title: MSSQLSERVER_1203 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1203 (Database Engine error)
ms.assetid: 33a35f00-98c8-46c6-b432-544b326b6117
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3cea816a60ccd1b90d849194766edebd2d64d0b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675433"
---
# <a name="mssqlserver_1203"></a><span data-ttu-id="f191f-102">MSSQLSERVER_1203</span><span class="sxs-lookup"><span data-stu-id="f191f-102">MSSQLSERVER_1203</span></span>
    
## <a name="details"></a><span data-ttu-id="f191f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f191f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f191f-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="f191f-104">Product Name</span></span>|<span data-ttu-id="f191f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f191f-105">SQL Server</span></span>|  
|<span data-ttu-id="f191f-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f191f-106">Event ID</span></span>|<span data-ttu-id="f191f-107">1203</span><span class="sxs-lookup"><span data-stu-id="f191f-107">1203</span></span>|  
|<span data-ttu-id="f191f-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="f191f-108">Event Source</span></span>|<span data-ttu-id="f191f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f191f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f191f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f191f-110">Component</span></span>|<span data-ttu-id="f191f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f191f-111">SQLEngine</span></span>|  
|<span data-ttu-id="f191f-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f191f-112">Symbolic Name</span></span>|<span data-ttu-id="f191f-113">LK_NOT</span><span class="sxs-lookup"><span data-stu-id="f191f-113">LK_NOT</span></span>|  
|<span data-ttu-id="f191f-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f191f-114">Message Text</span></span>|<span data-ttu-id="f191f-115">El Id. de proceso %d intentó desbloquear un recurso que no es de su propiedad: %.\*ls.</span><span class="sxs-lookup"><span data-stu-id="f191f-115">Process ID %d attempted to unlock a resource it does not own: %.\*ls.</span></span> <span data-ttu-id="f191f-116">Vuelva a intentar repetir la transacción porque este error puede producirse por una condición de sincronización.</span><span class="sxs-lookup"><span data-stu-id="f191f-116">Retry the transaction, because this error may be caused by a timing condition.</span></span> <span data-ttu-id="f191f-117">Si el problema persiste, póngase en contacto con el administrador de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f191f-117">If the problem persists, contact the database administrator.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f191f-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="f191f-118">Explanation</span></span>  
 <span data-ttu-id="f191f-119">Este error se genera cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está ocupado en alguna actividad diferente a la limpieza de estado posterior al procesamiento y descubre que la página que está intentando desbloquear está ya desbloqueada.</span><span class="sxs-lookup"><span data-stu-id="f191f-119">This error occurs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is engaged in some activity other than ordinary post-processing cleanup and it finds that a particular page that it is trying to unlock is already unlocked.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="f191f-120">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="f191f-120">Possible Causes</span></span>  
 <span data-ttu-id="f191f-121">Es posible que la causa subyacente de este error esté relacionada con problemas estructurales dentro de la base de datos afectada.</span><span class="sxs-lookup"><span data-stu-id="f191f-121">The underlying cause of this error may be related to structural problems within the affected database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f191f-122">administra la adquisición y liberación de las páginas para mantener el control de simultaneidad en el entorno multiusuario.</span><span class="sxs-lookup"><span data-stu-id="f191f-122">manages the acquisition and release of pages to maintain concurrency control in the multiuser environment.</span></span> <span data-ttu-id="f191f-123">Este mecanismo se mantiene usando varias estructuras de bloqueo internas que identifican la página y el tipo de bloqueo existente.</span><span class="sxs-lookup"><span data-stu-id="f191f-123">This mechanism is maintained by using various internal lock structures that identify the page and the type of lock present.</span></span> <span data-ttu-id="f191f-124">Los bloqueos se adquieren para el procesamiento de páginas afectadas y liberadas cuando el procesamiento finaliza.</span><span class="sxs-lookup"><span data-stu-id="f191f-124">Locks are acquired for processing of affected pages and released when the processing is finished.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f191f-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f191f-125">User Action</span></span>  
 <span data-ttu-id="f191f-126">Ejecute DBCC CHECKDB en la base de datos a la que pertenece el objeto.</span><span class="sxs-lookup"><span data-stu-id="f191f-126">Execute DBCC CHECKDB against the database in which the object belongs.</span></span> <span data-ttu-id="f191f-127">Si DBCC CHECKDB no notifica errores, intente restablecer la conexión y ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="f191f-127">If DBCC CHECKDB reports no errors, try to reestablish the connection and execute the command.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f191f-128">Si está ejecutando DBCC CHECKDB con una de las cláusulas REPAIR y no se corrige el problema de índice, o si no está seguro del efecto que DBCC CHECKDB con una cláusula REPAIR produce en los datos, póngase en contacto con el proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="f191f-128">If you are executing DBCC CHECKDB with one of the REPAIR clauses does not correct the index problem, or if you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider.</span></span>  
  
  
