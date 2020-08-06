---
title: 'Lección 4: crear una base de datos en Azure Storage | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a9ae1501-b614-49d3-b975-6569da8350b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 50fca85111d5897b738e577e7735049e0b055a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677079"
---
# <a name="lesson-4-create-a-database-in-azure-storage"></a><span data-ttu-id="1680d-102">Lección 4: Crear una base de datos en Azure Storage</span><span class="sxs-lookup"><span data-stu-id="1680d-102">Lesson 4: Create a database in Azure Storage</span></span>
  <span data-ttu-id="1680d-103">En esta lección, obtendrá información sobre cómo crear una base de datos mediante la característica archivos de datos de SQL Server en Azure.</span><span class="sxs-lookup"><span data-stu-id="1680d-103">In this lesson, you will learn how to create a database using the SQL Server Data Files in Azure feature.</span></span> <span data-ttu-id="1680d-104">Tenga en cuenta que, antes que esta lección, debe completar las lecciones 1, 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="1680d-104">Note that before this lesson, you must complete the Lesson 1, 2, and 3.</span></span> <span data-ttu-id="1680d-105">La lección 3 es un paso muy importante porque debe almacenar la información sobre el contenedor de Azure Storage y su nombre de directiva asociado y la clave SAS en el almacén de credenciales de SQL Server antes de la lección 4.</span><span class="sxs-lookup"><span data-stu-id="1680d-105">Lesson 3 is a very important step because you need to store the information about your Azure storage container and its associated policy name and SAS key in the SQL Server credential store before Lesson 4.</span></span>  
  
 <span data-ttu-id="1680d-106">Para cada contenedor de almacenamiento utilizado por un archivo de datos o de registro, debe crear una credencial de SQL Server cuyo nombre coincida con la ruta de acceso del contenedor.</span><span class="sxs-lookup"><span data-stu-id="1680d-106">For each storage container used by a data or log file, you must create a SQL Server Credential whose name matches the container path.</span></span> <span data-ttu-id="1680d-107">A continuación, puede crear una nueva base de datos en Azure Storage</span><span class="sxs-lookup"><span data-stu-id="1680d-107">Then, you can create a new database in Azure Storage</span></span>  
  
 <span data-ttu-id="1680d-108">En esta lección se supone que ya completó los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1680d-108">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="1680d-109">Tiene una cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="1680d-109">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="1680d-110">Ha creado un contenedor en su cuenta de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="1680d-110">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="1680d-111">Ha creado una directiva en un contenedor con derechos de lectura, escritura y enumeración.</span><span class="sxs-lookup"><span data-stu-id="1680d-111">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="1680d-112">También generó una clave SAS.</span><span class="sxs-lookup"><span data-stu-id="1680d-112">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="1680d-113">Ha creado una credencial de SQL Server en el equipo de origen.</span><span class="sxs-lookup"><span data-stu-id="1680d-113">You have created a SQL Server credential on the source machine.</span></span>  
  
 <span data-ttu-id="1680d-114">Para crear una base de datos en Azure con la característica archivos de datos SQL Server en Azure Storage, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1680d-114">To create a database in Azure using the SQL Server Data Files in Azure Storage feature, follow these steps:</span></span>  
  
1.  <span data-ttu-id="1680d-115">Conéctese a SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="1680d-115">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="1680d-116">En el Explorador de objetos, conéctese a la instancia del Motor de base de datos instalado.</span><span class="sxs-lookup"><span data-stu-id="1680d-116">In Object Explorer, connect to the instance of Database Engine installed.</span></span>  
  
3.  <span data-ttu-id="1680d-117">En la barra de herramientas Estándar, haga clic en Nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="1680d-117">On the Standard tool bar, click New Query.</span></span>  
  
4.  <span data-ttu-id="1680d-118">Copie y pegue el ejemplo siguiente en la ventana de consulta, y modifíquelo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1680d-118">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="1680d-119">Observe que el campo FILENAME hace referencia a la ruta de acceso de URI del archivo de base de datos en el contenedor de almacenamiento y debe comenzar con https.</span><span class="sxs-lookup"><span data-stu-id="1680d-119">Note that the FILENAME field refers to the URI path of the database file in storage container and it must start with https.</span></span>  
  
    ```  
  
    --Create a database that uses a SQL Server credential    
    CREATE DATABASE TestDB1    
    ON   
    (NAME = TestDB1_data,   
       FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Data.mdf')   
     LOG ON   
    (NAME = TestDB1_log,   
        FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Log.ldf')   
    GO  
  
    ```  
  
     <span data-ttu-id="1680d-120">Agregue algunos datos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1680d-120">Add some data to your database.</span></span>  
  
    ```  
  
    USE TestDB1;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
5.  <span data-ttu-id="1680d-121">Para ver el nuevo TestDB1 en su servidor SQL Server local, actualice las bases de datos en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="1680d-121">To see the new TestDB1 in your on-premises SQL Server, refresh databases in the Object Explorer.</span></span>  
  
6.  <span data-ttu-id="1680d-122">Asimismo, para ver la base de datos recién creada en su cuenta de almacenamiento, conéctese a ella mediante SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="1680d-122">Similarly, to see the newly created database in your storage account, connect to your storage account via SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="1680d-123">Para obtener información sobre cómo conectarse a un almacenamiento de Azure mediante SQL Server Management Studio, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1680d-123">For information on how to connect to an Azure storage using SQL Server Management Studio, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="1680d-124">Primero, obtenga la información de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="1680d-124">First, get the storage account information.</span></span> <span data-ttu-id="1680d-125">Inicie sesión en el Portal de administración.</span><span class="sxs-lookup"><span data-stu-id="1680d-125">Log in to the Management Portal.</span></span> <span data-ttu-id="1680d-126">A continuación, haga clic en **Almacenamiento** y elija su cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="1680d-126">Then, click **Storage** and choose your storage account.</span></span> <span data-ttu-id="1680d-127">Cuando se seleccione una cuenta de almacenamiento, haga clic en **administrar claves de acceso** en la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="1680d-127">When a storage account is selected, click **Manage Access Keys** at the bottom of the page.</span></span> <span data-ttu-id="1680d-128">Se abrirá un cuadro de diálogo similar a esta:</span><span class="sxs-lookup"><span data-stu-id="1680d-128">This opens a similar dialog window:</span></span>  
  
         <span data-ttu-id="1680d-129">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-1.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="1680d-129">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-1.gif "SQL 14 CTP2")</span></span>  
  
    2.  <span data-ttu-id="1680d-130">Copie los valores de **nombre de cuenta de almacenamiento** y clave de **acceso principal** en la ventana de diálogo **conectar a Azure Storage** en SSMS.</span><span class="sxs-lookup"><span data-stu-id="1680d-130">Copy the **Storage Account Name** and **Primary Access Key** values to the **Connect to Azure Storage** dialog window in SSMS.</span></span> <span data-ttu-id="1680d-131">Después, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="1680d-131">Then, click **Connect**.</span></span> <span data-ttu-id="1680d-132">De esta forma, la información sobre los contenedores de la cuenta de almacenamiento en SSMS aparecerán como se muestra en la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="1680d-132">This brings the information about storage account containers to SSMS as shown in the following screenshot:</span></span>  
  
         <span data-ttu-id="1680d-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="1680d-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="1680d-134">En la captura de pantalla siguiente se muestra la nueva base de datos creada tanto en el entorno local como en el Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="1680d-134">The following screenshot demonstrates the new created database both in on-premises and Azure Storage environment.</span></span>  
  
 <span data-ttu-id="1680d-135">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2b.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="1680d-135">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2b.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="1680d-136">**Nota:** Si hay referencias activas a los archivos de datos en un contenedor, se produce un error en cualquier intento de eliminar la credencial de SQL Server asociada.</span><span class="sxs-lookup"><span data-stu-id="1680d-136">**Note:** If there are any active references to data files in a container, any attempts to delete the associated SQL Server credential fails.</span></span> <span data-ttu-id="1680d-137">De igual forma, si ya hay una concesión en un archivo de base de datos específico de un blob y desea eliminarlo, primero debe interrumpirla en el blob.</span><span class="sxs-lookup"><span data-stu-id="1680d-137">Similarly, if there is already a lease on a specific database file in a blob and you want to delete it, first you need to break the lease on the blob.</span></span> <span data-ttu-id="1680d-138">Para interrumpir la concesión, puede usar la [concesión de blobs](https://msdn.microsoft.com/library/azure/ee691972.aspx).</span><span class="sxs-lookup"><span data-stu-id="1680d-138">To break the lease, you can use [Lease Blob](https://msdn.microsoft.com/library/azure/ee691972.aspx).</span></span>  
  
 <span data-ttu-id="1680d-139">Mediante esta nueva característica, puede configurar SQL Server de modo que cualquier instrucción CREATE DATABASE será, de forma predeterminada, una base de datos habilitada para la nube.</span><span class="sxs-lookup"><span data-stu-id="1680d-139">Using this new feature, you can configure SQL Server so that any CREATE DATABASE statement will default to a cloud enabled database.</span></span> <span data-ttu-id="1680d-140">En otras palabras, puede establecer las ubicaciones predeterminadas de datos y de registro en SQL Server Management Studio propiedades de la instancia de servidor, de modo que cada vez que cree una base de datos, todos los archivos de base de datos (. MDF,. ldf) se crean como blobs en páginas en Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="1680d-140">In other words, you can set default data and log locations in SQL Server Management Studio Server instance properties so anytime you create a database, all database files (.mdf, .ldf) are created as page blobs in Azure Storage.</span></span>  
  
 <span data-ttu-id="1680d-141">Para crear una base de datos en Azure Storage mediante SQL Server Management Studio interfaz de usuario, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1680d-141">To create a database in Azure Storage by using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="1680d-142">En el Explorador de objetos, conéctese a una instancia del Motor de base de datos de SQL Server y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="1680d-142">In Object Explorer, connect to an instance of the SQL Server Database Engine and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1680d-143">Haga clic con el botón secundario en Bases de datos y, a continuación, en Nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="1680d-143">Right-click Databases, and then click New Database.</span></span>  
  
3.  <span data-ttu-id="1680d-144">En el cuadro de diálogo Nueva base de datos, escriba un nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="1680d-144">In the New Database dialog window, type a database name.</span></span>  
  
4.  <span data-ttu-id="1680d-145">Cambie los valores predeterminados de los archivos de datos y de registro de transacciones principales, en la cuadrícula Archivos de la base de datos, haga clic en la celda correspondiente y especifique el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="1680d-145">Change the default values of the primary data and transaction log files, in the Database files grid, click the appropriate cell and enter the new value.</span></span> <span data-ttu-id="1680d-146">Además, especifique la ruta de acceso a la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="1680d-146">Also, specify the path for the file location.</span></span> <span data-ttu-id="1680d-147">En Ruta de acceso, escriba la ruta de acceso a la dirección URL del contenedor de almacenamiento, como `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span><span class="sxs-lookup"><span data-stu-id="1680d-147">For Path, type the URL path of the storage container, such as `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span></span> <span data-ttu-id="1680d-148">En Nombre de archivo, escriba los nombres de archivo físico de los archivos de base de datos (.mdf, .ldf).</span><span class="sxs-lookup"><span data-stu-id="1680d-148">For FileName, type the physical file names of the database files (.mdf, .ldf).</span></span>  
  
     <span data-ttu-id="1680d-149">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-4.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="1680d-149">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-4.gif "SQL 14 CTP2")</span></span>  
  
     <span data-ttu-id="1680d-150">Para obtener más información, consulte [Agregar archivos de datos o de registro a una base de datos](databases/add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="1680d-150">For more information, see [Add Data or Log Files to a Database](databases/add-data-or-log-files-to-a-database.md).</span></span>  
  
5.  <span data-ttu-id="1680d-151">Conserve los demás valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="1680d-151">Keep all other default values.</span></span>  
  
6.  <span data-ttu-id="1680d-152">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="1680d-152">Click OK.</span></span>  
  
 <span data-ttu-id="1680d-153">Para ver el nuevo TestDB1 en su servidor SQL Server local, actualice las bases de datos en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="1680d-153">To see the new TestDB1 in your on-premises SQL Server, refresh databases in the Object Explorer.</span></span> <span data-ttu-id="1680d-154">Asimismo, para ver la base de datos recién creada en su cuenta de almacenamiento, conéctese a ella mediante SQL Server Management Studio (SSMS), según se explicó anteriormente en esta lección.</span><span class="sxs-lookup"><span data-stu-id="1680d-154">Similarly, to see the newly created database in your storage account, connect to your storage account via SQL Server Management Studio (SSMS) as explained earlier in this lesson.</span></span>  
  
 <span data-ttu-id="1680d-155">**Lección siguiente:**</span><span class="sxs-lookup"><span data-stu-id="1680d-155">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="1680d-156">Lección 5. &#40;opcional&#41; cifrar la base de datos mediante TDE</span><span class="sxs-lookup"><span data-stu-id="1680d-156">Lesson 5. &#40;Optional&#41; Encrypt your database using TDE</span></span>](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)  
  
  
