---
title: 'Lección 3: escribir una copia de seguridad completa de la base de datos en el servicio Azure Blob Storage | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 454c8296-64e9-46ed-b141-5ebfbc8a4fe2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 17e7e6b608d248a48cde52f1107bb910f06d64ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743718"
---
# <a name="lesson-3-write-a-full-database-backup-to-the-azure-blob-storage-service"></a><span data-ttu-id="0c89d-102">Lección 3: Escribir una copia de seguridad completa de la base de datos en el servicio Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="0c89d-102">Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service</span></span>
  <span data-ttu-id="0c89d-103">En esta lección se muestra el uso de la instrucción TSQL para realizar una copia de seguridad completa de la base de datos en el servicio Azure BLOB Storage.</span><span class="sxs-lookup"><span data-stu-id="0c89d-103">This lesson demonstrates the use of tsql statement to perform a full database backup to Azure Blob storage service.</span></span>  
  
## <a name="perform-a-full-database-backup-to-the-azure-blob-storage-service"></a><span data-ttu-id="0c89d-104">Realizar una copia de seguridad completa de la base de datos en el servicio Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="0c89d-104">Perform a Full Database Backup to the Azure Blob Storage Service</span></span>  
 <span data-ttu-id="0c89d-105">Para realizar una copia de seguridad completa de la base de datos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0c89d-105">To create a full database backup, use the following steps:</span></span>  
  
1.  <span data-ttu-id="0c89d-106">Conectarse a [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c89d-106">Connect to [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="0c89d-107">En el **Explorador de objetos**, conéctese a la instancia de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c89d-107">In the **Object Explorer**, connect to the instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
3.  <span data-ttu-id="0c89d-108">En el menú Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="0c89d-108">On the Standard menu bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="0c89d-109">Copie y pegue el siguiente ejemplo en la ventana de consulta, realice las modificaciones necesarias y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="0c89d-109">Copy and paste the following example into the query window, modify as needed, and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE[AdventureWorks2012]   
    TO URL = 'https://mystorageaccount.blob.core.windows.net/privatecontainertest/AdventureWorks2012.bak'   
    /* URL includes the endpoint for the BLOB service, followed by the container name, and the name of the backup file*/   
    WITH CREDENTIAL = 'mycredential';  
    /* name of the credential you created in the previous step */   
    GO  
  
    ```  
  
5.  <span data-ttu-id="0c89d-110">En el Explorador de objetos, conéctese a Almacenamiento de Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="0c89d-110">In the object explorer, connect to Azure Storage.</span></span> <span data-ttu-id="0c89d-111">Busque el contenedor y los archivos de copia de seguridad recién creados.</span><span class="sxs-lookup"><span data-stu-id="0c89d-111">Browse to find the container and the newly created backup files.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="0c89d-112">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="0c89d-112">Next Lesson</span></span>  
 <span data-ttu-id="0c89d-113">[Lección 4: realizar una restauración a partir de una copia de seguridad completa de la base de datos](../../2014/tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md).</span><span class="sxs-lookup"><span data-stu-id="0c89d-113">[Lesson 4: Perform a Restore From a Full Database Backup](../../2014/tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md).</span></span>  
  
  
