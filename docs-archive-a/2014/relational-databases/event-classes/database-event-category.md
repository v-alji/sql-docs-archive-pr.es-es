---
title: Base de datos (categoría de eventos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- event classes [SQL Server], Database event category
- Database event category [SQL Server]
- SQL Server event classes, Database event category
ms.assetid: b61af738-f144-4992-b0b2-d44cb7240991
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2860e1434611393c941a639280343f736073c709
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674832"
---
# <a name="database-event-category"></a><span data-ttu-id="f5d7e-102">Base de datos (categoría de eventos)</span><span class="sxs-lookup"><span data-stu-id="f5d7e-102">Database Event Category</span></span>
  <span data-ttu-id="f5d7e-103">La categoría de evento **Base de datos** contiene clases de eventos para supervisar [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5d7e-103">The **Database** event category contains event classes to monitor the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5d7e-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f5d7e-104">In This Section</span></span>  
  
|<span data-ttu-id="f5d7e-105">Tema</span><span class="sxs-lookup"><span data-stu-id="f5d7e-105">Topic</span></span>|<span data-ttu-id="f5d7e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5d7e-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f5d7e-107">Data File Auto Grow (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="f5d7e-107">Data File Auto Grow Event Class</span></span>](data-file-auto-grow-event-class.md)|<span data-ttu-id="f5d7e-108">Indica que el archivo de datos creció automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f5d7e-108">Indicates that the data file grew automatically.</span></span> <span data-ttu-id="f5d7e-109">Este evento no se desencadena si se aumentó explícitamente el archivo de datos mediante ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="f5d7e-109">This event is not triggered if the data file is grown explicitly through ALTER DATABASE.</span></span>|  
|[<span data-ttu-id="f5d7e-110">Data File Auto Shrink (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="f5d7e-110">Data File Auto Shrink Event Class</span></span>](data-file-auto-shrink-event-class.md)|<span data-ttu-id="f5d7e-111">Indica que se ha reducido el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="f5d7e-111">Indicates that the data file has been shrunk.</span></span>|  
|[<span data-ttu-id="f5d7e-112">Database Mirroring Connection (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="f5d7e-112">Database Mirroring Connection Event Class</span></span>](database-mirroring-connection-event-class.md)|<span data-ttu-id="f5d7e-113">Evento generado para informar del estado de una conexión de transporte para la creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f5d7e-113">An event generated to report the status of a transport connection for database mirroring.</span></span>|  
|[<span data-ttu-id="f5d7e-114">Database Mirroring State Change (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="f5d7e-114">Database Mirroring State Change Event Class</span></span>](database-mirroring-state-change-event-class.md)|<span data-ttu-id="f5d7e-115">Indica cuando cambia el estado de una base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="f5d7e-115">Indicates when the state of a mirrored database changes.</span></span>|  
|[<span data-ttu-id="f5d7e-116">Database Suspect Data Page (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="f5d7e-116">Database Suspect Data Page Event Class</span></span>](database-suspect-data-page-event-class.md)|<span data-ttu-id="f5d7e-117">Indica cuando una página se agrega a la tabla **suspect_pages** en la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="f5d7e-117">Indicates when a page is added to the **suspect_pages** table in the **msdb** database.</span></span>|  
|[<span data-ttu-id="f5d7e-118">Log File Auto Grow (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="f5d7e-118">Log File Auto Grow Event Class</span></span>](log-file-auto-grow-event-class.md)|<span data-ttu-id="f5d7e-119">Indica que el archivo de registro creció automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f5d7e-119">Indicates that the log file grew automatically.</span></span> <span data-ttu-id="f5d7e-120">Este evento no se desencadena si el archivo de registro se aumentó explícitamente mediante ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="f5d7e-120">This event is not triggered if the log file is grown explicitly through ALTER DATABASE.</span></span>|  
|[<span data-ttu-id="f5d7e-121">Log File Auto Shrink (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="f5d7e-121">Log File Auto Shrink Event Class</span></span>](log-file-auto-shrink-event-class.md)|<span data-ttu-id="f5d7e-122">Indica que el archivo de registro creció automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f5d7e-122">Indicates that the log file grew automatically.</span></span> <span data-ttu-id="f5d7e-123">Este evento no se desencadena si el archivo de registro se reduce explícitamente mediante la instrucción ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="f5d7e-123">This event is not triggered if the log file shrinks explicitly through ALTER DATABASE.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5d7e-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5d7e-124">See Also</span></span>  
 [<span data-ttu-id="f5d7e-125">Eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="f5d7e-125">Extended Events</span></span>](../extended-events/extended-events.md)  
  
  
