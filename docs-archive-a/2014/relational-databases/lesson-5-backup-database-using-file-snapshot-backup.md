---
title: 'Lección 6: migrar una base de datos de una máquina de origen local a un equipo de destino en Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: d9134ade-7b03-4c5c-8ed3-3bc369a61691
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b9af8a260493561f9728d1677b7667bd3f36cb46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675364"
---
# <a name="lesson-6-migrate-a-database-from-a-source-machine-on-premises-to-a-destination-machine-in-azure"></a><span data-ttu-id="873e5-102">Lección 6: Migrar una base de datos desde un equipo de origen local a un equipo de destino en Azure</span><span class="sxs-lookup"><span data-stu-id="873e5-102">Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure</span></span>
  <span data-ttu-id="873e5-103">En esta lección se supone que ya tiene otro SQL Server, que puede residir en otro equipo local o en una máquina virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="873e5-103">This lesson assumes that you already have another SQL Server, which might reside in another on-premises computer or in a virtual machine in Azure.</span></span> <span data-ttu-id="873e5-104">Para obtener información sobre cómo crear una máquina virtual SQL Server en Azure, consulte [aprovisionamiento de una máquina virtual SQL Server en Azure](https://www.windowsazure.com/manage/windows/common-tasks/install-sql-server/).</span><span class="sxs-lookup"><span data-stu-id="873e5-104">For information on how to create a SQL Server virtual machine in Azure, see [Provisioning a SQL Server Virtual Machine on Azure](https://www.windowsazure.com/manage/windows/common-tasks/install-sql-server/).</span></span> <span data-ttu-id="873e5-105">Después de aprovisionar una máquina virtual SQL Server en Azure, asegúrese de que puede conectarse a una instancia de SQL Server en esta máquina virtual a través de SQL Server Management Studio en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="873e5-105">After provisioning a SQL Server virtual machine in Azure, make sure that you can connect to an instance of SQL Server in this virtual machine via SQL Server Management Studio in another computer.</span></span>  
  
 <span data-ttu-id="873e5-106">En esta lección también se supone que ya completó los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="873e5-106">This lesson also assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="873e5-107">Tiene una cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="873e5-107">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="873e5-108">Ha creado un contenedor en su cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="873e5-108">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="873e5-109">Ha creado una directiva en un contenedor con derechos de lectura, escritura y enumeración.</span><span class="sxs-lookup"><span data-stu-id="873e5-109">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="873e5-110">También generó una clave SAS.</span><span class="sxs-lookup"><span data-stu-id="873e5-110">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="873e5-111">Ha creado una credencial de SQL Server en el equipo de origen.</span><span class="sxs-lookup"><span data-stu-id="873e5-111">You have created a SQL Server credential on the source machine.</span></span>  
  
-   <span data-ttu-id="873e5-112">Ya ha creado una máquina virtual de destino SQL Server en Azure.</span><span class="sxs-lookup"><span data-stu-id="873e5-112">You already have created a destination SQL Server virtual machine in Azure.</span></span> <span data-ttu-id="873e5-113">Para crearla, se recomienda que seleccione una imagen de plataforma que incluya SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="873e5-113">We recommend that you create it by selecting a platform image that includes SQL Server 2014.</span></span>  
  
 <span data-ttu-id="873e5-114">Para migrar una base de datos de SQL Server local a otra máquina virtual de Azure, puede seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="873e5-114">To migrate a database from SQL Server on-premises to another virtual machine in Azure, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="873e5-115">En la máquina de origen (que es un equipo local en este tutorial), abra una ventana de consulta en SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="873e5-115">In the source machine (which is an on-premises computer in this tutorial), open a query window in SQL Server Management Studio.</span></span> <span data-ttu-id="873e5-116">Separe la base de datos para moverla a otra máquina ejecutando estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="873e5-116">Detach your database to move it to another machine by executing these statements:</span></span>  
  
    ```  
    -- Detach the database in the source machine   
    USE master  
    EXEC sp_detach_db 'TestDB1', 'true';  
    ```  
  
2.  <span data-ttu-id="873e5-117">Si necesita transferir una base de datos a un equipo de destino, primero debe prepararlo.</span><span class="sxs-lookup"><span data-stu-id="873e5-117">If you need to transfer a database to a destination machine, first you must prepare it.</span></span> <span data-ttu-id="873e5-118">Para preparar el equipo de destino, primero debe crear una credencial de SQL Server en dicho equipo.</span><span class="sxs-lookup"><span data-stu-id="873e5-118">To prepare your destination machine, first you need to create a SQL Server credential in the destination machine.</span></span> <span data-ttu-id="873e5-119">Si es una base de datos cifrada, también debe importar el certificado de la máquina de origen a la de destino.</span><span class="sxs-lookup"><span data-stu-id="873e5-119">If it is an encrypted database, you need to import the certificate from the source machine to the destination machine as well.</span></span>  
  
    1.  <span data-ttu-id="873e5-120">Para crear una credencial de SQL Server en el equipo de destino, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="873e5-120">To create a SQL Server Credential in the destination machine, follow these steps:</span></span>  
  
        1.  <span data-ttu-id="873e5-121">Conéctese al equipo de destino mediante SQL Server Management Studio en el equipo de origen.</span><span class="sxs-lookup"><span data-stu-id="873e5-121">Connect to the destination machine via SQL Server Management Studio in your source computer.</span></span>  <span data-ttu-id="873e5-122">O bien, inicie SQL Server Management Studio en el equipo de destino directamente.</span><span class="sxs-lookup"><span data-stu-id="873e5-122">Or, start SQL Server Management Studio in your destination computer directly.</span></span>  
  
        2.  <span data-ttu-id="873e5-123">En la barra de herramientas Estándar , haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="873e5-123">On the Standard tool bar, click **New Query**.</span></span>  
  
        3.  <span data-ttu-id="873e5-124">Copie y pegue el ejemplo siguiente en la ventana de consulta, y modifíquelo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="873e5-124">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="873e5-125">La siguiente instrucción crea una credencial de SQL Server para almacenar el certificado de acceso compartido del contenedor de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="873e5-125">The following statement creates a SQL Server Credential to store your storage container's Shared Access Certificate.</span></span>  
  
            ```sql  
  
            USE master   
            GO   
            CREATE CREDENTIAL [http://teststorageaccnt.blob.core.windows.net/testcontainer]   
            WITH IDENTITY='SHARED ACCESS SIGNATURE',   
            SECRET = 'your SAS key'   
            GO  
  
            ```  
  
        4.  <span data-ttu-id="873e5-126">Para ver todas las credenciales disponibles, puede ejecutar la siguiente instrucción en la ventana de consulta:</span><span class="sxs-lookup"><span data-stu-id="873e5-126">To see all available credentials, you can run the following statement in the query window:</span></span>  
  
            ```sql  
            SELECT * from sys.credentials   
            ```  
  
        5.  <span data-ttu-id="873e5-127">Cuando se conecte al servidor de destino, abra la ventana de consulta y ejecute:</span><span class="sxs-lookup"><span data-stu-id="873e5-127">When connected to the destination server, open query window, and run:</span></span>  
  
            ```sql  
  
            -- Create a master key and a server certificate   
            USE master   
            GO   
            CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'MySQLKey01'; -- You may use a different password.   
            GO   
            CREATE CERTIFICATE MySQLCert   
            FROM FILE = 'C:\certs\MySQLCert.CER'   
            WITH PRIVATE KEY   
            (   
            FILE = 'C:\certs\MySQLPrivateKeyFile.PVK',   
            DECRYPTION BY PASSWORD = 'MySQLKey01'   
            );   
            GO  
  
            ```  
  
             <span data-ttu-id="873e5-128">Al final de este paso, la máquina de destino ha importado el certificado de cifrado cuya copia de seguridad se realizó desde la máquina de origen.</span><span class="sxs-lookup"><span data-stu-id="873e5-128">At the end of this step, the destination machine has imported the encryption certificate that was backed up from the source machine.</span></span> <span data-ttu-id="873e5-129">A continuación, puede adjuntar los archivos de datos en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="873e5-129">Next, you can attach the data files in the destination machine.</span></span>  
  
    2.  <span data-ttu-id="873e5-130">A continuación, cree una base de datos con los archivos de datos y de registro que apuntan a los archivos existentes en Azure Storage mediante la opción FOR ATTACH.</span><span class="sxs-lookup"><span data-stu-id="873e5-130">Then, create a database with data and log files pointing to the existing files in Azure Storage by using FOR ATTACH option.</span></span> <span data-ttu-id="873e5-131">En la ventana de consulta, ejecute la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="873e5-131">In the query window, run the following statement:</span></span>  
  
        ```sql  
  
        --Create a database on the destination server   
        CREATE DATABASE TestDB1onDest   
        ON   
        (NAME = TestDB1_data,   
            FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Data.mdf' )   
        LOG ON   
         (NAME = TestDB1_log,   
            FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Log.ldf')   
        FOR ATTACH   
        GO  
  
        ```  
  
    3.  <span data-ttu-id="873e5-132">En el Explorador de objetos, haga clic en Bases de datos y, a continuación, haga clic con el botón secundario en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="873e5-132">On the Object Explorer, click Databases, right-click Refresh.</span></span> <span data-ttu-id="873e5-133">Debe poder ver la base de datos creada recientemente TestDB1onDest.</span><span class="sxs-lookup"><span data-stu-id="873e5-133">You should be able to see the newly created database TestDB1onDest listed.</span></span>  
  
    4.  <span data-ttu-id="873e5-134">Después, en la ventana de consulta, ejecute la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="873e5-134">Next, run the following statement in the query window:</span></span>  
  
        ```sql  
  
        USE TestDB1onDest   
        SELECT * FROM Table1;   
        GO  
  
        ```  
  
         <span data-ttu-id="873e5-135">Debería enumerar todos los datos que especificó en la lección 4.</span><span class="sxs-lookup"><span data-stu-id="873e5-135">This should list all the data you entered in Lesson 4.</span></span>  
  
 <span data-ttu-id="873e5-136">Tenga en cuenta que la base de datos cifrada se transfirió a otra instancia de cálculo sin mover los datos.</span><span class="sxs-lookup"><span data-stu-id="873e5-136">Note that the encrypted database was transferred to another compute instance with no data movement.</span></span>  
  
 <span data-ttu-id="873e5-137">Para crear una base de datos con archivos de datos y de registro que señalen a los archivos existentes en Azure Storage mediante SQL Server Management Studio interfaz de usuario, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="873e5-137">To create a database with data and log files pointing to the existing files in Azure Storage using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="873e5-138">En el **Explorador de objetos**, conéctese a una instancia del Motor de base de datos de SQL Server y expándala.</span><span class="sxs-lookup"><span data-stu-id="873e5-138">In **Object Explorer**, connect to an instance of the SQL Server Database Engine and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="873e5-139">Haga clic con el botón derecho en **Bases de datos**y, después, haga clic en **Nueva base de datos**.</span><span class="sxs-lookup"><span data-stu-id="873e5-139">Right-click **Databases**, and then click **New Database**.</span></span> <span data-ttu-id="873e5-140">A continuación, haga clic con el botón secundario en TestDB1.</span><span class="sxs-lookup"><span data-stu-id="873e5-140">Then, right-click TestDB1.</span></span> <span data-ttu-id="873e5-141">Haga clic en Tareas y, a continuación, haga clic en Separar.</span><span class="sxs-lookup"><span data-stu-id="873e5-141">Click Tasks, and then click Detach.</span></span> <span data-ttu-id="873e5-142">En la ventana del cuadro de diálogo Separar, active Quitar conexiones.</span><span class="sxs-lookup"><span data-stu-id="873e5-142">In the Detach dialog window, check Drop Connections.</span></span> <span data-ttu-id="873e5-143">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="873e5-143">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="873e5-144">Conéctese a la máquina de destino, que tiene SQL Server 2014 CTP2 o posterior.</span><span class="sxs-lookup"><span data-stu-id="873e5-144">Connect to the destination machine, which has SQL Server 2014 CTP2 or later.</span></span> <span data-ttu-id="873e5-145">Para preparar la máquina de destino, debe crear una credencial de SQL Server en ella para señalar al mismo contenedor en el que colocó TestDB1.</span><span class="sxs-lookup"><span data-stu-id="873e5-145">To prepare your destination machine, you need to create a SQL Server credential in the destination machine to point to the same container that you put TestDB1 in.</span></span> <span data-ttu-id="873e5-146">Si va a volver a adjuntar la base de datos en el mismo equipo, no es necesario crear otra credencial.</span><span class="sxs-lookup"><span data-stu-id="873e5-146">If you are going to re-attach in the same computer, you do not need to create another credential.</span></span>  
  
4.  <span data-ttu-id="873e5-147">En **Explorador de objetos**, haga clic con el botón derecho en **bases** de datos y haga clic en **asociar**.</span><span class="sxs-lookup"><span data-stu-id="873e5-147">In **Object Explorer**, right-click **Databases** and click **Attach**.</span></span>  
  
5.  <span data-ttu-id="873e5-148">En el cuadro de diálogo **adjuntar bases de datos** , para especificar la base de datos que se va a adjuntar, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="873e5-148">In the **Attach Databases** dialog box, to specify the database to be attached, click **Add**.</span></span> <span data-ttu-id="873e5-149">En la ventana de diálogo **buscar archivos de base de datos** :</span><span class="sxs-lookup"><span data-stu-id="873e5-149">In the **Locate Database Files** dialog window:</span></span>  
  
     <span data-ttu-id="873e5-150">En ubicación del archivo de datos de la base de datos, escriba: `https://teststorageaccnt.blob.core.windows.net/testcontainer/` .</span><span class="sxs-lookup"><span data-stu-id="873e5-150">For Database Data File Location, type: `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span></span>  
  
     <span data-ttu-id="873e5-151">En nombre de archivo, escriba: `TestDB1Data.mdf` .</span><span class="sxs-lookup"><span data-stu-id="873e5-151">For File name, type: `TestDB1Data.mdf`.</span></span>  
  
6.  <span data-ttu-id="873e5-152">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="873e5-152">Click **OK**.</span></span>  
  
     <span data-ttu-id="873e5-153">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-6-7.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="873e5-153">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-6-7.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="873e5-154">**Lección siguiente:**</span><span class="sxs-lookup"><span data-stu-id="873e5-154">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="873e5-155">Lección 7: Mover los archivos de datos a Azure Storage</span><span class="sxs-lookup"><span data-stu-id="873e5-155">Lesson 7: Move your data files to Azure Storage</span></span>](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)  
  
