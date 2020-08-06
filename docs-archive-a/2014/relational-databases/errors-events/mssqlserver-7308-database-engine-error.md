---
title: MSSQLSERVER_7308 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7308 (Database Engine error)
- single-threaded apartment mode
ms.assetid: cca9eab9-afb9-463d-abfd-0802257e2c99
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9978f35ebe41eeda1470220772f87e83ab1ad942
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673011"
---
# <a name="mssqlserver_7308"></a><span data-ttu-id="10e8d-102">MSSQLSERVER_7308</span><span class="sxs-lookup"><span data-stu-id="10e8d-102">MSSQLSERVER_7308</span></span>
    
## <a name="details"></a><span data-ttu-id="10e8d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="10e8d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10e8d-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="10e8d-104">Product Name</span></span>|<span data-ttu-id="10e8d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="10e8d-105">SQL Server</span></span>|  
|<span data-ttu-id="10e8d-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="10e8d-106">Event ID</span></span>|<span data-ttu-id="10e8d-107">7308</span><span class="sxs-lookup"><span data-stu-id="10e8d-107">7308</span></span>|  
|<span data-ttu-id="10e8d-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="10e8d-108">Event Source</span></span>|<span data-ttu-id="10e8d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="10e8d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="10e8d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="10e8d-110">Component</span></span>|<span data-ttu-id="10e8d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="10e8d-111">SQLEngine</span></span>|  
|<span data-ttu-id="10e8d-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="10e8d-112">Symbolic Name</span></span>|<span data-ttu-id="10e8d-113">RMT_STA_DISABLED</span><span class="sxs-lookup"><span data-stu-id="10e8d-113">RMT_STA_DISABLED</span></span>|  
|<span data-ttu-id="10e8d-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="10e8d-114">Message Text</span></span>|<span data-ttu-id="10e8d-115">El proveedor OLE DB '%ls' no puede usarse para consultas distribuidas porque está configurado para ejecutarse en el modo de subprocesamiento controlado simple.</span><span class="sxs-lookup"><span data-stu-id="10e8d-115">OLE DB provider '%ls' cannot be used for distributed queries because the provider is configured to run in single-threaded apartment mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="10e8d-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="10e8d-116">Explanation</span></span>  
 <span data-ttu-id="10e8d-117">Ha utilizado un proveedor OLE DB que está configurado para ejecutarse en modo de subprocesamiento controlado simple (STA).</span><span class="sxs-lookup"><span data-stu-id="10e8d-117">You have used an OLE DB provider that is configured to run in single-threaded apartment (STA) mode.</span></span> <span data-ttu-id="10e8d-118">Los proveedores OLE DB que se ejecutan en modo de subprocesamiento controlado simple (STA) no se pueden utilizar para consultas distribuidas.</span><span class="sxs-lookup"><span data-stu-id="10e8d-118">OLE DB providers that run in single-threaded apartment (STA) mode cannot be used for distributed queries.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="10e8d-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="10e8d-119">User Action</span></span>  
 <span data-ttu-id="10e8d-120">Para resolver este error, configure el proveedor para ejecutarse en modo de contenedor multiproceso (MTA).</span><span class="sxs-lookup"><span data-stu-id="10e8d-120">To resolve this error, configure the provider to run in multithreaded apartment (MTA) mode.</span></span> <span data-ttu-id="10e8d-121">Si el proveedor no admite MTA y no puede realizar una actualización a una versión que admita MTA, considere la posibilidad de configurarlo para ejecutarse fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="10e8d-121">If the provider does not support MTA, and the provider cannot be upgraded to a version that supports MTA, consider configuring the provider to run out-of-process.</span></span> <span data-ttu-id="10e8d-122">El fabricante del proveedor debe indicarle si éste admite MTA o si se ha de ejecutar fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="10e8d-122">The provider vendor should be able to tell you if the provider supports MTA or running out-of-process.</span></span>  
  
  
