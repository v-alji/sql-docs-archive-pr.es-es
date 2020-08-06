---
title: Funcionamiento de los puntos de comprobación para tablas con optimización para memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 47975bd5-373f-43cd-946a-da8e8088b610
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 07560ea0bf147198fb759f6769ae1c6d5c68a71e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749913"
---
# <a name="checkpoint-operation-for-memory-optimized-tables"></a><span data-ttu-id="6b78b-102">Funcionamiento de los puntos de comprobación para tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="6b78b-102">Checkpoint Operation for Memory-Optimized Tables</span></span>
  <span data-ttu-id="6b78b-103">Es necesario que se produzca un punto de comprobación periódicamente para los datos optimizados para memoria en los archivos delta y de datos para avanzar la parte activa del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="6b78b-103">A checkpoint needs to occur periodically for memory-optimized data in data and delta files to advance the active part of transaction log.</span></span> <span data-ttu-id="6b78b-104">El punto de comprobación permite que las tablas optimizadas para memoria se restauren o se recuperen hasta el último punto de comprobación correcto y después se aplique la parte activa del registro de transacciones para actualizar las tablas optimizadas para memoria al momento dado actual.</span><span class="sxs-lookup"><span data-stu-id="6b78b-104">The checkpoint allows memory-optimized tables to restore or recover to the last successful checkpoint and then the active portion of transaction log is applied to update the memory-optimized tables to complete the recovery.</span></span> <span data-ttu-id="6b78b-105">La operación de punto de comprobación para las tablas basadas en disco y para las tablas optimizadas para memoria es distinta.</span><span class="sxs-lookup"><span data-stu-id="6b78b-105">The checkpoint operation for disk-based tables and memory-optimized tables are distinct operations.</span></span> <span data-ttu-id="6b78b-106">A continuación se describen los diferentes escenarios y el comportamiento de punto de comprobación para las tablas en disco y para las optimizadas para memoria:</span><span class="sxs-lookup"><span data-stu-id="6b78b-106">The following describes different scenarios and the checkpoint behavior for disk-based and memory-optimized tables:</span></span>  
  
## <a name="manual-checkpoint"></a><span data-ttu-id="6b78b-107">Punto de comprobación manual</span><span class="sxs-lookup"><span data-stu-id="6b78b-107">Manual Checkpoint</span></span>  
 <span data-ttu-id="6b78b-108">Cuando se emite un punto de comprobación manual, cierra el punto de comprobación tanto para las tablas optimizadas para memoria como para las basadas en disco.</span><span class="sxs-lookup"><span data-stu-id="6b78b-108">When you issue a manual checkpoint, it closes the checkpoint for both disk-based and memory-optimized tables.</span></span> <span data-ttu-id="6b78b-109">El archivo de datos activo se cierra aunque puede estar parcialmente lleno.</span><span class="sxs-lookup"><span data-stu-id="6b78b-109">The active data file is closed even though it may be partially filled.</span></span>  
  
## <a name="automatic-checkpoint"></a><span data-ttu-id="6b78b-110">Punto de comprobación automático</span><span class="sxs-lookup"><span data-stu-id="6b78b-110">Automatic Checkpoint</span></span>  
 <span data-ttu-id="6b78b-111">El punto de comprobación automático se implementa de forma distinta para las tablas basadas en disco y las tablas optimizadas para memoria debido a las diferentes formas en que se conservan los datos.</span><span class="sxs-lookup"><span data-stu-id="6b78b-111">Automatic checkpoint is implemented differently for disk-based and memory-optimized tables because of the different ways the data is persisted.</span></span>  
  
 <span data-ttu-id="6b78b-112">Para las tablas basadas en disco, se usa un punto de comprobación automático basado en la opción de configuración del intervalo de recuperación (para obtener más información, vea [Cambiar el tiempo de recuperación de destino de una base de datos &#40;SQL Server&#41;](../logs/change-the-target-recovery-time-of-a-database-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="6b78b-112">For disk-based tables, an automatic checkpoint is taken based on the recovery interval configuration option (for more information, see [Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../logs/change-the-target-recovery-time-of-a-database-sql-server.md)).</span></span>  
  
 <span data-ttu-id="6b78b-113">En el caso de las tablas optimizadas para memoria, se toma un punto de comprobación automático cuando el archivo de registro de transacciones es mayor que 512 MB desde el último punto de control.</span><span class="sxs-lookup"><span data-stu-id="6b78b-113">For memory-optimized tables, an automatic checkpoint is taken when transaction log file becomes bigger than 512 MB since the last checkpoint.</span></span> <span data-ttu-id="6b78b-114">512 MB incluye las entradas del registro de transacciones para las tablas optimizadas para memoria y en disco.</span><span class="sxs-lookup"><span data-stu-id="6b78b-114">512 MB includes transaction log records for both disk-based and memory-optimized tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b78b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b78b-115">See Also</span></span>  
 [<span data-ttu-id="6b78b-116">Crear y administrar el almacenamiento de objetos optimizados para memoria</span><span class="sxs-lookup"><span data-stu-id="6b78b-116">Creating and Managing Storage for Memory-Optimized Objects</span></span>](creating-and-managing-storage-for-memory-optimized-objects.md)  
  
  
