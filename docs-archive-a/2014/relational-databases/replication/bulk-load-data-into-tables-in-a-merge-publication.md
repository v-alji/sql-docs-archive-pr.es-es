---
title: Cargar datos de forma masiva en tablas en una publicación de combinación (programación de la replicación con Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- bulk load [SQL Server replication]
- merge replication bulk loading [SQL Server replication]
- sp_addtabletocontents
ms.assetid: 16e6498a-b449-4051-aec4-ea814a2ad993
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f669a1f7132aa0f588fd89fb9747a7dc9017fcf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750754"
---
# <a name="bulk-load-data-into-tables-in-a-merge-publication-replication-transact-sql-programming"></a><span data-ttu-id="b057e-102">Realizar una carga masiva de datos en tablas de una publicación de mezcla (programación de la replicación con Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b057e-102">Bulk-Load Data into Tables in a Merge Publication (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="b057e-103">Cuando los datos se cargan en las tablas utilizando [bcp Utility](../../tools/bcp-utility.md) o el comando [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) de forma predeterminada, los desencadenadores de replicación de mezcla que mantienen datos del seguimiento en la tabla del sistema [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql) no se activan.</span><span class="sxs-lookup"><span data-stu-id="b057e-103">When data is loaded into tables using the [bcp Utility](../../tools/bcp-utility.md) or the [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) command, by default, the merge replication triggers that maintain tracking data in the [MSmerge_contents](/sql/relational-databases/system-tables/msmerge-contents-transact-sql) system table are not fired.</span></span> <span data-ttu-id="b057e-104">Puede forzar a que se activen los desencadenadores de replicación de mezcla cuando se cargan los datos o puede insertar mediante programación los metadatos de la replicación generados después de la operación de copia masiva utilizando los procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="b057e-104">You can either force the merge replication triggers to fire as the data is loaded, or you can insert the generated replication metadata programmatically after the bulk copy operation using replication stored procedures.</span></span>  
  
### <a name="to-bulk-load-data-into-tables-published-by-merge-replication-using-the-bcp-utility"></a><span data-ttu-id="b057e-105">Para realizar la carga masiva de datos en tablas publicadas mediante replicación de mezcla utilizando la utilidad bcp</span><span class="sxs-lookup"><span data-stu-id="b057e-105">To bulk-load data into tables published by merge replication using the bcp utility</span></span>  
  
1.  <span data-ttu-id="b057e-106">En el publicador o suscriptor, ejecute [bcp Utility](../../tools/bcp-utility.md) o [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) para insertar los datos en una tabla publicada utilizando la replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="b057e-106">At either the Publisher or Subscriber, execute the [bcp Utility](../../tools/bcp-utility.md) or [BULK INSERT](/sql/t-sql/statements/bulk-insert-transact-sql) to insert data into a table published using merge replication.</span></span>  
  
2.  <span data-ttu-id="b057e-107">Utilice uno de los métodos siguientes para asegurarse de que los metadatos de replicación se generan para los datos insertados.</span><span class="sxs-lookup"><span data-stu-id="b057e-107">Use one of the following methods to ensure that replication metadata is generated for the inserted data.</span></span>  
  
    -   <span data-ttu-id="b057e-108">Ejecute la copia masiva mediante la opción de FIRE_TRIGGERS.</span><span class="sxs-lookup"><span data-stu-id="b057e-108">Execute the bulk copy using the FIRE_TRIGGERS option.</span></span>  
  
    -   <span data-ttu-id="b057e-109">En la base de datos en la que se insertaron los datos, ejecute [sp_addtabletocontents &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addtabletocontents-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b057e-109">On the database into which data was inserted, execute [sp_addtabletocontents &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addtabletocontents-transact-sql).</span></span> <span data-ttu-id="b057e-110">Especifique el nombre de la tabla en la que se insertaron los datos **@table_name** .</span><span class="sxs-lookup"><span data-stu-id="b057e-110">Specify the table name into which the data was inserted for **@table_name**.</span></span>  
  
  
