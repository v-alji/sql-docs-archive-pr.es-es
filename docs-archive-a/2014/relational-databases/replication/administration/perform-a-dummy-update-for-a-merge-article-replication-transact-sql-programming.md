---
title: Realizar una actualización ficticia de un artículo de mezcla (programación de la replicación con Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_mergedummyupdate
- dummy updates [SQL Server replication]
ms.assetid: 2f339210-4d85-4843-bd94-e86f7100d3ef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07fa0f868b2c3f98496046b138424d7d3a2fa2fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748087"
---
# <a name="perform-a-dummy-update-for-a-merge-article-replication-transact-sql-programming"></a><span data-ttu-id="083b6-102">Realizar una actualización ficticia de un artículo de mezcla (programación de la replicación con Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="083b6-102">Perform a Dummy Update for a Merge Article (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="083b6-103">La replicación de mezcla utiliza los desencadenadores como parte del proceso de la replicación; cuando se actualiza una tabla tabla publicada, se activa un desencadenador de actualización.</span><span class="sxs-lookup"><span data-stu-id="083b6-103">Merge replication uses triggers as part of the replication process; when an update is made to published table, an update trigger fires.</span></span> <span data-ttu-id="083b6-104">En algunos casos, los datos pueden actualizarse sin que el desencadenador se active, como durante las operaciones de UPDATETEXT y WRITETEXT.</span><span class="sxs-lookup"><span data-stu-id="083b6-104">In some cases, data can be updated without the trigger firing, such as during the WRITETEXT and UPDATETEXT operations.</span></span> <span data-ttu-id="083b6-105">En estos casos, necesita agregar explícitamente una instrucción UPDATE ficticia para replicar el cambio.</span><span class="sxs-lookup"><span data-stu-id="083b6-105">In these cases, you need to add a dummy UPDATE statement explicitly to replicate the change.</span></span> <span data-ttu-id="083b6-106">Puede agregar una instrucción UPDATE ficticia mediante los procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="083b6-106">You can add a dummy UPDATE statement using replication stored procedures.</span></span>  
  
### <a name="to-add-a-dummy-update-statement"></a><span data-ttu-id="083b6-107">Para agregar una instrucción UPDATE ficticia</span><span class="sxs-lookup"><span data-stu-id="083b6-107">To add a dummy UPDATE statement</span></span>  
  
1.  <span data-ttu-id="083b6-108">Ejecute la operación (por ejemplo, UPDATETEXT) en una fila de una tabla publicada de mezcla que requiera una actualización ficticia.</span><span class="sxs-lookup"><span data-stu-id="083b6-108">Execute the operation (for example, UPDATETEXT) on a row in a merge published table  that requires a dummy update.</span></span>  
  
2.  <span data-ttu-id="083b6-109">En el servidor (publicador o suscriptor) de la base de datos donde se realizó la modificación, ejecute [sp_mergedummyupdate &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergedummyupdate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="083b6-109">At the server (Publisher or Subscriber) on the database where the change was made, execute [sp_mergedummyupdate &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergedummyupdate-transact-sql).</span></span> <span data-ttu-id="083b6-110">Especifique la tabla en la que se realizó el cambio **@source_object** y el identificador único de la fila modificada para **@rowguid** .</span><span class="sxs-lookup"><span data-stu-id="083b6-110">Specify the table on which the change was made for **@source_object**, and the unique identifier of the changed row for **@rowguid**.</span></span>  
  
3.  <span data-ttu-id="083b6-111">Sincronice la suscripción para replicar la fila cambiada.</span><span class="sxs-lookup"><span data-stu-id="083b6-111">Synchronize the subscription to replicate the changed row.</span></span>  
  
  
