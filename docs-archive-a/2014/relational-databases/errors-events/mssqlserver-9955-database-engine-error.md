---
title: MSSQLSERVER_9955 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9955 (Database Engine error)
ms.assetid: 77f30570-7790-4747-b372-eac71c036e19
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56b9f9b4b7923f8973bd7167c3c1bf77e92300c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672018"
---
# <a name="mssqlserver_9955"></a><span data-ttu-id="d56e2-102">MSSQLSERVER_9955</span><span class="sxs-lookup"><span data-stu-id="d56e2-102">MSSQLSERVER_9955</span></span>
    
## <a name="details"></a><span data-ttu-id="d56e2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d56e2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d56e2-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="d56e2-104">Product Name</span></span>|<span data-ttu-id="d56e2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d56e2-105">SQL Server</span></span>|  
|<span data-ttu-id="d56e2-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d56e2-106">Event ID</span></span>|<span data-ttu-id="d56e2-107">9955</span><span class="sxs-lookup"><span data-stu-id="d56e2-107">9955</span></span>|  
|<span data-ttu-id="d56e2-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="d56e2-108">Event Source</span></span>|<span data-ttu-id="d56e2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d56e2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d56e2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d56e2-110">Component</span></span>|<span data-ttu-id="d56e2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d56e2-111">SQLEngine</span></span>|  
|<span data-ttu-id="d56e2-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d56e2-112">Symbolic Name</span></span>|<span data-ttu-id="d56e2-113">FTXT2_MSSEARCHACCESSDENY</span><span class="sxs-lookup"><span data-stu-id="d56e2-113">FTXT2_MSSEARCHACCESSDENY</span></span>|  
|<span data-ttu-id="d56e2-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d56e2-114">Message Text</span></span>|<span data-ttu-id="d56e2-115">SQL Server no pudo crear la canalización con nombre '%ls' para comunicarse con el demonio de filtro de texto completo (error de Windows: %d).</span><span class="sxs-lookup"><span data-stu-id="d56e2-115">SQL Server failed to create named pipe '%ls' to communicate with the full-text filter daemon (Windows error: %d).</span></span> <span data-ttu-id="d56e2-116">Quizá existe ya una canalización con nombre para un proceso de host de demonio de filtro, el sistema está bajo de recursos o la búsqueda del número de identificación de seguridad (SID) del grupo de cuentas de demonio de filtro dio error.</span><span class="sxs-lookup"><span data-stu-id="d56e2-116">Either a named pipe already exists for a filter daemon host process, the system is low on resources, or the security identification number (SID) lookup for the filter daemon account group failed.</span></span> <span data-ttu-id="d56e2-117">Para resolver este error, termine los procesos de demonio de filtro de texto completo que se estén ejecutando y, si es necesario, configure de nuevo la cuenta de servicio del iniciador del demonio de texto completo.</span><span class="sxs-lookup"><span data-stu-id="d56e2-117">To resolve this error, terminate any running full-text filter daemon processes, and if necessary reconfigure the full-text daemon launcher service account.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d56e2-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="d56e2-118">Explanation</span></span>  
 <span data-ttu-id="d56e2-119">Este mensaje se produce porque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no pudo crear una canalización con nombre para comunicarse con el demonio de filtro de texto completo.</span><span class="sxs-lookup"><span data-stu-id="d56e2-119">This message occurs because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failed to create a named pipe to communicate with the full-text filter daemon.</span></span> <span data-ttu-id="d56e2-120">Quizá existe ya una canalización con nombre para un proceso de host de demonio de filtro, el sistema está bajo de recursos o la búsqueda del número de identificación de seguridad (SID) del grupo de cuentas de demonio de filtro dio error.</span><span class="sxs-lookup"><span data-stu-id="d56e2-120">Either a named pipe already exists for a filter daemon host process, the system is low on resources, or the security identification number (SID) lookup for the filter daemon account group failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d56e2-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d56e2-121">User Action</span></span>  
 <span data-ttu-id="d56e2-122">Para resolver este error, termine los procesos de demonio de filtro de texto completo que se estén ejecutando y, si es necesario, configure de nuevo la cuenta host del demonio de texto completo con el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d56e2-122">To resolve this error, terminate any running full-text filter daemon processes, and if necessary reconfigure the full-text daemon host account by using the SQL Server Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d56e2-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d56e2-123">See Also</span></span>  
 <span data-ttu-id="d56e2-124">[Administrador de configuración de SQL Server](../sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="d56e2-124">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="d56e2-125">[Establecer la cuenta de servicio para el selector de demonio de filtro de texto completo](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="d56e2-125">[Set the Service Account for the Full-text Filter Daemon Launcher](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 [<span data-ttu-id="d56e2-126">Búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="d56e2-126">Full-Text Search</span></span>](../search/full-text-search.md)  
  
  
