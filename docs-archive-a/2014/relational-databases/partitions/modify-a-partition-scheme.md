---
title: Modificación de un esquema de partición | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 515de63f-dfc5-434d-9adb-f3b5992f745a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d57984228e23143d2061df6bf447f978f9bd3c46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674785"
---
# <a name="modify-a-partition-scheme"></a><span data-ttu-id="fc865-102">Modificar un esquema de partición</span><span class="sxs-lookup"><span data-stu-id="fc865-102">Modify a Partition Scheme</span></span>
  <span data-ttu-id="fc865-103">Para modificar un esquema de partición en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , puede diseñar un grupo de archivos que contenga la siguiente partición que se agregará a la tabla con particiones mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc865-103">You can modify a partition scheme in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by designating a filegroup to hold the next partition that is added to a partitioned table using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="fc865-104">Para hacerlo debe asignar la propiedad NEXT USED a un grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="fc865-104">You do this by assigning the NEXT USED property to a filegroup.</span></span> <span data-ttu-id="fc865-105">Puede asignar la propiedad NEXT USED a un grupo de archivos vacío o a uno que ya contenga una partición.</span><span class="sxs-lookup"><span data-stu-id="fc865-105">You can assign the NEXT USED property to an empty filegroup or to one that already holds a partition.</span></span> <span data-ttu-id="fc865-106">Es decir, un grupo de archivos puede tener más de una partición.</span><span class="sxs-lookup"><span data-stu-id="fc865-106">In other words, a filegroup can hold more than one partition.</span></span>  
  
 <span data-ttu-id="fc865-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="fc865-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fc865-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="fc865-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fc865-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="fc865-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="fc865-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fc865-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fc865-111">**Para crear una tabla o un índice con particiones, use:**</span><span class="sxs-lookup"><span data-stu-id="fc865-111">**To create a partitioned table or index, using:**</span></span>  
  
     [<span data-ttu-id="fc865-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fc865-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fc865-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fc865-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fc865-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="fc865-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="fc865-115">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="fc865-115">Limitations and Restrictions</span></span>  
 <span data-ttu-id="fc865-116">Los grupos de archivos afectados por ALTER PARTITION SCHEME deben estar en línea.</span><span class="sxs-lookup"><span data-stu-id="fc865-116">Any filegroup affected by ALTER PARTITION SCHEME must be online.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fc865-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fc865-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fc865-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="fc865-118">Permissions</span></span>  
 <span data-ttu-id="fc865-119">Los siguientes permisos pueden utilizarse para ejecutar ALTER PARTITION SCHEME:</span><span class="sxs-lookup"><span data-stu-id="fc865-119">The following permissions can be used to execute ALTER PARTITION SCHEME:</span></span>  
  
-   <span data-ttu-id="fc865-120">Permiso ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="fc865-120">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="fc865-121">De forma predeterminada, este permiso corresponde a los miembros del rol fijo de servidor **sysadmin** y a los roles fijos de base de datos **db_owner** y **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="fc865-121">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="fc865-122">Permiso CONTROL o ALTER en la base de datos en la que se ha creado el esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="fc865-122">CONTROL or ALTER permission on the database in which the partition scheme was created.</span></span>  
  
-   <span data-ttu-id="fc865-123">Permiso CONTROL SERVER o ALTER ANY DATABASE en el servidor de la base de datos en la que se ha creado el esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="fc865-123">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition scheme was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fc865-124">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fc865-124">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="fc865-125">**Para modificar un esquema de partición:**</span><span class="sxs-lookup"><span data-stu-id="fc865-125">**To modify a partition scheme:**</span></span>  
  
 <span data-ttu-id="fc865-126">Esta acción específica no se puede realizar mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc865-126">This specific action cannot be performed using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="fc865-127">Para modificar un esquema de partición, primero debe eliminar el esquema y después crear uno nuevo con las propiedades deseadas mediante el Asistente para la creación de particiones.</span><span class="sxs-lookup"><span data-stu-id="fc865-127">In order to modify a partition scheme, you must first delete the scheme and then create a new one with the desired properties using the Create Partition Wizard.</span></span> <span data-ttu-id="fc865-128">Para obtener más información, vea [crear tablas e índices con particiones mediante SQL Server Management Studio](create-partitioned-tables-and-indexes.md#SSMSProcedure) en **crear tablas e índices con particiones**.</span><span class="sxs-lookup"><span data-stu-id="fc865-128">For more information, see [Create Partitioned Tables and Indexes Using SQL Server Management Studio](create-partitioned-tables-and-indexes.md#SSMSProcedure) under **Create Partitioned Tables and Indexes**.</span></span>  
  
#### <a name="to-delete-a-partition-scheme"></a><span data-ttu-id="fc865-129">Para eliminar un esquema de partición</span><span class="sxs-lookup"><span data-stu-id="fc865-129">To delete a partition scheme</span></span>  
  
1.  <span data-ttu-id="fc865-130">Haga clic en el signo más para expandir la base de datos donde desea eliminar el esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="fc865-130">Click the plus sign to expand the database where you want to delete the partition scheme.</span></span>  
  
2.  <span data-ttu-id="fc865-131">Haga clic en el signo más para expandir la carpeta **Almacenamiento** .</span><span class="sxs-lookup"><span data-stu-id="fc865-131">Click the plus sign to expand the **Storage** folder.</span></span>  
  
3.  <span data-ttu-id="fc865-132">Haga clic en el signo más para expandir la carpeta **Esquemas de partición** .</span><span class="sxs-lookup"><span data-stu-id="fc865-132">Click the plus sign to expand the **Partition Schemes** folder.</span></span>  
  
4.  <span data-ttu-id="fc865-133">Haga clic con el botón derecho en el esquema de partición que quiere eliminar y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="fc865-133">Right-click the partition scheme you want to delete and select **Delete**.</span></span>  
  
5.  <span data-ttu-id="fc865-134">En el cuadro de diálogo **Eliminar objeto** , asegúrese de que está seleccionado el esquema de partición correcta y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fc865-134">In the **Delete Object** dialog box, ensure that the correct partition scheme is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fc865-135">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fc865-135">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-a-partition-scheme"></a><span data-ttu-id="fc865-136">Para modificar un esquema de partición</span><span class="sxs-lookup"><span data-stu-id="fc865-136">To modify a partition scheme</span></span>  
  
1.  <span data-ttu-id="fc865-137">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc865-137">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fc865-138">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="fc865-138">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fc865-139">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="fc865-139">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- add five new filegroups to the AdventureWorks2012 database  
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
    GO  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP test5fg;  
    GO  
    -- if the "myRangePF1" partition function and the "myRangePS1" partition scheme exist,  
    -- drop them from the AdventureWorks2012 database  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
    DROP PARTITION FUNCTION myRangePF1;  
    GO  
    IF EXISTS (SELECT * FROM sys.partition_schemes  
        WHERE name = 'myRangePS1')  
    DROP PARTITION SCHEME myRangePS1;  
    GO  
    -- create the new partition function "myRangePF1" with four partition groups  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    -- create the new partition scheme "myRangePS1"that will use   
    -- the "myRangePF1" partition function with five file groups.  
    -- The last filegroup, "test5fg," will be kept empty but marked  
    -- as the next used filegroup in the partition scheme.  
    CREATE PARTITION SCHEME myRangePS1  
    AS PARTITION myRangePF1  
    TO (test1fg, test2fg, test3fg, test4fg, test5fg);  
    GO  
    --Split "myRangePS1" between boundary_values 100 and 1000  
    --to create two partitions between boundary_values 100 and 500  
    --and between boundary_values 500 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    SPLIT RANGE (500);  
    GO  
    -- Allow the "myRangePS1" partition scheme to use the filegroup "test5fg"  
    -- for the partition with boundary_values of 100 and 500  
    ALTER PARTITION SCHEME myRangePS1  
    NEXT USED test5fg;  
    GO  
    ```  
  
 <span data-ttu-id="fc865-140">Para obtener más información, vea [ALTER PARTITION SCHEME &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-scheme-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fc865-140">For more information, see [ALTER PARTITION SCHEME &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-scheme-transact-sql).</span></span>  
  
  
