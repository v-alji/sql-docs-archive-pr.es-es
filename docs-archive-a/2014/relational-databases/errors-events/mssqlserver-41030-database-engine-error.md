---
title: MSSQLSERVER_41030 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41030 (Database Engine error)
ms.assetid: c85341ae-0fbf-42ae-9275-4cfe678238f0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b137b739d4c1641b88983708df62d2e52fd0eab5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748120"
---
# <a name="mssqlserver_41030"></a><span data-ttu-id="60ff8-102">MSSQLSERVER_41030</span><span class="sxs-lookup"><span data-stu-id="60ff8-102">MSSQLSERVER_41030</span></span>
    
## <a name="details"></a><span data-ttu-id="60ff8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="60ff8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60ff8-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="60ff8-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="60ff8-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="60ff8-105">Event ID</span></span>|<span data-ttu-id="60ff8-106">41030</span><span class="sxs-lookup"><span data-stu-id="60ff8-106">41030</span></span>|  
|<span data-ttu-id="60ff8-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="60ff8-107">Event Source</span></span>|<span data-ttu-id="60ff8-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="60ff8-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="60ff8-109">Componente</span><span class="sxs-lookup"><span data-stu-id="60ff8-109">Component</span></span>|<span data-ttu-id="60ff8-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="60ff8-110">SQLEngine</span></span>|  
|<span data-ttu-id="60ff8-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="60ff8-111">Symbolic Name</span></span>|<span data-ttu-id="60ff8-112">OPEN_CLUSTER_SUB_KEY</span><span class="sxs-lookup"><span data-stu-id="60ff8-112">OPEN_CLUSTER_SUB_KEY</span></span>|  
|<span data-ttu-id="60ff8-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="60ff8-113">Message Text</span></span>|<span data-ttu-id="60ff8-114">No se pudo abrir la subclave del Registro '%.\*ls' de clústeres de conmutación por error de Windows Server (WSFC) (código de error %d).</span><span class="sxs-lookup"><span data-stu-id="60ff8-114">Failed to open the Windows Server Failover Clustering registry subkey '%.\*ls' (Error code %d).</span></span>  <span data-ttu-id="60ff8-115">La clave principal del clúster es la clave raíz del clúster.</span><span class="sxs-lookup"><span data-stu-id="60ff8-115">The parent key is the cluster root key.</span></span>  <span data-ttu-id="60ff8-116">Puede que el servicio WSFC no se esté ejecutando o no esté accesible en su estado actual, o que los argumentos especificados no sean válidos.</span><span class="sxs-lookup"><span data-stu-id="60ff8-116">The WSFC service may not be running or may not be accessible in its current state, or the specified arguments are invalid.</span></span> <span data-ttu-id="60ff8-117">Si el grupo de disponibilidad correspondiente se ha quitado, este error es previsible.</span><span class="sxs-lookup"><span data-stu-id="60ff8-117">If the corresponding availability group has been dropped, this error is expected.</span></span> <span data-ttu-id="60ff8-118">Para obtener más información sobre este código de error, vea "Códigos de error del sistema” en la documentación de Desarrollo en Windows.</span><span class="sxs-lookup"><span data-stu-id="60ff8-118">For information about this error code, see "System Error Codes" in the Windows Development documentation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="60ff8-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="60ff8-119">Explanation</span></span>  
 <span data-ttu-id="60ff8-120">Si se destruye un clúster de WSFC, quita todas las claves del Registro relacionadas con [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60ff8-120">If a WSFC cluster is destroyed, it removes all registry keys related to [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="60ff8-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="60ff8-121">User Action</span></span>  
 <span data-ttu-id="60ff8-122">Después de volver crear un clúster de WSFC, deshabilite y vuelva a habilitar AlwaysOn en todos los nodos del clúster en los que haya una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] habilitada para AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="60ff8-122">After re-creating a WSFC cluster, disable and then re-enable AlwaysOn on every cluster node on which an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is enabled for AlwaysOn.</span></span> <span data-ttu-id="60ff8-123">Puede usar el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para realizar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="60ff8-123">You can use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for this task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60ff8-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="60ff8-124">See Also</span></span>  
 <span data-ttu-id="60ff8-125">[Habilitar y deshabilitar Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60ff8-125">[Enable and Disable AlwaysOn Availability Groups &#40;SQL Server&#41;](../../database-engine/availability-groups/windows/enable-and-disable-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="60ff8-126">Clústeres de conmutación por error de Windows Server &#40;WSFC&#41; con SQL Server</span><span class="sxs-lookup"><span data-stu-id="60ff8-126">Windows Server Failover Clustering &#40;WSFC&#41; with SQL Server</span></span>](../../sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server.md)  
  
  
