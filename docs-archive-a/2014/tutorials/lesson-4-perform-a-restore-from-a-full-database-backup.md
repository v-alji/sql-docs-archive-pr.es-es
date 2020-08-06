---
title: 'Lección 4: realizar una restauración a partir de una copia de seguridad completa de la base de datos | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 580f76e6-9802-4abc-9043-db6de592c733
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 9906ea14c2f76a49644a8f76fbd894adf8b9d500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671866"
---
# <a name="lesson-4-perform-a-restore-from-a-full-database-backup"></a><span data-ttu-id="cb9e9-102">Lección 4: Realización de una restauración desde una copia de seguridad completa de la base de datos</span><span class="sxs-lookup"><span data-stu-id="cb9e9-102">Lesson 4: Perform a Restore From a Full Database Backup</span></span>
  <span data-ttu-id="cb9e9-103">En esta lección se muestra el uso de una instrucción tsql para realizar una restauración desde una copia de seguridad completa de la base de datos creada en la lección anterior.</span><span class="sxs-lookup"><span data-stu-id="cb9e9-103">This lesson demonstrates the use of a tsql statement to perform a restore from a full database backup created in the previous lesson.</span></span>  
  
## <a name="perform-a-restore-of-a-database-backup"></a><span data-ttu-id="cb9e9-104">Realizar una restauración de una copia de seguridad de la base de datos</span><span class="sxs-lookup"><span data-stu-id="cb9e9-104">Perform a Restore of a Database Backup</span></span>  
 <span data-ttu-id="cb9e9-105">Para restaurar una copia de seguridad completa de la base de datos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cb9e9-105">To restore a full database backup, use the following steps:</span></span>  
  
1.  <span data-ttu-id="cb9e9-106">Conectarse a [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb9e9-106">Connect to [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="cb9e9-107">En el **Explorador de objetos**, conéctese a la instancia de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb9e9-107">In the **Object Explorer**, connect to the instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
3.  <span data-ttu-id="cb9e9-108">En el menú Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="cb9e9-108">On the Standard menu bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="cb9e9-109">Copie y pegue el ejemplo siguiente en la ventana de consulta, y modifíquelo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="cb9e9-109">Copy and paste the following example into the query window, modify as needed.</span></span>  
  
    ```  
    RESTORE DATABASE AdventureWorks2012   
    FROM URL = 'https://mystorageaccount.blob.core.windows.net/privatecontainertest/AdventureWorks2012.bak'   
    WITH CREDENTIAL = 'mycredential';  
    , STATS = 5 - use this to see monitor the progress  
    GO  
  
    ```  
  
5.  <span data-ttu-id="cb9e9-110">Compruebe la instrucción T-SQL y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="cb9e9-110">Verify the T-SQL statement and click **Execute**</span></span>  
  
### <a name="return-to-tutorials-portal"></a><span data-ttu-id="cb9e9-111">Volver al portal de tutoriales</span><span class="sxs-lookup"><span data-stu-id="cb9e9-111">Return to Tutorials Portal</span></span>  
 <span data-ttu-id="cb9e9-112">[Tutorial: SQL Server copias de seguridad y restauración en Azure BLOB Storage Service](../relational-databases/tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="cb9e9-112">[Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service](../relational-databases/tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md).</span></span>  
  
  
