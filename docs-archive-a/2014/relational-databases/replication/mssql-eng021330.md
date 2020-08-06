---
title: MSSQL_ENG021330 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021330 error
ms.assetid: e2bb2e21-62a7-4689-b68b-bdfba3fdd985
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4338756a641b23bfc6f52da6b3de296bb6415756
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745209"
---
# <a name="mssql_eng021330"></a><span data-ttu-id="d4aa8-102">MSSQL_ENG021330</span><span class="sxs-lookup"><span data-stu-id="d4aa8-102">MSSQL_ENG021330</span></span>
    
## <a name="message-details"></a><span data-ttu-id="d4aa8-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="d4aa8-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4aa8-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="d4aa8-104">Product Name</span></span>|<span data-ttu-id="d4aa8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4aa8-105">SQL Server</span></span>|  
|<span data-ttu-id="d4aa8-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d4aa8-106">Event ID</span></span>|<span data-ttu-id="d4aa8-107">21330</span><span class="sxs-lookup"><span data-stu-id="d4aa8-107">21330</span></span>|  
|<span data-ttu-id="d4aa8-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="d4aa8-108">Event Source</span></span>|<span data-ttu-id="d4aa8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d4aa8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d4aa8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d4aa8-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="d4aa8-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d4aa8-111">Symbolic Name</span></span>||  
|<span data-ttu-id="d4aa8-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d4aa8-112">Message Text</span></span>|<span data-ttu-id="d4aa8-113">No se pudo crear un subdirectorio bajo el directorio de trabajo de replicación.(%1!)</span><span class="sxs-lookup"><span data-stu-id="d4aa8-113">Failed to create a sub-directory under the replication working directory.(%ls)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d4aa8-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="d4aa8-114">Explanation</span></span>  
 <span data-ttu-id="d4aa8-115">Este error se puede producir cuando una suscripción se inicializa manualmente y hay un problema para crear el directorio en el que se almacenan los scripts de replicación.</span><span class="sxs-lookup"><span data-stu-id="d4aa8-115">This error can occur when a subscription is initialized manually, and there is a problem creating the directory in which replication scripts are stored.</span></span> <span data-ttu-id="d4aa8-116">Este error puede deberse a un problema de permisos: cuando se inicializa una suscripción sin utilizar una instantánea, la cuenta con la que se ejecuta el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el publicador debe tener permisos de escritura para la carpeta de la instantánea en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="d4aa8-116">The error can be caused by a permissions issue: when a subscription is initialized without using a snapshot, the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs at the Publisher must have write permissions on the snapshot folder at the Distributor.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d4aa8-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d4aa8-117">User Action</span></span>  
 <span data-ttu-id="d4aa8-118">Compruebe que se ha especificado la ruta de acceso correcta para la carpeta de instantáneas y que la cuenta con la que se ejecuta el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el publicador dispone de permisos suficientes.</span><span class="sxs-lookup"><span data-stu-id="d4aa8-118">Ensure that the correct path has been specified for the snapshot folder and that the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs at the Publisher has sufficient permissions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4aa8-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d4aa8-119">See Also</span></span>  
 <span data-ttu-id="d4aa8-120">[Especificar la ubicación de instantáneas predeterminada](snapshot-options.md#snapshot-folder-locations) </span><span class="sxs-lookup"><span data-stu-id="d4aa8-120">[Specify the Default Snapshot Location](snapshot-options.md#snapshot-folder-locations) </span></span>  
 <span data-ttu-id="d4aa8-121">[Referencia de errores y eventos &#40;replicación&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="d4aa8-121">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="d4aa8-122">Inicializar una suscripción transaccional sin una instantánea</span><span class="sxs-lookup"><span data-stu-id="d4aa8-122">Initialize a Transactional Subscription Without a Snapshot</span></span>](initialize-a-transactional-subscription-without-a-snapshot.md)  
  
  
