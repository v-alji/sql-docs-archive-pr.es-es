---
title: Movimiento de un índice existente a un grupo de archivos diferente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- moving tables
- switching filegroups for index
- moving indexes
- indexes [SQL Server], moving
- filegroups [SQL Server], switching
ms.assetid: 167ebe77-487d-4ca8-9452-4b2c7d5cb96e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c99847dcb8d4d65272dd3660c7fd60d3efb8d951
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677087"
---
# <a name="move-an-existing-index-to-a-different-filegroup"></a><span data-ttu-id="4551e-102">Mover un índice existente a un grupo de archivos diferente</span><span class="sxs-lookup"><span data-stu-id="4551e-102">Move an Existing Index to a Different Filegroup</span></span>
  <span data-ttu-id="4551e-103">En este tema se describe cómo mover un índice existente de su grupo de archivos actual a otro distinto en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4551e-103">This topic describes how to move an existing index from its current filegroup to a different filegroup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4551e-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="4551e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4551e-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="4551e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4551e-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4551e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4551e-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4551e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4551e-108">**Para mover un índice existente a un grupo de archivos diferente, usando:**</span><span class="sxs-lookup"><span data-stu-id="4551e-108">**To move an existing index to a different filegroup, using:**</span></span>  
  
     [<span data-ttu-id="4551e-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4551e-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4551e-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4551e-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4551e-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4551e-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4551e-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="4551e-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="4551e-113">Si una tabla base tiene un índice clúster, al mover el índice clúster a un nuevo grupo de archivos se mueve también la tabla a ese grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="4551e-113">If a table has a clustered index, moving the clustered index to a new filegroup moves the table to that filegroup.</span></span>  
  
-   <span data-ttu-id="4551e-114">No puede mover los índices creados mediante una restricción UNIQUE o PRIMARY KEY con [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4551e-114">You cannot move indexes created using a UNIQUE or PRIMARY KEY constraint using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="4551e-115">Para mover estos índices, use la instrucción [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql) con la opción (DROP_EXISTING=ON) en [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4551e-115">To move these indexes use the [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql) statement with the (DROP_EXISTING=ON) option in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4551e-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4551e-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4551e-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="4551e-117">Permissions</span></span>  
 <span data-ttu-id="4551e-118">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="4551e-118">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="4551e-119">El usuario debe ser miembro del rol fijo de servidor **sysadmin** o de los roles fijos de base de datos **db_ddladmin** y **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="4551e-119">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4551e-120">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4551e-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup-using-table-designer"></a><span data-ttu-id="4551e-121">Para mover un índice existente a un grupo de archivos diferente usando el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="4551e-121">To move an existing index to a different filegroup using Table Designer</span></span>  
  
1.  <span data-ttu-id="4551e-122">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla que contiene el índice que desea mover.</span><span class="sxs-lookup"><span data-stu-id="4551e-122">In Object Explorer, click the plus sign to expand the database that contains the table containing the index that you want to move.</span></span>  
  
2.  <span data-ttu-id="4551e-123">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="4551e-123">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="4551e-124">Haga clic con el botón derecho en la tabla que contiene el índice que quiere mover y seleccione **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="4551e-124">Right-click the table containing the index that you want to move and select **Design**.</span></span>  
  
4.  <span data-ttu-id="4551e-125">En el menú **Diseñador de tablas** , haga clic en **Índices o claves**.</span><span class="sxs-lookup"><span data-stu-id="4551e-125">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="4551e-126">Seleccione el índice que desea mover.</span><span class="sxs-lookup"><span data-stu-id="4551e-126">Select the index that you want to move.</span></span>  
  
6.  <span data-ttu-id="4551e-127">En la cuadrícula principal, expanda **Especificación de espacio de datos**.</span><span class="sxs-lookup"><span data-stu-id="4551e-127">In the main grid, expand **Data Space Specification**.</span></span>  
  
7.  <span data-ttu-id="4551e-128">Seleccione **Nombre de esquema de partición o grupo de archivos** y seleccione en la lista el esquema de grupo de archivos o de partición al que desea mover el índice.</span><span class="sxs-lookup"><span data-stu-id="4551e-128">Select **Filegroup or Partition Scheme Name** and select from the list the filegroup or partition scheme to where you want to move the index.</span></span>  
  
8.  <span data-ttu-id="4551e-129">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="4551e-129">Click **Close**.</span></span>  
  
9. <span data-ttu-id="4551e-130">En el menú **Archivo** , seleccione **Guardar**_nombre_tabla_.</span><span class="sxs-lookup"><span data-stu-id="4551e-130">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup-in-object-explorer"></a><span data-ttu-id="4551e-131">Para mover un índice existente a un grupo de archivos distinto en el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="4551e-131">To move an existing index to a different filegroup in Object Explorer</span></span>  
  
1.  <span data-ttu-id="4551e-132">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla que contiene el índice que desea mover.</span><span class="sxs-lookup"><span data-stu-id="4551e-132">In Object Explorer, click the plus sign to expand the database that contains the table containing the index that you want to move.</span></span>  
  
2.  <span data-ttu-id="4551e-133">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="4551e-133">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="4551e-134">Haga clic en el signo más para expandir la tabla que contiene el índice que desea mover.</span><span class="sxs-lookup"><span data-stu-id="4551e-134">Click the plus sign to expand the table containing the index that you want to move.</span></span>  
  
4.  <span data-ttu-id="4551e-135">Haga clic en el signo más para expandir la carpeta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="4551e-135">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="4551e-136">Haga clic con el botón derecho en el índice que quiere mover y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4551e-136">Right-click the index that you want to move and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="4551e-137">En **Seleccionar una página**, seleccione **Almacenamiento**.</span><span class="sxs-lookup"><span data-stu-id="4551e-137">Under **Select a page**, select **Storage**.</span></span>  
  
7.  <span data-ttu-id="4551e-138">Seleccione el grupo de archivos al que desee mover el índice.</span><span class="sxs-lookup"><span data-stu-id="4551e-138">Select the filegroup in which to move the index.</span></span>  
  
     <span data-ttu-id="4551e-139">Si la tabla o el índice tienen particiones, seleccione el esquema de particiones al que desee mover el índice.</span><span class="sxs-lookup"><span data-stu-id="4551e-139">If the table or index is partitioned, select the partition scheme in which to move the index.</span></span> <span data-ttu-id="4551e-140">Para obtener más información acerca de los índices con particiones, vea [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="4551e-140">For more information about partitioned indexes, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
     <span data-ttu-id="4551e-141">Si lo que desea mover es un índice clúster, puede utilizar el procesamiento en línea.</span><span class="sxs-lookup"><span data-stu-id="4551e-141">If you are moving a clustered index, you can use online processing.</span></span> <span data-ttu-id="4551e-142">El procesamiento en línea permite que varios usuarios obtengan acceso al mismo tiempo a los datos subyacentes, así como a índices no clúster durante la operación de índice.</span><span class="sxs-lookup"><span data-stu-id="4551e-142">Online processing allows concurrent user access to the underlying data and to nonclustered indexes during the index operation.</span></span> <span data-ttu-id="4551e-143">Para más información, consulte [Perform Index Operations Online](perform-index-operations-online.md).</span><span class="sxs-lookup"><span data-stu-id="4551e-143">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
     <span data-ttu-id="4551e-144">En equipos multiprocesador que usan [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], puede configurar el número de procesadores que desea usar para ejecutar la instrucción de índice; para ello, especifique un valor máximo de grado de paralelismo.</span><span class="sxs-lookup"><span data-stu-id="4551e-144">On multiprocessor computers using [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can configure the number of processors used to execute the index statement by specifying a maximum degree of parallelism value.</span></span> <span data-ttu-id="4551e-145">La característica Operaciones indizadas en paralelo no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4551e-145">The Parallel indexed operations feature is not available in every edition of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4551e-146">Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], vea [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="4551e-146">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="4551e-147">Para obtener más información sobre las operaciones indexadas en paralelo, vea [Configurar operaciones de índice en paralelo](configure-parallel-index-operations.md).</span><span class="sxs-lookup"><span data-stu-id="4551e-147">For more information about Parallel indexed operations, see [Configure Parallel Index Operations](configure-parallel-index-operations.md).</span></span>  
  
8.  <span data-ttu-id="4551e-148">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="4551e-148">Click **OK**.</span></span>  
  
 <span data-ttu-id="4551e-149">La información siguiente está disponible en la página **Almacenamiento** del cuadro de diálogo **Propiedades del índice -** _nombre de índice_:</span><span class="sxs-lookup"><span data-stu-id="4551e-149">The following information is available on the **Storage** page of the **Index Properties -** _index_name_ dialog box:</span></span>  
  
 <span data-ttu-id="4551e-150">**Grupo de archivos**</span><span class="sxs-lookup"><span data-stu-id="4551e-150">**Filegroup**</span></span>  
 <span data-ttu-id="4551e-151">Almacena el índice en el grupo de archivos especificado.</span><span class="sxs-lookup"><span data-stu-id="4551e-151">Stores the index in the specified filegroup.</span></span> <span data-ttu-id="4551e-152">En la lista solo se muestran los grupos de archivos (fila) estándar.</span><span class="sxs-lookup"><span data-stu-id="4551e-152">The list only displays standard (row) filegroups.</span></span> <span data-ttu-id="4551e-153">La selección de lista predeterminada es el grupo de archivos PRIMARY de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4551e-153">The default list selection is the PRIMARY filegroup of the database.</span></span>  
  
 <span data-ttu-id="4551e-154">**Grupo de archivos de flujo de archivos**</span><span class="sxs-lookup"><span data-stu-id="4551e-154">**Filestream filegroup**</span></span>  
 <span data-ttu-id="4551e-155">Especifica el grupo de archivos para los datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4551e-155">Specifies the filegroup for FILESTREAM data.</span></span> <span data-ttu-id="4551e-156">En esta lista solo se muestran los grupos de archivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4551e-156">This list displays only FILESTREAM filegroups.</span></span> <span data-ttu-id="4551e-157">La selección de lista predeterminada es el grupo de archivos PRIMARY FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4551e-157">The default list selection is the PRIMARY FILESTREAM filegroup.</span></span>  
  
 <span data-ttu-id="4551e-158">**Esquema de partición**</span><span class="sxs-lookup"><span data-stu-id="4551e-158">**Partition scheme**</span></span>  
 <span data-ttu-id="4551e-159">Almacena el índice en un esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="4551e-159">Stores the index in a partition scheme.</span></span> <span data-ttu-id="4551e-160">Al hacer clic en **Esquema de partición** , se habilita la cuadrícula que se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="4551e-160">Clicking **Partition Scheme** enables the grid below.</span></span> <span data-ttu-id="4551e-161">La selección de lista predeterminada es el esquema de partición utilizado para almacenar los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="4551e-161">The default list selection is the partition scheme that is used for storing the table data.</span></span> <span data-ttu-id="4551e-162">Si se selecciona un esquema de partición distinto de la lista, se actualizará la información en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4551e-162">When you select a different partition scheme in the list, the information in the grid is updated.</span></span>  
  
 <span data-ttu-id="4551e-163">La opción de esquema de partición no estará disponible si no hay ningún esquema de partición en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4551e-163">The partition scheme option is unavailable if there are no partition schemes in the database.</span></span>  
  
 <span data-ttu-id="4551e-164">**Esquema de partición Filestream**</span><span class="sxs-lookup"><span data-stu-id="4551e-164">**Filestream partition scheme**</span></span>  
 <span data-ttu-id="4551e-165">Especifica el esquema de partición de los datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="4551e-165">Specifies the partition scheme for FILESTREAM data.</span></span> <span data-ttu-id="4551e-166">El esquema de partición debe ser simétrico al esquema especificado en la opción **Esquema de partición** .</span><span class="sxs-lookup"><span data-stu-id="4551e-166">The partition scheme must be symmetric with the scheme that is specified in the **Partition scheme** option.</span></span>  
  
 <span data-ttu-id="4551e-167">Si no tiene particiones, el campo está en blanco.</span><span class="sxs-lookup"><span data-stu-id="4551e-167">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="4551e-168">**Parámetro del esquema de partición**</span><span class="sxs-lookup"><span data-stu-id="4551e-168">**Partition Scheme Parameter**</span></span>  
 <span data-ttu-id="4551e-169">Muestra el nombre de la columna que participa en el esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="4551e-169">Displays the name of the column that participates in the partition scheme.</span></span>  
  
 <span data-ttu-id="4551e-170">**Columna de la tabla**</span><span class="sxs-lookup"><span data-stu-id="4551e-170">**Table Column**</span></span>  
 <span data-ttu-id="4551e-171">Seleccione la tabla o vista que se asignará al esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="4551e-171">Select the table or view to map to the partition scheme.</span></span>  
  
 <span data-ttu-id="4551e-172">**Tipo de datos de la columna**</span><span class="sxs-lookup"><span data-stu-id="4551e-172">**Column Data Type**</span></span>  
 <span data-ttu-id="4551e-173">Muestra información de tipo de datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="4551e-173">Displays data type information about the column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4551e-174">Si la columna de tabla es una columna calculada, **Tipo de datos de la columna** mostrará "columna calculada".</span><span class="sxs-lookup"><span data-stu-id="4551e-174">If the table column is a computed column, **Column Data Type** displays "computed column."</span></span>  
  
 <span data-ttu-id="4551e-175">**Permitir procesamiento en línea de instrucciones DML al mover el índice**</span><span class="sxs-lookup"><span data-stu-id="4551e-175">**Allow online processing of DML statements while moving the index**</span></span>  
 <span data-ttu-id="4551e-176">Permite a los usuarios obtener acceso a los datos de la tabla subyacente o del índice clúster, así como a todos los índices no clúster asociados durante las operaciones de índice.</span><span class="sxs-lookup"><span data-stu-id="4551e-176">Allows users to access the underlying table or clustered index data and any associated nonclustered indexes during the index operation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4551e-177">Esta opción no estará disponible para los índices XML ni cuando el índice sea un índice clúster deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="4551e-177">This option is not available for XML indexes, or if the index is a disabled clustered index.</span></span>  
  
 <span data-ttu-id="4551e-178">**Establecer grado máximo de paralelismo**</span><span class="sxs-lookup"><span data-stu-id="4551e-178">**Set maximum degree of parallelism**</span></span>  
 <span data-ttu-id="4551e-179">Limita el número de procesadores que se van a utilizar durante la ejecución de planes paralelos.</span><span class="sxs-lookup"><span data-stu-id="4551e-179">Limits the number of processors to use during parallel plan execution.</span></span> <span data-ttu-id="4551e-180">El valor predeterminado es 0, que utiliza el número real de CPU disponibles.</span><span class="sxs-lookup"><span data-stu-id="4551e-180">The default value, 0, uses the actual number of available CPUs.</span></span> <span data-ttu-id="4551e-181">Si el valor se establece en 1, se suprime la generación de planes paralelos; si el valor se establece en un número mayor que 1, se restringe el número máximo de procesadores que se utilizan en la ejecución de una única consulta.</span><span class="sxs-lookup"><span data-stu-id="4551e-181">Setting the value to 1 suppresses parallel plan generation; setting the value to a number greater than 1 restricts the maximum number of processors used by a single query execution.</span></span> <span data-ttu-id="4551e-182">Esta opción solo está disponible si el cuadro de diálogo está en los estados **Volver a generar** o **Volver a crear** .</span><span class="sxs-lookup"><span data-stu-id="4551e-182">This option only becomes available if the dialog box is in the **Rebuild** or **Recreate** state.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4551e-183">Si especifica un valor superior al número de CPU disponibles, se utilizará el número real de CPU disponibles.</span><span class="sxs-lookup"><span data-stu-id="4551e-183">If a value greater than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4551e-184">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4551e-184">Using Transact-SQL</span></span>  
  
#### <a name="to-move-an-existing-index-to-a-different-filegroup"></a><span data-ttu-id="4551e-185">Para mover un índice existente a un grupo de archivos diferente</span><span class="sxs-lookup"><span data-stu-id="4551e-185">To move an existing index to a different filegroup</span></span>  
  
1.  <span data-ttu-id="4551e-186">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4551e-186">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4551e-187">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="4551e-187">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4551e-188">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="4551e-188">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Creates the TransactionsFG1 filegroup on the AdventureWorks2012 database  
    ALTER DATABASE AdventureWorks2012  
    ADD FILEGROUP TransactionsFG1;  
    GO  
    /* Adds the TransactionsFG1dat3 file to the TransactionsFG1 filegroup. Please note that you will have to change the filename parameter in this statement to execute it without errors.  
    */  
    ALTER DATABASE AdventureWorks2012   
    ADD FILE   
    (  
        NAME = TransactionsFG1dat3,  
        FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\TransactionsFG1dat3.ndf',  
        SIZE = 5MB,  
        MAXSIZE = 100MB,  
        FILEGROWTH = 5MB  
    )  
    TO FILEGROUP TransactionsFG1;  
    GO  
    /*Creates the IX_Employee_OrganizationLevel_OrganizationNode index  
      on the TransactionsPS1 filegroup and drops the original IX_Employee_OrganizationLevel_OrganizationNode index.  
    */  
    CREATE NONCLUSTERED INDEX IX_Employee_OrganizationLevel_OrganizationNode  
        ON HumanResources.Employee (OrganizationLevel, OrganizationNode)  
        WITH (DROP_EXISTING = ON)  
        ON TransactionsFG1;  
    GO  
    ```  
  
 <span data-ttu-id="4551e-189">Para obtener más información, vea [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4551e-189">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
