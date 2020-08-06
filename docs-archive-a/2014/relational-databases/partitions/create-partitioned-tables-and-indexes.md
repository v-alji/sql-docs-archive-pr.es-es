---
title: Creación de tablas e índices con particiones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.createpartition.partitionscheme.f1
- sql12.swb.createpartition.selectoutput.f1
- sql12.swb.createpartition.finish.f1
- sql12.swb.createpartition.summary.f1
- sql12.swb.createpartition.mappartition.f1
- sql12.swb.createpartition.partitioncolumn.f1
- sql12.swb.createpartition.progress.f1
- sql12.swb.createpartition.createjob.f1
- sql12.swb.createpartition.getstart.f1
- sql12.swb.createpartition.partitionfunction.f1
helpviewer_keywords:
- partitioned indexes [SQL Server], creating
- partition schemes [SQL Server], creating
- partition functions [SQL Server], creating
- partitioned tables [SQL Server], creating
- partition functions [SQL Server]
- partition schemes [SQL Server]
ms.assetid: 7641df10-1921-42a7-ba6e-4cb03b3ba9c8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 76ccd8b784902f8542f06f3823e5f8dcb78e9201
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671502"
---
# <a name="create-partitioned-tables-and-indexes"></a><span data-ttu-id="c32de-102">Crear tablas e índices con particiones</span><span class="sxs-lookup"><span data-stu-id="c32de-102">Create Partitioned Tables and Indexes</span></span>
  <span data-ttu-id="c32de-103">Puede crear una tabla o índice con particiones en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c32de-103">You can create a partitioned table or index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c32de-104">Los datos en tablas e índices con particiones se dividen horizontalmente en unidades que pueden propagarse por más de un grupo de archivos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c32de-104">The data in partitioned tables and indexes is horizontally divided into units that can be spread across more than one filegroup in a database.</span></span> <span data-ttu-id="c32de-105">Las particiones pueden hacer que las tablas y los índices grandes sean más escalables y fáciles de administrar.</span><span class="sxs-lookup"><span data-stu-id="c32de-105">Partitioning can make large tables and indexes more manageable and scalable.</span></span>  
  
 <span data-ttu-id="c32de-106">La creación de una tabla o índice con particiones tiene lugar normalmente en cuatro partes:</span><span class="sxs-lookup"><span data-stu-id="c32de-106">Creating a partitioned table or index typically happens in four parts:</span></span>  
  
1.  <span data-ttu-id="c32de-107">Crear un grupo o grupos de archivos y los archivos correspondientes que contendrán las particiones especificadas por el esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="c32de-107">Create a filegroup or filegroups and corresponding files that will hold the partitions specified by the partition scheme.</span></span>  
  
2.  <span data-ttu-id="c32de-108">Crear una función de partición que asigna las filas de una tabla o un índice a particiones según los valores de una columna especificada.</span><span class="sxs-lookup"><span data-stu-id="c32de-108">Create a partition function that maps the rows of a table or index into partitions based on the values of a specified column.</span></span>  
  
3.  <span data-ttu-id="c32de-109">Crear un esquema de partición que asigna las particiones de una tabla o índice con particiones a los nuevos grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="c32de-109">Create a partition scheme that maps the partitions of a partitioned table or index to the new filegroups.</span></span>  
  
4.  <span data-ttu-id="c32de-110">Crear o modificar una tabla o un índice y especificar el esquema de partición como ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="c32de-110">Create or modify a table or index and specify the partition scheme as the storage location.</span></span>  
  
 <span data-ttu-id="c32de-111">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="c32de-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c32de-112">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="c32de-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c32de-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="c32de-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c32de-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c32de-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c32de-115">**Para crear una tabla o un índice con particiones, use:**</span><span class="sxs-lookup"><span data-stu-id="c32de-115">**To create a partitioned table or index, using:**</span></span>  
  
     [<span data-ttu-id="c32de-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c32de-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c32de-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c32de-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c32de-118">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="c32de-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c32de-119">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="c32de-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c32de-120">El ámbito de una función y un esquema de partición se limita a la base de datos en la que se han creado.</span><span class="sxs-lookup"><span data-stu-id="c32de-120">The scope of a partition function and scheme is limited to the database in which they have been created.</span></span> <span data-ttu-id="c32de-121">En la base de datos, las funciones de partición residen en un espacio de nombres independiente de las demás funciones.</span><span class="sxs-lookup"><span data-stu-id="c32de-121">Within the database, partition functions reside in a separate namespace from other functions.</span></span>  
  
-   <span data-ttu-id="c32de-122">Si algunas filas de una función de partición tienen columnas de partición con valores NULL, estas filas se asignan a la partición situada más a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="c32de-122">If any rows within a partition function have partitioning columns with null values, these rows are allocated to the left-most partition.</span></span> <span data-ttu-id="c32de-123">Sin embargo, si se especifica NULL como valor de límite y se indica RIGHT, la partición situada más a la izquierda permanece vacía y los valores NULL se colocan en la segunda partición.</span><span class="sxs-lookup"><span data-stu-id="c32de-123">However, if NULL is specified as a boundary value and RIGHT is indicated, the left-most partition remains empty and NULL values are placed in the second partition.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c32de-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c32de-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c32de-125">Permisos</span><span class="sxs-lookup"><span data-stu-id="c32de-125">Permissions</span></span>  
 <span data-ttu-id="c32de-126">La creación de una tabla con particiones requiere el permiso CREATE TABLE en la base de datos y el permiso ALTER en el esquema en el que se crea la tabla.</span><span class="sxs-lookup"><span data-stu-id="c32de-126">Creating a partitioned table requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span> <span data-ttu-id="c32de-127">Crear un índice con particiones requiere el permiso ALTER en la tabla o vista donde se crea el índice.</span><span class="sxs-lookup"><span data-stu-id="c32de-127">Creating a partitioned index requires ALTER permission on the table or view where the index is being created.</span></span> <span data-ttu-id="c32de-128">Crear una tabla o índice con particiones requiere alguno de los permisos adicionales siguientes:</span><span class="sxs-lookup"><span data-stu-id="c32de-128">Creating either a partitioned table or index requires any one of the following additional permissions:</span></span>  
  
-   <span data-ttu-id="c32de-129">Permiso ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="c32de-129">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="c32de-130">De forma predeterminada, este permiso corresponde a los miembros del rol fijo de servidor **sysadmin** y a los roles fijos de base de datos **db_owner** y **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="c32de-130">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="c32de-131">Permiso CONTROL o ALTER en la base de datos en la que se está creando la función de partición y el esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="c32de-131">CONTROL or ALTER permission on the database in which the partition function and partition scheme are being created.</span></span>  
  
-   <span data-ttu-id="c32de-132">Permiso CONTROL SERVER o ALTER ANY DATABASE en el servidor de la base de datos en la que se está creando la función de partición y el esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="c32de-132">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition function and partition scheme are being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c32de-133">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c32de-133">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="c32de-134">Siga los pasos de este procedimiento para crear uno o más grupos de archivos, los archivos correspondientes y una tabla.</span><span class="sxs-lookup"><span data-stu-id="c32de-134">Follow the steps in this procedure to create one or more filegroups, corresponding files, and a table.</span></span> <span data-ttu-id="c32de-135">Hará referencia a estos objetos en el siguiente procedimiento al crear la tabla con particiones.</span><span class="sxs-lookup"><span data-stu-id="c32de-135">You will reference these objects in the next procedure when you create the partitioned table.</span></span>  
  
#### <a name="to-create-new-filegroups-for-a-partitioned-table"></a><span data-ttu-id="c32de-136">Para crear nuevos grupos de archivos en una tabla con particiones</span><span class="sxs-lookup"><span data-stu-id="c32de-136">To create new filegroups for a partitioned table</span></span>  
  
1.  <span data-ttu-id="c32de-137">En el Explorador de objetos, haga clic con el botón derecho en la base de datos en la que quiere crear una tabla con particiones y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c32de-137">In Object Explorer, right-click the database in which you want to create a partitioned table and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="c32de-138">En el cuadro de diálogo **Propiedades de la base de datos -** *nombre de base de datos*, en **Seleccionar una página**, seleccione **Grupos de archivos**.</span><span class="sxs-lookup"><span data-stu-id="c32de-138">In the **Database Properties -** *database_name* dialog box, under **Select a page**, select **Filegroups**.</span></span>  
  
3.  <span data-ttu-id="c32de-139">En **Filas**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c32de-139">Under **Rows**, click **Add**.</span></span> <span data-ttu-id="c32de-140">En la nueva fila, escriba el nombre del grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="c32de-140">In the new row, enter the filegroup name.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="c32de-141">Siempre debe haber un grupo de archivos adicional además de los que especifique para los valores de límite cuando cree las particiones.</span><span class="sxs-lookup"><span data-stu-id="c32de-141">You must always have one extra filegroup in addition to the number of filegroups specified for the boundary values when you are creating partitions.</span></span>  
  
4.  <span data-ttu-id="c32de-142">Continúe agregando filas hasta que haya creado todos los grupos de archivos que la tabla con particiones.</span><span class="sxs-lookup"><span data-stu-id="c32de-142">Continue adding rows until you have created all of the filegroups for the partitioned table.</span></span>  
  
5.  <span data-ttu-id="c32de-143">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="c32de-143">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="c32de-144">En **Seleccionar una página**, seleccione **Archivos**.</span><span class="sxs-lookup"><span data-stu-id="c32de-144">Under **Select a page**, select **Files**.</span></span>  
  
7.  <span data-ttu-id="c32de-145">En **Filas**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c32de-145">Under **Rows**, click **Add**.</span></span> <span data-ttu-id="c32de-146">En la nueva fila, escriba un nombre de archivo y seleccione un grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="c32de-146">In the new row, enter a filename and select a filegroup.</span></span>  
  
8.  <span data-ttu-id="c32de-147">Continúe agregando filas hasta que haya creado al menos un archivo para cada grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="c32de-147">Continue adding rows until you have created at least one file for each filegroup.</span></span>  
  
9. <span data-ttu-id="c32de-148">Expanda la carpeta de **Tablas** y cree una tabla como haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="c32de-148">Expand the **Tables** folder and create a table as you normally would.</span></span> <span data-ttu-id="c32de-149">Para obtener más información, vea [Crear tablas &#40;motor de base de datos&#41;](../tables/create-tables-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="c32de-149">For more information, see [Create Tables &#40;Database Engine&#41;](../tables/create-tables-database-engine.md).</span></span> <span data-ttu-id="c32de-150">O bien, puede especificar una tabla existente en el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="c32de-150">Alternatively, you can specify an existing table in the next procedure.</span></span>  
  
#### <a name="to-create-a-partitioned-table"></a><span data-ttu-id="c32de-151">Para crear una tabla con particiones</span><span class="sxs-lookup"><span data-stu-id="c32de-151">To create a partitioned table</span></span>  
  
1.  <span data-ttu-id="c32de-152">Haga clic con el botón derecho en la tabla donde quiere crear las particiones, seleccione **Almacenamiento** y, después, haga clic en **Crear partición...** .</span><span class="sxs-lookup"><span data-stu-id="c32de-152">Right-click the table that you wish to partition, point to **Storage**, and then click **Create Partition...**.</span></span>  
  
2.  <span data-ttu-id="c32de-153">En el **Asistente para la creación de particiones**, en la página **Asistente para la creación de particiones** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c32de-153">In the **Create Partition Wizard**, on the **Welcome to the Create Partition Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="c32de-154">En la página **Seleccionar una columna de particionamiento** , en la cuadrícula de **Columnas de particionamiento disponibles** , seleccione la columna en la que desea crear particiones de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c32de-154">On the **Select a Partitioning Column** page, in the **Available partitioning columns** grid, select the column on which you want to partition your table.</span></span> <span data-ttu-id="c32de-155">En la cuadrícula **Columnas de particionamiento disponibles** solo se mostrarán las columnas con tipos de datos que se pueden utilizar para crear particiones de los datos.</span><span class="sxs-lookup"><span data-stu-id="c32de-155">Only columns with data types that can be used to partition data will be displayed in the **Available partitioning columns** grid.</span></span> <span data-ttu-id="c32de-156">Si selecciona una columna calculada como columna de partición, la columna se debe designar como una columna PERSISTED.</span><span class="sxs-lookup"><span data-stu-id="c32de-156">If you select a computed column as the partitioning column, the column must be designated as a persisted column.</span></span>  
  
     <span data-ttu-id="c32de-157">Las opciones de que dispone para la columna de partición y el intervalo de valores vienen determinados, principalmente, por el grado en que los datos se pueden agrupar de un modo lógico.</span><span class="sxs-lookup"><span data-stu-id="c32de-157">The choices you have for the partitioning column and the values range are determined primarily by the extent to which your data can be grouped in a logical way.</span></span> <span data-ttu-id="c32de-158">Por ejemplo, puede decidir dividir los datos en agrupaciones lógicas por meses o trimestres del año.</span><span class="sxs-lookup"><span data-stu-id="c32de-158">For example, you may choose to divide your data into logical groupings by months or quarters of a year.</span></span> <span data-ttu-id="c32de-159">Las consultas que planea realizar en los datos determinarán si esta agrupación lógica es adecuada para administrar las particiones de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c32de-159">The queries you plan to make against your data will determine whether this logical grouping is adequate for managing your table partitions.</span></span> <span data-ttu-id="c32de-160">Todos los tipos de datos, excepto `text`, `ntext`, `image`, `xml`, `timestamp`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, los tipos de datos de alias o los tipos definidos por el usuario CLR, se pueden utilizar como columnas de partición.</span><span class="sxs-lookup"><span data-stu-id="c32de-160">All data types are valid for use as partitioning columns, except `text`, `ntext`, `image`, `xml`, `timestamp`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, alias data types, or CLR user-defined data types.</span></span>  
  
     <span data-ttu-id="c32de-161">En esta página están disponibles las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c32de-161">The following additional options are available on this page:</span></span>  
  
     <span data-ttu-id="c32de-162">**Colocar esta tabla en la tabla con partición seleccionada**</span><span class="sxs-lookup"><span data-stu-id="c32de-162">**Collocate this table to the selected partitioned table**</span></span>  
     <span data-ttu-id="c32de-163">Permite seleccionar una tabla con particiones que contenga los datos relacionados para combinar con esta tabla en la columna de partición.</span><span class="sxs-lookup"><span data-stu-id="c32de-163">Allows you to select a partitioned table that contains related data to join with this table on the partitioning column.</span></span> <span data-ttu-id="c32de-164">Las tablas con particiones combinadas en las columnas de partición suelen dar lugar a consultas más eficientes.</span><span class="sxs-lookup"><span data-stu-id="c32de-164">Tables with partitions joined on the partitioning columns are typically queried more efficiently.</span></span>  
  
     <span data-ttu-id="c32de-165">**Alinear almacenamiento de índices no únicos e índices únicos con una columna de partición indizada**</span><span class="sxs-lookup"><span data-stu-id="c32de-165">**Storage-align non-unique indexes and unique indexes with an indexed partition column**</span></span>  
     <span data-ttu-id="c32de-166">Alinea todos los índices de la tabla que tiene particiones con el mismo esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="c32de-166">Aligns all indexes of the table that are partitioned with the same partition scheme.</span></span> <span data-ttu-id="c32de-167">Cuando una tabla y sus índices están alineados, puede mover las particiones dentro y fuera de las tablas con particiones de forma más eficaz, porque se usa el mismo algoritmo para crear las particiones de los datos.</span><span class="sxs-lookup"><span data-stu-id="c32de-167">When a table and its indexes are aligned, you can move partitions in and out of partitioned tables more effectively, because your data is partitioned with the same algorithm.</span></span>  
  
     <span data-ttu-id="c32de-168">Después de seleccionar la columna de partición y otras opciones, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c32de-168">After selecting the partitioning column and any other options, click **Next**.</span></span>  
  
4.  <span data-ttu-id="c32de-169">En la página **Seleccionar una función de partición** , en **Seleccionar una función de partición**, haga clic en **Nueva función de partición** o en **Función de partición existente**.</span><span class="sxs-lookup"><span data-stu-id="c32de-169">On the **Select a Partition Function** page, under **Select partition function**, click either **New partition function** or **Existing partition function**.</span></span> <span data-ttu-id="c32de-170">Si elige **Nueva función de partición**, escriba el nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="c32de-170">If you choose **New partition function**, enter the name of the function.</span></span> <span data-ttu-id="c32de-171">Si elige **Función de partición existente**, seleccione el nombre de la función que quiera usar en la lista.</span><span class="sxs-lookup"><span data-stu-id="c32de-171">If you choose **Existing partition function**, select the name of the function you'd like to use from the list.</span></span> <span data-ttu-id="c32de-172">La opción **Función de partición existente** no estará disponible si no hay otras funciones de partición en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c32de-172">The **Existing partition function** option will not be available if there are no other partition functions on the database.</span></span>  
  
     <span data-ttu-id="c32de-173">Después de completar esta página, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c32de-173">After completing this page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="c32de-174">En la página **Seleccionar un esquema de partición** , en **Seleccionar un esquema de partición**, haga clic en **Nuevo esquema de partición** o **Esquema de partición existente**.</span><span class="sxs-lookup"><span data-stu-id="c32de-174">On the **Select a Partition Scheme** page, under **Select partition scheme**, click either **New partition scheme** or **Existing partition scheme**.</span></span> <span data-ttu-id="c32de-175">Si elige **Nuevo esquema de partición**, escriba el nombre del esquema.</span><span class="sxs-lookup"><span data-stu-id="c32de-175">If you choose **New partition scheme**, enter the name of the scheme.</span></span> <span data-ttu-id="c32de-176">Si elige **Esquema de partición existente**, seleccione el nombre del esquema que quiera usar en la lista.</span><span class="sxs-lookup"><span data-stu-id="c32de-176">If you choose **Existing partition scheme**, select the name of the scheme you'd like to use from the list.</span></span> <span data-ttu-id="c32de-177">La opción **Esquema de partición existente** no estará disponible si no hay otros esquemas de partición en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c32de-177">The **Existing partition scheme** option will not be available if there are no other partition schemes on the database.</span></span>  
  
     <span data-ttu-id="c32de-178">Después de completar esta página, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c32de-178">After completing this page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="c32de-179">En la página **Asignar particiones** , debajo de **Intervalo**, seleccione **Límite izquierdo** o **Límite derecho** para especificar si se debe incluir el valor de límite superior o inferior de cada grupo de archivos que se crea.</span><span class="sxs-lookup"><span data-stu-id="c32de-179">On the **Map Partitions** page, under **Range**, select either **Left boundary** or **Right boundary** to specify whether to include the highest or lowest bounding value within each filegroup you create.</span></span> <span data-ttu-id="c32de-180">Siempre debe escribir un grupo de archivos adicional además de los que especifique para los valores de límite cuando cree las particiones.</span><span class="sxs-lookup"><span data-stu-id="c32de-180">You must always enter one extra filegroup in addition to the number of filegroups specified for the boundary values when you are creating partitions.</span></span>  
  
     <span data-ttu-id="c32de-181">En la cuadrícula **Seleccione grupos de archivos y especifique valores límite** , debajo de **Grupo de archivos**, seleccione el grupo de archivos en el que desea crear particiones de los datos.</span><span class="sxs-lookup"><span data-stu-id="c32de-181">In the **Select filegroups and specify boundary values** grid, under **Filegroup**, select the filegroup into which you want to partition your data.</span></span> <span data-ttu-id="c32de-182">Debajo de **Límite**, escriba el valor límite para cada grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="c32de-182">Under **Boundary**, enter the boundary value for each filegroup.</span></span> <span data-ttu-id="c32de-183">Si el valor límite está vacío, la función de partición asigna la tabla o el índice completos a una sola partición y usa el nombre de la función de partición.</span><span class="sxs-lookup"><span data-stu-id="c32de-183">If boundary value is left empty, the partition function maps the whole table or index into a single partition using the partition function name.</span></span>  
  
     <span data-ttu-id="c32de-184">En esta página están disponibles las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c32de-184">The following additional options are available on this page:</span></span>  
  
     <span data-ttu-id="c32de-185">**Establecer límites...**</span><span class="sxs-lookup"><span data-stu-id="c32de-185">**Set Boundaries...**</span></span>  
     <span data-ttu-id="c32de-186">Abre el cuadro de diálogo **Establecer valores límite** para seleccionar los valores límite y los rangos de fechas que desea para las particiones.</span><span class="sxs-lookup"><span data-stu-id="c32de-186">Opens the **Set Boundary Values** dialog box to select the boundary values and date ranges you want for your partitions.</span></span> <span data-ttu-id="c32de-187">Esta opción solo está disponible cuando ha seleccionado una columna de partición que contiene uno de los tipos de datos siguientes: `date`, `datetime`, `smalldatetime`, `datetime2` o `datetimeoffset`.</span><span class="sxs-lookup"><span data-stu-id="c32de-187">This option is only available when you have selected a partitioning column that contains one of the following data types: `date`, `datetime`, `smalldatetime`, `datetime2`, or `datetimeoffset`.</span></span>  
  
     <span data-ttu-id="c32de-188">**Estimar almacenamiento**</span><span class="sxs-lookup"><span data-stu-id="c32de-188">**Estimate storage**</span></span>  
     <span data-ttu-id="c32de-189">Calcula el número de filas, el espacio necesario y el espacio disponible para el almacenamiento de cada grupo de archivos especificado para las particiones.</span><span class="sxs-lookup"><span data-stu-id="c32de-189">Estimates rowcount, required space, and available space for storage for each filegroup specified for the partitions.</span></span> <span data-ttu-id="c32de-190">Estos valores se muestran en la cuadrícula como valores de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="c32de-190">These values are displayed in the grid as read-only values.</span></span>  
  
     <span data-ttu-id="c32de-191">El cuadro de diálogo **Establecer valores límite** admite las opciones adicionales siguientes:</span><span class="sxs-lookup"><span data-stu-id="c32de-191">The **Set Boundary Values** dialog box allows for the following additional options:</span></span>  
  
     <span data-ttu-id="c32de-192">**Fecha de inicio**</span><span class="sxs-lookup"><span data-stu-id="c32de-192">**Start date**</span></span>  
     <span data-ttu-id="c32de-193">Selecciona la fecha de inicio para los valores de rango de las particiones.</span><span class="sxs-lookup"><span data-stu-id="c32de-193">Selects the starting date for the range values of your partitions.</span></span>  
  
     <span data-ttu-id="c32de-194">**Fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="c32de-194">**End date**</span></span>  
     <span data-ttu-id="c32de-195">Selecciona la fecha de finalización para los valores de rango de las particiones.</span><span class="sxs-lookup"><span data-stu-id="c32de-195">Selects the ending date for the range values of your partitions.</span></span> <span data-ttu-id="c32de-196">Si ha seleccionado la opción **Límite izquierdo** en la página **Asignar particiones** , esta fecha será el último valor para cada grupo de archivos o partición.</span><span class="sxs-lookup"><span data-stu-id="c32de-196">If you selected **Left boundary** on the **Map Partitions** page, this date will be the last value for each filegroup/partition.</span></span> <span data-ttu-id="c32de-197">Si ha seleccionado la opción **Límite derecho** en la página **Asignar particiones** , esta fecha será el primer valor en el grupo de archivos siguiente al último.</span><span class="sxs-lookup"><span data-stu-id="c32de-197">If you selected **Right boundary** on the **Map Partitions** page, this date will be the first value in the next-to-last filegroup.</span></span>  
  
     <span data-ttu-id="c32de-198">**Intervalo de fechas**</span><span class="sxs-lookup"><span data-stu-id="c32de-198">**Date range**</span></span>  
     <span data-ttu-id="c32de-199">Selecciona la granularidad de fechas o el incremento de los valores de rango que desea para cada partición.</span><span class="sxs-lookup"><span data-stu-id="c32de-199">Selects the date granularity or range value increment you want for each partition.</span></span>  
  
     <span data-ttu-id="c32de-200">Después de completar esta página, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c32de-200">After completing this page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="c32de-201">En la página **Seleccionar la opción de salida** , especifique cómo desea completar la tabla con particiones.</span><span class="sxs-lookup"><span data-stu-id="c32de-201">In the **Select an Output Option** page, specify how you want to complete your partitioned table.</span></span> <span data-ttu-id="c32de-202">Seleccione **Crear script** para crear un script SQL basado en las páginas anteriores del asistente.</span><span class="sxs-lookup"><span data-stu-id="c32de-202">Select **Create Script** to create a SQL script based the previous pages in the wizard.</span></span> <span data-ttu-id="c32de-203">Seleccione **Ejecutar inmediatamente** para crear la nueva tabla con particiones después de completar todas las páginas restantes del asistente.</span><span class="sxs-lookup"><span data-stu-id="c32de-203">Select **Run immediately** to create the new partitioned table after completing all remaining pages in the wizard.</span></span> <span data-ttu-id="c32de-204">Seleccione **Programar** para crear la tabla con particiones en un momento predeterminado en el futuro.</span><span class="sxs-lookup"><span data-stu-id="c32de-204">Select **Schedule** to create the new partitioned table at a predetermined time in the future.</span></span>  
  
     <span data-ttu-id="c32de-205">Si selecciona **Crear script**, las opciones siguientes están disponibles debajo de **Opciones de script**:</span><span class="sxs-lookup"><span data-stu-id="c32de-205">If you select **Create script**, the following options are available under **Script options**:</span></span>  
  
     <span data-ttu-id="c32de-206">**Generar script en archivo**</span><span class="sxs-lookup"><span data-stu-id="c32de-206">**Script to file**</span></span>  
     <span data-ttu-id="c32de-207">Genera el script como un archivo .sql.</span><span class="sxs-lookup"><span data-stu-id="c32de-207">Generates the script as a .sql file.</span></span> <span data-ttu-id="c32de-208">Escriba un nombre de archivo y ubicación en el cuadro de diálogo **Nombre de archivo** o haga clic en **Examinar** para abrir **Ubicación del archivo script** .</span><span class="sxs-lookup"><span data-stu-id="c32de-208">Enter a file name and location in the **File name** box or click **Browse** to open the **Script File Location** dialog box.</span></span> <span data-ttu-id="c32de-209">En **Guardar como**, seleccione **Texto Unicode** o **Texto ANSI**.</span><span class="sxs-lookup"><span data-stu-id="c32de-209">From **Save As**, select **Unicode text** or **ANSI text**.</span></span>  
  
     <span data-ttu-id="c32de-210">**Generar script en Portapapeles**</span><span class="sxs-lookup"><span data-stu-id="c32de-210">**Script to Clipboard**</span></span>  
     <span data-ttu-id="c32de-211">Guarda el script en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="c32de-211">Saves the script to the Clipboard.</span></span>  
  
     <span data-ttu-id="c32de-212">**Generar script en la ventana Nueva consulta**</span><span class="sxs-lookup"><span data-stu-id="c32de-212">**Script to New Query Window**</span></span>  
     <span data-ttu-id="c32de-213">Genera el script en una nueva ventana del Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="c32de-213">Generates the script to a new Query Editor window.</span></span> <span data-ttu-id="c32de-214">Esta es la selección predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c32de-214">This is the default selection.</span></span>  
  
     <span data-ttu-id="c32de-215">Si selecciona **Programar**, haga clic en **Cambiar programación**.</span><span class="sxs-lookup"><span data-stu-id="c32de-215">If you select **Schedule**, click **Change schedule**.</span></span>  
  
    1.  <span data-ttu-id="c32de-216">En el cuadro de diálogo **Nueva programación de trabajo**, en el cuadro **Nombre**, escriba el nombre de la programación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c32de-216">In the **New Job Schedule** dialog box, in the **Name** box, enter the job schedule's name.</span></span>  
  
    2.  <span data-ttu-id="c32de-217">En la lista **Tipo de programación** , seleccione el tipo de la programación:</span><span class="sxs-lookup"><span data-stu-id="c32de-217">On the **Schedule type** list, select the type of schedule:</span></span>  
  
        -   <span data-ttu-id="c32de-218">**Iniciar automáticamente al iniciar el Agente SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="c32de-218">**Start automatically when SQL Server Agent starts**</span></span>  
  
        -   <span data-ttu-id="c32de-219">**Iniciar al quedar inactivas las CPU**</span><span class="sxs-lookup"><span data-stu-id="c32de-219">**Start whenever the CPUs become idle**</span></span>  
  
        -   <span data-ttu-id="c32de-220">**Periódica**.</span><span class="sxs-lookup"><span data-stu-id="c32de-220">**Recurring**.</span></span> <span data-ttu-id="c32de-221">Seleccione esta opción si la nueva tabla con particiones se actualiza con la nueva información de forma regular.</span><span class="sxs-lookup"><span data-stu-id="c32de-221">Select this option if your new partitioned table updates with new information on a regular basis.</span></span>  
  
        -   <span data-ttu-id="c32de-222">**Una vez**.</span><span class="sxs-lookup"><span data-stu-id="c32de-222">**One time**.</span></span> <span data-ttu-id="c32de-223">Esta es la selección predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c32de-223">This is the default selection.</span></span>  
  
    3.  <span data-ttu-id="c32de-224">Active o desactive la casilla **Habilitado** para habilitar o deshabilitar la programación.</span><span class="sxs-lookup"><span data-stu-id="c32de-224">Select or clear the **Enabled** check box to enable or disable the schedule.</span></span>  
  
    4.  <span data-ttu-id="c32de-225">Si selecciona **Periódica**:</span><span class="sxs-lookup"><span data-stu-id="c32de-225">If you select **Recurring**:</span></span>  
  
        1.  <span data-ttu-id="c32de-226">En **Frecuencia**, en la lista **Sucede** , especifique la frecuencia de repetición:</span><span class="sxs-lookup"><span data-stu-id="c32de-226">Under **Frequency**, on the **Occurs** list, specify the frequency of occurrence:</span></span>  
  
            -   <span data-ttu-id="c32de-227">Si selecciona **Diario**, en el cuadro **Se repite cada** , escriba la frecuencia con que se repite la programación de trabajo en días.</span><span class="sxs-lookup"><span data-stu-id="c32de-227">If you select **Daily**, in the **Recurs every** box, enter how often the job schedule repeats in days.</span></span>  
  
            -   <span data-ttu-id="c32de-228">Si selecciona **Semanal**, en el cuadro **Se repite cada** , escriba la frecuencia con que se repite la programación de trabajo en semanas.</span><span class="sxs-lookup"><span data-stu-id="c32de-228">If you select **Weekly**, in the **Recurs every** box, enter how often the job schedule repeats in weeks.</span></span> <span data-ttu-id="c32de-229">Seleccione el día o días de la semana en que se ejecuta la programación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c32de-229">Select the day or days of the week on which the job schedule is run.</span></span>  
  
            -   <span data-ttu-id="c32de-230">Si selecciona **Mensual**, seleccione **Día** o **El**.</span><span class="sxs-lookup"><span data-stu-id="c32de-230">If you select **Monthly**, select either **Day** or **The**.</span></span>  
  
                -   <span data-ttu-id="c32de-231">Si selecciona **Día**, especifique la fecha del mes que desea que se ejecute la programación de trabajo y con qué frecuencia debe repetirse la programación de trabajo en meses.</span><span class="sxs-lookup"><span data-stu-id="c32de-231">If you select **Day**, enter both the date of the month you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="c32de-232">Por ejemplo, si quiere que la programación de trabajo se ejecute el decimoquinto día de cada mes, seleccione **Día** y escriba "15" en el primer cuadro y "2" en el segundo.</span><span class="sxs-lookup"><span data-stu-id="c32de-232">For example, if you want the job schedule to run on the 15th day of the month every other month, select **Day** and enter "15" in the first box and "2" in the second box.</span></span> <span data-ttu-id="c32de-233">Tenga en cuenta que el mayor número permitido en el segundo cuadro es "99".</span><span class="sxs-lookup"><span data-stu-id="c32de-233">Please note that the largest number allowed in the second box is "99".</span></span>  
  
                -   <span data-ttu-id="c32de-234">Si selecciona **El**, seleccione el día concreto de la semana del mes en que desea que se ejecute la programación de trabajo y con qué frecuencia debe repetirse la programación de trabajo en meses.</span><span class="sxs-lookup"><span data-stu-id="c32de-234">If you select **The**, select the specific day of the week within the month that you want the job schedule to run and how often the job schedule repeats in months.</span></span> <span data-ttu-id="c32de-235">Por ejemplo, si quiere que la programación de trabajo se ejecute el último día de la semana de cada mes, seleccione **Día**, seleccione **último** en la primera lista y **día de la semana** en la segunda y, después, escriba "2" en el último cuadro.</span><span class="sxs-lookup"><span data-stu-id="c32de-235">For example, if you want the job schedule to run on the last weekday of the month every other month, select **Day**, select **last** from the first list and **weekday** from the second list, and then enter "2" in the last box.</span></span> <span data-ttu-id="c32de-236">En las primeras dos listas, también puede seleccionar **primero**, **segundo**, **tercero**o **cuarto**, así como días de la semana concretos (por ejemplo: domingo o miércoles).</span><span class="sxs-lookup"><span data-stu-id="c32de-236">You can also select **first**, **second**, **third**, or **fourth**, as well as specific weekdays (for example: Sunday or Wednesday) from the first two lists.</span></span> <span data-ttu-id="c32de-237">Tenga en cuenta que el mayor número permitido en el último cuadro es "99".</span><span class="sxs-lookup"><span data-stu-id="c32de-237">Please note that the largest number allowed in the last box is "99".</span></span>  
  
        2.  <span data-ttu-id="c32de-238">Debajo de **Frecuencia diaria**, especifique la frecuencia con que se repite la programación de trabajo en el día en que se ejecuta:</span><span class="sxs-lookup"><span data-stu-id="c32de-238">Under **Daily frequency**, specify how often the job schedule repeats on the day the job schedule runs:</span></span>  
  
            -   <span data-ttu-id="c32de-239">Si selecciona **Sucede una vez a las**, escriba la hora concreta en que debe ejecutarse la programación de trabajo en el cuadro **Sucede una vez a las** .</span><span class="sxs-lookup"><span data-stu-id="c32de-239">If you select **Occurs once at**, enter the specific time of day when the job schedule should run in the **Occurs once at** box.</span></span> <span data-ttu-id="c32de-240">Especifique la hora, minuto y segundo del día, así como a.m. o p.m.</span><span class="sxs-lookup"><span data-stu-id="c32de-240">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
            -   <span data-ttu-id="c32de-241">Si selecciona **Sucede cada**, especifique la frecuencia con que se ejecuta la programación de trabajo durante el día seleccionado en **Frecuencia**.</span><span class="sxs-lookup"><span data-stu-id="c32de-241">If you select **Occurs every**, specify how often the job schedule runs during the day chosen under **Frequency**.</span></span> <span data-ttu-id="c32de-242">Por ejemplo, si quiere que la programación de trabajo se repita cada dos horas al día cuando se ejecuta, seleccione **Sucede cada**, escriba "2" en el primer cuadro y, después, seleccione **horas** en la lista.</span><span class="sxs-lookup"><span data-stu-id="c32de-242">For example, if you want the job schedule to repeat every 2 hours during the day that the job schedule is run, select **Occurs every**, enter "2" in the first box, and then select **hour(s)** from the list.</span></span> <span data-ttu-id="c32de-243">En esta lista también puede seleccionar **minutos** y **segundos**.</span><span class="sxs-lookup"><span data-stu-id="c32de-243">From this list you can also select **minute(s)** and **second(s)**.</span></span> <span data-ttu-id="c32de-244">Tenga en cuenta que el mayor número permitido en el primer cuadro es "100".</span><span class="sxs-lookup"><span data-stu-id="c32de-244">Please note that the largest number allowed in the first box is "100".</span></span>  
  
                 <span data-ttu-id="c32de-245">En el cuadro **A partir de** , especifique la hora en que la programación de trabajo debe iniciar su ejecución.</span><span class="sxs-lookup"><span data-stu-id="c32de-245">In the **Starting at** box, enter the time that the job schedule should start running.</span></span> <span data-ttu-id="c32de-246">En el cuadro **Finaliza** , especifique la hora en que la programación de trabajo debe dejar de repetirse.</span><span class="sxs-lookup"><span data-stu-id="c32de-246">In the **Ending at** box, enter the time that the job schedule should stop repeating.</span></span> <span data-ttu-id="c32de-247">Especifique la hora, minuto y segundo del día, así como a.m. o p.m.</span><span class="sxs-lookup"><span data-stu-id="c32de-247">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
        3.  <span data-ttu-id="c32de-248">Debajo de **Duración**, en **Fecha de inicio**, escriba la fecha en que desea que la programación de trabajo inicie su ejecución.</span><span class="sxs-lookup"><span data-stu-id="c32de-248">Under **Duration**, in **Start date**, enter the date that you want the job schedule to start running.</span></span> <span data-ttu-id="c32de-249">Seleccione **Fecha de finalización** o **Sin fecha de finalización** para indicar cuándo se debe detener la ejecución de la programación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c32de-249">Select **End date** or **No end date** to indicate when the job schedule should stop running.</span></span> <span data-ttu-id="c32de-250">Si selecciona **Fecha de finalización**, escriba la fecha en que desea que deje de ejecutarse la programación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c32de-250">If you select **End date**, enter the date that you want to job schedule to stop running.</span></span>  
  
    5.  <span data-ttu-id="c32de-251">Si selecciona **Una vez**, debajo de **Única repetición**, en el cuadro **Fecha** , escriba la fecha en que se ejecutará la programación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c32de-251">If you select **One Time**, under **One-time occurrence**, in the **Date** box, enter the date that the job schedule will be run.</span></span> <span data-ttu-id="c32de-252">En el cuadro **Hora** , especifique la hora a la que se ejecutará la programación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c32de-252">In the **Time** box, enter the time that the job schedule will be run.</span></span> <span data-ttu-id="c32de-253">Especifique la hora, minuto y segundo del día, así como a.m. o p.m.</span><span class="sxs-lookup"><span data-stu-id="c32de-253">Enter the hour, minute, and second of the day, as well as AM or PM.</span></span>  
  
    6.  <span data-ttu-id="c32de-254">Debajo de **Resumen**, en **Descripción**, compruebe que todos los valores de la programación de trabajo son correctos.</span><span class="sxs-lookup"><span data-stu-id="c32de-254">Under **Summary**, in **Description**, verify that all job schedule settings are correct.</span></span>  
  
    7.  <span data-ttu-id="c32de-255">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="c32de-255">Click **OK**.</span></span>  
  
     <span data-ttu-id="c32de-256">Después de completar esta página, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c32de-256">After completing this page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="c32de-257">En la página **Revisar resumen** , debajo de **Revisar opciones seleccionadas**, expanda todas las opciones disponibles para comprobar que todos los valores de la partición son correctos.</span><span class="sxs-lookup"><span data-stu-id="c32de-257">On the **Review Summary** page, under **Review your selections**, expand all available options to verify that all partition settings are correct.</span></span> <span data-ttu-id="c32de-258">Si todo está como se esperaba, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="c32de-258">If everything is as expected, click **Finish**.</span></span>  
  
9. <span data-ttu-id="c32de-259">En la página **Progreso del Asistente para la creación de particiones** , supervise la información de estado sobre las acciones del Asistente para la creación de particiones.</span><span class="sxs-lookup"><span data-stu-id="c32de-259">On the **Create Partition Wizard Progress** page, monitor status information about the actions of the Create Partition Wizard.</span></span> <span data-ttu-id="c32de-260">Según las opciones que se seleccionen en el asistente, la página de progreso puede contener una o varias acciones.</span><span class="sxs-lookup"><span data-stu-id="c32de-260">Depending on the options that you selected in the wizard, the progress page might contain one or more actions.</span></span> <span data-ttu-id="c32de-261">El cuadro superior muestra el estado general del asistente y el número de mensajes de estado, error y advertencia que ha recibido.</span><span class="sxs-lookup"><span data-stu-id="c32de-261">The top box displays the overall status of the wizard and the number of status, error, and warning messages that the wizard has received.</span></span>  
  
     <span data-ttu-id="c32de-262">Las siguientes opciones están disponibles en la página **Progreso del Asistente para la creación de particiones** :</span><span class="sxs-lookup"><span data-stu-id="c32de-262">The following options are available on the **Create Partition Wizard Progress** page:</span></span>  
  
     <span data-ttu-id="c32de-263">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="c32de-263">**Details**</span></span>  
     <span data-ttu-id="c32de-264">Proporciona la acción, el estado y los mensajes devueltos por la acción llevada a cabo por el asistente.</span><span class="sxs-lookup"><span data-stu-id="c32de-264">Provides the action, status, and any messages that are returned from action taken by the wizard.</span></span>  
  
     <span data-ttu-id="c32de-265">**Acción**</span><span class="sxs-lookup"><span data-stu-id="c32de-265">**Action**</span></span>  
     <span data-ttu-id="c32de-266">Especifica el tipo y el nombre de cada acción.</span><span class="sxs-lookup"><span data-stu-id="c32de-266">Specifies the type and name of each action.</span></span>  
  
     <span data-ttu-id="c32de-267">**Estado**</span><span class="sxs-lookup"><span data-stu-id="c32de-267">**Status**</span></span>  
     <span data-ttu-id="c32de-268">Indica si la acción del asistente como conjunto ha devuelto el valor **Correcto** o **Error**.</span><span class="sxs-lookup"><span data-stu-id="c32de-268">Indicates whether the wizard action as a whole returned the value of **Success** or **Failure**.</span></span>  
  
     <span data-ttu-id="c32de-269">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="c32de-269">**Message**</span></span>  
     <span data-ttu-id="c32de-270">Proporciona los mensajes de error o de advertencia devueltos por el proceso.</span><span class="sxs-lookup"><span data-stu-id="c32de-270">Provides any error or warning messages that are returned from the process.</span></span>  
  
     <span data-ttu-id="c32de-271">**Report**</span><span class="sxs-lookup"><span data-stu-id="c32de-271">**Report**</span></span>  
     <span data-ttu-id="c32de-272">Crea un informe que contiene los resultados del Asistente para la creación de particiones.</span><span class="sxs-lookup"><span data-stu-id="c32de-272">Creates a report that contains the results of the Create Partition Wizard.</span></span> <span data-ttu-id="c32de-273">Las opciones son **Ver informe**, **Guardar informe en archivo**, **Copiar informe al Portapapeles**y **Enviar informe como correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="c32de-273">The options are **View Report**, **Save Report to File**, **Copy Report to Clipboard**, and **Send Report as Email**.</span></span>  
  
     <span data-ttu-id="c32de-274">**Ver informe**</span><span class="sxs-lookup"><span data-stu-id="c32de-274">**View Report**</span></span>  
     <span data-ttu-id="c32de-275">Abre el cuadro de diálogo **Ver informe** , que contiene un informe de texto del progreso del Asistente para la creación de particiones.</span><span class="sxs-lookup"><span data-stu-id="c32de-275">Opens the **View Report** dialog box, which contains a text report of the progress of the Create Partition Wizard.</span></span>  
  
     <span data-ttu-id="c32de-276">**Guardar informe en archivo**</span><span class="sxs-lookup"><span data-stu-id="c32de-276">**Save Report to File**</span></span>  
     <span data-ttu-id="c32de-277">Abre el cuadro de diálogo **Guardar informe como** .</span><span class="sxs-lookup"><span data-stu-id="c32de-277">Opens the **Save Report As** dialog box.</span></span>  
  
     <span data-ttu-id="c32de-278">**Copiar informe al Portapapeles**</span><span class="sxs-lookup"><span data-stu-id="c32de-278">**Copy Report to Clipboard**</span></span>  
     <span data-ttu-id="c32de-279">Copia los resultados del informe de progreso del asistente al Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="c32de-279">Copies the results of the wizard's progress report to the Clipboard.</span></span>  
  
     <span data-ttu-id="c32de-280">**Enviar informe como correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="c32de-280">**Send Report as Email**</span></span>  
     <span data-ttu-id="c32de-281">Copia los resultados del informe de progreso del asistente en un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c32de-281">Copies the results of the wizard's progress report into an email message.</span></span>  
  
     <span data-ttu-id="c32de-282">Cuando termine, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="c32de-282">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="c32de-283">El Asistente para la creación de particiones crea la función y el esquema de partición y aplica las particiones a la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="c32de-283">The Create Partition Wizard creates the partition function and scheme and then applies the partitioning to the specified table.</span></span> <span data-ttu-id="c32de-284">Para comprobar las particiones de tabla, en el Explorador de objetos, haga clic con el botón derecho en la tabla y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c32de-284">To verify the table partitioning, in Object Explorer, right-click the table and select **Properties**.</span></span> <span data-ttu-id="c32de-285">Haga clic en la página **Almacenamiento** .</span><span class="sxs-lookup"><span data-stu-id="c32de-285">Click the **Storage** page.</span></span> <span data-ttu-id="c32de-286">La página muestra información como el nombre de la función y el esquema de partición y el número de particiones.</span><span class="sxs-lookup"><span data-stu-id="c32de-286">The page displays information such as the name of the partition function and scheme and the number of partitions.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c32de-287">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c32de-287">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-partitioned-table"></a><span data-ttu-id="c32de-288">Para crear una tabla con particiones</span><span class="sxs-lookup"><span data-stu-id="c32de-288">To create a partitioned table</span></span>  
  
1.  <span data-ttu-id="c32de-289">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c32de-289">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c32de-290">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="c32de-290">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c32de-291">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c32de-291">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c32de-292">En el ejemplo se crean nuevos grupos de archivos, una función de partición y un esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="c32de-292">The example creates new filegroups, a partition function, and a partition scheme.</span></span> <span data-ttu-id="c32de-293">Se crea una nueva tabla con el esquema de partición especificado como ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="c32de-293">A new table is created with the partition scheme specified as the storage location.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Adds four new filegroups to the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test1fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test4fg;   
  
    -- Adds one file for each filegroup.  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test1dat1,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t1dat1.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test1fg;  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test2dat2,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t2dat2.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test2fg;  
    GO  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test3dat3,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t3dat3.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test3fg;  
    GO  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = test4dat4,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\t4dat4.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP test4fg;  
    GO  
    -- Creates a partition function called myRangePF1 that will partition a table into four partitions  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
        AS RANGE LEFT FOR VALUES (1, 100, 1000) ;  
    GO  
    -- Creates a partition scheme called myRangePS1 that applies myRangePF1 to the four filegroups created above  
    CREATE PARTITION SCHEME myRangePS1  
        AS PARTITION myRangePF1  
        TO (test1fg, test2fg, test3fg, test4fg) ;  
    GO  
    -- Creates a partitioned table called PartitionTable that uses myRangePS1 to partition col1  
    CREATE TABLE PartitionTable (col1 int PRIMARY KEY, col2 char(10))  
        ON myRangePS1 (col1) ;  
    GO  
    ```  
  
#### <a name="to-determine-if-a-table-is-partitioned"></a><span data-ttu-id="c32de-294">Para determinar si se crean particiones de una tabla</span><span class="sxs-lookup"><span data-stu-id="c32de-294">To determine if a table is partitioned</span></span>  
  
1.  <span data-ttu-id="c32de-295">La consulta siguiente devuelve una o más filas si la tabla tiene particiones `PartitionTable` .</span><span class="sxs-lookup"><span data-stu-id="c32de-295">The following query returns one or more rows if the table `PartitionTable` is partitioned.</span></span> <span data-ttu-id="c32de-296">Si la tabla no tiene particiones, no se devuelve ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="c32de-296">If the table is not partitioned, no rows are returned.</span></span>  
  
    ```  
    SELECT *   
    FROM sys.tables AS t   
    JOIN sys.indexes AS i   
        ON t.[object_id] = i.[object_id]   
        AND i.[type] IN (0,1)   
    JOIN sys.partition_schemes ps   
        ON i.data_space_id = ps.data_space_id   
    WHERE t.name = 'PartitionTable';   
    GO  
    ```  
  
#### <a name="to-determine-the-boundary-values-for-a-partitioned-table"></a><span data-ttu-id="c32de-297">Para determinar los valores de límite para una tabla con particiones</span><span class="sxs-lookup"><span data-stu-id="c32de-297">To determine the boundary values for a partitioned table</span></span>  
  
1.  <span data-ttu-id="c32de-298">La consulta siguiente devuelve los valores de límite para cada partición de la tabla `PartitionTable` .</span><span class="sxs-lookup"><span data-stu-id="c32de-298">The following query returns the boundary values for each partition in the `PartitionTable` table.</span></span>  
  
    ```  
    SELECT t.name AS TableName, i.name AS IndexName, p.partition_number, p.partition_id, i.data_space_id, f.function_id, f.type_desc, r.boundary_id, r.value AS BoundaryValue   
    FROM sys.tables AS t  
    JOIN sys.indexes AS i  
        ON t.object_id = i.object_id  
    JOIN sys.partitions AS p  
        ON i.object_id = p.object_id AND i.index_id = p.index_id   
    JOIN  sys.partition_schemes AS s   
        ON i.data_space_id = s.data_space_id  
    JOIN sys.partition_functions AS f   
        ON s.function_id = f.function_id  
    LEFT JOIN sys.partition_range_values AS r   
        ON f.function_id = r.function_id and r.boundary_id = p.partition_number  
    WHERE t.name = 'PartitionTable' AND i.type <= 1  
    ORDER BY p.partition_number;  
    ```  
  
#### <a name="to-determine-the-partition-column-for-a-partitioned-table"></a><span data-ttu-id="c32de-299">Para determinar la columna de partición de una tabla con particiones</span><span class="sxs-lookup"><span data-stu-id="c32de-299">To determine the partition column for a partitioned table</span></span>  
  
1.  <span data-ttu-id="c32de-300">La consulta siguiente devuelve el nombre de la columna de partición de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c32de-300">The following query returns the name of the partitioning column for table.</span></span> <span data-ttu-id="c32de-301">`PartitionTable`.</span><span class="sxs-lookup"><span data-stu-id="c32de-301">`PartitionTable`.</span></span>  
  
    ```  
    SELECT   
        t.[object_id] AS ObjectID   
        , t.name AS TableName   
        , ic.column_id AS PartitioningColumnID   
        , c.name AS PartitioningColumnName   
    FROM sys.tables AS t   
    JOIN sys.indexes AS i   
        ON t.[object_id] = i.[object_id]   
        AND i.[type] <= 1 -- clustered index or a heap   
    JOIN sys.partition_schemes AS ps   
        ON ps.data_space_id = i.data_space_id   
    JOIN sys.index_columns AS ic   
        ON ic.[object_id] = i.[object_id]   
        AND ic.index_id = i.index_id   
        AND ic.partition_ordinal >= 1 -- because 0 = non-partitioning column   
    JOIN sys.columns AS c   
        ON t.[object_id] = c.[object_id]   
        AND ic.column_id = c.column_id   
    WHERE t.name = 'PartitionTable' ;   
    GO  
    ```  
  
 <span data-ttu-id="c32de-302">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="c32de-302">For more information, see:</span></span>  
  
-   [<span data-ttu-id="c32de-303">Opciones File y Filegroup de ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c32de-303">ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options)  
  
-   [<span data-ttu-id="c32de-304">CREATE PARTITION FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c32de-304">CREATE PARTITION FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-partition-function-transact-sql)  
  
-   [<span data-ttu-id="c32de-305">CREATE PARTITION SCHEME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c32de-305">CREATE PARTITION SCHEME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-partition-scheme-transact-sql)  
  
-   [<span data-ttu-id="c32de-306">CREATE TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c32de-306">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
  
