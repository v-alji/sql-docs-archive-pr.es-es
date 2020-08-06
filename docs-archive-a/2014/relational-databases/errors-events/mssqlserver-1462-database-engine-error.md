---
title: MSSQLSERVER_1462 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1462 (Database Engine error)
ms.assetid: 680e9c1c-a9d6-4765-b601-956d0a83324c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 704b847bde2d7b4da9da91b4b24bfe2b9e2afa07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675943"
---
# <a name="mssqlserver_1462"></a><span data-ttu-id="59343-102">MSSQLSERVER_1462</span><span class="sxs-lookup"><span data-stu-id="59343-102">MSSQLSERVER_1462</span></span>
    
## <a name="details"></a><span data-ttu-id="59343-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="59343-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="59343-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="59343-104">Product Name</span></span>|<span data-ttu-id="59343-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="59343-105">SQL Server</span></span>|  
|<span data-ttu-id="59343-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="59343-106">Event ID</span></span>|<span data-ttu-id="59343-107">1462</span><span class="sxs-lookup"><span data-stu-id="59343-107">1462</span></span>|  
|<span data-ttu-id="59343-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="59343-108">Event Source</span></span>|<span data-ttu-id="59343-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="59343-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="59343-110">Componente</span><span class="sxs-lookup"><span data-stu-id="59343-110">Component</span></span>|<span data-ttu-id="59343-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="59343-111">SQLEngine</span></span>|  
|<span data-ttu-id="59343-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="59343-112">Symbolic Name</span></span>|<span data-ttu-id="59343-113">DBM_DISABLED_DUE_TO_FAILED_REDO</span><span class="sxs-lookup"><span data-stu-id="59343-113">DBM_DISABLED_DUE_TO_FAILED_REDO</span></span>|  
|<span data-ttu-id="59343-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="59343-114">Message Text</span></span>|<span data-ttu-id="59343-115">La creación de reflejo de la base de datos está deshabilitada debido a una operación de puesta al día con errores.</span><span class="sxs-lookup"><span data-stu-id="59343-115">Database mirroring is disabled due to a failed redo operation.</span></span> <span data-ttu-id="59343-116">No se puede reanudar.</span><span class="sxs-lookup"><span data-stu-id="59343-116">Unable to resume.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="59343-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="59343-117">Explanation</span></span>  
 <span data-ttu-id="59343-118">La creación de reflejo de la base de datos no puede poner al día una entrada de registro en el reflejo.</span><span class="sxs-lookup"><span data-stu-id="59343-118">Database mirroring failed to redo a log record on the mirror.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="59343-119">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="59343-119">Possible Causes</span></span>  
 <span data-ttu-id="59343-120">La causa más probable es que se haya completado una operación de agregar archivos en la base de datos principal pero que haya generado un error en la base de datos reflejada al ser diferentes los nombres de archivo o estructuras de directorio en el servidor principal y reflejado.</span><span class="sxs-lookup"><span data-stu-id="59343-120">The most likely cause is that an add-file operation completed on the principal database but then failed on the mirror database because file names or directory structures differ on the principal server and mirror server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="59343-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="59343-121">User Action</span></span>  
 <span data-ttu-id="59343-122">Busque la causa de este error en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59343-122">Look in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log for the cause of this error.</span></span> <span data-ttu-id="59343-123">Intente resolver la causa y reanude la creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="59343-123">Try to resolve the cause and resume mirroring on the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59343-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59343-124">See Also</span></span>  
 [<span data-ttu-id="59343-125">Solucionar problemas de configuración de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="59343-125">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
