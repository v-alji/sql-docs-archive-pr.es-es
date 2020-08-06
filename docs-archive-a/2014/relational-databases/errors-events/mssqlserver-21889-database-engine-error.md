---
title: MSSQLSERVER_21889 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21889 (Database Engine error)
ms.assetid: ae199540-7986-4cc2-b782-cd22793236d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c152a542550d7b81af880545f526037baeb4644e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747006"
---
# <a name="mssqlserver_21889"></a><span data-ttu-id="6201d-102">MSSQLSERVER_21889</span><span class="sxs-lookup"><span data-stu-id="6201d-102">MSSQLSERVER_21889</span></span>
    
## <a name="details"></a><span data-ttu-id="6201d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6201d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6201d-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="6201d-104">Product Name</span></span>|<span data-ttu-id="6201d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6201d-105">SQL Server</span></span>|  
|<span data-ttu-id="6201d-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="6201d-106">Event ID</span></span>|<span data-ttu-id="6201d-107">21889</span><span class="sxs-lookup"><span data-stu-id="6201d-107">21889</span></span>|  
|<span data-ttu-id="6201d-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="6201d-108">Event Source</span></span>|<span data-ttu-id="6201d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6201d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6201d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6201d-110">Component</span></span>|<span data-ttu-id="6201d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6201d-111">SQLEngine</span></span>|  
|<span data-ttu-id="6201d-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6201d-112">Symbolic Name</span></span>|<span data-ttu-id="6201d-113">SQLErrorNum21889</span><span class="sxs-lookup"><span data-stu-id="6201d-113">SQLErrorNum21889</span></span>|  
|<span data-ttu-id="6201d-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6201d-114">Message Text</span></span>|<span data-ttu-id="6201d-115">La instancia '%s' de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no es un publicador de replicación.</span><span class="sxs-lookup"><span data-stu-id="6201d-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance '%s' is not a replication publisher.</span></span> <span data-ttu-id="6201d-116">Ejecute `sp_adddistributor` en la instancia '%s' de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el distribuidor '%s' a fin de habilitar la instancia para hospedar la base de datos de publicación '%s'.</span><span class="sxs-lookup"><span data-stu-id="6201d-116">Run `sp_adddistributor` on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance '%s' with distributor '%s' in order to enable the instance to host the publishing database '%s'.</span></span> <span data-ttu-id="6201d-117">Asegúrese de especificar el mismo inicio de sesión y contraseña que se usarán para el publicador original.</span><span class="sxs-lookup"><span data-stu-id="6201d-117">Make certain to specify the same login and password as that used for the original publisher.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6201d-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="6201d-118">Explanation</span></span>  
 <span data-ttu-id="6201d-119">Para hospedar la base de datos del publicador, la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe ser un publicador de replicación.</span><span class="sxs-lookup"><span data-stu-id="6201d-119">In order to host the publisher database, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be a replication publisher.</span></span> <span data-ttu-id="6201d-120">`sp_validate_redirected_publisher` llama a `sp_helpdistributor` en el servidor remoto para determinar si el servidor es un publicador de replicación.</span><span class="sxs-lookup"><span data-stu-id="6201d-120">`sp_validate_redirected_publisher` calls `sp_helpdistributor` at the remote server to determine whether the server is a replication publisher.</span></span> <span data-ttu-id="6201d-121">Se devuelve este error cuando la ejecución del procedimiento almacenado `sp_helpdistributor` indica que la instancia de destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no es un publicador de replicación.</span><span class="sxs-lookup"><span data-stu-id="6201d-121">This error is returned when execution of the stored procedure `sp_helpdistributor` indicates that the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not a replication publisher.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6201d-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6201d-122">User Action</span></span>  
 <span data-ttu-id="6201d-123">Ejecute `sp_adddistributor` en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda la base de datos del publicador.</span><span class="sxs-lookup"><span data-stu-id="6201d-123">Execute `sp_adddistributor` at the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the publisher database.</span></span> <span data-ttu-id="6201d-124">Al ejecutar `sp_adddistributor`, especifique el distribuidor correcto.</span><span class="sxs-lookup"><span data-stu-id="6201d-124">When running `sp_adddistributor`, specify the correct distributor.</span></span> <span data-ttu-id="6201d-125">Use el mismo valor para el *@password* parámetro que el que se utilizó cuando `sp_adddistributor` se ejecutó inicialmente en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="6201d-125">Use the same value for the *@password* parameter as that used when `sp_adddistributor` was initially run at the distributor.</span></span>  
  
  
