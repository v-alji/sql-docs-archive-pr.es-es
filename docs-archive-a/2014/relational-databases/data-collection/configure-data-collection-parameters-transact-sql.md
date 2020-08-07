---
title: Configurar parámetros para la recopilación de datos (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
ms.assetid: 850905b6-35d2-4ed1-ab51-de64daa832b2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a8333b47612b4fbd933ef132e886b8125ffb58a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747033"
---
# <a name="configure-data-collection-parameters-transact-sql"></a><span data-ttu-id="0039b-102">Configurar parámetros para la recopilación de datos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0039b-102">Configure Data Collection Parameters (Transact-SQL)</span></span>
  <span data-ttu-id="0039b-103">Antes de crear un conjunto de recopilación personalizado, primero debe configurar los parámetros de recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="0039b-103">Before you create a custom collection set, you must first configure data collection parameters.</span></span> <span data-ttu-id="0039b-104">Puede hacerlo mediante los procedimientos almacenados que se proporcionan con el recopilador de datos.</span><span class="sxs-lookup"><span data-stu-id="0039b-104">You can do this by using the stored procedures that are provided with the data collector.</span></span> <span data-ttu-id="0039b-105">Para realizar esta tarea debe usar el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y llevar a cabo el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0039b-105">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0039b-106">Solo se configuran una vez los parámetros de recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="0039b-106">You only configure data collection parameters once.</span></span> <span data-ttu-id="0039b-107">Tras la configuración, esos parámetros se usan para cualquier conjunto de recopilación adicional que cree.</span><span class="sxs-lookup"><span data-stu-id="0039b-107">After configuration, these parameters are used for any additional collection sets that you create.</span></span>  
  
### <a name="configure-data-collection-parameters"></a><span data-ttu-id="0039b-108">Configurar parámetros para la recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="0039b-108">Configure data collection parameters</span></span>  
  
1.  <span data-ttu-id="0039b-109">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese a la base de datos donde desea crear un conjunto de recopilación personalizado.</span><span class="sxs-lookup"><span data-stu-id="0039b-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the database where you want to create a custom collection set.</span></span>  
  
2.  <span data-ttu-id="0039b-110">En el Editor de consultas, emita las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="0039b-110">In Query Editor, issue the following statements.</span></span>  
  
    ```sql  
    USE msdb;  
    EXEC sp_syscollector_set_warehouse_instance_name N'INSTANCE_NAME';-- where instance name is the name of the SQL Server instance  
    EXEC sp_syscollector_set_warehouse_database_name N'MDW';  
    EXEC sp_syscollector_set_cache_directory N'D:\tempdata';  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0039b-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0039b-111">See Also</span></span>  
 <span data-ttu-id="0039b-112">[Recopilación de datos](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="0039b-112">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="0039b-113">Procedimientos almacenados del recopilador de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0039b-113">Data Collector Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql)  
  
  
