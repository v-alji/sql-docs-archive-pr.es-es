---
title: MSSQLSERVER_32044 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32044 (Database Engine error)
ms.assetid: f2d073be-d9a1-4837-8a38-028d3e3403bd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27d9655c3a908f1302f048c6f68159d4f610367a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672068"
---
# <a name="mssqlserver_32044"></a><span data-ttu-id="a65a1-102">MSSQLSERVER_32044</span><span class="sxs-lookup"><span data-stu-id="a65a1-102">MSSQLSERVER_32044</span></span>
    
## <a name="details"></a><span data-ttu-id="a65a1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a65a1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a65a1-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a65a1-104">Product Name</span></span>|<span data-ttu-id="a65a1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a65a1-105">SQL Server</span></span>|  
|<span data-ttu-id="a65a1-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a65a1-106">Event ID</span></span>|<span data-ttu-id="a65a1-107">32044</span><span class="sxs-lookup"><span data-stu-id="a65a1-107">32044</span></span>|  
|<span data-ttu-id="a65a1-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a65a1-108">Event Source</span></span>|<span data-ttu-id="a65a1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a65a1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a65a1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a65a1-110">Component</span></span>|<span data-ttu-id="a65a1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a65a1-111">SQLEngine</span></span>|  
|<span data-ttu-id="a65a1-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a65a1-112">Symbolic Name</span></span>|<span data-ttu-id="a65a1-113">SQLErrorNum32044</span><span class="sxs-lookup"><span data-stu-id="a65a1-113">SQLErrorNum32044</span></span>|  
|<span data-ttu-id="a65a1-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a65a1-114">Message Text</span></span>|<span data-ttu-id="a65a1-115">Se produjo la alerta de 'sobrecarga de confirmación del servidor reflejado'.</span><span class="sxs-lookup"><span data-stu-id="a65a1-115">The alert for 'mirror commit overhead' has been raised.</span></span> <span data-ttu-id="a65a1-116">El valor actual de '%d' sobrepasa el umbral '%d'.</span><span class="sxs-lookup"><span data-stu-id="a65a1-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a65a1-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="a65a1-117">Explanation</span></span>  
 <span data-ttu-id="a65a1-118">Este evento de creación de reflejo de la base de datos se genera en la instancia del servidor principal para indicar que el tiempo de espera de confirmación agregado alcanzó o superó el valor umbral especificado por el usuario debido a la creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a65a1-118">This database mirroring event is issued on the principal server instance to indicate that the aggregate commit wait time reached or exceeded a user-specified threshold value because of database mirroring.</span></span> <span data-ttu-id="a65a1-119">El tiempo de espera es el producto del número de transacciones y el tiempo de cada una.</span><span class="sxs-lookup"><span data-stu-id="a65a1-119">The wait time is the product of the number of transactions and the time of each.</span></span> <span data-ttu-id="a65a1-120">Por ejemplo, los siguientes casos producen 1000 milisegundos de tiempo de espera: 1000 transacciones \* 1 milisegundo y 1 transacción \* 1000 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="a65a1-120">For example, the following cases both produce 1000 milliseconds of wait time: 1000 transactions \* 1 millisecond, and 1 transaction \* 1000 milliseconds.</span></span> <span data-ttu-id="a65a1-121">El aumento en el tiempo de espera de confirmación puede deberse a una sobrecarga en el recuento de transacciones, retrasos al enviar el registro o retrasos al vaciar el registro en la instancia del servidor reflejado.</span><span class="sxs-lookup"><span data-stu-id="a65a1-121">An increased commit wait time can be caused by a surge in the transaction count, delays in sending the log, or delays in flushing the log on the mirror server instance.</span></span>  
  
 <span data-ttu-id="a65a1-122">La cantidad de sobrecarga de confirmación de reflejo es una medida del rendimiento que le puede ayudar a evaluar el impacto sobre el rendimiento actual del funcionamiento sincrónico.</span><span class="sxs-lookup"><span data-stu-id="a65a1-122">The amount of mirror commit overhead is a performance metric that can help you evaluate the current performance impact of synchronous operation.</span></span> <span data-ttu-id="a65a1-123">Esta medida solo es relevante en el modo de alta seguridad.</span><span class="sxs-lookup"><span data-stu-id="a65a1-123">This metric is relevant only in high-safety mode.</span></span> <span data-ttu-id="a65a1-124">Como el modo de alta seguridad es sincrónico, la instancia del servidor principal espera a confirmar la transacción después de enviar una entrada de registro a la instancia del servidor reflejado hasta que recibe la confirmación de que la instancia del servidor reflejado ha escrito la entrada de registro en el disco.</span><span class="sxs-lookup"><span data-stu-id="a65a1-124">Because high-safety mode is synchronous, the principal server instance waits to commit the transaction after it sends a log record to the mirror server instance until it receives confirmation that the mirror server instance has written the log record to disk.</span></span> <span data-ttu-id="a65a1-125">La entrada de registro permanece en disco en la instancia del servidor reflejado mientras espera a ser restaurada en la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="a65a1-125">The log record remains on disk on the mirror server instance while it waits to be restored to the mirror database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a65a1-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a65a1-126">User Action</span></span>  
 <span data-ttu-id="a65a1-127">Compruebe las cargas en las instancias del servidor principal y reflejado y su conexión de red para localizar la causa.</span><span class="sxs-lookup"><span data-stu-id="a65a1-127">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a65a1-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a65a1-128">See Also</span></span>  
 <span data-ttu-id="a65a1-129">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a65a1-129">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="a65a1-130">Usar alertas y umbrales de advertencia de las métricas de rendimiento de la creación de reflejo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a65a1-130">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
