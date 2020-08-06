---
title: Opciones de artículos para la replicación transaccional | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- articles [SQL Server replication], transactional replication options
- transactional replication, article options
ms.assetid: 3469b185-0ea5-4690-a71c-717230d886b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1cc13a3d11e35ed47eac4ff401fb8b7cb607b32b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673632"
---
# <a name="article-options-for-transactional-replication"></a><span data-ttu-id="724a9-102">Opciones de artículos para la replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="724a9-102">Article Options for Transactional Replication</span></span>
  <span data-ttu-id="724a9-103">Existen varias opciones para artículos en las publicaciones transaccionales.</span><span class="sxs-lookup"><span data-stu-id="724a9-103">There are a number of options for articles in transactional publications.</span></span> <span data-ttu-id="724a9-104">Con la replicación transaccional puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="724a9-104">With transactional replication, you can do the following:</span></span>  
  
-   <span data-ttu-id="724a9-105">Especificar cómo se propagan los cambios desde el publicador a los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="724a9-105">Specify how changes are propagated from the Publisher to Subscribers.</span></span> <span data-ttu-id="724a9-106">Para más información, vea [Especificar cómo se propagan los cambios para los artículos transaccionales](transactional-articles-specify-how-changes-are-propagated.md).</span><span class="sxs-lookup"><span data-stu-id="724a9-106">For more information, see [Specify How Changes Are Propagated for Transactional Articles](transactional-articles-specify-how-changes-are-propagated.md).</span></span>  
  
-   <span data-ttu-id="724a9-107">Especificar que se replique la ejecución de un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="724a9-107">Specify that the execution of a stored procedure be replicated.</span></span> <span data-ttu-id="724a9-108">Esto resulta de utilidad al replicar los resultados de los procedimientos almacenados orientados al mantenimiento que afectan a grandes cantidades de datos.</span><span class="sxs-lookup"><span data-stu-id="724a9-108">This is useful in replicating the results of maintenance-oriented stored procedures that affect large amounts of data.</span></span> <span data-ttu-id="724a9-109">Para más información, vea [Publishing Stored Procedure Execution in Transactional Replication](publishing-stored-procedure-execution-in-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="724a9-109">For more information, see [Publishing Stored Procedure Execution in Transactional Replication](publishing-stored-procedure-execution-in-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="724a9-110">Especificar opciones de esquema, por ejemplo si las restricciones y los desencadenadores se copian en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="724a9-110">Specify schema options, such as whether constraints and triggers are copied to the Subscriber.</span></span> <span data-ttu-id="724a9-111">Para obtener más información, vea [Especificar opciones de esquema](../publish/specify-schema-options.md).</span><span class="sxs-lookup"><span data-stu-id="724a9-111">For more information, see [Specify Schema Options](../publish/specify-schema-options.md).</span></span>  
  
-   <span data-ttu-id="724a9-112">Utilizar filtros de fila y columna.</span><span class="sxs-lookup"><span data-stu-id="724a9-112">Use row filters and column filters.</span></span> <span data-ttu-id="724a9-113">Filtrar artículos de tabla permite crear particiones de los datos que se van a publicar.</span><span class="sxs-lookup"><span data-stu-id="724a9-113">Filtering table articles enables you to create partitions of data to be published.</span></span> <span data-ttu-id="724a9-114">Para obtener más información, vea [Filtrar datos publicados](../publish/filter-published-data.md).</span><span class="sxs-lookup"><span data-stu-id="724a9-114">For more information, see [Filter Published Data](../publish/filter-published-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="724a9-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="724a9-115">See Also</span></span>  
 [<span data-ttu-id="724a9-116">Publicar datos y objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="724a9-116">Publish Data and Database Objects</span></span>](../publish/publish-data-and-database-objects.md)  
  
  
