---
title: 'Lección 8: Restaurar una base de datos a Azure Storage | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a9f99670-e1de-441e-972c-69faffcac17a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: adec725d1b519fb67560dc572823ba0a116aaa54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677076"
---
# <a name="lesson-8-restore-a-database-to-azure-storage"></a><span data-ttu-id="0af69-103">Lección 8:</span><span class="sxs-lookup"><span data-stu-id="0af69-103">Lesson 8.</span></span> <span data-ttu-id="0af69-104">Restaurar una base de datos en Azure Storage</span><span class="sxs-lookup"><span data-stu-id="0af69-104">Restore a database to Azure Storage</span></span>
  <span data-ttu-id="0af69-105">En esta lección, aprenderá a crear un archivo de copia de seguridad localmente y, a continuación, lo restaurará en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="0af69-105">In this lesson, you will learn how to create a backup file locally and then restore it to Azure Storage.</span></span> <span data-ttu-id="0af69-106">Tenga en cuenta que puede tener la base de datos en el entorno local o en una máquina virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="0af69-106">Note that you can have your database either on either on-premises or in a virtual machine in Azure.</span></span> <span data-ttu-id="0af69-107">Para seguir esta lección, no es necesario completar las lecciones 4, 5, 6 y 7.</span><span class="sxs-lookup"><span data-stu-id="0af69-107">To follow this lesson, you do not need to complete Lesson 4, 5, 6, and 7.</span></span>  
  
 <span data-ttu-id="0af69-108">En esta lección se supone que ya completó los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0af69-108">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="0af69-109">Tiene una cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="0af69-109">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="0af69-110">Ha creado un contenedor en su cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="0af69-110">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="0af69-111">Ha creado una directiva en un contenedor con derechos de lectura, escritura y enumeración.</span><span class="sxs-lookup"><span data-stu-id="0af69-111">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="0af69-112">También generó una clave SAS.</span><span class="sxs-lookup"><span data-stu-id="0af69-112">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="0af69-113">Ha creado una credencial de SQL Server en el equipo de origen basada en la Firma de acceso compartido.</span><span class="sxs-lookup"><span data-stu-id="0af69-113">You have created a SQL Server credential on the source machine based on Shared Access Signature.</span></span>  
  
-   <span data-ttu-id="0af69-114">Ha creado una base de datos en el equipo de origen.</span><span class="sxs-lookup"><span data-stu-id="0af69-114">You have created a database in the source machine.</span></span>  
  
 <span data-ttu-id="0af69-115">Para restaurar una base de datos a Azure Storage, puede seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0af69-115">To restore a database to Azure Storage, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="0af69-116">En el equipo de origen, inicie SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="0af69-116">In the source machine, start SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="0af69-117">Cuando se conecte a la base de datos recién creada, abra la ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="0af69-117">When connected to the newly created database, open the query window.</span></span> <span data-ttu-id="0af69-118">Ejecute la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="0af69-118">Run the following statement:</span></span>  
  
    ```sql  
  
    USE TestDB3Restore;   
    GO   
    BACKUP DATABASE TestDB3Restore   
    TO DISK = 'C:\BACKUP\TestDB3Restore.Bak'   
       WITH FORMAT,   
       NAME = 'Full Backup of TestDB3Restore'   
    GO  
  
    ```  
  
3.  <span data-ttu-id="0af69-119">Después, copie y ejecute las instrucciones siguientes en la ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="0af69-119">Next, copy and run the following statements in the Query window.</span></span>  
  
    ```sql  
  
    USE master;   
    GO   
    RESTORE DATABASE TestDB3Restore    
    FROM DISK = 'C:\BACKUP\TestDB3Restore.bak'    
    WITH REPLACE,   
    MOVE 'TestDB3Restore' TO 'https://teststorageaccnt.blob.core.windows.net/testcontainrestore/TestDB3Restore.mdf',     
    MOVE 'TestDB3Restore_log' TO 'https://teststorageaccnt.blob.core.windows.net/testcontainrestore/TestDB3Restore_log.ldf';   
    GO  
  
    ```  
  
     <span data-ttu-id="0af69-120">Al final de este paso, el contenedor debe enumerar los archivos (.ldf) y datos (.mdf) en el Portal de administración.</span><span class="sxs-lookup"><span data-stu-id="0af69-120">At the end of this step, your container should list data (.mdf) and (.ldf) files on the Management Portal.</span></span>  
  
 <span data-ttu-id="0af69-121">Para restaurar una base de datos con archivos de datos y de registro que apunten a Azure Storage mediante SQL Server Management Studio interfaz de usuario, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0af69-121">To restore a database with data and log files pointing to Azure Storage using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="0af69-122">En **Explorador de objetos**, haga clic en el nombre del servidor para expandir el árbol de servidores.</span><span class="sxs-lookup"><span data-stu-id="0af69-122">In **Object Explorer**, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="0af69-123">Expanda **bases**de datos y, a continuación, seleccione la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0af69-123">Expand **Databases**, and, select your database.</span></span>  
  
3.  <span data-ttu-id="0af69-124">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y, después, haga clic en **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="0af69-124">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="0af69-125">En la página **General** , en la sección origen de la **restauración** , haga clic en dispositivo de **origen** .</span><span class="sxs-lookup"><span data-stu-id="0af69-125">On the **General** page, in the **Restore** source section, click **Source** device.</span></span>  
  
5.  <span data-ttu-id="0af69-126">Haga clic en el botón Examinar del cuadro de texto **Dispositivo de origen**, que abre el cuadro de diálogo **Seleccionar dispositivos de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="0af69-126">Click the browse button for the **Source** device text box, which opens the **Select Backup Devices** dialog box.</span></span>  
  
6.  <span data-ttu-id="0af69-127">En el cuadro de texto Medios de copia de seguridad, seleccione **Archivo** y haga clic en el botón **Agregar** para buscar el archivo de copia de seguridad (.bak).</span><span class="sxs-lookup"><span data-stu-id="0af69-127">In the Backup media text box, select **File**, and click the **Add** button to locate the backup (.bak) file.</span></span> <span data-ttu-id="0af69-128">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0af69-128">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="0af69-129">Haga clic en **archivos** en la primera página.</span><span class="sxs-lookup"><span data-stu-id="0af69-129">Click **Files** on the first page.</span></span>  
  
8.  <span data-ttu-id="0af69-130">En la sección restaurar **archivos de base de datos** como, en el campo **restaurar como** , escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0af69-130">In the **Restore Database Files** as section, under **Restore As** field, type the followings:</span></span>  
  
     <span data-ttu-id="0af69-131">En archivo de datos, escriba: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS.mdf` .</span><span class="sxs-lookup"><span data-stu-id="0af69-131">For data file, type: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS.mdf`.</span></span> <span data-ttu-id="0af69-132">En archivo de registro, escriba: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS_log.ldf` .</span><span class="sxs-lookup"><span data-stu-id="0af69-132">For log file, type: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS_log.ldf`.</span></span>  
  
     <span data-ttu-id="0af69-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-8.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="0af69-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-8.gif "SQL 14 CTP2")</span></span>  
  
9. <span data-ttu-id="0af69-134">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0af69-134">Click **OK**.</span></span>  
  
 <span data-ttu-id="0af69-135">Cuando se realice la restauración, inicie sesión en el Portal de administración.</span><span class="sxs-lookup"><span data-stu-id="0af69-135">When the restore is done, log in to the Management Portal.</span></span> <span data-ttu-id="0af69-136">Debe poder ver los archivos .mdf y .ldf en el contenedor como sigue:</span><span class="sxs-lookup"><span data-stu-id="0af69-136">You should be able to see the .mdf and .ldf files in the container as follows:</span></span>  
  
 <span data-ttu-id="0af69-137">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-9.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="0af69-137">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-9.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="0af69-138">**Lección siguiente:**</span><span class="sxs-lookup"><span data-stu-id="0af69-138">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="0af69-139">Lección 9. Restaurar una base de datos desde Azure Storage</span><span class="sxs-lookup"><span data-stu-id="0af69-139">Lesson 9. Restore a database from Azure Storage</span></span>](../relational-databases/lesson-8-restore-as-new-database-from-log-backup.md)  
  
  
