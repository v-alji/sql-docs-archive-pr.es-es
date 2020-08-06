---
title: Modificación de una función de partición | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: ae5bfc09-f27a-4ea9-9518-485278b11674
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: bf14e633e62839b1abca7f38f833efab933c18f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744668"
---
# <a name="modify-a-partition-function"></a><span data-ttu-id="b1c45-102">Modificar una función de partición</span><span class="sxs-lookup"><span data-stu-id="b1c45-102">Modify a Partition Function</span></span>
  <span data-ttu-id="b1c45-103">Puede cambiar el modo en que se crean las particiones de una tabla o un índice en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] al sumar o restar el número de particiones especificadas, en aumentos de 1, en la función de partición de la tabla o el índice con particiones mediante [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1c45-103">You can change the way a table or index is partitioned in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by adding or subtracting the number of partitions specified, in increments of 1, in the partition function of the partitioned table or index by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b1c45-104">Lo que sucede al agregar una partición es que se "divide" una partición existente en dos particiones y se vuelven a definir los límites de las particiones nuevas.</span><span class="sxs-lookup"><span data-stu-id="b1c45-104">When you add a partition, you do so by "splitting" an existing partition into two partitions and redefining the boundaries of the new partitions.</span></span> <span data-ttu-id="b1c45-105">Al quitar una partición, se "mezclan" los límites de dos particiones en una sola.</span><span class="sxs-lookup"><span data-stu-id="b1c45-105">When you drop a partition, you do so by "merging" the boundaries of two partitions into one.</span></span> <span data-ttu-id="b1c45-106">Lo que hace esta última acción es volver a llenar una partición y dejar la otra sin asignar.</span><span class="sxs-lookup"><span data-stu-id="b1c45-106">This last action repopulates one partition and leaves the other partition unassigned.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="b1c45-107">Varias tablas o índices pueden utilizar la misma función de partición.</span><span class="sxs-lookup"><span data-stu-id="b1c45-107">More than one table or index can use the same partition function.</span></span> <span data-ttu-id="b1c45-108">Cuando se modifica una función de partición, afecta a todas las funciones en una sola transacción.</span><span class="sxs-lookup"><span data-stu-id="b1c45-108">When you modify a partition function, you affect all of them in a single transaction.</span></span> <span data-ttu-id="b1c45-109">Compruebe las dependencias de la función de partición antes de modificarla.</span><span class="sxs-lookup"><span data-stu-id="b1c45-109">Check the partition function's dependencies before modifying it.</span></span>  
  
 <span data-ttu-id="b1c45-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="b1c45-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b1c45-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="b1c45-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b1c45-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="b1c45-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b1c45-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b1c45-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b1c45-114">**Para modificar una función de partición, use:**</span><span class="sxs-lookup"><span data-stu-id="b1c45-114">**To modify a partition function, using:**</span></span>  
  
     [<span data-ttu-id="b1c45-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b1c45-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b1c45-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b1c45-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b1c45-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="b1c45-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b1c45-118">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="b1c45-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b1c45-119">ALTER PARTITION FUNCTION solo se puede utilizar para dividir en dos una partición o para mezclar dos particiones en una sola.</span><span class="sxs-lookup"><span data-stu-id="b1c45-119">ALTER PARTITION FUNCTION can only be used for splitting one partition into two, or for merging two partitions into one.</span></span> <span data-ttu-id="b1c45-120">Para cambiar el modo en que se crean las particiones de una tabla o un índice (de 10 a 5 particiones, por ejemplo) puede recurrir a cualquiera de las opciones que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="b1c45-120">To change the way a table or index is partitioned (from 10 partitions to 5, for example), you can use any one of the following options:</span></span>  
  
    -   <span data-ttu-id="b1c45-121">Cree una nueva tabla con particiones con la función de partición deseada y, a continuación, inserte los datos de la tabla antigua en la tabla nueva mediante la instrucción INSERT INTO... SELECT FROM [!INCLUDE[tsql](../../includes/tsql-md.md)] o con el **Asistente para administrar particiones** en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1c45-121">Create a new partitioned table with the desired partition function, and then insert the data from the old table into the new table by using either an INSERT INTO ... SELECT FROM [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or the **Manage Partition Wizard** in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
    -   <span data-ttu-id="b1c45-122">Cree un índice clúster con particiones en un montón.</span><span class="sxs-lookup"><span data-stu-id="b1c45-122">Create a partitioned clustered index on a heap.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b1c45-123">El resultado de quitar un índice clúster con particiones es un montón con particiones.</span><span class="sxs-lookup"><span data-stu-id="b1c45-123">Dropping a partitioned clustered index results in a partitioned heap.</span></span>  
  
    -   <span data-ttu-id="b1c45-124">Quite y vuelva a generar un índice con particiones existente mediante la instrucción CREATE INDEX de [!INCLUDE[tsql](../../includes/tsql-md.md)] con la cláusula DROP EXISTING = ON.</span><span class="sxs-lookup"><span data-stu-id="b1c45-124">Drop and rebuild an existing partitioned index by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX statement with the DROP EXISTING = ON clause.</span></span>  
  
    -   <span data-ttu-id="b1c45-125">Ejecute una secuencia de instrucciones ALTER PARTITION FUNCTION.</span><span class="sxs-lookup"><span data-stu-id="b1c45-125">Perform a sequence of ALTER PARTITION FUNCTION statements.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b1c45-126">no proporciona compatibilidad de replicación para modificar una función de partición.</span><span class="sxs-lookup"><span data-stu-id="b1c45-126">does not provide replication support for modifying a partition function.</span></span> <span data-ttu-id="b1c45-127">Si desea realizar cambios en una función de partición de una base de datos de publicación, deberá hacerlo manualmente en la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="b1c45-127">If you want to make changes to a partition function in the publication database, you must do this manually in the subscription database.</span></span>  
  
-   <span data-ttu-id="b1c45-128">Todos los grupos de archivos que estén afectados por ALTER PARTITION FUNCTION deben estar en línea.</span><span class="sxs-lookup"><span data-stu-id="b1c45-128">All filegroups that are affected by ALTER PARTITION FUNCTION must be online.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b1c45-129">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b1c45-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b1c45-130">Permisos</span><span class="sxs-lookup"><span data-stu-id="b1c45-130">Permissions</span></span>  
 <span data-ttu-id="b1c45-131">Se pueden utilizar cualquiera de los siguientes permisos para ejecutar ALTER PARTITION FUNCTION:</span><span class="sxs-lookup"><span data-stu-id="b1c45-131">Any one of the following permissions can be used to execute ALTER PARTITION FUNCTION:</span></span>  
  
-   <span data-ttu-id="b1c45-132">Permiso ALTER ANY DATASPACE.</span><span class="sxs-lookup"><span data-stu-id="b1c45-132">ALTER ANY DATASPACE permission.</span></span> <span data-ttu-id="b1c45-133">De forma predeterminada, este permiso corresponde a los miembros del rol fijo de servidor **sysadmin** y a los roles fijos de base de datos **db_owner** y **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="b1c45-133">This permission defaults to members of the **sysadmin** fixed server role and the **db_owner** and **db_ddladmin** fixed database roles.</span></span>  
  
-   <span data-ttu-id="b1c45-134">Permiso CONTROL o ALTER en la base de datos en la que se ha creado la función de partición.</span><span class="sxs-lookup"><span data-stu-id="b1c45-134">CONTROL or ALTER permission on the database in which the partition function was created.</span></span>  
  
-   <span data-ttu-id="b1c45-135">Permiso CONTROL SERVER o ALTER ANY DATABASE en el servidor de la base de datos en la que se ha creado la función de partición.</span><span class="sxs-lookup"><span data-stu-id="b1c45-135">CONTROL SERVER or ALTER ANY DATABASE permission on the server of the database in which the partition function was created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b1c45-136">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b1c45-136">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="b1c45-137">**Para modificar una función de partición:**</span><span class="sxs-lookup"><span data-stu-id="b1c45-137">**To modify a partition function:**</span></span>  
  
 <span data-ttu-id="b1c45-138">Esta acción específica no se puede realizar mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1c45-138">This specific action cannot be performed using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b1c45-139">Para modificar una función de partición, primero debe eliminar la función y después crear una nueva con las propiedades deseadas mediante el Asistente para la creación de particiones.</span><span class="sxs-lookup"><span data-stu-id="b1c45-139">In order to modify a partition function, you must first delete the function and then create a new one with the desired properties using the Create Partition Wizard.</span></span> <span data-ttu-id="b1c45-140">Para obtener más información, vea</span><span class="sxs-lookup"><span data-stu-id="b1c45-140">For more information, see</span></span>  
  
#### <a name="to-delete-a-partition-function"></a><span data-ttu-id="b1c45-141">Para eliminar una función de partición</span><span class="sxs-lookup"><span data-stu-id="b1c45-141">To delete a partition function</span></span>  
  
1.  <span data-ttu-id="b1c45-142">Expanda la base de datos donde desea eliminar la función de partición y después expanda la carpeta **Almacenamiento** .</span><span class="sxs-lookup"><span data-stu-id="b1c45-142">Expand the database where you want to delete the partition function and then expand the **Storage** folder.</span></span>  
  
2.  <span data-ttu-id="b1c45-143">Expanda la carpeta de **Funciones de partición** .</span><span class="sxs-lookup"><span data-stu-id="b1c45-143">Expand the **Partition Functions** folder.</span></span>  
  
3.  <span data-ttu-id="b1c45-144">Haga clic con el botón derecho en la función de partición que quiera eliminar y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="b1c45-144">Right-click the partition function you want to delete and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="b1c45-145">En el cuadro de diálogo **Eliminar objeto** , asegúrese de que está seleccionada la función de partición correcta y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b1c45-145">In the **Delete Object** dialog box, ensure that the correct partition function is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b1c45-146">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b1c45-146">Using Transact-SQL</span></span>  
  
#### <a name="to-split-a-single-partition-into-two-partitions"></a><span data-ttu-id="b1c45-147">Para dividir una única partición en dos particiones</span><span class="sxs-lookup"><span data-stu-id="b1c45-147">To split a single partition into two partitions</span></span>  
  
1.  <span data-ttu-id="b1c45-148">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1c45-148">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b1c45-149">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="b1c45-149">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b1c45-150">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b1c45-150">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Look for a previous version of the partition function "myRangePF1" and deletes it if it is found.  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
        DROP PARTITION FUNCTION myRangePF1;  
    GO  
    -- Create a new partition function called "myRangePF1" that partitions a table into four partitions.  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    --Split the partition between boundary_values 100 and 1000  
    --to create two partitions between boundary_values 100 and 500  
    --and between boundary_values 500 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    SPLIT RANGE (500);  
    ```  
  
#### <a name="to-merge-two-partitions-into-one-partition"></a><span data-ttu-id="b1c45-151">Para combinar dos particiones en una única partición</span><span class="sxs-lookup"><span data-stu-id="b1c45-151">To merge two partitions into one partition</span></span>  
  
1.  <span data-ttu-id="b1c45-152">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1c45-152">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b1c45-153">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="b1c45-153">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b1c45-154">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b1c45-154">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Look for a previous version of the partition function "myRangePF1" and deletes it if it is found.  
    IF EXISTS (SELECT * FROM sys.partition_functions  
        WHERE name = 'myRangePF1')  
        DROP PARTITION FUNCTION myRangePF1;  
    GO  
    -- Create a new partition function called "myRangePF1" that partitions a table into four partitions.  
    CREATE PARTITION FUNCTION myRangePF1 (int)  
    AS RANGE LEFT FOR VALUES ( 1, 100, 1000 );  
    GO  
    --Merge the partitions between boundary_values 1 and 100  
    --and between boundary_values 100 and 1000 to create one partition  
    --between boundary_values 1 and 1000.  
    ALTER PARTITION FUNCTION myRangePF1 ()  
    MERGE RANGE (100);  
    ```  
  
 <span data-ttu-id="b1c45-155">Para obtener más información, vea [ALTER PARTITION FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1c45-155">For more information, see [ALTER PARTITION FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-partition-function-transact-sql).</span></span>  
  
  
