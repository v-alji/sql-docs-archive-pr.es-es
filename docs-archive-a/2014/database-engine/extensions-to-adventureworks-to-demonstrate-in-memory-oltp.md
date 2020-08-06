---
title: Extensiones de AdventureWorks para mostrar OLTP en memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0186b7f2-cead-4203-8360-b6890f37cde8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 73a87751aa6cd4734f81b60cdd87a62939ba4ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749435"
---
# <a name="extensions-to-adventureworks-to-demonstrate-in-memory-oltp"></a><span data-ttu-id="02a6f-102">Extensiones de AdventureWorks para mostrar OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="02a6f-102">Extensions to AdventureWorks to Demonstrate In-Memory OLTP</span></span>
    
## <a name="overview"></a><span data-ttu-id="02a6f-103">Información general</span><span class="sxs-lookup"><span data-stu-id="02a6f-103">Overview</span></span>  
 <span data-ttu-id="02a6f-104">Este ejemplo muestra la nueva característica [!INCLUDE[hek_2](../includes/hek-2-md.md)] , que forma parte de [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02a6f-104">This sample showcases the new [!INCLUDE[hek_2](../includes/hek-2-md.md)] feature, which is part of [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="02a6f-105">Muestra las nuevas tablas optimizadas para memoria y los procedimientos almacenados compilados de forma nativa, y se puede usar para mostrar las ventajas de rendimiento de [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02a6f-105">It shows the new memory-optimized tables and natively-compiled stored procedures, and can be used to demonstrate performance benefits of [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="02a6f-106">Para ver este tema de SQL Server 2016, consulte [Extensiones de AdventureWorks para mostrar OLTP en memoria](https://msdn.microsoft.com/library/mt465764.aspx)</span><span class="sxs-lookup"><span data-stu-id="02a6f-106">To view this topic for SQL Server 2016, see [Extensions to AdventureWorks to Demonstrate In-Memory OLTP](https://msdn.microsoft.com/library/mt465764.aspx)</span></span>  
  
 <span data-ttu-id="02a6f-107">El ejemplo migra 5 tablas de la base de datos AdventureWorks a tablas optimizadas para memoria e incluye una carga de trabajo de demostración para el procesamiento de pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="02a6f-107">The sample migrates 5 tables in the AdventureWorks database to memory-optimized, and it includes a demo workload for sales order processing.</span></span> <span data-ttu-id="02a6f-108">Puede usar esta carga de trabajo de demostración para ver la ventaja de rendimiento que supone emplear [!INCLUDE[hek_2](../includes/hek-2-md.md)] en el servidor.</span><span class="sxs-lookup"><span data-stu-id="02a6f-108">You can use this demo workload to see the performance benefit of using [!INCLUDE[hek_2](../includes/hek-2-md.md)] on your server.</span></span>  
  
 <span data-ttu-id="02a6f-109">En la descripción del ejemplo se explican los compromisos realizados al migrar las tablas a [!INCLUDE[hek_2](../includes/hek-2-md.md)] para compensar las características que no se admiten (todavía) en las tablas optimizadas para memoria en [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02a6f-109">In the description of the sample we discuss the tradeoffs that were made in migrating the tables to [!INCLUDE[hek_2](../includes/hek-2-md.md)] to account for the features that are not (yet) supported for memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="02a6f-110">La documentación de este ejemplo está estructurada de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="02a6f-110">The documentation of this sample is structured as follows:</span></span>  
  
-   <span data-ttu-id="02a6f-111">[Requisitos previos](#Prerequisites) para instalar el ejemplo y ejecutar la carga de trabajo de demostración</span><span class="sxs-lookup"><span data-stu-id="02a6f-111">[Prerequisites](#Prerequisites) for installing the sample and running the demo workload</span></span>  
  
-   <span data-ttu-id="02a6f-112">Instrucciones para [Instalar el ejemplo de In-Memory OLTP basado en AdventureWorks](#InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks)</span><span class="sxs-lookup"><span data-stu-id="02a6f-112">Instructions for [Installing the In-Memory OLTP sample based on AdventureWorks](#InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks)</span></span>  
  
-   <span data-ttu-id="02a6f-113">[Descripción de las tablas y los procedimientos de ejemplo](#Descriptionofthesampletablesandprocedures) : incluye descripciones de las tablas y los procedimientos agregados a AdventureWorks por el [!INCLUDE[hek_2](../includes/hek-2-md.md)] ejemplo, así como consideraciones para migrar algunas de las tablas originales de AdventureWorks a la optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="02a6f-113">[Description of the sample tables and procedures](#Descriptionofthesampletablesandprocedures) - this includes descriptions of the tables and procedures added to AdventureWorks by the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample, as well as considerations for migrating some of the original AdventureWorks tables to memory-optimized</span></span>  
  
-   <span data-ttu-id="02a6f-114">Instrucciones para realizar [Medidas de rendimiento con la carga de trabajo de demostración](#PerformanceMeasurementsusingtheDemoWorkload): contiene instrucciones para instalar y ejecutar ostress, una herramienta que se usa para controlar la carga de trabajo y para ejecutar la carga de trabajo de demostración propiamente dicha.</span><span class="sxs-lookup"><span data-stu-id="02a6f-114">Instructions for performing [Performance Measurements using the Demo Workload](#PerformanceMeasurementsusingtheDemoWorkload) - this includes instructions for installing and running ostress, a tool using for driving the workload, as well as running the demo workload itself</span></span>  
  
-   [<span data-ttu-id="02a6f-115">Uso de memoria y de espacio en disco del ejemplo</span><span class="sxs-lookup"><span data-stu-id="02a6f-115">Memory and Disk Space Utilization in the Sample</span></span>](#MemoryandDiskSpaceUtilizationintheSample)  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="02a6f-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="02a6f-116">Prerequisites</span></span>  
  
-   [!INCLUDE[ssSQL14](../includes/sssql14-md.md)]<span data-ttu-id="02a6f-117">RTM: Evaluation, Developer o Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="02a6f-117">RTM - Evaluation, Developer, or Enterprise edition</span></span>  
  
-   <span data-ttu-id="02a6f-118">Para las pruebas de rendimiento, un servidor con unas especificaciones similares al entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="02a6f-118">For performance testing, a server with specifications similar to your production environment.</span></span> <span data-ttu-id="02a6f-119">Para esta muestra concreta, debe haber al menos 16 GB de memoria disponible para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02a6f-119">For this particular sample you should have at least 16GB of memory available to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="02a6f-120">Para obtener instrucciones generales sobre el hardware de [!INCLUDE[hek_2](../includes/hek-2-md.md)] , consulte la siguiente entrada de blog:[https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/](https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/)</span><span class="sxs-lookup"><span data-stu-id="02a6f-120">For general guidelines on hardware for [!INCLUDE[hek_2](../includes/hek-2-md.md)], see the following blog post:[https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/](https://cloudblogs.microsoft.com/sqlserver/2013/08/01/hardware-considerations-for-in-memory-oltp-in-sql-server-2014/)</span></span>  
  
##  <a name="installing-the-hek_2-sample-based-on-adventureworks"></a><a name="InstallingtheIn-MemoryOLTPsamplebasedonAdventureWorks"></a><span data-ttu-id="02a6f-121">Instalar el [!INCLUDE[hek_2](../includes/hek-2-md.md)] ejemplo basado en AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="02a6f-121">Installing the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample based on AdventureWorks</span></span>  
 <span data-ttu-id="02a6f-122">Siga estos pasos para instalar el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02a6f-122">Follow these steps to install the sample:</span></span>  
  
1.  <span data-ttu-id="02a6f-123">Descargue el archivo de la copia de seguridad completa de la base de datos AdventureWorks2014:</span><span class="sxs-lookup"><span data-stu-id="02a6f-123">Download the archive for the full backup of the AdventureWorks2014 database:</span></span>  
  
    1.  <span data-ttu-id="02a6f-124">Abra lo siguiente: [https://msftdbprodsamples.codeplex.com/downloads/get/880661](https://msftdbprodsamples.codeplex.com/downloads/get/880661) .</span><span class="sxs-lookup"><span data-stu-id="02a6f-124">Open the following: [https://msftdbprodsamples.codeplex.com/downloads/get/880661](https://msftdbprodsamples.codeplex.com/downloads/get/880661).</span></span>  
  
    2.  <span data-ttu-id="02a6f-125">Se le pedirá que guarde el archivo en una carpeta local.</span><span class="sxs-lookup"><span data-stu-id="02a6f-125">When prompted to save the file to a local folder.</span></span>  
  
2.  <span data-ttu-id="02a6f-126">Extraiga el archivo **AdventureWorks2014.bak** a una carpeta local, por ejemplo 'c:\temp'.</span><span class="sxs-lookup"><span data-stu-id="02a6f-126">Extract the **AdventureWorks2014.bak** file to a local folder, for example 'c:\temp'.</span></span>  
  
3.  <span data-ttu-id="02a6f-127">Restaure la copia de seguridad de la base de datos mediante [!INCLUDE[tsql](../includes/tsql-md.md)] o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="02a6f-127">Restore the database backup using [!INCLUDE[tsql](../includes/tsql-md.md)] or [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="02a6f-128">Identifique la carpeta de destino y el nombre del archivo de datos, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02a6f-128">Identify the target folder and filename for the data file, for example</span></span>  
  
         <span data-ttu-id="02a6f-129">'h:\DATA\AdventureWorks2014_Data.mdf'</span><span class="sxs-lookup"><span data-stu-id="02a6f-129">'h:\DATA\AdventureWorks2014_Data.mdf'</span></span>  
  
    2.  <span data-ttu-id="02a6f-130">Identifique la carpeta de destino y el nombre del archivo de registro, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02a6f-130">Identify the target folder and filename for the log file, for example</span></span>  
  
         <span data-ttu-id="02a6f-131">'i:\DATA\AdventureWorks2014_log.ldf'</span><span class="sxs-lookup"><span data-stu-id="02a6f-131">'i:\DATA\AdventureWorks2014_log.ldf'</span></span>  
  
        1.  <span data-ttu-id="02a6f-132">El archivo de registro debe colocarse en otra unidad diferente que el archivo de datos, idealmente en una unidad de baja latencia como un almacenamiento SSD o PCIe, para obtener el máximo rendimiento.</span><span class="sxs-lookup"><span data-stu-id="02a6f-132">The log file should be placed on a different drive than the data file, ideally a low latency drive such as an SSD or PCIe storage, for maximum performance.</span></span>  
  
     <span data-ttu-id="02a6f-133">Script T-SQL de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02a6f-133">Example T-SQL script:</span></span>  
  
    ```  
    RESTORE DATABASE [AdventureWorks2014]   
      FROM DISK = N'C:\temp\AdventureWorks2014.bak'   
        WITH FILE = 1,    
      MOVE N'AdventureWorks2014_Data' TO N'h:\DATA\AdventureWorks2014_Data.mdf',    
      MOVE N'AdventureWorks2014_Log' TO N'i:\DATA\AdventureWorks2014_log.ldf'  
     GO  
    ```  
  
4.  <span data-ttu-id="02a6f-134">Ejecute el comando siguiente en la ventana de consulta de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]para cambiar el propietario de la base de datos a un inicio de sesión del servidor:</span><span class="sxs-lookup"><span data-stu-id="02a6f-134">Change the database owner to a login on your server, by running the following command in the query window of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]:</span></span>  
  
    ```  
    ALTER AUTHORIZATION ON DATABASE::AdventureWorks2014 TO [<NewLogin>]  
    ```  
  
5.  <span data-ttu-id="02a6f-135">Descargue el script de ejemplo ' [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample. SQL ' del [ejemplo de OLTP en memoria SQL Server 2014 RTM](https://go.microsoft.com/fwlink/?LinkID=396372) en una carpeta local.</span><span class="sxs-lookup"><span data-stu-id="02a6f-135">Download the sample script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql' from [SQL Server 2014 RTM In-Memory OLTP Sample](https://go.microsoft.com/fwlink/?LinkID=396372) to a local folder.</span></span>  
  
6.  <span data-ttu-id="02a6f-136">Actualice el valor de la variable ' checkpoint_files_location ' en el script ' [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample. SQL ' para que apunte a la ubicación de destino de los [!INCLUDE[hek_2](../includes/hek-2-md.md)] archivos de punto de comprobación.</span><span class="sxs-lookup"><span data-stu-id="02a6f-136">Update the value for the variable 'checkpoint_files_location' in the script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql', to point to the target location for the [!INCLUDE[hek_2](../includes/hek-2-md.md)] checkpoint files.</span></span> <span data-ttu-id="02a6f-137">Los archivos de punto de comprobación deben colocarse en una unidad que tenga un buen rendimiento de E/S secuencial.</span><span class="sxs-lookup"><span data-stu-id="02a6f-137">The checkpoint files should be placed on a drive with good sequential IO performance.</span></span>  
  
     <span data-ttu-id="02a6f-138">Actualice el valor de la variable 'database_name' para que señale a la base de datos AdventureWorks2014.</span><span class="sxs-lookup"><span data-stu-id="02a6f-138">Update the value for the variable 'database_name' to point to the AdventureWorks2014 database.</span></span>  
  
    1.  <span data-ttu-id="02a6f-139">Asegúrese de incluir la barra diagonal inversa ' \' como parte del nombre de ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="02a6f-139">Be sure to include the backslash '\' as part of the path name</span></span>  
  
    2.  <span data-ttu-id="02a6f-140">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02a6f-140">Example:</span></span>  
  
        ```  
        :setvar checkpoint_files_location "d:\DBData\"  
        ...  
        :setvar database_name "AdventureWorks2014"  
        ```  
  
7.  <span data-ttu-id="02a6f-141">Ejecute el script de ejemplo de una de estas dos formas:</span><span class="sxs-lookup"><span data-stu-id="02a6f-141">Execute the sample script, in one of two ways:</span></span>  
  
    1.  <span data-ttu-id="02a6f-142">Con la utilidad de línea de comandos sqlcmd.</span><span class="sxs-lookup"><span data-stu-id="02a6f-142">Using the sqlcmd command-line utility.</span></span> <span data-ttu-id="02a6f-143">Por ejemplo, ejecutando el siguiente comando desde el símbolo del sistema en la carpeta que contiene el script:</span><span class="sxs-lookup"><span data-stu-id="02a6f-143">For example, for example by running the following command from the command-line prompt in the folder containing the script:</span></span>  
  
        ```  
        sqlcmd -S . -E -i "ssSQL14 RTM hek_2 Sample.sql"  
        ```  
  
    2.  <span data-ttu-id="02a6f-144">Con Management Studio:</span><span class="sxs-lookup"><span data-stu-id="02a6f-144">Using Management Studio:</span></span>  
  
        1.  <span data-ttu-id="02a6f-145">Abra el script ' [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample. SQL ' en una ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="02a6f-145">Open the script '[!INCLUDE[ssSQL14](../includes/sssql14-md.md)] RTM [!INCLUDE[hek_2](../includes/hek-2-md.md)] Sample.sql' in a query window</span></span>  
  
        2.  <span data-ttu-id="02a6f-146">Conéctese al servidor de destino que contiene la base de datos AdventureWorks2014.</span><span class="sxs-lookup"><span data-stu-id="02a6f-146">Connect to the target server that contains the database AdventureWorks2014</span></span>  
  
        3.  <span data-ttu-id="02a6f-147">Habilite el modo SQLCMD; para ello, haga clic en "modo de consulta > SQLCMD"</span><span class="sxs-lookup"><span data-stu-id="02a6f-147">Enable SQLCMD Mode, by clicking on 'Query -> SQLCMD Mode'</span></span>  
  
        4.  <span data-ttu-id="02a6f-148">Haga clic en el botón ' ejecutar ' para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="02a6f-148">Click the button 'Execute' to run the script</span></span>  
  
##  <a name="description-of-the-sample-tables-and-procedures"></a><a name="Descriptionofthesampletablesandprocedures"></a> <span data-ttu-id="02a6f-149">Descripción de las tablas y los procedimientos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02a6f-149">Description of the sample tables and procedures</span></span>  
 <span data-ttu-id="02a6f-150">El ejemplo crea nuevas tablas para productos y pedidos de venta basadas en tablas existentes en AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="02a6f-150">The sample creates new tables for products and sales orders, based on existing tables in AdventureWorks.</span></span> <span data-ttu-id="02a6f-151">El esquema de las nuevas tablas es similar a las tablas existentes, con algunas diferencias, como se explica a continuación.</span><span class="sxs-lookup"><span data-stu-id="02a6f-151">The schema of the new tables is similar to the existing tables, with a few differences, as explained below.</span></span>  
  
 <span data-ttu-id="02a6f-152">Las nuevas tablas optimizadas para memoria llevan el sufijo "_inmem".</span><span class="sxs-lookup"><span data-stu-id="02a6f-152">The new memory-optimized tables carry the suffix '_inmem'.</span></span> <span data-ttu-id="02a6f-153">El ejemplo también incluye las tablas correspondientes que llevan el sufijo "_ondisk"; estas tablas se pueden usar para realizar una comparación uno a uno entre el rendimiento de las tablas optimizadas para memoria y las tablas basadas en disco del sistema.</span><span class="sxs-lookup"><span data-stu-id="02a6f-153">The sample also includes corresponding tables carrying the suffix '_ondisk' - these tables can be used to make a one-to-one comparison between the performance of memory-optimized tables and disk-based tables on your system..</span></span>  
  
 <span data-ttu-id="02a6f-154">Tenga en cuenta que las tablas optimizadas para memoria empleadas en la carga de trabajo para la comparación de rendimiento son totalmente durables y con registro completo.</span><span class="sxs-lookup"><span data-stu-id="02a6f-154">Note that the memory-optimized tables used in the workload for performance comparison are fully durable and fully logged.</span></span> <span data-ttu-id="02a6f-155">No sacrifican la durabilidad o la confiabilidad para conseguir la mejora del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="02a6f-155">They do not sacrifice durability or reliability to attain the performance gain.</span></span>  
  
 <span data-ttu-id="02a6f-156">La carga de trabajo de destino de este ejemplo es el procesamiento de pedidos de venta, donde también tenemos en cuenta la información sobre productos y descuentos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-156">The target workload for this sample is sales order processing, where we consider also information about products and discounts.</span></span> <span data-ttu-id="02a6f-157">Para eso se usan las tablas SalesOrderHeader, SalesOrderDetail, Product, SpecialOffer y SpecialOfferProduct.</span><span class="sxs-lookup"><span data-stu-id="02a6f-157">To this end, the table SalesOrderHeader, SalesOrderDetail, Product, SpecialOffer, and SpecialOfferProduct.</span></span>  
  
 <span data-ttu-id="02a6f-158">Se emplean dos nuevos procedimientos almacenados, Sales.usp_InsertSalesOrder_inmem y Sales.usp_UpdateSalesOrderShipInfo_inmem, para insertar pedidos de venta y actualizar la información de envío de un pedido de venta determinado.</span><span class="sxs-lookup"><span data-stu-id="02a6f-158">Two new stored procedures, Sales.usp_InsertSalesOrder_inmem and Sales.usp_UpdateSalesOrderShipInfo_inmem, are used to insert sales orders and to update the shipping information of a given sales order.</span></span>  
  
 <span data-ttu-id="02a6f-159">El nuevo esquema 'Demo' contiene tablas del asistente y procedimientos almacenados para ejecutar una carga de trabajo de demostración.</span><span class="sxs-lookup"><span data-stu-id="02a6f-159">The new schema 'Demo' contains helper tables and stored procedures to execute a demo workload.</span></span>  
  
 <span data-ttu-id="02a6f-160">En concreto, el ejemplo de [!INCLUDE[hek_2](../includes/hek-2-md.md)] agrega los siguientes objetos a AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="02a6f-160">Concretely, the [!INCLUDE[hek_2](../includes/hek-2-md.md)] sample adds the following objects to AdventureWorks:</span></span>  
  
### <a name="tables-added-by-the-sample"></a><span data-ttu-id="02a6f-161">Tablas agregadas por el ejemplo</span><span class="sxs-lookup"><span data-stu-id="02a6f-161">Tables added by the sample</span></span>  
  
#### <a name="the-new-tables"></a><span data-ttu-id="02a6f-162">Las nuevas tablas</span><span class="sxs-lookup"><span data-stu-id="02a6f-162">The New Tables</span></span>  
 <span data-ttu-id="02a6f-163">Sales.SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-163">Sales.SalesOrderHeader_inmem</span></span>  
  
-   <span data-ttu-id="02a6f-164">Información de encabezado sobre los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="02a6f-164">Header information about sales orders.</span></span> <span data-ttu-id="02a6f-165">Cada pedido de venta tiene una fila en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="02a6f-165">Each sales order has one row in this table.</span></span>  
  
 <span data-ttu-id="02a6f-166">Sales.SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-166">Sales.SalesOrderDetail_inmem</span></span>  
  
-   <span data-ttu-id="02a6f-167">Detalles de los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="02a6f-167">Details of sales orders.</span></span> <span data-ttu-id="02a6f-168">Cada artículo de un pedido de venta tiene una fila en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="02a6f-168">Each line item of a sales order has one row in this table.</span></span>  
  
 <span data-ttu-id="02a6f-169">Sales.SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-169">Sales.SpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="02a6f-170">Información sobre ofertas especiales, incluido el porcentaje de descuento asociado a cada oferta especial.</span><span class="sxs-lookup"><span data-stu-id="02a6f-170">Information about special offers, including the discount percentage associated with each special offer.</span></span>  
  
 <span data-ttu-id="02a6f-171">Sales.SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-171">Sales.SpecialOfferProduct_inmem</span></span>  
  
-   <span data-ttu-id="02a6f-172">Tabla de referencia entre las ofertas especiales y los productos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-172">Reference table between special offers and products.</span></span> <span data-ttu-id="02a6f-173">Cada oferta especial puede abarcar cero o más productos, y cada producto puede estar incluido en cero o más ofertas especiales.</span><span class="sxs-lookup"><span data-stu-id="02a6f-173">Each special offer can feature zero or more products, and each product can be featured in zero or more special offers.</span></span>  
  
 <span data-ttu-id="02a6f-174">Production.Product_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-174">Production.Product_inmem</span></span>  
  
-   <span data-ttu-id="02a6f-175">Información sobre productos, incluido el precio de venta.</span><span class="sxs-lookup"><span data-stu-id="02a6f-175">Information about products, including their list price.</span></span>  
  
 <span data-ttu-id="02a6f-176">Demo.DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="02a6f-176">Demo.DemoSalesOrderDetailSeed</span></span>  
  
-   <span data-ttu-id="02a6f-177">Se usa en la carga de trabajo de demostración para generar pedidos de venta de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="02a6f-177">Used in the demo workload to construct sample sales orders.</span></span>  
  
 <span data-ttu-id="02a6f-178">Variaciones basadas en disco de las tablas:</span><span class="sxs-lookup"><span data-stu-id="02a6f-178">Disk-based variations of the tables:</span></span>  
  
-   <span data-ttu-id="02a6f-179">Sales.SalesOrderHeader_ondisk</span><span class="sxs-lookup"><span data-stu-id="02a6f-179">Sales.SalesOrderHeader_ondisk</span></span>  
  
-   <span data-ttu-id="02a6f-180">Sales.SalesOrderDetail_ondisk</span><span class="sxs-lookup"><span data-stu-id="02a6f-180">Sales.SalesOrderDetail_ondisk</span></span>  
  
-   <span data-ttu-id="02a6f-181">Sales.SpecialOffer_ondisk</span><span class="sxs-lookup"><span data-stu-id="02a6f-181">Sales.SpecialOffer_ondisk</span></span>  
  
-   <span data-ttu-id="02a6f-182">Sales.SpecialOfferProduct_ondisk</span><span class="sxs-lookup"><span data-stu-id="02a6f-182">Sales.SpecialOfferProduct_ondisk</span></span>  
  
-   <span data-ttu-id="02a6f-183">Production.Product_ondisk</span><span class="sxs-lookup"><span data-stu-id="02a6f-183">Production.Product_ondisk</span></span>  
  
#### <a name="differences-between-original-disk-based-and-the-and-new-memory-optimized-tables"></a><span data-ttu-id="02a6f-184">Diferencias entre las tablas originales basadas en disco y las nuevas tablas optimizadas para memoria</span><span class="sxs-lookup"><span data-stu-id="02a6f-184">Differences between original disk-based and the and new memory-optimized tables</span></span>  
 <span data-ttu-id="02a6f-185">En general, las nuevas tablas de este ejemplo emplean las mismas columnas y los mismos tipos de datos que las tablas originales.</span><span class="sxs-lookup"><span data-stu-id="02a6f-185">For the most part, the new tables introduced by this sample use the same columns and the same data types as the original tables.</span></span> <span data-ttu-id="02a6f-186">Sin embargo, hay algunas diferencias.</span><span class="sxs-lookup"><span data-stu-id="02a6f-186">However, there are a few differences.</span></span> <span data-ttu-id="02a6f-187">A continuación se enumeran las diferencias y el motivo de los cambios.</span><span class="sxs-lookup"><span data-stu-id="02a6f-187">We list the differences below, along with a rationale for the changes.</span></span>  
  
 <span data-ttu-id="02a6f-188">Sales.SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-188">Sales.SalesOrderHeader_inmem</span></span>  
  
-   <span data-ttu-id="02a6f-189">Las*restricciones DEFAULT* se admiten en las tablas optimizadas para memoria y la mayoría de las restricciones DEFAULT se migran tal cual.</span><span class="sxs-lookup"><span data-stu-id="02a6f-189">*Default constraints* are supported for memory-optimized tables, and most default constraints we migrated as is.</span></span> <span data-ttu-id="02a6f-190">Sin embargo, la tabla original Sales.SalesOrderHeader contiene dos restricciones DEFAULT que recuperan la fecha actual, para las columnas OrderDate y ModifiedDate.</span><span class="sxs-lookup"><span data-stu-id="02a6f-190">However, the original table Sales.SalesOrderHeader contains two default constraints that retrieve the current date, for the columns OrderDate and ModifiedDate.</span></span> <span data-ttu-id="02a6f-191">En una carga de trabajo de procesamiento de pedidos de alto rendimiento con mucha simultaneidad, cualquier recurso global puede convertirse en un punto de contención.</span><span class="sxs-lookup"><span data-stu-id="02a6f-191">In a high throughput order processing workload with a lot of concurrency, any global resource can become a point of contention.</span></span> <span data-ttu-id="02a6f-192">La hora del sistema es un recurso global y hemos observado que puede convertirse en un cuello de botella cuando se ejecuta una carga de trabajo de [!INCLUDE[hek_2](../includes/hek-2-md.md)] que inserta pedidos de venta, especialmente si es necesario recuperar la hora del sistema para varias columnas en el encabezado del pedido de venta, así como los detalles del pedido de venta.</span><span class="sxs-lookup"><span data-stu-id="02a6f-192">System time is such a global resource, and we have observed that it can become a bottleneck when running an [!INCLUDE[hek_2](../includes/hek-2-md.md)] workload that inserts sales orders, in particular if the system time needs to be retrieved for multiple columns in the sales order header, as well as the sales order details.</span></span> <span data-ttu-id="02a6f-193">Para resolver el problema en este ejemplo se recupera la hora del sistema solo una vez para cada pedido de venta que se inserta, y se usa ese valores para las columnas datetime de SalesOrderHeader_inmem y SalesOrderDetail_inmem, en el procedimiento almacenado Sales.usp_InsertSalesOrder_inmem.</span><span class="sxs-lookup"><span data-stu-id="02a6f-193">The problem is addressed in this sample by retrieving the system time only once for each sales order that is inserted, and use that value for the datetime columns in SalesOrderHeader_inmem and SalesOrderDetail_inmem, in the stored procedure Sales.usp_InsertSalesOrder_inmem.</span></span>  
  
-   <span data-ttu-id="02a6f-194">*UDT de alias:* la tabla original usa dos tipos de datos definidos por el usuario (UDT) de alias, dbo.OrderNumber y dbo.AccountNumber, para las columnas PurchaseOrderNumber y AccountNumber, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="02a6f-194">*Alias UDTs* - The original table uses two alias user-defined data types (UDTs) dbo.OrderNumber and dbo.AccountNumber, for the columns PurchaseOrderNumber and AccountNumber, respectively.</span></span> [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] <span data-ttu-id="02a6f-195">no admite UDT de alias para las tablas optimizadas para memoria, por lo que las tablas nuevas usan los tipos de datos del sistema nvarchar(25) y nvarchar(15), respectivamente.</span><span class="sxs-lookup"><span data-stu-id="02a6f-195">does not support alias UDT for memory-optimized tables, thus the new tables use system data types nvarchar(25) and nvarchar(15), respectively.</span></span>  
  
-   <span data-ttu-id="02a6f-196">*Columnas que aceptan valores NULL en claves de índice:* en la tabla original, la columna SalesPersonID acepta valores NULL, mientras que en las tablas nuevas esa columna no acepta valores NULL y tiene una restricción DEFAULT con el valor (-1).</span><span class="sxs-lookup"><span data-stu-id="02a6f-196">*Nullable columns in index keys* - In the original table, the column SalesPersonID is nullable, while in the new tables the column is not nullable and has a default constraint with value (-1).</span></span> <span data-ttu-id="02a6f-197">Esto se debe a que los índices de las tablas optimizadas para memoria no pueden tener columnas que aceptan valores NULL en la clave de índice; -1 es un suplente para NULL en este caso.</span><span class="sxs-lookup"><span data-stu-id="02a6f-197">This is because indexes on memory-optimized tables cannot have nullable columns in the index key; -1 is a surrogate for NULL in this case.</span></span>  
  
-   <span data-ttu-id="02a6f-198">*Columnas calculadas:* se omiten las columnas calculadas SalesOrderNumber y TotalDue, ya que [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] no admite columnas calculadas en tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="02a6f-198">*Computed columns* - The computed columns SalesOrderNumber and TotalDue are omitted, as [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] does not support computed columns in memory-optimized tables.</span></span> <span data-ttu-id="02a6f-199">La nueva vista Sales.vSalesOrderHeader_extended_inmem refleja las columnas SalesOrderNumber y TotalDue.</span><span class="sxs-lookup"><span data-stu-id="02a6f-199">The new view Sales.vSalesOrderHeader_extended_inmem reflects the columns SalesOrderNumber and TotalDue.</span></span> <span data-ttu-id="02a6f-200">Por tanto, puede usar esta vista si se necesitan estas columnas.</span><span class="sxs-lookup"><span data-stu-id="02a6f-200">Therefore, you can use this view if these columns are needed.</span></span>  
  
-   <span data-ttu-id="02a6f-201">Las tablas optimizadas para memoria no admiten*restricciones de clave externa* en [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02a6f-201">*Foreign key constraints* are not supported for memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="02a6f-202">Además, SalesOrderHeader_inmem es una tabla sin interrupción en la carga de trabajo de ejemplo, y las restricciones de clave externa requieren un procesamiento adicional para todas las operaciones DML, ya que tienen que hacer búsquedas en todas las demás tablas a las que se hace referencia en estas restricciones.</span><span class="sxs-lookup"><span data-stu-id="02a6f-202">In addition, SalesOrderHeader_inmem is a hot table in the example workload, and foreign keys constraints require additional processing for all DML operations, as it requires lookups in all the other tables referenced in these constraints.</span></span> <span data-ttu-id="02a6f-203">Por tanto, la suposición es que la aplicación garantiza la integridad referencial, y la integridad referencial no se valida cuando se insertan filas.</span><span class="sxs-lookup"><span data-stu-id="02a6f-203">Therefore, the assumption is that the app ensures referential integrity, and referential integrity is not validated when rows are inserted.</span></span> <span data-ttu-id="02a6f-204">La integridad referencial de los datos de esta tabla se puede comprobar con el procedimiento almacenado dbo.usp_ValidateIntegrity, mediante el script siguiente:</span><span class="sxs-lookup"><span data-stu-id="02a6f-204">Referential integrity for the data in this table can be verified using the stored procedure dbo.usp_ValidateIntegrity, using the following script:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="02a6f-205">Las tablas optimizadas para memoria no admiten*restricciones CHECK* en SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="02a6f-205">*Check constraints* are not supported for memory-optimized tables in SQ Server 2014.</span></span> <span data-ttu-id="02a6f-206">La integridad del dominio se valida junto con la integridad referencial mediante este script:</span><span class="sxs-lookup"><span data-stu-id="02a6f-206">Domain integrity is validated along with referential integrity using this script:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="02a6f-207">*Rowguid:* la columna rowguid se omite.</span><span class="sxs-lookup"><span data-stu-id="02a6f-207">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="02a6f-208">Aunque se admite uniqueidentifier en las tablas optimizadas para memoria, la opción ROWGUIDCOL no se admite en [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02a6f-208">While uniqueidentifier is support for memory-optimized tables, the option ROWGUIDCOL is not supported in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="02a6f-209">Las columnas de esta clase se suelen usar para la replicación de mezcla o para tablas que incluyen columnas FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="02a6f-209">Columns of this kind are typically used for either merge replication or tables that have filestream columns.</span></span> <span data-ttu-id="02a6f-210">En este ejemplo no se incluye ninguna de ellas.</span><span class="sxs-lookup"><span data-stu-id="02a6f-210">This sample includes neither.</span></span>  
  
 <span data-ttu-id="02a6f-211">Sales.SalesOrderDetail</span><span class="sxs-lookup"><span data-stu-id="02a6f-211">Sales.SalesOrderDetail</span></span>  
  
-   <span data-ttu-id="02a6f-212">*Restricciones DEFAULT*: igual que en SalesOrderHeader, la restricción DEFAULT que requiere la fecha y la hora del sistema no se migra; en su lugar, el procedimiento almacenado que inserta pedidos de venta se encarga de insertar la fecha y la hora actuales del sistema en la primera inserción.</span><span class="sxs-lookup"><span data-stu-id="02a6f-212">*Default constraints* - similar to SalesOrderHeader, the default constraint requiring the system date/time is not migrated, instead the stored procedure inserting sales orders takes care of inserting the current system date/time on first insert.</span></span>  
  
-   <span data-ttu-id="02a6f-213">*Columnas calculadas*: la columna calculada LineTotal no se ha migrado, ya que en [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] no se admiten columnas calculadas en las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="02a6f-213">*Computed columns* - the computed column LineTotal was not migrated as computed columns are not supported with memory-optimized tables in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="02a6f-214">Para obtener acceso a esta columna, use la vista Sales.vSalesOrderDetail_extended_inmem.</span><span class="sxs-lookup"><span data-stu-id="02a6f-214">To access this column use the view Sales.vSalesOrderDetail_extended_inmem.</span></span>  
  
-   <span data-ttu-id="02a6f-215">*Rowguid:* la columna rowguid se omite.</span><span class="sxs-lookup"><span data-stu-id="02a6f-215">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="02a6f-216">Para obtener detalles, vea la descripción de la tabla SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="02a6f-216">For details see the description for the table SalesOrderHeader.</span></span>  
  
-   <span data-ttu-id="02a6f-217">Para las restricciones *CHECK* y de *clave externa* , vea la descripción de SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="02a6f-217">For *check* and *foreign key* constraints see the description of SalesOrderHeader.</span></span> <span data-ttu-id="02a6f-218">Se puede usar el script siguiente para comprobar la integridad del dominio y referencial de esta tabla:</span><span class="sxs-lookup"><span data-stu-id="02a6f-218">The following script can be used to verify domain and referential integrity for this table:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SalesOrderHeader_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
 <span data-ttu-id="02a6f-219">Production.Product</span><span class="sxs-lookup"><span data-stu-id="02a6f-219">Production.Product</span></span>  
  
-   <span data-ttu-id="02a6f-220">*UDT de alias*: en la tabla original se usa el tipo de datos definido por el usuario dbo.Flag, que equivale al tipo de datos del sistema bit.</span><span class="sxs-lookup"><span data-stu-id="02a6f-220">*Alias UDTs* - the original table uses the user-defined data type dbo.Flag, which is equivalent to the system data type bit.</span></span> <span data-ttu-id="02a6f-221">La tabla migrada usa el tipo de datos bit en su lugar.</span><span class="sxs-lookup"><span data-stu-id="02a6f-221">The migrated table uses the bit data type instead.</span></span>  
  
-   <span data-ttu-id="02a6f-222">*Intercalación BIN2* : las columnas Name y ProductNumber se incluyen en las claves de índice y, por tanto, deben tener intercalaciones BIN2 en [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02a6f-222">*BIN2 collation* - The columns Name and ProductNumber are included in index keys, and must thus have BIN2 collations in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span> <span data-ttu-id="02a6f-223">Aquí, la suposición es que la aplicación no emplea las características de intercalación, como no distinguir mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="02a6f-223">Here, the assumption is that the app does not rely on collation specifics, like case insensitivity.</span></span>  
  
-   <span data-ttu-id="02a6f-224">*Rowguid:* la columna rowguid se omite.</span><span class="sxs-lookup"><span data-stu-id="02a6f-224">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="02a6f-225">Para obtener detalles, vea la descripción de la tabla SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="02a6f-225">For details see the description for the table SalesOrderHeader.</span></span>  
  
-   <span data-ttu-id="02a6f-226">Las restricciones*UNIQUE*, *CHECK* y *de clave externa* are accounted for in two ways: the stored procedures Product.usp_InsertProduct_inmem y Product.usp_DeleteProduct_inmem can be used to insert y delete products; these procedures validate domain y referential integrity, y will fail if integrity is violated.</span><span class="sxs-lookup"><span data-stu-id="02a6f-226">*Unique*, *Check* and *Foreign Key constraints* are accounted for in two ways: the stored procedures Product.usp_InsertProduct_inmem and Product.usp_DeleteProduct_inmem can be used to insert and delete products; these procedures validate domain and referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="02a6f-227">Además, se puede usar el script siguiente para validar la integridad del dominio y referencial:</span><span class="sxs-lookup"><span data-stu-id="02a6f-227">In addition, the follow script can be used to validate domain and referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Production.Product')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
    -   <span data-ttu-id="02a6f-228">Tenga en cuenta que los procedimientos almacenados usp_InsertProduct_inmem y usp_DeleteProduct_inmem solo consideran las claves externas entre las tablas migradas.</span><span class="sxs-lookup"><span data-stu-id="02a6f-228">Note that the store procedures usp_InsertProduct_inmem and usp_DeleteProduct_inmem consider only foreign keys between the migrated tables.</span></span> <span data-ttu-id="02a6f-229">Las referencias a otras tablas ProductModel, ProductSubcategory y UnitMeasure no se tienen en cuenta.</span><span class="sxs-lookup"><span data-stu-id="02a6f-229">References to other tables ProductModel, ProductSubcategory, and UnitMeasure are not considered.</span></span>  
  
 <span data-ttu-id="02a6f-230">Sales.SpecialOffer</span><span class="sxs-lookup"><span data-stu-id="02a6f-230">Sales.SpecialOffer</span></span>  
  
-   <span data-ttu-id="02a6f-231">Las restricciones*CHECK* y *de clave externa* are accounted for in two ways: the stored procedures Sales.usp_InsertSpecialOffer_inmem y Sales.usp_DeleteSpecialOffer_inmem can be used to insert y delete special offers; these procedures validate domain y referential integrity, y will fail if integrity is violated.</span><span class="sxs-lookup"><span data-stu-id="02a6f-231">*Check* and *Foreign Key constraints* are accounted for in two ways: the stored procedures Sales.usp_InsertSpecialOffer_inmem and Sales.usp_DeleteSpecialOffer_inmem can be used to insert and delete special offers; these procedures validate domain and referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="02a6f-232">Además, se puede usar el script siguiente para validar la integridad del dominio y referencial:</span><span class="sxs-lookup"><span data-stu-id="02a6f-232">In addition, the follow script can be used to validate domain and referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SpecialOffer_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="02a6f-233">*Rowguid:* la columna rowguid se omite.</span><span class="sxs-lookup"><span data-stu-id="02a6f-233">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="02a6f-234">Para obtener detalles, vea la descripción de la tabla SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="02a6f-234">For details see the description for the table SalesOrderHeader.</span></span>  
  
 <span data-ttu-id="02a6f-235">Sales.SpecialOfferProduct</span><span class="sxs-lookup"><span data-stu-id="02a6f-235">Sales.SpecialOfferProduct</span></span>  
  
-   <span data-ttu-id="02a6f-236">Las*restricciones de clave externa* se abordan de dos maneras: se puede usar el procedimiento almacenado Sales.usp_InsertSpecialOfferProduct_inmem para insertar relaciones entre ofertas especiales y productos; este procedimiento valida la integridad referencial, y generará un error si se infringe la integridad.</span><span class="sxs-lookup"><span data-stu-id="02a6f-236">*Foreign Key constraints* are accounted for in two ways: the stored procedure Sales.usp_InsertSpecialOfferProduct_inmem can be used to insert relationships between special offers and products; this procedures validates referential integrity, and will fail if integrity is violated.</span></span> <span data-ttu-id="02a6f-237">Además, se puede usar el script siguiente para validar la integridad referencial:</span><span class="sxs-lookup"><span data-stu-id="02a6f-237">In addition, the follow script can be used to validate referential integrity as is:</span></span>  
  
    ```  
    DECLARE @o int = object_id(N'Sales.SpecialOfferProduct_inmem')  
    EXEC dbo.usp_ValidateIntegrity @o  
    ```  
  
-   <span data-ttu-id="02a6f-238">*Rowguid:* la columna rowguid se omite.</span><span class="sxs-lookup"><span data-stu-id="02a6f-238">*Rowguid* - The rowguid column is omitted.</span></span> <span data-ttu-id="02a6f-239">Para obtener detalles, vea la descripción de la tabla SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="02a6f-239">For details see the description for the table SalesOrderHeader.</span></span>  
  
#### <a name="considerations-for-indexes-on-memory-optimized-tables"></a><span data-ttu-id="02a6f-240">Consideraciones sobre los índices de tablas optimizadas para memoria</span><span class="sxs-lookup"><span data-stu-id="02a6f-240">Considerations for indexes on memory-optimized tables</span></span>  
 <span data-ttu-id="02a6f-241">El índice de línea base para las tablas optimizadas para memoria es el índice no clúster, que admite búsquedas de puntos (búsqueda de índice en predicado de igualdad), recorridos de intervalo (búsqueda de índice en predicados de desigualdad), exámenes de índice completos y exámenes ordenados.</span><span class="sxs-lookup"><span data-stu-id="02a6f-241">The baseline index for memory-optimized tables is the NONCLUSTERED index, which supports point lookups (index seek on equality predicate), range scans (index seek in inequality predicate), full index scans, and ordered scans.</span></span> <span data-ttu-id="02a6f-242">Además, los índices no clúster admiten búsquedas en las columnas iniciales de la clave de índice.</span><span class="sxs-lookup"><span data-stu-id="02a6f-242">In addition, NONCLUSTERED indexes support searching on leading columns of the index key.</span></span> <span data-ttu-id="02a6f-243">De hecho, los índices no clúster optimizados para memoria admiten todas las operaciones compatibles con los índices no clúster basados en disco, con la única excepción de los exámenes hacia atrás.</span><span class="sxs-lookup"><span data-stu-id="02a6f-243">In fact memory-optimized NONCLUSTERED indexes support all the operations supported by disk-based NONCLUSTERED indexes, with the only exception being backward scans.</span></span> <span data-ttu-id="02a6f-244">Por tanto, el uso de índices no clúster es una opción segura para los índices.</span><span class="sxs-lookup"><span data-stu-id="02a6f-244">Therefore, using NONCLUSTERED indexes is a safe choice for your indexes.</span></span>  
  
 <span data-ttu-id="02a6f-245">Se pueden usar índices hash para optimizar aún más la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="02a6f-245">HASH indexes are can be used to further optimize the workload.</span></span> <span data-ttu-id="02a6f-246">Están optimizados especialmente para las búsquedas de puntos y las inserciones de filas.</span><span class="sxs-lookup"><span data-stu-id="02a6f-246">They are particularly optimized for point lookups and row inserts.</span></span> <span data-ttu-id="02a6f-247">Sin embargo, hay que tener en cuenta que no admiten recorridos de intervalo, exámenes ordenados ni búsquedas en columnas de clave de índice iniciales.</span><span class="sxs-lookup"><span data-stu-id="02a6f-247">However, one must consider that they do not support range scans, ordered scans, or search on leading index key columns.</span></span> <span data-ttu-id="02a6f-248">Por tanto, hay que tener cuidado cuando se usen estos índices.</span><span class="sxs-lookup"><span data-stu-id="02a6f-248">Therefore, care needs to be taken when using these indexes.</span></span> <span data-ttu-id="02a6f-249">Además, es necesario especificar el bucket_count en el momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="02a6f-249">In addition, it is necessary to specify the bucket_count at create time.</span></span> <span data-ttu-id="02a6f-250">Normalmente se debe establecer entre una y dos veces el número de valores de clave de índice, pero la sobrestimación no suele suponer ningún problema.</span><span class="sxs-lookup"><span data-stu-id="02a6f-250">It should usually be set at between one and two times the number of index key values, but overestimating is usually not a problem.</span></span>  
  
 <span data-ttu-id="02a6f-251">Vea los Libros en pantalla para obtener más información sobre las [directrices para usar índices](https://technet.microsoft.com/library/dn133166\(v=sql.120\).aspx) y las directrices para [elegir el número correcto de depósitos](https://technet.microsoft.com/library/dn494956\(v=sql.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="02a6f-251">See Books Online for more details about [index guidelines](https://technet.microsoft.com/library/dn133166\(v=sql.120\).aspx) and guidelines for [choosing the right bucket_count](https://technet.microsoft.com/library/dn494956\(v=sql.120\).aspx).</span></span>  
  
 <span data-ttu-id="02a6f-252">Los índices de las tablas migradas se han optimizado para la carga de trabajo de procesamiento de pedidos de venta de demostración.</span><span class="sxs-lookup"><span data-stu-id="02a6f-252">The indexes on the migrated tables have been tuned for the demo sales order processing workload.</span></span> <span data-ttu-id="02a6f-253">La carga de trabajo usa inserciones y búsquedas de puntos en las tablas Sales.SalesOrderHeader_inmem y Sales.SalesOrderDetail_inmem, y también usa búsquedas de puntos en las columnas de clave principal en las tablas Production.Product_inmem y Sales.SpecialOffer_inmem.</span><span class="sxs-lookup"><span data-stu-id="02a6f-253">The workload relies on inserts and point lookups in the tables Sales.SalesOrderHeader_inmem and Sales.SalesOrderDetail_inmem, and it also relies on point lookups on the primary key columns in the tables Production.Product_inmem and Sales.SpecialOffer_inmem.</span></span>  
  
 <span data-ttu-id="02a6f-254">Sales.SalesOrderHeader_inmem tiene tres índices, que son todos índices HASH por motivos de rendimiento, y porque no se necesita ningún examen ordenado o recorrido de intervalo para la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="02a6f-254">Sales.SalesOrderHeader_inmem has three indexes, which are all HASH indexes for performance reasons, and because no ordered or range scans are needed for the workload.</span></span>  
  
-   <span data-ttu-id="02a6f-255">Índice HASH de (SalesOrderID): bucket_count tiene un tamaño de 10 millones (redondeado hasta 16 millones), ya que el número esperado de pedidos de venta es 10 millones</span><span class="sxs-lookup"><span data-stu-id="02a6f-255">HASH index on (SalesOrderID): bucket_count is sized at 10 million (rounded up to 16 million), because the expected number of sales orders is 10 million</span></span>  
  
-   <span data-ttu-id="02a6f-256">Índice HASH de (SalesPersonID): el bucket_count es 1 millón.</span><span class="sxs-lookup"><span data-stu-id="02a6f-256">HASH index on (SalesPersonID): bucket_count is 1 million.</span></span> <span data-ttu-id="02a6f-257">El conjunto de datos especificado no tiene muchos vendedores, pero permite el crecimiento futuro, y además no hay penalización de rendimiento por las búsquedas de puntos si el valor bucket_count está sobredimensionado.</span><span class="sxs-lookup"><span data-stu-id="02a6f-257">The data set provided does not have a lot of sales persons, but this allows for future growth, plus you don't pay a performance penalty for point lookups if the bucket_count is oversized.</span></span>  
  
-   <span data-ttu-id="02a6f-258">Índice HASH de (CustomerID): el bucket_count es 1 millón.</span><span class="sxs-lookup"><span data-stu-id="02a6f-258">HASH index on (CustomerID): bucket_count is 1 million.</span></span> <span data-ttu-id="02a6f-259">El conjunto de datos especificado no tiene muchos clientes, pero permite el crecimiento futuro.</span><span class="sxs-lookup"><span data-stu-id="02a6f-259">The data set provided does not have a lot of customers, but this allows for future growth.</span></span>  
  
 <span data-ttu-id="02a6f-260">Sales.SalesOrderDetail_inmem tiene tres índices, que son todos índices HASH por motivos de rendimiento, y porque no se necesita ningún examen ordenado o recorrido de intervalo para la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="02a6f-260">Sales.SalesOrderDetail_inmem has three indexes, which are all HASH indexes for performance reasons, and because no ordered or range scans are needed for the workload.</span></span>  
  
-   <span data-ttu-id="02a6f-261">Índice HASH de (SalesOrderID, SalesOrderDetailID): este es el índice de clave principal, y aunque las búsquedas en (SalesOrderID, SalesOrderDetailID) serán poco frecuentes, el uso de un índice hash para la clave acelera las inserciones de filas.</span><span class="sxs-lookup"><span data-stu-id="02a6f-261">HASH index on (SalesOrderID, SalesOrderDetailID): this is the primary key index, and even though lookups on (SalesOrderID, SalesOrderDetailID) will be infrequent, using a hash index for the key speeds up row inserts.</span></span> <span data-ttu-id="02a6f-262">El bucket_count tiene un tamaño de 50 millones (redondeado hasta 67 millones): el número esperado de pedidos de venta es de 10 millones y tiene un tamaño promedio de 5 artículos por pedido.</span><span class="sxs-lookup"><span data-stu-id="02a6f-262">The bucket_count is sized at 50 million (rounded up to 67 million): the expected number of sales orders is 10 million, and this is sized to have an average of 5 items per order</span></span>  
  
-   <span data-ttu-id="02a6f-263">Índice HASH de (SalesOrderID): las búsquedas por pedido de venta son frecuentes; es conveniente buscar todos los artículos correspondientes a un único pedido.</span><span class="sxs-lookup"><span data-stu-id="02a6f-263">HASH index on (SalesOrderID): lookups by sales order are frequent: you will want to find all the line items corresponding to a single order.</span></span>  <span data-ttu-id="02a6f-264">bucket_count tiene un tamaño de 10 millones (redondeado hasta 16 millones), ya que el número esperado de pedidos de venta es 10 millones</span><span class="sxs-lookup"><span data-stu-id="02a6f-264">bucket_count is sized at 10 million (rounded up to 16 million), because the expected number of sales orders is 10 million</span></span>  
  
-   <span data-ttu-id="02a6f-265">Índice HASH de (ProductID): el bucket_count es 1 millón.</span><span class="sxs-lookup"><span data-stu-id="02a6f-265">HASH index on (ProductID): bucket_count is 1 million.</span></span> <span data-ttu-id="02a6f-266">El conjunto de datos especificado no tiene muchos productos, pero permite el crecimiento futuro.</span><span class="sxs-lookup"><span data-stu-id="02a6f-266">The data set provided does not have a lot of product, but this allows for future growth.</span></span>  
  
 <span data-ttu-id="02a6f-267">Production.Product_inmem tiene tres índices</span><span class="sxs-lookup"><span data-stu-id="02a6f-267">Production.Product_inmem has three indexes</span></span>  
  
-   <span data-ttu-id="02a6f-268">Índice HASH de (ProductID): las búsquedas de ProductID son la ruta crítica para la carga de trabajo de demostración, por lo que es un índice hash</span><span class="sxs-lookup"><span data-stu-id="02a6f-268">HASH index on (ProductID): lookups on ProductID are in the critical path for the demo workload, therefore this is a hash index</span></span>  
  
-   <span data-ttu-id="02a6f-269">Índice no clúster de (Name): permitirá exámenes ordenados de los nombres de producto</span><span class="sxs-lookup"><span data-stu-id="02a6f-269">NONCLUSTERED index on (Name): this will allow ordered scans of product names</span></span>  
  
-   <span data-ttu-id="02a6f-270">Índice no clúster de (ProductNumber): permitirá exámenes ordenados de los números de producto</span><span class="sxs-lookup"><span data-stu-id="02a6f-270">NONCLUSTERED index on (ProductNumber): this will allow ordered scans of product numbers</span></span>  
  
 <span data-ttu-id="02a6f-271">Sales.SpecialOffer_inmem tiene un índice HASH en (SpecialOfferID): las búsquedas de puntos de ofertas especiales son una parte crítica de la carga de trabajo de demostración.</span><span class="sxs-lookup"><span data-stu-id="02a6f-271">Sales.SpecialOffer_inmem has one HASH index on (SpecialOfferID): point lookups of special offers are in the critical part of the demo workload.</span></span> <span data-ttu-id="02a6f-272">El bucket_count tiene un tamaño de 1 millón para permitir el crecimiento futuro.</span><span class="sxs-lookup"><span data-stu-id="02a6f-272">The bucket_count is sized at 1 million to allow for future growth.</span></span>  
  
 <span data-ttu-id="02a6f-273">No se hace referencia a Sales.SpecialOfferProduct_inmem en la carga de trabajo de demostración, por lo que no hay necesidad de usar índices hash en esta tabla para optimizar la carga de trabajo; los índices de (SpecialOfferID, ProductID) y (ProductID) no son agrupados.</span><span class="sxs-lookup"><span data-stu-id="02a6f-273">Sales.SpecialOfferProduct_inmem is not referenced in the demo workload, and thus there is no apparent need to use hash indexes on this table to optimize the workload - the indexes on (SpecialOfferID, ProductID) and (ProductID) are NONCLUSTERED.</span></span>  
  
 <span data-ttu-id="02a6f-274">Observe que en la información anterior algunos valores de bucket_count están sobredimensionados, pero no los bucket_counts de los índices de SalesOrderHeader_inmem y SalesOrderDetail_inmem: tienen un tamaño para 10 millones de pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="02a6f-274">Notice that in the above some of the bucket_counts are over-sized, but not the bucket_counts for the indexes on SalesOrderHeader_inmem and SalesOrderDetail_inmem: they are sized for just 10 million sales orders.</span></span> <span data-ttu-id="02a6f-275">Esto se hace para permitir la instalación del ejemplo en sistemas con poca disponibilidad de memoria, aunque en esos casos la carga de trabajo de demostración producirá un error si no hay memoria suficiente.</span><span class="sxs-lookup"><span data-stu-id="02a6f-275">This was done to allow installing the sample on systems with low memory availability, although in those cases the demo workload will fail with out-of-memory.</span></span> <span data-ttu-id="02a6f-276">Si desea escalar el ejemplo más allá de 10 millones de pedidos de venta, no dude en aumentar los números de cubos en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="02a6f-276">If you do want to scale well beyond 10 million sales orders, feel free to increase the bucket counts accordingly.</span></span>  
  
#### <a name="considerations-for-memory-utilization"></a><span data-ttu-id="02a6f-277">Consideraciones sobre el uso de memoria</span><span class="sxs-lookup"><span data-stu-id="02a6f-277">Considerations for memory utilization</span></span>  
 <span data-ttu-id="02a6f-278">El uso de memoria en la base de datos de ejemplo, tanto antes como después de ejecutar la carga de trabajo de demostración, se describe en la sección [Uso de memoria para las tablas optimizadas para memoria](#Memoryutilizationforthememory-optimizedtables).</span><span class="sxs-lookup"><span data-stu-id="02a6f-278">Memory utilization in the sample database, both before and after running the demo workload, is discussed in the Section [Memory utilization for the memory-optimized tables](#Memoryutilizationforthememory-optimizedtables).</span></span>  
  
### <a name="stored-procedures-added-by-the-sample"></a><span data-ttu-id="02a6f-279">Procedimientos almacenados agregados por el ejemplo</span><span class="sxs-lookup"><span data-stu-id="02a6f-279">Stored Procedures added by the sample</span></span>  
 <span data-ttu-id="02a6f-280">Los dos procedimientos almacenados principales para insertar pedidos de venta y actualizar los detalles de envío son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="02a6f-280">The two key stored procedures for inserting sales order and updating shipping details are as follows:</span></span>  
  
-   <span data-ttu-id="02a6f-281">Sales.usp_InsertSalesOrder_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-281">Sales.usp_InsertSalesOrder_inmem</span></span>  
  
    -   <span data-ttu-id="02a6f-282">Inserta un nuevo pedido de venta en la base de datos y genera el SalesOrderID para ese pedido.</span><span class="sxs-lookup"><span data-stu-id="02a6f-282">Inserts a new sales order in the database and outputs the SalesOrderID for that sales order.</span></span> <span data-ttu-id="02a6f-283">Como parámetros de entrada toma los detalles del encabezado del pedido de venta, así como los artículos del pedido.</span><span class="sxs-lookup"><span data-stu-id="02a6f-283">As input parameters it takes details for the sales order header, as well as the line items in the order.</span></span>  
  
    -   <span data-ttu-id="02a6f-284">Parámetro de salida:</span><span class="sxs-lookup"><span data-stu-id="02a6f-284">Output parameter:</span></span>  
  
        -   <span data-ttu-id="02a6f-285">@SalesOrderID int: el valor SalesOrderID del pedido de venta que se acaba de insertar</span><span class="sxs-lookup"><span data-stu-id="02a6f-285">@SalesOrderID int - the SalesOrderID for the sales order that was just inserted</span></span>  
  
    -   <span data-ttu-id="02a6f-286">Parámetros de entrada (obligatorios):</span><span class="sxs-lookup"><span data-stu-id="02a6f-286">Input parameters (required):</span></span>  
  
        -   <span data-ttu-id="02a6f-287">@DueDate datetime2</span><span class="sxs-lookup"><span data-stu-id="02a6f-287">@DueDate datetime2</span></span>  
  
        -   <span data-ttu-id="02a6f-288">@CustomerID int</span><span class="sxs-lookup"><span data-stu-id="02a6f-288">@CustomerID int</span></span>  
  
        -   <span data-ttu-id="02a6f-289">@BillToAddressID [int]</span><span class="sxs-lookup"><span data-stu-id="02a6f-289">@BillToAddressID [int]</span></span>  
  
        -   <span data-ttu-id="02a6f-290">@ShipToAddressID [int]</span><span class="sxs-lookup"><span data-stu-id="02a6f-290">@ShipToAddressID [int]</span></span>  
  
        -   <span data-ttu-id="02a6f-291">@ShipMethodID [int]</span><span class="sxs-lookup"><span data-stu-id="02a6f-291">@ShipMethodID [int]</span></span>  
  
        -   <span data-ttu-id="02a6f-292">@SalesOrderDetails Sales.SalesOrderDetailType_inmem: TVP que contiene los elementos de línea del pedido</span><span class="sxs-lookup"><span data-stu-id="02a6f-292">@SalesOrderDetails Sales.SalesOrderDetailType_inmem - TVP that contains the line items of the order</span></span>  
  
    -   <span data-ttu-id="02a6f-293">Parámetros de entrada (opcionales):</span><span class="sxs-lookup"><span data-stu-id="02a6f-293">Input parameters (optional):</span></span>  
  
        -   <span data-ttu-id="02a6f-294">@Status [tinyint]</span><span class="sxs-lookup"><span data-stu-id="02a6f-294">@Status [tinyint]</span></span>  
  
        -   <span data-ttu-id="02a6f-295">@OnlineOrderFlag [bit]</span><span class="sxs-lookup"><span data-stu-id="02a6f-295">@OnlineOrderFlag [bit]</span></span>  
  
        -   <span data-ttu-id="02a6f-296">@PurchaseOrderNumber [nvarchar](25\)</span><span class="sxs-lookup"><span data-stu-id="02a6f-296">@PurchaseOrderNumber [nvarchar](25\)</span></span>  
  
        -   <span data-ttu-id="02a6f-297">@AccountNumber [nvarchar](15\)</span><span class="sxs-lookup"><span data-stu-id="02a6f-297">@AccountNumber [nvarchar](15\)</span></span>  
  
        -   <span data-ttu-id="02a6f-298">@SalesPersonID [int]</span><span class="sxs-lookup"><span data-stu-id="02a6f-298">@SalesPersonID [int]</span></span>  
  
        -   <span data-ttu-id="02a6f-299">@TerritoryID [int]</span><span class="sxs-lookup"><span data-stu-id="02a6f-299">@TerritoryID [int]</span></span>  
  
        -   <span data-ttu-id="02a6f-300">@CreditCardID [int]</span><span class="sxs-lookup"><span data-stu-id="02a6f-300">@CreditCardID [int]</span></span>  
  
        -   <span data-ttu-id="02a6f-301">@CreditCardApprovalCode [varchar](15\)</span><span class="sxs-lookup"><span data-stu-id="02a6f-301">@CreditCardApprovalCode [varchar](15\)</span></span>  
  
        -   <span data-ttu-id="02a6f-302">@CurrencyRateID [int]</span><span class="sxs-lookup"><span data-stu-id="02a6f-302">@CurrencyRateID [int]</span></span>  
  
        -   <span data-ttu-id="02a6f-303">@Comment nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="02a6f-303">@Comment nvarchar(128)</span></span>  
  
-   <span data-ttu-id="02a6f-304">Sales.usp_UpdateSalesOrderShipInfo_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-304">Sales.usp_UpdateSalesOrderShipInfo_inmem</span></span>  
  
    -   <span data-ttu-id="02a6f-305">Actualice la información de envío para un pedido de venta determinado.</span><span class="sxs-lookup"><span data-stu-id="02a6f-305">Update the shipping information for a given sales order.</span></span> <span data-ttu-id="02a6f-306">Esto también actualizará la información de envío de todos los artículos del pedido de venta.</span><span class="sxs-lookup"><span data-stu-id="02a6f-306">This will also update the shipping information for all line items of the sales order.</span></span>  
  
    -   <span data-ttu-id="02a6f-307">Se trata de un procedimiento contenedor para los procedimientos almacenados compilados de forma nativa Sales.usp_UpdateSalesOrderShipInfo_native con lógica de reintento para abordar posibles conflictos (inesperados) con las transacciones simultáneas que actualizan el mismo pedido.</span><span class="sxs-lookup"><span data-stu-id="02a6f-307">This is a wrapper procedure for the natively compiled stored procedures Sales.usp_UpdateSalesOrderShipInfo_native with retry logic to deal with (unexpected) potential conflicts with concurrent transactions updating the same order.</span></span> <span data-ttu-id="02a6f-308">Para obtener más información acerca de la lógica de reintento, vea [este tema](https://technet.microsoft.com/library/dn169141\(v=sql.120\).aspx)en los Libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="02a6f-308">For more information about retry logic see the Books Online topic [here](https://technet.microsoft.com/library/dn169141\(v=sql.120\).aspx).</span></span>  
  
-   <span data-ttu-id="02a6f-309">Sales.usp_UpdateSalesOrderShipInfo_native</span><span class="sxs-lookup"><span data-stu-id="02a6f-309">Sales.usp_UpdateSalesOrderShipInfo_native</span></span>  
  
    -   <span data-ttu-id="02a6f-310">Este es el procedimiento almacenado compilado de forma nativa que procesa realmente la actualización de la información de envío.</span><span class="sxs-lookup"><span data-stu-id="02a6f-310">This is the natively compiled stored procedure that actually processes the update to the shipping information.</span></span> <span data-ttu-id="02a6f-311">Está pensado para que se le llame desde el procedimiento almacenado contenedor Sales.usp_UpdateSalesOrderShipInfo_inmem.</span><span class="sxs-lookup"><span data-stu-id="02a6f-311">It is means to be called from the wrapper stored procedure Sales.usp_UpdateSalesOrderShipInfo_inmem.</span></span> <span data-ttu-id="02a6f-312">Si el cliente puede resolver los errores e implementa lógica de reintento, puede llamar a este procedimiento directamente, en lugar de usar el procedimiento almacenado contenedor.</span><span class="sxs-lookup"><span data-stu-id="02a6f-312">If the client can deal with failures and implements retry logic, you can call this procedure directly, rather than using the wrapper stored procedure.</span></span>  
  
 <span data-ttu-id="02a6f-313">El procedimiento almacenado siguiente se emplea para la carga de trabajo de demostración.</span><span class="sxs-lookup"><span data-stu-id="02a6f-313">The following stored procedure is used for the demo workload.</span></span>  
  
-   <span data-ttu-id="02a6f-314">Demo.usp_DemoReset</span><span class="sxs-lookup"><span data-stu-id="02a6f-314">Demo.usp_DemoReset</span></span>  
  
    -   <span data-ttu-id="02a6f-315">Restablece la demostración vaciando y reinicializando las tablas SalesOrderHeader y SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="02a6f-315">Resets the demo by emptying and reseeding the SalesOrderHeader and SalesOrderDetail tables.</span></span>  
  
 <span data-ttu-id="02a6f-316">Los procedimientos almacenados siguientes se usan para insertar y eliminar información de las tablas optimizadas para memoria garantizando la integridad del dominio y referencial.</span><span class="sxs-lookup"><span data-stu-id="02a6f-316">The following stored procedures are used for inserting in and deleting from memory-optimized tables while guaranteeing domain and referential integrity.</span></span>  
  
-   <span data-ttu-id="02a6f-317">Production.usp_InsertProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-317">Production.usp_InsertProduct_inmem</span></span>  
  
-   <span data-ttu-id="02a6f-318">Production.usp_DeleteProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-318">Production.usp_DeleteProduct_inmem</span></span>  
  
-   <span data-ttu-id="02a6f-319">Sales.usp_InsertSpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-319">Sales.usp_InsertSpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="02a6f-320">Sales.usp_DeleteSpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-320">Sales.usp_DeleteSpecialOffer_inmem</span></span>  
  
-   <span data-ttu-id="02a6f-321">Sales.usp_InsertSpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-321">Sales.usp_InsertSpecialOfferProduct_inmem</span></span>  
  
 <span data-ttu-id="02a6f-322">Por último, el procedimiento almacenado siguiente se usa para comprobar la integridad del dominio y referencial.</span><span class="sxs-lookup"><span data-stu-id="02a6f-322">Finally the following stored procedure is used to verify domain and referential integrity.</span></span>  
  
1.  <span data-ttu-id="02a6f-323">dbo.usp_ValidateIntegrity</span><span class="sxs-lookup"><span data-stu-id="02a6f-323">dbo.usp_ValidateIntegrity</span></span>  
  
    -   <span data-ttu-id="02a6f-324">Parámetro opcional: @object_id, identificador del objeto cuya integridad se va a validar</span><span class="sxs-lookup"><span data-stu-id="02a6f-324">Optional parameter: @object_id - ID of the object to validate integrity for</span></span>  
  
    -   <span data-ttu-id="02a6f-325">Este procedimiento usa las tablas dbo.DomainIntegrity, dbo.ReferentialIntegrity y dbo.UniqueIntegrity para las reglas de integridad que es necesario comprobar; el ejemplo rellena estas tablas según las restricciones CHECK, UNIQUE y de clave externa existentes en las tablas originales de la base de datos AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="02a6f-325">This procedure relies on the tables dbo.DomainIntegrity, dbo.ReferentialIntegrity, and dbo.UniqueIntegrity for the integrity rules that need to be verified - the sample populates these tables based on the check, foreign key, and unique constraints that exist for the original tables in the AdventureWorks database.</span></span>  
  
    -   <span data-ttu-id="02a6f-326">Usa los procedimientos del asistente dbo.usp_GenerateCKCheck, dbo.usp_GenerateFKCheck y dbo.GenerateUQCheck para generar el código T-SQL necesario para realizar las comprobaciones de integridad.</span><span class="sxs-lookup"><span data-stu-id="02a6f-326">It relies on the helper procedures dbo.usp_GenerateCKCheck, dbo.usp_GenerateFKCheck, and dbo.GenerateUQCheck to generate the T-SQL needed for performing the integrity checks.</span></span>  
  
##  <a name="performance-measurements-using-the-demo-workload"></a><a name="PerformanceMeasurementsusingtheDemoWorkload"></a> <span data-ttu-id="02a6f-327">Medidas de rendimiento con la carga de trabajo de demostración</span><span class="sxs-lookup"><span data-stu-id="02a6f-327">Performance Measurements using the Demo Workload</span></span>  
 <span data-ttu-id="02a6f-328">Ostress es una herramienta de línea de comandos desarrollada por el equipo de soporte técnico de [!INCLUDE[msCoName](../includes/msconame-md.md)] CSS [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02a6f-328">Ostress is a command-line tool that was developed by the [!INCLUDE[msCoName](../includes/msconame-md.md)] CSS [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] support team.</span></span> <span data-ttu-id="02a6f-329">Esta herramienta se puede usar para ejecutar consultas o ejecutar procedimientos almacenados en paralelo.</span><span class="sxs-lookup"><span data-stu-id="02a6f-329">This tool can be used to execute queries or run stored procedures in parallel.</span></span> <span data-ttu-id="02a6f-330">Puede configurar el número de subprocesos para ejecutar una instrucción T-SQL proporcionada en paralelo y puede especificar cuántas veces se debe ejecutar la instrucción en este subproceso; ostress recorrerá los subprocesos y ejecutará la instrucción en todos ellos en paralelo.</span><span class="sxs-lookup"><span data-stu-id="02a6f-330">You can configure the number of threads to run a given T-SQL statement in parallel, and you can specify how many times the statement should be executed on this thread; ostress will spin up the threads and execute the statement on all threads in parallel.</span></span> <span data-ttu-id="02a6f-331">Una vez que concluya la ejecución en todos los subprocesos, ostress notificará el tiempo empleado en finalizar la ejecución en todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-331">After execution finishes for all threads, ostress will report the time taken for all threads to finish execution.</span></span>  
  
### <a name="installing-ostress"></a><span data-ttu-id="02a6f-332">Instalar ostress</span><span class="sxs-lookup"><span data-stu-id="02a6f-332">Installing ostress</span></span>  
 <span data-ttu-id="02a6f-333">Ostress se instala como parte de las utilidades de RML; no hay ninguna instalación independiente para ostress.</span><span class="sxs-lookup"><span data-stu-id="02a6f-333">Ostress is installed as part of the RML Utilities; there is no standalone installation for ostress.</span></span>  
  
 <span data-ttu-id="02a6f-334">Pasos para la instalación:</span><span class="sxs-lookup"><span data-stu-id="02a6f-334">Installation steps:</span></span>  
  
1.  <span data-ttu-id="02a6f-335">Descargue y ejecute el paquete de instalación x64 para las utilidades de RML desde la página siguiente:[https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx](https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx)</span><span class="sxs-lookup"><span data-stu-id="02a6f-335">Download and run the x64 installation package for the RML utilities from the following page: [https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx](https://blogs.msdn.com/b/psssql/archive/2013/10/29/cumulative-update-2-to-the-rml-utilities-for-microsoft-sql-server-released.aspx)</span></span>  
  
2.  <span data-ttu-id="02a6f-336">Si aparece un cuadro de diálogo que indica que algunos archivos están en uso, haga clic en "Continue" (Continuar).</span><span class="sxs-lookup"><span data-stu-id="02a6f-336">If there is a dialog box saying certain files are in use, click 'Continue'</span></span>  
  
### <a name="running-ostress"></a><span data-ttu-id="02a6f-337">Ejecutar ostress</span><span class="sxs-lookup"><span data-stu-id="02a6f-337">Running ostress</span></span>  
 <span data-ttu-id="02a6f-338">Ostress se ejecuta desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="02a6f-338">Ostress is run from the command-line prompt.</span></span> <span data-ttu-id="02a6f-339">Es mejor ejecutar la herramienta desde "RML Cmd Prompt”, que se instala como parte de las utilidades de RML.</span><span class="sxs-lookup"><span data-stu-id="02a6f-339">It is most convenient to run the tool from the "RML Cmd Prompt", which is installed as part of the RML Utilities.</span></span>  
  
 <span data-ttu-id="02a6f-340">Para abrir RML Cmd Prompt, siga estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="02a6f-340">To open the RML Cmd Prompt follow these instructions:</span></span>  
  
 <span data-ttu-id="02a6f-341">En Windows Server 2012 [R2] y en Windows 8 y 8.1, haga clic en la tecla Windows para abrir el menú Inicio y escriba "rml".</span><span class="sxs-lookup"><span data-stu-id="02a6f-341">In Windows Server 2012 [R2] and in Windows 8 and 8.1, open the start menu by clicking the Windows key, and type 'rml'.</span></span> <span data-ttu-id="02a6f-342">Haga clic en "RML Cmd Prompt", que aparecerá en la lista de resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="02a6f-342">Click on "RML Cmd Prompt", which will be in the list of search results.</span></span>  
  
 <span data-ttu-id="02a6f-343">Asegúrese de que el símbolo del sistema se encuentra en la carpeta de instalación de las utilidades de RML.</span><span class="sxs-lookup"><span data-stu-id="02a6f-343">Ensure that the command prompt is located in the RML Utilities installation folder.</span></span> <span data-ttu-id="02a6f-344">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02a6f-344">For example:</span></span>  
  
 ![](../../2014/database-engine/media/SQLServer2014RTMIn-MemoryOLTP01.jpg)  
  
 <span data-ttu-id="02a6f-345">Las opciones de línea de comandos para ostress se pueden ver si se ejecuta ostress.exe sin ninguna opción de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-345">The command-line options for ostress can be seen when simply running ostress.exe without any command-line options.</span></span> <span data-ttu-id="02a6f-346">Las opciones principales que hay que tener en cuenta para ejecutar ostress con este ejemplo son:</span><span class="sxs-lookup"><span data-stu-id="02a6f-346">The main options to consider for running ostress with this sample are:</span></span>  
  
-   <span data-ttu-id="02a6f-347">-S nombre de la instancia de [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] con la que se va a conectar</span><span class="sxs-lookup"><span data-stu-id="02a6f-347">-S name of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to connect to</span></span>  
  
-   <span data-ttu-id="02a6f-348">-E usar autenticación de Windows para conectarse (valor predeterminado); Si usa [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] la autenticación de, use las opciones-usted y-P para especificar el nombre de usuario y la contraseña, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="02a6f-348">-E use Windows authentication to connect (default); if you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authentication, use the options -U and -P to specify the username and password, respectively</span></span>  
  
-   <span data-ttu-id="02a6f-349">-d nombre de la base de datos; para este ejemplo, AdventureWorks2014</span><span class="sxs-lookup"><span data-stu-id="02a6f-349">-d name of the database, for this example AdventureWorks2014</span></span>  
  
-   <span data-ttu-id="02a6f-350">-Q instrucción T-SQL que se va a ejecutar</span><span class="sxs-lookup"><span data-stu-id="02a6f-350">-Q the T-SQL statement to be executed</span></span>  
  
-   <span data-ttu-id="02a6f-351">-n número de conexiones que procesan cada archivo de entrada o consulta</span><span class="sxs-lookup"><span data-stu-id="02a6f-351">-n number of connections processing each input file/query</span></span>  
  
-   <span data-ttu-id="02a6f-352">-r número de iteraciones para que cada conexión ejecute cada archivo de entrada o consulta</span><span class="sxs-lookup"><span data-stu-id="02a6f-352">-r the number of iterations for each connection to execute each input file/query</span></span>  
  
### <a name="demo-workload"></a><span data-ttu-id="02a6f-353">Carga de trabajo de demostración</span><span class="sxs-lookup"><span data-stu-id="02a6f-353">Demo Workload</span></span>  
 <span data-ttu-id="02a6f-354">El procedimiento almacenado principal que se usa en la carga de trabajo de demostración es Sales.usp_InsertSalesOrder_inmem/ondisk.</span><span class="sxs-lookup"><span data-stu-id="02a6f-354">The main stored procedure used in the demo workload is Sales.usp_InsertSalesOrder_inmem/ondisk.</span></span> <span data-ttu-id="02a6f-355">El script siguiente crea un parámetro con valores de tabla (TVP) con datos de ejemplo y llama al procedimiento para insertar un pedido de venta con 5 artículos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-355">The script in the below constructs a table-valued parameter (TVP) with sample data, and calls the procedure to insert a sales order with 5 line items.</span></span>  
  
 <span data-ttu-id="02a6f-356">La herramienta ostress se emplea para ejecutar las llamadas a procedimientos almacenados en paralelo, con el fin de simular que los clientes insertan los pedidos de venta simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="02a6f-356">The ostress tool is used to execute the stored procedure calls in parallel, to simulate clients inserting sales orders concurrently.</span></span>  
  
 <span data-ttu-id="02a6f-357">Restablezca la demostración después de cada prueba de esfuerzo ejecutando Demo.usp_DemoReset.</span><span class="sxs-lookup"><span data-stu-id="02a6f-357">Reset the demo after each stress run executing Demo.usp_DemoReset.</span></span> <span data-ttu-id="02a6f-358">Este procedimiento elimina las filas de las tablas optimizadas para memoria, trunca las tablas basadas en disco y ejecuta un punto de comprobación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-358">This procedure deletes the rows in the memory-optimized tables, truncates the disk-based tables, and executes a database checkpoint.</span></span>  
  
 <span data-ttu-id="02a6f-359">El script siguiente se ejecuta simultáneamente para simular una carga de trabajo de procesamiento de pedidos de venta:</span><span class="sxs-lookup"><span data-stu-id="02a6f-359">The following script is executed concurrently to simulate a sales order processing workload:</span></span>  
  
```  
DECLARE   
      @i int = 0,   
      @od Sales.SalesOrderDetailType_inmem,   
      @SalesOrderID int,   
      @DueDate datetime2 = sysdatetime(),   
      @CustomerID int = rand() * 8000,   
      @BillToAddressID int = rand() * 10000,   
      @ShipToAddressID int = rand() * 10000,   
      @ShipMethodID int = (rand() * 5) + 1;   
  
INSERT INTO @od   
SELECT OrderQty, ProductID, SpecialOfferID   
FROM Demo.DemoSalesOrderDetailSeed   
WHERE OrderID= cast((rand()*106) + 1 as int);   
  
WHILE (@i < 20)   
BEGIN;   
      EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od;   
      SET @i += 1   
END  
  
```  
  
 <span data-ttu-id="02a6f-360">Con este script, cada pedido de ejemplo que se crea se inserta 20 veces, mediante 20 procedimientos almacenados que se ejecutan en un bucle WHILE.</span><span class="sxs-lookup"><span data-stu-id="02a6f-360">With this script, each sample order that is constructed is inserted 20 times, through 20 stored procedures executed in a WHILE loop.</span></span> <span data-ttu-id="02a6f-361">El bucle se usa para tener en cuenta el hecho de que la base de datos se emplea para crear el pedido de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="02a6f-361">The loop is used to account for the fact that the database is used to construct the sample order.</span></span> <span data-ttu-id="02a6f-362">En los entornos de producción típicos, la aplicación de nivel intermedio creará el pedido de venta que se va a insertar.</span><span class="sxs-lookup"><span data-stu-id="02a6f-362">In typical production environments, the mid-tier application will construct the sales order to be inserted.</span></span>  
  
 <span data-ttu-id="02a6f-363">El script anterior inserta los pedidos de venta en tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="02a6f-363">The above script inserts sales orders into memory-optimized tables.</span></span> <span data-ttu-id="02a6f-364">El script para insertar pedidos de venta en tablas basadas en disco se deriva reemplazando las dos instancias de "_inmem" por "_ondisk".</span><span class="sxs-lookup"><span data-stu-id="02a6f-364">The script to insert sales orders into disk-based tables is derived by replacing the two occurrences of '_inmem' with '_ondisk'.</span></span>  
  
 <span data-ttu-id="02a6f-365">Se usará la herramienta ostress para ejecutar los scripts con varias conexiones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="02a6f-365">We will use the ostress tool to execute the scripts using several concurrent connections.</span></span> <span data-ttu-id="02a6f-366">Se usará el parámetro "-n" para controlar el número de conexiones y el parámetro "r" para controlar cuántas veces se ejecuta el script en cada conexión.</span><span class="sxs-lookup"><span data-stu-id="02a6f-366">We will use the parameter '-n' to control the number of connections, and the parameter 'r' to control how many times the script is executed on each connection.</span></span>  
  
#### <a name="functional-validation-of-the-workload"></a><span data-ttu-id="02a6f-367">Validación funcional de la carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="02a6f-367">Functional Validation of the Workload</span></span>  
 <span data-ttu-id="02a6f-368">Para comprobar que todo funciona, comenzaremos con una prueba de ejemplo, con 10 conexiones simultáneas y 5 iteraciones, insertando un total de 10 \* 5 \* 20 = 1000 pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="02a6f-368">To verify everything works, we will start with a sample test, using 10 concurrent connects and 5 iterations, inserting a total of 10 \* 5 \* 20 = 1000 sales order.</span></span>  
  
 <span data-ttu-id="02a6f-369">Con el comando siguiente suponemos que se usa la instancia predeterminada en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="02a6f-369">With the below command we assume using the default instance on the local machine.</span></span> <span data-ttu-id="02a6f-370">Si va a usar una instancia con nombre o un servidor remoto, cambie el nombre del servidor en consecuencia con el parámetro -S.</span><span class="sxs-lookup"><span data-stu-id="02a6f-370">If you are using a named instance or using a remote server, change the server name accordingly, using the parameter -S.</span></span>  
  
 <span data-ttu-id="02a6f-371">Para insertar 1000 pedidos de venta en tablas optimizadas para memoria, use el comando siguiente en RML Cmd Prompt:</span><span class="sxs-lookup"><span data-stu-id="02a6f-371">Insert 1000 sales orders in memory-optimized tables use the following command in the RML Cmd Prompt:</span></span>  
  
 <span data-ttu-id="02a6f-372">Haga clic en el botón Copy para copiar el comando y péguelo en el símbolo del sistema de las utilidades de RML.</span><span class="sxs-lookup"><span data-stu-id="02a6f-372">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n10 -r5 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_inmem, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="02a6f-373">Si todo funciona como se espera, la ventana de comandos será similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="02a6f-373">If everything works as expected, your command window will look similar to the following.</span></span> <span data-ttu-id="02a6f-374">No se esperan mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="02a6f-374">Error messages are not expected.</span></span>  
  
 ![](../../2014/database-engine/media/SQLServer2014RTMIn-MemoryOLTP02.jpg)  
  
 <span data-ttu-id="02a6f-375">Para validar que la carga de trabajo también funciona como se espera en las tablas basadas en disco, ejecute el comando siguiente en RML Cmd Prompt:</span><span class="sxs-lookup"><span data-stu-id="02a6f-375">Validate that also the workload functions as expected for disk-based tables by running the following command in the RML Cmd Prompt:</span></span>  
  
 <span data-ttu-id="02a6f-376">Haga clic en el botón Copy para copiar el comando y péguelo en el símbolo del sistema de las utilidades de RML.</span><span class="sxs-lookup"><span data-stu-id="02a6f-376">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n10 -r5 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_ondisk, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_ondisk @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
#### <a name="running-the-workload"></a><span data-ttu-id="02a6f-377">Ejecutar la carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="02a6f-377">Running the Workload</span></span>  
 <span data-ttu-id="02a6f-378">Para probar la escala insertamos 10 millones de pedidos de venta usando 100 conexiones.</span><span class="sxs-lookup"><span data-stu-id="02a6f-378">To test at scale we insert 10 million sales orders, using 100 connections.</span></span> <span data-ttu-id="02a6f-379">Esta prueba funciona razonablemente bien en un servidor modesto (por ejemplo, 8 núcleos físicos y 16 lógicos) y con un almacenamiento SSD básico para el registro.</span><span class="sxs-lookup"><span data-stu-id="02a6f-379">This test performs reasonably on a modest server (e.g., 8 physical, 16 logical cores), and basic SSD storage for the log.</span></span> <span data-ttu-id="02a6f-380">Si la prueba no funciona correctamente en el hardware, vea la sección [Solucionar problemas de pruebas de ejecución lenta](#Troubleshootingslow-runningtests). Si quiere reducir el nivel de esfuerzo de esta prueba, disminuya el número de conexiones cambiando el parámetro "-n".</span><span class="sxs-lookup"><span data-stu-id="02a6f-380">If the test does not perform well on your hardware, take look at the Section [Troubleshooting slow-running tests](#Troubleshootingslow-runningtests).If you want to reduce the level of stress for this test, lower the number of connections by changing the parameter '-n'.</span></span> <span data-ttu-id="02a6f-381">Por ejemplo, para reducir el número de conexiones a 40, cambie el parámetro "-n100" a "-n40".</span><span class="sxs-lookup"><span data-stu-id="02a6f-381">For example to lower the connection count to 40, change the parameter '-n100' to '-n40'.</span></span>  
  
 <span data-ttu-id="02a6f-382">Como medida de rendimiento de la carga de trabajo usamos el tiempo transcurrido notificado por ostress.exe después de ejecutar la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="02a6f-382">As a performance measure for the workload we use the elapsed time as reported by ostress.exe after running the workload.</span></span>  
  
##### <a name="memory-optimized-tables"></a><span data-ttu-id="02a6f-383">Tablas optimizadas para memoria</span><span class="sxs-lookup"><span data-stu-id="02a6f-383">Memory-optimized tables</span></span>  
 <span data-ttu-id="02a6f-384">Empezaremos ejecutando la carga de trabajo en las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="02a6f-384">We will start by running the workload on memory-optimized tables.</span></span> <span data-ttu-id="02a6f-385">El comando siguiente abre 100 subprocesos, cada uno de los cuales se ejecuta para 5.000 iteraciones.</span><span class="sxs-lookup"><span data-stu-id="02a6f-385">The following command opens 100 threads, each running for 5,000 iterations.</span></span>  <span data-ttu-id="02a6f-386">Cada iteración inserta 20 pedidos de venta en transacciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="02a6f-386">Each iteration inserts 20 sales orders in separate transactions.</span></span> <span data-ttu-id="02a6f-387">Hay 20 inserciones por iteración para compensar el hecho de que la base de datos se usa para generar los datos que se van a insertar.</span><span class="sxs-lookup"><span data-stu-id="02a6f-387">There are 20 inserts per iteration to compensate for the fact that the database is used to generate the data to be inserted.</span></span> <span data-ttu-id="02a6f-388">Esto produce un total de 20 \* 5000 \* 100 = 10 000 000 inserciones de pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="02a6f-388">This yield a total of 20 \* 5,000 \* 100 = 10,000,000 sales order inserts.</span></span>  
  
 <span data-ttu-id="02a6f-389">Abra RML Cmd Prompt y ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="02a6f-389">Open the RML Cmd Prompt, and execute the following command:</span></span>  
  
 <span data-ttu-id="02a6f-390">Haga clic en el botón Copy para copiar el comando y péguelo en el símbolo del sistema de las utilidades de RML.</span><span class="sxs-lookup"><span data-stu-id="02a6f-390">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n100 -r5000 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_inmem, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_inmem @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="02a6f-391">En un servidor de prueba con un número total de 8 núcleos físicos (16 lógicos), se tardaron 2 minutos y 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-391">On one test server with a total number of 8 physical (16 logical) cores, this took 2 minutes and 5 seconds.</span></span> <span data-ttu-id="02a6f-392">En un segundo servidor de prueba con 24 núcleos físicos (48 lógicos), se tardó 1 minuto y 0 segundos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-392">On a second test server with 24 physical (48 logical) cores, this took 1 minute and 0 seconds.</span></span>  
  
 <span data-ttu-id="02a6f-393">Observe el uso de la CPU mientras se está ejecutando la carga de trabajo, por ejemplo con el Administrador de tareas.</span><span class="sxs-lookup"><span data-stu-id="02a6f-393">Observe the CPU utilization while the workload is running, for example using task manager.</span></span> <span data-ttu-id="02a6f-394">Verá que el uso de la CPU está cercano al 100 %.</span><span class="sxs-lookup"><span data-stu-id="02a6f-394">You will see that CPU utilization is close to 100%.</span></span> <span data-ttu-id="02a6f-395">De lo contrario, tiene un cuello de botella en la E/S de registro; vea también [Solucionar problemas de pruebas de ejecución lenta](#Troubleshootingslow-runningtests).</span><span class="sxs-lookup"><span data-stu-id="02a6f-395">If this is not the case, you have a log IO bottleneck see also [Troubleshooting slow-running tests](#Troubleshootingslow-runningtests).</span></span>  
  
##### <a name="disk-based-tables"></a><span data-ttu-id="02a6f-396">Tablas basadas en disco</span><span class="sxs-lookup"><span data-stu-id="02a6f-396">Disk-based tables</span></span>  
 <span data-ttu-id="02a6f-397">El comando siguiente ejecutará la carga de trabajo en tablas basadas en disco.</span><span class="sxs-lookup"><span data-stu-id="02a6f-397">The following command will run the workload on disk-based tables.</span></span> <span data-ttu-id="02a6f-398">Tenga en cuenta que esta carga de trabajo puede tardar bastante tiempo en ejecutarse, lo que se debe en gran medida a la contención de bloqueos temporales del sistema.</span><span class="sxs-lookup"><span data-stu-id="02a6f-398">Note that this workload may take a while to execute, which is largely due to latch contention in the system.</span></span> <span data-ttu-id="02a6f-399">Las tablas con optimización para memoria no tienen bloqueos temporales y por tanto no experimentan este problema.</span><span class="sxs-lookup"><span data-stu-id="02a6f-399">Memory-optimized table are latch-free and thus do not suffer from this problem.</span></span>  
  
 <span data-ttu-id="02a6f-400">Abra RML Cmd Prompt y ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="02a6f-400">Open the RML Cmd Prompt, and execute the following command:</span></span>  
  
 <span data-ttu-id="02a6f-401">Haga clic en el botón Copy para copiar el comando y péguelo en el símbolo del sistema de las utilidades de RML.</span><span class="sxs-lookup"><span data-stu-id="02a6f-401">Click the Copy button to copy the command, and paste it into the RML Utilities command prompt.</span></span>  
  
```  
ostress.exe -n100 -r5000 -S. -E -dAdventureWorks2014 -q -Q"DECLARE @i int = 0, @od Sales.SalesOrderDetailType_ondisk, @SalesOrderID int, @DueDate datetime2 = sysdatetime(), @CustomerID int = rand() * 8000, @BillToAddressID int = rand() * 10000, @ShipToAddressID int = rand() * 10000, @ShipMethodID int = (rand() * 5) + 1; INSERT INTO @od SELECT OrderQty, ProductID, SpecialOfferID FROM Demo.DemoSalesOrderDetailSeed WHERE OrderID= cast((rand()*106) + 1 as int); while (@i < 20) begin; EXEC Sales.usp_InsertSalesOrder_ondisk @SalesOrderID OUTPUT, @DueDate, @CustomerID, @BillToAddressID, @ShipToAddressID, @ShipMethodID, @od; set @i += 1 end"  
```  
  
 <span data-ttu-id="02a6f-402">En un servidor de prueba con un número total de 8 núcleos físicos (16 lógicos), se tardaron 41 minutos y 25 segundos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-402">On one test server with a total number of 8 physical (16 logical) cores, this took 41 minutes and 25 seconds.</span></span> <span data-ttu-id="02a6f-403">En un segundo servidor de prueba con 24 núcleos físicos (48 lógicos), se tardaron 52 minutos y 16 segundos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-403">On a second test server with 24 physical (48 logical) cores, this took 52 minutes and 16 seconds.</span></span>  
  
 <span data-ttu-id="02a6f-404">La causa principal de la diferencia de rendimiento entre las tablas optimizadas para memoria y las tablas basadas en disco en esta prueba es el hecho de que cuando se usan tablas basadas en disco, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no puede utilizar totalmente la CPU.</span><span class="sxs-lookup"><span data-stu-id="02a6f-404">The main factor in the performance difference between memory-optimized tables and disk-based tables in this test is the fact that when using disk-based tables, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot not fully utilize the CPU.</span></span> <span data-ttu-id="02a6f-405">El motivo es la contención de bloqueos temporales: las transacciones simultáneas intentan escribir en la misma página de datos; los bloqueos temporales se usan para asegurarse de que solo una transacción puede escribir en una página a la vez.</span><span class="sxs-lookup"><span data-stu-id="02a6f-405">The reason is latch contention: concurrent transactions are attempting to write to the same data page; latches are used to ensure only one transaction at a time can write to a page.</span></span> <span data-ttu-id="02a6f-406">El motor de [!INCLUDE[hek_2](../includes/hek-2-md.md)] no tiene bloqueos temporales y las filas de datos no se organizan en páginas.</span><span class="sxs-lookup"><span data-stu-id="02a6f-406">The [!INCLUDE[hek_2](../includes/hek-2-md.md)] engine is latch-free, and data rows are not organized in pages.</span></span> <span data-ttu-id="02a6f-407">Por lo tanto, las transacciones simultáneas no bloquean las inserciones de las demás, lo [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que permite que se use totalmente la CPU.</span><span class="sxs-lookup"><span data-stu-id="02a6f-407">Thus, concurrent transactions do not block each other's inserts, thus enabling [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to fully utilize the CPU.</span></span>  
  
 <span data-ttu-id="02a6f-408">Puede observar el uso de la CPU mientras se está ejecutando la carga de trabajo, por ejemplo con el Administrador de tareas.</span><span class="sxs-lookup"><span data-stu-id="02a6f-408">You can observe the CPU utilization while the workload is running, for example using task manager.</span></span> <span data-ttu-id="02a6f-409">Con las tablas basadas en disco verá que el uso de la CPU está muy alejado del 100 %.</span><span class="sxs-lookup"><span data-stu-id="02a6f-409">You will see with disk-based tables the CPU utilization is far from 100%.</span></span> <span data-ttu-id="02a6f-410">En una configuración de prueba con 16 procesadores lógicos, el uso rondaría el 24 %.</span><span class="sxs-lookup"><span data-stu-id="02a6f-410">On a test configuration with 16 logical processors, the utilization would hover around 24%.</span></span>  
  
 <span data-ttu-id="02a6f-411">Opcionalmente, puede ver el número de esperas de bloqueos temporales por segundo mediante el Monitor de rendimiento, con el contador de rendimiento "\SQL Server:Bloqueos temporales\Esperas de bloqueos temporales/s".</span><span class="sxs-lookup"><span data-stu-id="02a6f-411">Optionally, you can view the number of latch waits per second using Performance Monitor, with the performance counter '\SQL Server:Latches\Latch Waits/sec'.</span></span>  
  
#### <a name="resetting-the-demo"></a><span data-ttu-id="02a6f-412">Restablecer la demostración</span><span class="sxs-lookup"><span data-stu-id="02a6f-412">Resetting the demo</span></span>  
 <span data-ttu-id="02a6f-413">Para restablecer la demostración, abra RML Cmd Prompt y ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="02a6f-413">To reset the demo, open the RML Cmd Prompt, and execute the following command:</span></span>  
  
```  
ostress.exe -S. -E -dAdventureWorks2014 -Q"EXEC Demo.usp_DemoReset"  
```  
  
 <span data-ttu-id="02a6f-414">Según el hardware, puede tardar unos minutos en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="02a6f-414">Depending on the hardware this may take a few minutes to run.</span></span>  
  
 <span data-ttu-id="02a6f-415">Se recomienda restablecer la demostración tras cada ejecución.</span><span class="sxs-lookup"><span data-stu-id="02a6f-415">We recommend a reset after every demo run.</span></span> <span data-ttu-id="02a6f-416">Como esta carga de trabajo solo realiza inserciones, cada ejecución consume más memoria, por lo que es necesario un restablecimiento para no quedarse sin memoria.</span><span class="sxs-lookup"><span data-stu-id="02a6f-416">Because this workload is insert-only, each run will consume more memory, and thus a reset is required to prevent running out of memory.</span></span> <span data-ttu-id="02a6f-417">La cantidad de memoria consumida después de una ejecución se explica en la sección [Utilización de memoria después de ejecutar la carga de trabajo](#Memoryutilizationafterrunningtheworkload).</span><span class="sxs-lookup"><span data-stu-id="02a6f-417">The amount of memory consumed after a run is discussed in Section [Memory utilization after running the workload](#Memoryutilizationafterrunningtheworkload).</span></span>  
  
###  <a name="troubleshooting-slow-running-tests"></a><a name="Troubleshootingslow-runningtests"></a> <span data-ttu-id="02a6f-418">Solucionar problemas de pruebas de ejecución lenta</span><span class="sxs-lookup"><span data-stu-id="02a6f-418">Troubleshooting slow-running tests</span></span>  
 <span data-ttu-id="02a6f-419">Los resultados de prueba variarán normalmente según el hardware, y también el nivel de simultaneidad empleado en la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="02a6f-419">Test results will typically vary with hardware, and also the level of concurrency used in the test run.</span></span> <span data-ttu-id="02a6f-420">He aquí varios aspectos que hay que examinar si los resultados no son los esperados:</span><span class="sxs-lookup"><span data-stu-id="02a6f-420">A couple of things to look for if the results are not as expected:</span></span>  
  
-   <span data-ttu-id="02a6f-421">Número de transacciones simultáneas: cuando se ejecuta la carga de trabajo en un solo subproceso, el aumento del rendimiento con [!INCLUDE[hek_2](../includes/hek-2-md.md)] probablemente será menor del doble.</span><span class="sxs-lookup"><span data-stu-id="02a6f-421">Number of concurrent transactions: When running the workload on a single thread, performance gain with [!INCLUDE[hek_2](../includes/hek-2-md.md)] will likely be less than 2X.</span></span> <span data-ttu-id="02a6f-422">La contención de bloqueos temporales solo supone un gran problema si hay un nivel elevado de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="02a6f-422">Latch contention is only a big problem if there is a high level of concurrency.</span></span>  
  
-   <span data-ttu-id="02a6f-423">Pocos núcleos disponibles para [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]: esto significa que habrá un bajo nivel de simultaneidad en el sistema, ya que solo puede haber tantas transacciones que se ejecutan simultáneamente como núcleos disponibles haya en SQL.</span><span class="sxs-lookup"><span data-stu-id="02a6f-423">Low number of cores available to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]: This means there will be a low level of concurrency in the system, as there can only be as many concurrently executing transactions as there are cores available to SQL.</span></span>  
  
    -   <span data-ttu-id="02a6f-424">Síntoma: si la utilización de la CPU es alta cuando se ejecuta la carga de trabajo en tablas basadas en disco, significa que no hay mucha contención, lo que apunta a una falta de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="02a6f-424">Symptom: if the CPU utilization is high when running the workload on disk-based tables, this means there is not a lot of contention, pointing to a lack of concurrency.</span></span>  
  
-   <span data-ttu-id="02a6f-425">Velocidad de la unidad de registro: si la unidad de registro no puede seguir el nivel de rendimiento de transacciones del sistema, la carga de trabajo se convierte en un cuello de botella para la E/S de registro.</span><span class="sxs-lookup"><span data-stu-id="02a6f-425">Speed of the log drive: If the log drive cannot keep up with the level of transaction throughput in the system, the workload becomes bottlenecked on log IO.</span></span> <span data-ttu-id="02a6f-426">Aunque el registro es más eficaz con [!INCLUDE[hek_2](../includes/hek-2-md.md)], si la E/S de registro es un cuello de botella, se limita el aumento potencial de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="02a6f-426">Although logging is more efficient with [!INCLUDE[hek_2](../includes/hek-2-md.md)], if log IO is a bottleneck, the potential performance gain is limited.</span></span>  
  
    -   <span data-ttu-id="02a6f-427">Síntoma: si la utilización de la CPU no está cercana al 100 % o tiene muchos picos cuando se ejecuta la carga de trabajo en tablas optimizadas para memoria, es posible que haya un cuello de botella de la E/S de registro.</span><span class="sxs-lookup"><span data-stu-id="02a6f-427">Symptom: if the CPU utilization is not close to 100% or is very spiky when running the workload on memory-optimized tables, it is possible there is a log IO bottleneck.</span></span> <span data-ttu-id="02a6f-428">Esto se puede confirmar abriendo el Monitor de recursos y examinando la longitud de la cola de la unidad de registro.</span><span class="sxs-lookup"><span data-stu-id="02a6f-428">This can be confirmed by opening Resource Monitor and looking at the queue length for the log drive.</span></span>  
  
##  <a name="memory-and-disk-space-utilization-in-the-sample"></a><a name="MemoryandDiskSpaceUtilizationintheSample"></a> <span data-ttu-id="02a6f-429">Uso de memoria y de espacio en disco del ejemplo</span><span class="sxs-lookup"><span data-stu-id="02a6f-429">Memory and Disk Space Utilization in the Sample</span></span>  
 <span data-ttu-id="02a6f-430">A continuación se describe qué cabe esperar en cuando a uso de la memoria y del espacio en disco para la base de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="02a6f-430">In the below we describe what to expect in terms of memory and disk space utilization for the sample database.</span></span> <span data-ttu-id="02a6f-431">También se muestran los resultados obtenidos en un servidor de prueba con 16 núcleos lógicos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-431">We also show the results we have seen in on a test server with 16 logical cores.</span></span>  
  
###  <a name="memory-utilization-for-the-memory-optimized-tables"></a><a name="Memoryutilizationforthememory-optimizedtables"></a> <span data-ttu-id="02a6f-432">Uso de memoria para las tablas optimizadas para memoria</span><span class="sxs-lookup"><span data-stu-id="02a6f-432">Memory utilization for the memory-optimized tables</span></span>  
  
#### <a name="overall-utilization-of-the-database"></a><span data-ttu-id="02a6f-433">Utilización global de la base de datos</span><span class="sxs-lookup"><span data-stu-id="02a6f-433">Overall utilization of the database</span></span>  
 <span data-ttu-id="02a6f-434">Se puede usar la consulta siguiente para obtener la utilización de memoria total para [!INCLUDE[hek_2](../includes/hek-2-md.md)] en el sistema.</span><span class="sxs-lookup"><span data-stu-id="02a6f-434">The following query can be used to obtain the total memory utilization for [!INCLUDE[hek_2](../includes/hek-2-md.md)] in the system.</span></span>  
  
```  
SELECT type  
   , name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
 <span data-ttu-id="02a6f-435">Instantánea justo después de crearse la base de datos:</span><span class="sxs-lookup"><span data-stu-id="02a6f-435">Snapshot after the database has just been created:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="02a6f-436">**type**</span><span class="sxs-lookup"><span data-stu-id="02a6f-436">**type**</span></span>|<span data-ttu-id="02a6f-437">**name**</span><span class="sxs-lookup"><span data-stu-id="02a6f-437">**name**</span></span>|<span data-ttu-id="02a6f-438">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="02a6f-438">**pages_MB**</span></span>|  
|<span data-ttu-id="02a6f-439">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-439">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-440">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="02a6f-440">Default</span></span>|<span data-ttu-id="02a6f-441">94</span><span class="sxs-lookup"><span data-stu-id="02a6f-441">94</span></span>|  
|<span data-ttu-id="02a6f-442">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-442">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-443">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="02a6f-443">DB_ID_5</span></span>|<span data-ttu-id="02a6f-444">877</span><span class="sxs-lookup"><span data-stu-id="02a6f-444">877</span></span>|  
|<span data-ttu-id="02a6f-445">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-445">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-446">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="02a6f-446">Default</span></span>|<span data-ttu-id="02a6f-447">0</span><span class="sxs-lookup"><span data-stu-id="02a6f-447">0</span></span>|  
|<span data-ttu-id="02a6f-448">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-448">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-449">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="02a6f-449">Default</span></span>|<span data-ttu-id="02a6f-450">0</span><span class="sxs-lookup"><span data-stu-id="02a6f-450">0</span></span>|  
  
 <span data-ttu-id="02a6f-451">Los distribuidores de memoria predeterminados contienen estructuras de memoria de todo el sistema y son relativamente pequeños.</span><span class="sxs-lookup"><span data-stu-id="02a6f-451">The default memory clerks contain system-wide memory structures and are relatively small.</span></span> <span data-ttu-id="02a6f-452">El distribuidor de memoria para la base de datos de usuario, en este caso la base de datos con el identificador 5, tiene unos 900 MB.</span><span class="sxs-lookup"><span data-stu-id="02a6f-452">The memory clerk for the user database, in this case database with ID 5, is about 900MB.</span></span>  
  
#### <a name="memory-utilization-per-table"></a><span data-ttu-id="02a6f-453">Utilización de memoria por tabla</span><span class="sxs-lookup"><span data-stu-id="02a6f-453">Memory utilization per table</span></span>  
 <span data-ttu-id="02a6f-454">Se puede usar la consulta siguiente para explorar en profundidad la utilización de memoria de las tablas individuales y sus índices:</span><span class="sxs-lookup"><span data-stu-id="02a6f-454">The following query can be used to drill down into the memory utilization of the individual tables and their indexes:</span></span>  
  
```  
SELECT object_name(t.object_id) AS [Table Name]  
     , memory_allocated_for_table_kb  
 , memory_allocated_for_indexes_kb  
FROM sys.dm_db_xtp_table_memory_stats dms JOIN sys.tables t   
ON dms.object_id=t.object_id  
WHERE t.type='U'  
```  
  
 <span data-ttu-id="02a6f-455">A continuación se muestran los resultados de esta consulta para una instalación nueva del ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02a6f-455">The following shows the results of this query for a fresh installation of the sample:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="02a6f-456">**Nombre de tabla**</span><span class="sxs-lookup"><span data-stu-id="02a6f-456">**Table Name**</span></span>|<span data-ttu-id="02a6f-457">**memory_allocated_for_table_kb**</span><span class="sxs-lookup"><span data-stu-id="02a6f-457">**memory_allocated_for_table_kb**</span></span>|<span data-ttu-id="02a6f-458">**memory_allocated_for_indexes_kb**</span><span class="sxs-lookup"><span data-stu-id="02a6f-458">**memory_allocated_for_indexes_kb**</span></span>|  
|<span data-ttu-id="02a6f-459">SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-459">SpecialOfferProduct_inmem</span></span>|<span data-ttu-id="02a6f-460">64</span><span class="sxs-lookup"><span data-stu-id="02a6f-460">64</span></span>|<span data-ttu-id="02a6f-461">3840</span><span class="sxs-lookup"><span data-stu-id="02a6f-461">3840</span></span>|  
|<span data-ttu-id="02a6f-462">DemoSalesOrderHeaderSeed</span><span class="sxs-lookup"><span data-stu-id="02a6f-462">DemoSalesOrderHeaderSeed</span></span>|<span data-ttu-id="02a6f-463">1984</span><span class="sxs-lookup"><span data-stu-id="02a6f-463">1984</span></span>|<span data-ttu-id="02a6f-464">5504</span><span class="sxs-lookup"><span data-stu-id="02a6f-464">5504</span></span>|  
|<span data-ttu-id="02a6f-465">SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-465">SalesOrderDetail_inmem</span></span>|<span data-ttu-id="02a6f-466">15316</span><span class="sxs-lookup"><span data-stu-id="02a6f-466">15316</span></span>|<span data-ttu-id="02a6f-467">663552</span><span class="sxs-lookup"><span data-stu-id="02a6f-467">663552</span></span>|  
|<span data-ttu-id="02a6f-468">DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="02a6f-468">DemoSalesOrderDetailSeed</span></span>|<span data-ttu-id="02a6f-469">64</span><span class="sxs-lookup"><span data-stu-id="02a6f-469">64</span></span>|<span data-ttu-id="02a6f-470">10432</span><span class="sxs-lookup"><span data-stu-id="02a6f-470">10432</span></span>|  
|<span data-ttu-id="02a6f-471">SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-471">SpecialOffer_inmem</span></span>|<span data-ttu-id="02a6f-472">3</span><span class="sxs-lookup"><span data-stu-id="02a6f-472">3</span></span>|<span data-ttu-id="02a6f-473">8192</span><span class="sxs-lookup"><span data-stu-id="02a6f-473">8192</span></span>|  
|<span data-ttu-id="02a6f-474">SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-474">SalesOrderHeader_inmem</span></span>|<span data-ttu-id="02a6f-475">7168</span><span class="sxs-lookup"><span data-stu-id="02a6f-475">7168</span></span>|<span data-ttu-id="02a6f-476">147456</span><span class="sxs-lookup"><span data-stu-id="02a6f-476">147456</span></span>|  
|<span data-ttu-id="02a6f-477">Product_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-477">Product_inmem</span></span>|<span data-ttu-id="02a6f-478">124</span><span class="sxs-lookup"><span data-stu-id="02a6f-478">124</span></span>|<span data-ttu-id="02a6f-479">12352</span><span class="sxs-lookup"><span data-stu-id="02a6f-479">12352</span></span>|  
  
 <span data-ttu-id="02a6f-480">Como puede ver, las tablas son bastante pequeñas: SalesOrderHeader_inmem tiene unos 7 MB y SalesOrderDetail_inmem unos 15 MB de tamaño.</span><span class="sxs-lookup"><span data-stu-id="02a6f-480">As you can see the tables are fairly small: SalesOrderHeader_inmem is about 7MB, and SalesOrderDetail_inmem is about 15MB in size.</span></span>  
  
 <span data-ttu-id="02a6f-481">Lo sorprendente aquí es el tamaño de la memoria asignada para los índices, en comparación con el tamaño de los datos de tabla.</span><span class="sxs-lookup"><span data-stu-id="02a6f-481">What is striking here is the size of the memory allocated for indexes, compared to the size of the table data.</span></span> <span data-ttu-id="02a6f-482">Esto se debe a que los índices hash del ejemplo tienen establecido previamente un tamaño de datos mayor.</span><span class="sxs-lookup"><span data-stu-id="02a6f-482">That is because the hash indexes in the sample are pre-sized for a larger data size.</span></span> <span data-ttu-id="02a6f-483">Observe que los índices hash tienen un tamaño fijo y por tanto su tamaño no crece junto con el tamaño de los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="02a6f-483">Note that hash indexes have a fixed size, and thus their size will not grow with the size of data in the table.</span></span>  
  
####  <a name="memory-utilization-after-running-the-workload"></a><a name="Memoryutilizationafterrunningtheworkload"></a> <span data-ttu-id="02a6f-484">Utilización de memoria después de ejecutar la carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="02a6f-484">Memory utilization after running the workload</span></span>  
 <span data-ttu-id="02a6f-485">Después de insertar 10 millones de pedidos de venta, la utilización total de memoria es similar a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="02a6f-485">After insert 10 million sales orders, the all-up memory utilization looks similar to the following:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="02a6f-486">**type**</span><span class="sxs-lookup"><span data-stu-id="02a6f-486">**type**</span></span>|<span data-ttu-id="02a6f-487">**name**</span><span class="sxs-lookup"><span data-stu-id="02a6f-487">**name**</span></span>|<span data-ttu-id="02a6f-488">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="02a6f-488">**pages_MB**</span></span>|  
|<span data-ttu-id="02a6f-489">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-489">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-490">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="02a6f-490">Default</span></span>|<span data-ttu-id="02a6f-491">146</span><span class="sxs-lookup"><span data-stu-id="02a6f-491">146</span></span>|  
|<span data-ttu-id="02a6f-492">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-492">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-493">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="02a6f-493">DB_ID_5</span></span>|<span data-ttu-id="02a6f-494">7374</span><span class="sxs-lookup"><span data-stu-id="02a6f-494">7374</span></span>|  
|<span data-ttu-id="02a6f-495">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-495">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-496">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="02a6f-496">Default</span></span>|<span data-ttu-id="02a6f-497">0</span><span class="sxs-lookup"><span data-stu-id="02a6f-497">0</span></span>|  
|<span data-ttu-id="02a6f-498">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-498">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-499">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="02a6f-499">Default</span></span>|<span data-ttu-id="02a6f-500">0</span><span class="sxs-lookup"><span data-stu-id="02a6f-500">0</span></span>|  
  
 <span data-ttu-id="02a6f-501">Como puede ver, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usa un bit por debajo de 8 GB para las tablas y los índices optimizados para memoria de la base de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="02a6f-501">As you can see, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is using a bit under 8GB for the memory-optimized tables and indexes in the sample database.</span></span>  
  
 <span data-ttu-id="02a6f-502">Examinando el uso detallado de memoria por tabla después de ejecutar un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02a6f-502">Looking at the detailed memory usage per table after one example run:</span></span>  
  
```  
SELECT object_name(t.object_id) AS [Table Name]  
     , memory_allocated_for_table_kb  
 , memory_allocated_for_indexes_kb  
FROM sys.dm_db_xtp_table_memory_stats dms JOIN sys.tables t   
ON dms.object_id=t.object_id  
WHERE t.type='U'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="02a6f-503">**Nombre de tabla**</span><span class="sxs-lookup"><span data-stu-id="02a6f-503">**Table Name**</span></span>|<span data-ttu-id="02a6f-504">**memory_allocated_for_table_kb**</span><span class="sxs-lookup"><span data-stu-id="02a6f-504">**memory_allocated_for_table_kb**</span></span>|<span data-ttu-id="02a6f-505">**memory_allocated_for_indexes_kb**</span><span class="sxs-lookup"><span data-stu-id="02a6f-505">**memory_allocated_for_indexes_kb**</span></span>|  
|<span data-ttu-id="02a6f-506">SalesOrderDetail_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-506">SalesOrderDetail_inmem</span></span>|<span data-ttu-id="02a6f-507">5113761</span><span class="sxs-lookup"><span data-stu-id="02a6f-507">5113761</span></span>|<span data-ttu-id="02a6f-508">663552</span><span class="sxs-lookup"><span data-stu-id="02a6f-508">663552</span></span>|  
|<span data-ttu-id="02a6f-509">DemoSalesOrderDetailSeed</span><span class="sxs-lookup"><span data-stu-id="02a6f-509">DemoSalesOrderDetailSeed</span></span>|<span data-ttu-id="02a6f-510">64</span><span class="sxs-lookup"><span data-stu-id="02a6f-510">64</span></span>|<span data-ttu-id="02a6f-511">10368</span><span class="sxs-lookup"><span data-stu-id="02a6f-511">10368</span></span>|  
|<span data-ttu-id="02a6f-512">SpecialOffer_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-512">SpecialOffer_inmem</span></span>|<span data-ttu-id="02a6f-513">2</span><span class="sxs-lookup"><span data-stu-id="02a6f-513">2</span></span>|<span data-ttu-id="02a6f-514">8192</span><span class="sxs-lookup"><span data-stu-id="02a6f-514">8192</span></span>|  
|<span data-ttu-id="02a6f-515">SalesOrderHeader_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-515">SalesOrderHeader_inmem</span></span>|<span data-ttu-id="02a6f-516">1575679</span><span class="sxs-lookup"><span data-stu-id="02a6f-516">1575679</span></span>|<span data-ttu-id="02a6f-517">147456</span><span class="sxs-lookup"><span data-stu-id="02a6f-517">147456</span></span>|  
|<span data-ttu-id="02a6f-518">Product_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-518">Product_inmem</span></span>|<span data-ttu-id="02a6f-519">111</span><span class="sxs-lookup"><span data-stu-id="02a6f-519">111</span></span>|<span data-ttu-id="02a6f-520">12032</span><span class="sxs-lookup"><span data-stu-id="02a6f-520">12032</span></span>|  
|<span data-ttu-id="02a6f-521">SpecialOfferProduct_inmem</span><span class="sxs-lookup"><span data-stu-id="02a6f-521">SpecialOfferProduct_inmem</span></span>|<span data-ttu-id="02a6f-522">64</span><span class="sxs-lookup"><span data-stu-id="02a6f-522">64</span></span>|<span data-ttu-id="02a6f-523">3712</span><span class="sxs-lookup"><span data-stu-id="02a6f-523">3712</span></span>|  
|<span data-ttu-id="02a6f-524">DemoSalesOrderHeaderSeed</span><span class="sxs-lookup"><span data-stu-id="02a6f-524">DemoSalesOrderHeaderSeed</span></span>|<span data-ttu-id="02a6f-525">1984</span><span class="sxs-lookup"><span data-stu-id="02a6f-525">1984</span></span>|<span data-ttu-id="02a6f-526">5504</span><span class="sxs-lookup"><span data-stu-id="02a6f-526">5504</span></span>|  
  
 <span data-ttu-id="02a6f-527">Podemos ver un total de unos 6,5 GB de datos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-527">We can see a total of about 6.5GB of data.</span></span> <span data-ttu-id="02a6f-528">Observe que el tamaño de los índices de la tabla SalesOrderHeader_inmem y SalesOrderDetail_inmem es el mismo que el tamaño de los índices antes de insertar los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="02a6f-528">Notice that the size of the indexes on the table SalesOrderHeader_inmem and SalesOrderDetail_inmem is the same as the size of the indexes before inserting the sales orders.</span></span> <span data-ttu-id="02a6f-529">El tamaño del índice no cambió porque ambas tablas emplean índices hash y los índices hash son estáticos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-529">The index size did not change because both tables are using hash indexes, and hash indexes are static.</span></span>  
  
#### <a name="after-demo-reset"></a><span data-ttu-id="02a6f-530">Después de restablecer la demostración</span><span class="sxs-lookup"><span data-stu-id="02a6f-530">After demo reset</span></span>  
 <span data-ttu-id="02a6f-531">Se puede usar el procedimiento almacenado Demo.usp_DemoReset para restablecer la demostración.</span><span class="sxs-lookup"><span data-stu-id="02a6f-531">The stored procedure Demo.usp_DemoReset can be used to reset the demo.</span></span> <span data-ttu-id="02a6f-532">Elimina los datos de las tablas SalesOrderHeader_inmem y SalesOrderDetail_inmem, y reinicializa los datos de las tablas originales SalesOrderHeader y SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="02a6f-532">It deletes the data in the tables SalesOrderHeader_inmem and SalesOrderDetail_inmem, and re-seeds the data from the original tables SalesOrderHeader and SalesOrderDetail.</span></span>  
  
 <span data-ttu-id="02a6f-533">Ahora, aunque las filas de las tablas se han eliminado, esto no significa que la memoria se recupera inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="02a6f-533">Now, even though the rows in the tables have been deleted, this does not mean that memory is reclaimed immediately.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="02a6f-534">recupera memoria de las filas eliminadas de las tablas optimizadas para memoria en segundo plano, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="02a6f-534">reclaims memory from deleted rows in memory-optimized tables in the background, as needed.</span></span> <span data-ttu-id="02a6f-535">Verá que inmediatamente después de restablecer la demostración, sin ninguna carga de trabajo transaccional en el sistema, la memoria de las filas eliminadas aún no se ha recuperado:</span><span class="sxs-lookup"><span data-stu-id="02a6f-535">You will see that immediately after demo reset, with no transactional workload on the system, memory from deleted rows is not yet reclaimed:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="02a6f-536">**type**</span><span class="sxs-lookup"><span data-stu-id="02a6f-536">**type**</span></span>|<span data-ttu-id="02a6f-537">**name**</span><span class="sxs-lookup"><span data-stu-id="02a6f-537">**name**</span></span>|<span data-ttu-id="02a6f-538">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="02a6f-538">**pages_MB**</span></span>|  
|<span data-ttu-id="02a6f-539">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-539">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-540">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="02a6f-540">Default</span></span>|<span data-ttu-id="02a6f-541">2261</span><span class="sxs-lookup"><span data-stu-id="02a6f-541">2261</span></span>|  
|<span data-ttu-id="02a6f-542">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-542">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-543">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="02a6f-543">DB_ID_5</span></span>|<span data-ttu-id="02a6f-544">7396</span><span class="sxs-lookup"><span data-stu-id="02a6f-544">7396</span></span>|  
|<span data-ttu-id="02a6f-545">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-545">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-546">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="02a6f-546">Default</span></span>|<span data-ttu-id="02a6f-547">0</span><span class="sxs-lookup"><span data-stu-id="02a6f-547">0</span></span>|  
|<span data-ttu-id="02a6f-548">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-548">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-549">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="02a6f-549">Default</span></span>|<span data-ttu-id="02a6f-550">0</span><span class="sxs-lookup"><span data-stu-id="02a6f-550">0</span></span>|  
  
 <span data-ttu-id="02a6f-551">Esto es lo esperado: la memoria se recuperará cuando se ejecute la carga de trabajo transaccional.</span><span class="sxs-lookup"><span data-stu-id="02a6f-551">This is expected: memory will be reclaimed when the transactional workload is running.</span></span>  
  
 <span data-ttu-id="02a6f-552">Si inicia una segunda ejecución de la carga de trabajo de demostración, verá que la utilización de memoria disminuye inicialmente, a medida que se limpian las filas eliminadas previamente.</span><span class="sxs-lookup"><span data-stu-id="02a6f-552">If you start a second run of the demo workload you will see the memory utilization decrease initially, as the previously deleted rows are cleaned up.</span></span> <span data-ttu-id="02a6f-553">En algún momento el tamaño de la memoria aumentará de nuevo, hasta que finalice la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="02a6f-553">At some point the memory size will increase again, until the workload finishes.</span></span> <span data-ttu-id="02a6f-554">Después de insertar 10 millones de filas después de restablecer la demostración, el uso de memoria será muy similar al uso después de la primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="02a6f-554">After inserting 10 million rows after demo reset, the memory utilization will be very similar to the utilization after the first run.</span></span> <span data-ttu-id="02a6f-555">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02a6f-555">For example:</span></span>  
  
```  
SELECT type  
, name  
, pages_kb/1024 AS pages_MB   
FROM sys.dm_os_memory_clerks WHERE type LIKE '%xtp%'  
```  
  
||||  
|-|-|-|  
|<span data-ttu-id="02a6f-556">**type**</span><span class="sxs-lookup"><span data-stu-id="02a6f-556">**type**</span></span>|<span data-ttu-id="02a6f-557">**name**</span><span class="sxs-lookup"><span data-stu-id="02a6f-557">**name**</span></span>|<span data-ttu-id="02a6f-558">**pages_MB**</span><span class="sxs-lookup"><span data-stu-id="02a6f-558">**pages_MB**</span></span>|  
|<span data-ttu-id="02a6f-559">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-559">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-560">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="02a6f-560">Default</span></span>|<span data-ttu-id="02a6f-561">1863</span><span class="sxs-lookup"><span data-stu-id="02a6f-561">1863</span></span>|  
|<span data-ttu-id="02a6f-562">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-562">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-563">DB_ID_5</span><span class="sxs-lookup"><span data-stu-id="02a6f-563">DB_ID_5</span></span>|<span data-ttu-id="02a6f-564">7390</span><span class="sxs-lookup"><span data-stu-id="02a6f-564">7390</span></span>|  
|<span data-ttu-id="02a6f-565">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-565">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-566">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="02a6f-566">Default</span></span>|<span data-ttu-id="02a6f-567">0</span><span class="sxs-lookup"><span data-stu-id="02a6f-567">0</span></span>|  
|<span data-ttu-id="02a6f-568">MEMORYCLERK_XTP</span><span class="sxs-lookup"><span data-stu-id="02a6f-568">MEMORYCLERK_XTP</span></span>|<span data-ttu-id="02a6f-569">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="02a6f-569">Default</span></span>|<span data-ttu-id="02a6f-570">0</span><span class="sxs-lookup"><span data-stu-id="02a6f-570">0</span></span>|  
  
### <a name="disk-utilization-for-memory-optimized-tables"></a><span data-ttu-id="02a6f-571">Uso de disco para las tablas optimizadas para memoria</span><span class="sxs-lookup"><span data-stu-id="02a6f-571">Disk utilization for memory-optimized tables</span></span>  
 <span data-ttu-id="02a6f-572">El tamaño total en disco de los archivos de punto de comprobación de una base de datos en un momento dado se puede averiguar con la consulta:</span><span class="sxs-lookup"><span data-stu-id="02a6f-572">The overall on-disk size for the checkpoint files of a database at a given time can be found using the query:</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
  
```  
  
#### <a name="initial-state"></a><span data-ttu-id="02a6f-573">Estado inicial</span><span class="sxs-lookup"><span data-stu-id="02a6f-573">Initial state</span></span>  
 <span data-ttu-id="02a6f-574">Cuando se crean inicialmente el grupo de archivos de ejemplo y las tablas optimizadas para memoria de ejemplo, se crean previamente varios archivos de punto de comprobación y el sistema empieza a rellenar los archivos; el número de archivos de punto de comprobación creados previamente depende del número de procesadores lógicos del sistema.</span><span class="sxs-lookup"><span data-stu-id="02a6f-574">When the sample filegroup and sample memory-optimized tables are created initially, a number of checkpoint files are pre-created and the system starts filling the files - the number of checkpoint files pre-created depends on the number of logical processors in the system.</span></span> <span data-ttu-id="02a6f-575">Como el ejemplo es inicialmente muy pequeño, los archivos creados previamente estarán vacíos en su mayoría después de la creación inicial.</span><span class="sxs-lookup"><span data-stu-id="02a6f-575">As the sample is initially very small, the pre-created files will be mostly empty after initial create.</span></span>  
  
 <span data-ttu-id="02a6f-576">A continuación se muestra el tamaño inicial en disco del ejemplo en un equipo con 16 procesadores lógicos:</span><span class="sxs-lookup"><span data-stu-id="02a6f-576">The following shows the initial on-disk size for the sample on a machine with 16 logical processors:</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="02a6f-577">**Tamaño en disco en MB**</span><span class="sxs-lookup"><span data-stu-id="02a6f-577">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="02a6f-578">2312</span><span class="sxs-lookup"><span data-stu-id="02a6f-578">2312</span></span>|  
  
 <span data-ttu-id="02a6f-579">Como puede ver, hay una gran discrepancia entre el tamaño en disco de los archivos de punto de comprobación, que es 2,3 GB, y el tamaño de datos real, que es más cercano a 30 MB.</span><span class="sxs-lookup"><span data-stu-id="02a6f-579">As you can see, there is a big discrepancy between the on-disk size of the checkpoint files, which is 2.3GB, and the actual data size, which is closer to 30MB.</span></span>  
  
 <span data-ttu-id="02a6f-580">Para examinar más de cerca de dónde procede la utilización de espacio en disco, puede usar la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="02a6f-580">Looking closer at where the disk-space utilization comes from, you can use the following query.</span></span> <span data-ttu-id="02a6f-581">El tamaño del disco devuelto por esta consulta es aproximado en el caso de los archivos que tienen el estado 5 (REQUIRED FOR BACKUP/HA), 6 (IN TRANSITION TO TOMBSTONE) o 7 (TOMBSTONE).</span><span class="sxs-lookup"><span data-stu-id="02a6f-581">The size on disk returned by this query is approximate for files with state in 5 (REQUIRED FOR BACKUP/HA), 6 (IN TRANSITION TO TOMBSTONE), or 7 (TOMBSTONE).</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
 <span data-ttu-id="02a6f-582">Para el estado inicial del ejemplo, el resultado será similar al de un servidor con 16 procesadores lógicos:</span><span class="sxs-lookup"><span data-stu-id="02a6f-582">For the initial state of the sample, the result will look something like for a server with 16 logical processors:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="02a6f-583">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="02a6f-583">**state_desc**</span></span>|<span data-ttu-id="02a6f-584">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="02a6f-584">**file_type_desc**</span></span>|<span data-ttu-id="02a6f-585">**count**</span><span class="sxs-lookup"><span data-stu-id="02a6f-585">**count**</span></span>|<span data-ttu-id="02a6f-586">**Tamaño en disco en MB**</span><span class="sxs-lookup"><span data-stu-id="02a6f-586">**on-disk size MB**</span></span>|  
|<span data-ttu-id="02a6f-587">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="02a6f-587">PRECREATED</span></span>|<span data-ttu-id="02a6f-588">DATA</span><span class="sxs-lookup"><span data-stu-id="02a6f-588">DATA</span></span>|<span data-ttu-id="02a6f-589">16</span><span class="sxs-lookup"><span data-stu-id="02a6f-589">16</span></span>|<span data-ttu-id="02a6f-590">2048</span><span class="sxs-lookup"><span data-stu-id="02a6f-590">2048</span></span>|  
|<span data-ttu-id="02a6f-591">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="02a6f-591">PRECREATED</span></span>|<span data-ttu-id="02a6f-592">DELTA</span><span class="sxs-lookup"><span data-stu-id="02a6f-592">DELTA</span></span>|<span data-ttu-id="02a6f-593">16</span><span class="sxs-lookup"><span data-stu-id="02a6f-593">16</span></span>|<span data-ttu-id="02a6f-594">128</span><span class="sxs-lookup"><span data-stu-id="02a6f-594">128</span></span>|  
|<span data-ttu-id="02a6f-595">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="02a6f-595">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="02a6f-596">DATA</span><span class="sxs-lookup"><span data-stu-id="02a6f-596">DATA</span></span>|<span data-ttu-id="02a6f-597">1</span><span class="sxs-lookup"><span data-stu-id="02a6f-597">1</span></span>|<span data-ttu-id="02a6f-598">128</span><span class="sxs-lookup"><span data-stu-id="02a6f-598">128</span></span>|  
|<span data-ttu-id="02a6f-599">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="02a6f-599">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="02a6f-600">DELTA</span><span class="sxs-lookup"><span data-stu-id="02a6f-600">DELTA</span></span>|<span data-ttu-id="02a6f-601">1</span><span class="sxs-lookup"><span data-stu-id="02a6f-601">1</span></span>|<span data-ttu-id="02a6f-602">8</span><span class="sxs-lookup"><span data-stu-id="02a6f-602">8</span></span>|  
  
 <span data-ttu-id="02a6f-603">Como puede ver, la mayor parte del espacio la usan archivos de datos y delta creados previamente.</span><span class="sxs-lookup"><span data-stu-id="02a6f-603">As you can see, most of the space is used by precreated data and delta files.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="02a6f-604">ha creado previamente un par de archivos (datos, delta) por procesador lógico.</span><span class="sxs-lookup"><span data-stu-id="02a6f-604">pre-created one pair of (data, delta) files per logical processor.</span></span> <span data-ttu-id="02a6f-605">Además, los archivos de datos tienen un tamaño previo de 128 MB, y los archivos delta de 8 MB, para que la inserción de datos en estos archivos sea más eficaz.</span><span class="sxs-lookup"><span data-stu-id="02a6f-605">In addition, data files are pre-sized at 128MB, and delta files at 8MB, in order to make inserting data into these files more efficient.</span></span>  
  
 <span data-ttu-id="02a6f-606">Los datos reales de las tablas optimizadas para memoria están en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-606">The actual data in the memory-optimized tables is in the single data file.</span></span>  
  
#### <a name="after-running-the-workload"></a><span data-ttu-id="02a6f-607">Después de ejecutar la carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="02a6f-607">After running the workload</span></span>  
 <span data-ttu-id="02a6f-608">Después de una única serie de pruebas que inserta 10 millones de pedidos de venta, el tamaño total en disco es similar al siguiente (para un servidor de prueba de 16 núcleos):</span><span class="sxs-lookup"><span data-stu-id="02a6f-608">After a single test run that inserts 10 million sales orders, the overall on-disk size looks something like this (for a 16-core test server):</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="02a6f-609">**Tamaño en disco en MB**</span><span class="sxs-lookup"><span data-stu-id="02a6f-609">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="02a6f-610">8828</span><span class="sxs-lookup"><span data-stu-id="02a6f-610">8828</span></span>|  
  
 <span data-ttu-id="02a6f-611">El tamaño en disco está cercano a 9 GB, que es parecido al tamaño en memoria de los datos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-611">The on-disk size is close to 9GB, which comes close to the in-memory size of the data.</span></span>  
  
 <span data-ttu-id="02a6f-612">Si examinamos más de cerca los tamaños de los archivos de punto de comprobación en los distintos estados:</span><span class="sxs-lookup"><span data-stu-id="02a6f-612">Looking more closely at the sizes of the checkpoint files across the various states:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="02a6f-613">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="02a6f-613">**state_desc**</span></span>|<span data-ttu-id="02a6f-614">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="02a6f-614">**file_type_desc**</span></span>|<span data-ttu-id="02a6f-615">**count**</span><span class="sxs-lookup"><span data-stu-id="02a6f-615">**count**</span></span>|<span data-ttu-id="02a6f-616">**Tamaño en disco en MB**</span><span class="sxs-lookup"><span data-stu-id="02a6f-616">**on-disk size MB**</span></span>|  
|<span data-ttu-id="02a6f-617">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="02a6f-617">PRECREATED</span></span>|<span data-ttu-id="02a6f-618">DATA</span><span class="sxs-lookup"><span data-stu-id="02a6f-618">DATA</span></span>|<span data-ttu-id="02a6f-619">16</span><span class="sxs-lookup"><span data-stu-id="02a6f-619">16</span></span>|<span data-ttu-id="02a6f-620">2048</span><span class="sxs-lookup"><span data-stu-id="02a6f-620">2048</span></span>|  
|<span data-ttu-id="02a6f-621">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="02a6f-621">PRECREATED</span></span>|<span data-ttu-id="02a6f-622">DELTA</span><span class="sxs-lookup"><span data-stu-id="02a6f-622">DELTA</span></span>|<span data-ttu-id="02a6f-623">16</span><span class="sxs-lookup"><span data-stu-id="02a6f-623">16</span></span>|<span data-ttu-id="02a6f-624">128</span><span class="sxs-lookup"><span data-stu-id="02a6f-624">128</span></span>|  
|<span data-ttu-id="02a6f-625">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="02a6f-625">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="02a6f-626">DATA</span><span class="sxs-lookup"><span data-stu-id="02a6f-626">DATA</span></span>|<span data-ttu-id="02a6f-627">1</span><span class="sxs-lookup"><span data-stu-id="02a6f-627">1</span></span>|<span data-ttu-id="02a6f-628">128</span><span class="sxs-lookup"><span data-stu-id="02a6f-628">128</span></span>|  
|<span data-ttu-id="02a6f-629">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="02a6f-629">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="02a6f-630">DELTA</span><span class="sxs-lookup"><span data-stu-id="02a6f-630">DELTA</span></span>|<span data-ttu-id="02a6f-631">1</span><span class="sxs-lookup"><span data-stu-id="02a6f-631">1</span></span>|<span data-ttu-id="02a6f-632">8</span><span class="sxs-lookup"><span data-stu-id="02a6f-632">8</span></span>|  
  
 <span data-ttu-id="02a6f-633">Todavía tenemos 16 pares de archivos creados previamente, listos a medida que se cierran los puntos de comprobación.</span><span class="sxs-lookup"><span data-stu-id="02a6f-633">We still have 16 pairs of pre-created files, ready to go as checkpoints are closed.</span></span>  
  
 <span data-ttu-id="02a6f-634">Hay un par en construcción, que se usa hasta que se cierra el punto de comprobación actual.</span><span class="sxs-lookup"><span data-stu-id="02a6f-634">There is one pair under construction, which is used until the current checkpoint is closed.</span></span> <span data-ttu-id="02a6f-635">Junto con los archivos de punto de comprobación activos, esto nos da unos 6,5 GB de uso de disco para 6,5 GB de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="02a6f-635">Along with the active checkpoint files this gives about 6.5GB of disk utilization for 6.5GB of data in memory.</span></span> <span data-ttu-id="02a6f-636">Recuerde que los índices no se conservan en disco, por lo que el tamaño total en disco es menor que el tamaño en memoria en este caso.</span><span class="sxs-lookup"><span data-stu-id="02a6f-636">Recall that indexes are not persisted on disk, and thus the overall size on disk is smaller than the size in memory in this case.</span></span>  
  
#### <a name="after-demo-reset"></a><span data-ttu-id="02a6f-637">Después de restablecer la demostración</span><span class="sxs-lookup"><span data-stu-id="02a6f-637">After demo reset</span></span>  
 <span data-ttu-id="02a6f-638">Después de restablecer la demostración, el espacio en disco no se recupera inmediatamente si no hay ninguna carga de trabajo transaccional en el sistema, y no hay ningún punto de comprobación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="02a6f-638">After demo reset, disk space is not reclaimed immediately if there is no transactional workload on the system, and there are not database checkpoints.</span></span> <span data-ttu-id="02a6f-639">Para que los archivos de punto de comprobación pasen por sus diferentes etapas y después se descarten, tiene que haber varios puntos de comprobación y eventos de truncamiento del registro, con el fin de iniciar la combinación de los archivos de punto de comprobación e iniciar la recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="02a6f-639">For checkpoint files to be moved through their various stages and eventually be discarded, a number of checkpoints and log truncation events need to happen, to initiate merge of checkpoint files, as well as to initiate garbage collection.</span></span> <span data-ttu-id="02a6f-640">Estos ocurrirá automáticamente si tiene una carga de trabajo transaccional en el sistema [y realiza copias de seguridad de registros periódicas, en caso de que esté utilizando el modelo de recuperación completa], pero no cuando el sistema está inactivo, como ocurre en un escenario de demostración.</span><span class="sxs-lookup"><span data-stu-id="02a6f-640">These will happen automatically if you have a transactional workload in the system [and take regular log backups, in case you are using the FULL recovery model], but not when the system is idle, as in a demo scenario.</span></span>  
  
 <span data-ttu-id="02a6f-641">En el ejemplo, después de restablecer la demostración, puede ver algo similar a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="02a6f-641">In the example, after demo reset, you may see something like</span></span>  
  
```  
SELECT SUM(df.size) * 8 / 1024 AS [On-disk size in MB]  
FROM sys.filegroups f JOIN sys.database_files df   
   ON f.data_space_id=df.data_space_id  
WHERE f.type=N'FX'  
```  
  
||  
|-|  
|<span data-ttu-id="02a6f-642">**Tamaño en disco en MB**</span><span class="sxs-lookup"><span data-stu-id="02a6f-642">**On-disk size in MB**</span></span>|  
|<span data-ttu-id="02a6f-643">11839</span><span class="sxs-lookup"><span data-stu-id="02a6f-643">11839</span></span>|  
  
 <span data-ttu-id="02a6f-644">Con casi 12 GB, esto es mucho más significativo que los 9 GB teníamos antes de restablecer la demostración.</span><span class="sxs-lookup"><span data-stu-id="02a6f-644">At nearly 12GB, this is significantly more than the 9GB we had before the demo reset.</span></span> <span data-ttu-id="02a6f-645">Esto se debe a que se han iniciado algunas combinaciones de archivos de punto de comprobación, pero algunos destinos de mezcla todavía no se han instalado, y algunos de los archivos de origen de mezcla todavía no se han limpiado, como se puede ver aquí:</span><span class="sxs-lookup"><span data-stu-id="02a6f-645">This is because some checkpoint file merges have been started, but some of the merge targets have not yet been installed, and some of the merge source files have not yet been cleaned up, as can be seen from the following:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="02a6f-646">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="02a6f-646">**state_desc**</span></span>|<span data-ttu-id="02a6f-647">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="02a6f-647">**file_type_desc**</span></span>|<span data-ttu-id="02a6f-648">**count**</span><span class="sxs-lookup"><span data-stu-id="02a6f-648">**count**</span></span>|<span data-ttu-id="02a6f-649">**Tamaño en disco en MB**</span><span class="sxs-lookup"><span data-stu-id="02a6f-649">**on-disk size MB**</span></span>|  
|<span data-ttu-id="02a6f-650">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="02a6f-650">PRECREATED</span></span>|<span data-ttu-id="02a6f-651">DATA</span><span class="sxs-lookup"><span data-stu-id="02a6f-651">DATA</span></span>|<span data-ttu-id="02a6f-652">16</span><span class="sxs-lookup"><span data-stu-id="02a6f-652">16</span></span>|<span data-ttu-id="02a6f-653">2048</span><span class="sxs-lookup"><span data-stu-id="02a6f-653">2048</span></span>|  
|<span data-ttu-id="02a6f-654">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="02a6f-654">PRECREATED</span></span>|<span data-ttu-id="02a6f-655">DELTA</span><span class="sxs-lookup"><span data-stu-id="02a6f-655">DELTA</span></span>|<span data-ttu-id="02a6f-656">16</span><span class="sxs-lookup"><span data-stu-id="02a6f-656">16</span></span>|<span data-ttu-id="02a6f-657">128</span><span class="sxs-lookup"><span data-stu-id="02a6f-657">128</span></span>|  
|<span data-ttu-id="02a6f-658">ACTIVO</span><span class="sxs-lookup"><span data-stu-id="02a6f-658">ACTIVE</span></span>|<span data-ttu-id="02a6f-659">DATA</span><span class="sxs-lookup"><span data-stu-id="02a6f-659">DATA</span></span>|<span data-ttu-id="02a6f-660">38</span><span class="sxs-lookup"><span data-stu-id="02a6f-660">38</span></span>|<span data-ttu-id="02a6f-661">5152</span><span class="sxs-lookup"><span data-stu-id="02a6f-661">5152</span></span>|  
|<span data-ttu-id="02a6f-662">ACTIVO</span><span class="sxs-lookup"><span data-stu-id="02a6f-662">ACTIVE</span></span>|<span data-ttu-id="02a6f-663">DELTA</span><span class="sxs-lookup"><span data-stu-id="02a6f-663">DELTA</span></span>|<span data-ttu-id="02a6f-664">38</span><span class="sxs-lookup"><span data-stu-id="02a6f-664">38</span></span>|<span data-ttu-id="02a6f-665">1331</span><span class="sxs-lookup"><span data-stu-id="02a6f-665">1331</span></span>|  
|<span data-ttu-id="02a6f-666">MERGE TARGET</span><span class="sxs-lookup"><span data-stu-id="02a6f-666">MERGE TARGET</span></span>|<span data-ttu-id="02a6f-667">DATA</span><span class="sxs-lookup"><span data-stu-id="02a6f-667">DATA</span></span>|<span data-ttu-id="02a6f-668">7</span><span class="sxs-lookup"><span data-stu-id="02a6f-668">7</span></span>|<span data-ttu-id="02a6f-669">896</span><span class="sxs-lookup"><span data-stu-id="02a6f-669">896</span></span>|  
|<span data-ttu-id="02a6f-670">MERGE TARGET</span><span class="sxs-lookup"><span data-stu-id="02a6f-670">MERGE TARGET</span></span>|<span data-ttu-id="02a6f-671">DELTA</span><span class="sxs-lookup"><span data-stu-id="02a6f-671">DELTA</span></span>|<span data-ttu-id="02a6f-672">7</span><span class="sxs-lookup"><span data-stu-id="02a6f-672">7</span></span>|<span data-ttu-id="02a6f-673">56</span><span class="sxs-lookup"><span data-stu-id="02a6f-673">56</span></span>|  
|<span data-ttu-id="02a6f-674">MERGED SOURCE</span><span class="sxs-lookup"><span data-stu-id="02a6f-674">MERGED SOURCE</span></span>|<span data-ttu-id="02a6f-675">DATA</span><span class="sxs-lookup"><span data-stu-id="02a6f-675">DATA</span></span>|<span data-ttu-id="02a6f-676">13</span><span class="sxs-lookup"><span data-stu-id="02a6f-676">13</span></span>|<span data-ttu-id="02a6f-677">1772</span><span class="sxs-lookup"><span data-stu-id="02a6f-677">1772</span></span>|  
|<span data-ttu-id="02a6f-678">MERGED SOURCE</span><span class="sxs-lookup"><span data-stu-id="02a6f-678">MERGED SOURCE</span></span>|<span data-ttu-id="02a6f-679">DELTA</span><span class="sxs-lookup"><span data-stu-id="02a6f-679">DELTA</span></span>|<span data-ttu-id="02a6f-680">13</span><span class="sxs-lookup"><span data-stu-id="02a6f-680">13</span></span>|<span data-ttu-id="02a6f-681">455</span><span class="sxs-lookup"><span data-stu-id="02a6f-681">455</span></span>|  
  
 <span data-ttu-id="02a6f-682">Los destinos de mezcla se instalan y el origen de mezcla se limpia mientras la realiza actividad transaccional en el sistema.</span><span class="sxs-lookup"><span data-stu-id="02a6f-682">Merge targets are installed and merged source are cleaned up as transactional activity happens in the system.</span></span>  
  
 <span data-ttu-id="02a6f-683">Después de una segunda ejecución de la carga de trabajo de demostración, insertando 10 millones de pedidos de venta después de restablecer la demostración, verá que los archivos creados durante la primera ejecución de la carga de trabajo se han limpiado.</span><span class="sxs-lookup"><span data-stu-id="02a6f-683">After a second run of the demo workload, inserting 10 million sales orders after the demo reset, you will see that the files constructed during the first run of the workload have been cleaned up.</span></span> <span data-ttu-id="02a6f-684">Si ejecuta la consulta anterior varias veces mientras se está ejecutando la carga de trabajo, puede ver que los archivos de punto de comprobación pasaron por las distintas fases.</span><span class="sxs-lookup"><span data-stu-id="02a6f-684">If you run the above query several times while the workload is running, you can see the checkpoint files make their way through the various stages.</span></span>  
  
 <span data-ttu-id="02a6f-685">Después de que la segunda ejecución de la carga de trabajo inserta 10 millones de pedidos de venta, verá un uso de disco muy similar, aunque no necesariamente igual después de la primera ejecución, porque el sistema es dinámico por naturaleza.</span><span class="sxs-lookup"><span data-stu-id="02a6f-685">After the second run of the workload insert 10 million sales orders you will see disk utilization very similar to, though not necessarily the same as after the first run, as the system is dynamic in nature.</span></span> <span data-ttu-id="02a6f-686">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02a6f-686">For example:</span></span>  
  
```  
SELECT state_desc  
 , file_type_desc  
 , COUNT(*) AS [count]  
 , SUM(CASE  
   WHEN state = 5 AND file_type=0 THEN 128*1024*1024  
   WHEN state = 5 AND file_type=1 THEN 8*1024*1024  
   WHEN state IN (6,7) THEN 68*1024*1024  
   ELSE file_size_in_bytes  
    END) / 1024 / 1024 AS [on-disk size MB]   
FROM sys.dm_db_xtp_checkpoint_files  
GROUP BY state, state_desc, file_type, file_type_desc  
ORDER BY state, file_type  
```  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="02a6f-687">**state_desc**</span><span class="sxs-lookup"><span data-stu-id="02a6f-687">**state_desc**</span></span>|<span data-ttu-id="02a6f-688">**file_type_desc**</span><span class="sxs-lookup"><span data-stu-id="02a6f-688">**file_type_desc**</span></span>|<span data-ttu-id="02a6f-689">**count**</span><span class="sxs-lookup"><span data-stu-id="02a6f-689">**count**</span></span>|<span data-ttu-id="02a6f-690">**Tamaño en disco en MB**</span><span class="sxs-lookup"><span data-stu-id="02a6f-690">**on-disk size MB**</span></span>|  
|<span data-ttu-id="02a6f-691">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="02a6f-691">PRECREATED</span></span>|<span data-ttu-id="02a6f-692">DATA</span><span class="sxs-lookup"><span data-stu-id="02a6f-692">DATA</span></span>|<span data-ttu-id="02a6f-693">16</span><span class="sxs-lookup"><span data-stu-id="02a6f-693">16</span></span>|<span data-ttu-id="02a6f-694">2048</span><span class="sxs-lookup"><span data-stu-id="02a6f-694">2048</span></span>|  
|<span data-ttu-id="02a6f-695">PRECREATED</span><span class="sxs-lookup"><span data-stu-id="02a6f-695">PRECREATED</span></span>|<span data-ttu-id="02a6f-696">DELTA</span><span class="sxs-lookup"><span data-stu-id="02a6f-696">DELTA</span></span>|<span data-ttu-id="02a6f-697">16</span><span class="sxs-lookup"><span data-stu-id="02a6f-697">16</span></span>|<span data-ttu-id="02a6f-698">128</span><span class="sxs-lookup"><span data-stu-id="02a6f-698">128</span></span>|  
|<span data-ttu-id="02a6f-699">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="02a6f-699">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="02a6f-700">DATA</span><span class="sxs-lookup"><span data-stu-id="02a6f-700">DATA</span></span>|<span data-ttu-id="02a6f-701">2</span><span class="sxs-lookup"><span data-stu-id="02a6f-701">2</span></span>|<span data-ttu-id="02a6f-702">268</span><span class="sxs-lookup"><span data-stu-id="02a6f-702">268</span></span>|  
|<span data-ttu-id="02a6f-703">UNDER CONSTRUCTION</span><span class="sxs-lookup"><span data-stu-id="02a6f-703">UNDER CONSTRUCTION</span></span>|<span data-ttu-id="02a6f-704">DELTA</span><span class="sxs-lookup"><span data-stu-id="02a6f-704">DELTA</span></span>|<span data-ttu-id="02a6f-705">2</span><span class="sxs-lookup"><span data-stu-id="02a6f-705">2</span></span>|<span data-ttu-id="02a6f-706">16</span><span class="sxs-lookup"><span data-stu-id="02a6f-706">16</span></span>|  
|<span data-ttu-id="02a6f-707">ACTIVO</span><span class="sxs-lookup"><span data-stu-id="02a6f-707">ACTIVE</span></span>|<span data-ttu-id="02a6f-708">DATA</span><span class="sxs-lookup"><span data-stu-id="02a6f-708">DATA</span></span>|<span data-ttu-id="02a6f-709">41</span><span class="sxs-lookup"><span data-stu-id="02a6f-709">41</span></span>|<span data-ttu-id="02a6f-710">5608</span><span class="sxs-lookup"><span data-stu-id="02a6f-710">5608</span></span>|  
|<span data-ttu-id="02a6f-711">ACTIVO</span><span class="sxs-lookup"><span data-stu-id="02a6f-711">ACTIVE</span></span>|<span data-ttu-id="02a6f-712">DELTA</span><span class="sxs-lookup"><span data-stu-id="02a6f-712">DELTA</span></span>|<span data-ttu-id="02a6f-713">41</span><span class="sxs-lookup"><span data-stu-id="02a6f-713">41</span></span>|<span data-ttu-id="02a6f-714">328</span><span class="sxs-lookup"><span data-stu-id="02a6f-714">328</span></span>|  
  
 <span data-ttu-id="02a6f-715">En este caso, hay dos pares de archivos de punto de comprobación en el estado "under construction", lo que significa que varios pares de archivos pasaron por el estado "under construction", probablemente debido al elevado nivel de simultaneidad de la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="02a6f-715">In this case, there are two checkpoint file pairs in the 'under construction' state, which means multiple file pairs were moved to the 'under construction' state, likely due to the high level of concurrency in the workload.</span></span> <span data-ttu-id="02a6f-716">Varios subprocesos simultáneos necesitaron un nuevo par de archivos al mismo tiempo, por lo que se movió un par de "precreated" a "under construction".</span><span class="sxs-lookup"><span data-stu-id="02a6f-716">Multiple concurrent threads required a new file pair at the same time, and thus moved a pair from 'precreated' to 'under construction'.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a6f-717">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02a6f-717">See Also</span></span>  
 [<span data-ttu-id="02a6f-718">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="02a6f-718">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
