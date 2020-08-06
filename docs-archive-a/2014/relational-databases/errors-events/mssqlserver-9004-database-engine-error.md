---
title: MSSQLSERVER_9004 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9004 (Database Engine error)
ms.assetid: b528bb49-340c-4a81-9c8d-cefce6562f16
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 910665b4349e5b13c5abb4fd687dcf0c6fc122cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672037"
---
# <a name="mssqlserver_9004"></a><span data-ttu-id="822ea-102">MSSQLSERVER_9004</span><span class="sxs-lookup"><span data-stu-id="822ea-102">MSSQLSERVER_9004</span></span>
    
## <a name="details"></a><span data-ttu-id="822ea-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="822ea-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="822ea-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="822ea-104">Product Name</span></span>|<span data-ttu-id="822ea-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="822ea-105">SQL Server</span></span>|  
|<span data-ttu-id="822ea-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="822ea-106">Event ID</span></span>|<span data-ttu-id="822ea-107">9004</span><span class="sxs-lookup"><span data-stu-id="822ea-107">9004</span></span>|  
|<span data-ttu-id="822ea-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="822ea-108">Event Source</span></span>|<span data-ttu-id="822ea-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="822ea-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="822ea-110">Componente</span><span class="sxs-lookup"><span data-stu-id="822ea-110">Component</span></span>|<span data-ttu-id="822ea-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="822ea-111">SQLEngine</span></span>|  
|<span data-ttu-id="822ea-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="822ea-112">Symbolic Name</span></span>|<span data-ttu-id="822ea-113">LOG_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="822ea-113">LOG_CORRUPT</span></span>|  
|<span data-ttu-id="822ea-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="822ea-114">Message Text</span></span>|<span data-ttu-id="822ea-115">Se produjo un error mientras se procesaba el registro para la base de datos '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="822ea-115">An error occurred while processing the log for database '%.\*ls'.</span></span>  <span data-ttu-id="822ea-116">If possible, restore from backup.</span><span class="sxs-lookup"><span data-stu-id="822ea-116">If possible, restore from backup.</span></span> <span data-ttu-id="822ea-117">Si no dispone de una copia de seguridad, puede ser necesario generar de nuevo el registro.</span><span class="sxs-lookup"><span data-stu-id="822ea-117">If a backup is not available, it might be necessary to rebuild the log.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="822ea-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="822ea-118">Explanation</span></span>  
 <span data-ttu-id="822ea-119">Se encontró un error al procesar el registro durante la operación de reversión, recuperación o replicación.</span><span class="sxs-lookup"><span data-stu-id="822ea-119">An error was encountered while processing the log during rollback, recovery, or replication.</span></span> <span data-ttu-id="822ea-120">Esto puede indicar un error detectado por el sistema operativo o un error de coherencia interno detectado por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="822ea-120">This could indicate an error detected by the operating system-or an internal consistency error detected by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="822ea-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="822ea-121">User Action</span></span>  
 <span data-ttu-id="822ea-122">Este error se corregirá con una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="822ea-122">One of the following actions will correct this error:</span></span>  
  
-   <span data-ttu-id="822ea-123">Restaure desde una copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="822ea-123">Restore from a backup.</span></span>  
  
-   <span data-ttu-id="822ea-124">Vuelva a generar el registro</span><span class="sxs-lookup"><span data-stu-id="822ea-124">Rebuild the log.</span></span>  
  
 <span data-ttu-id="822ea-125">Además, consulte los registros de eventos y errores del sistema para identificar posibles causas del problema en el sistema.</span><span class="sxs-lookup"><span data-stu-id="822ea-125">Also, check system event and error logs to identify issues within the system that may have caused the problem.</span></span>  
  
  
