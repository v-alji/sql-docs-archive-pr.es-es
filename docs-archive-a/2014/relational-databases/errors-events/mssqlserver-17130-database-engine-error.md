---
title: MSSQLSERVER_17130 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17130 (Database Engine error)
ms.assetid: 7ce6afca-221d-402f-89df-da7e74a339a8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b63be325273e4df33d837ec1548ed46701323977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745796"
---
# <a name="mssqlserver_17130"></a><span data-ttu-id="eab23-102">MSSQLSERVER_17130</span><span class="sxs-lookup"><span data-stu-id="eab23-102">MSSQLSERVER_17130</span></span>
    
## <a name="details"></a><span data-ttu-id="eab23-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="eab23-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eab23-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="eab23-104">Product Name</span></span>|<span data-ttu-id="eab23-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="eab23-105">SQL Server</span></span>|  
|<span data-ttu-id="eab23-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="eab23-106">Event ID</span></span>|<span data-ttu-id="eab23-107">17130</span><span class="sxs-lookup"><span data-stu-id="eab23-107">17130</span></span>|  
|<span data-ttu-id="eab23-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="eab23-108">Event Source</span></span>|<span data-ttu-id="eab23-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="eab23-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="eab23-110">Componente</span><span class="sxs-lookup"><span data-stu-id="eab23-110">Component</span></span>|<span data-ttu-id="eab23-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="eab23-111">SQLEngine</span></span>|  
|<span data-ttu-id="eab23-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="eab23-112">Symbolic Name</span></span>|<span data-ttu-id="eab23-113">INIT_NOLOCKSPACE</span><span class="sxs-lookup"><span data-stu-id="eab23-113">INIT_NOLOCKSPACE</span></span>|  
|<span data-ttu-id="eab23-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="eab23-114">Message Text</span></span>|<span data-ttu-id="eab23-115">Memoria insuficiente para el número de bloqueos configurado.</span><span class="sxs-lookup"><span data-stu-id="eab23-115">Not enough memory for the configured number of locks.</span></span> <span data-ttu-id="eab23-116">Se está intentando iniciar con una tabla hash de bloqueos más pequeña, lo que puede afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="eab23-116">Attempting to start with a smaller lock hash table, which may impact performance.</span></span> <span data-ttu-id="eab23-117">Póngase en contacto con el administrador de la base de datos para configurar más memoria para esta instancia del motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="eab23-117">Contact the database administrator to configure more memory for this instance of the Database Engine.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eab23-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="eab23-118">Explanation</span></span>  
 <span data-ttu-id="eab23-119">No hay suficiente memoria para el tamaño de tabla hash del administrador de bloqueos deseado.</span><span class="sxs-lookup"><span data-stu-id="eab23-119">Not enough memory for the desired lock manager hash table size.</span></span>  <span data-ttu-id="eab23-120">Se intentará asignar una tabla hash menor.</span><span class="sxs-lookup"><span data-stu-id="eab23-120">An attempt will be made to allocate a smaller hash table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eab23-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="eab23-121">User Action</span></span>  
 <span data-ttu-id="eab23-122">Compruebe los parámetros de configuración de memoria del servidor (memoria de servidor máxima, memoria de servidor mínima) y si hay presiones de memoria.</span><span class="sxs-lookup"><span data-stu-id="eab23-122">Check server memory configuration parameters (min/max server memory), check for memory pressures.</span></span> <span data-ttu-id="eab23-123">Proporcione más memoria para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eab23-123">Provide SQL Server more memory.</span></span>  
  
  
