---
title: Configuración de operaciones de índice en paralelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index parallel operations [SQL Server]
- processors [SQL Server], parallel index operations
- max degree of parallelism option
- MAXDOP index option, parallel index operations
- parallel index operations [SQL Server]
ms.assetid: 8ec8c71e-5fc1-443a-92da-136ee3fc7f88
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8831aadae15af03a05f4ab03cfe514e54566df1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662905"
---
# <a name="configure-parallel-index-operations"></a><span data-ttu-id="66bba-102">Configurar operaciones de índice en paralelo</span><span class="sxs-lookup"><span data-stu-id="66bba-102">Configure Parallel Index Operations</span></span>
  <span data-ttu-id="66bba-103">En este tema se define el grado máximo de paralelismo y se explica cómo modificar este valor en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66bba-103">This topic defines max degree of parallelism and explains how to modify this setting in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="66bba-104">En los equipos multiprocesador que ejecutan [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise o superior, las instrucciones de índice pueden usar varios procesadores para realizar las operaciones de examen, ordenación e indización asociadas a la instrucción de índice, al igual que hacen otras consultas.</span><span class="sxs-lookup"><span data-stu-id="66bba-104">On multiprocessor computers that are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise or higher, index statements may use multiple processors to perform the scan, sort, and index operations associated with the index statement just like other queries do.</span></span> <span data-ttu-id="66bba-105">El número de procesadores utilizados para ejecutar una sola instrucción de índice viene determinado por la opción de configuración [Grado máximo de paralelismo](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) , la carga de trabajo actual y las estadísticas de índices.</span><span class="sxs-lookup"><span data-stu-id="66bba-105">The number of processors used to run a single index statement is determined by the [max degree of parallelism](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) configuration option, the current workload, and the index statistics.</span></span> <span data-ttu-id="66bba-106">La opción max degree of parallelism determina el número máximo de procesadores que se utilizarán en la ejecución de planes paralelos.</span><span class="sxs-lookup"><span data-stu-id="66bba-106">The max degree of parallelism option determines the maximum number of processors to use in parallel plan execution.</span></span> <span data-ttu-id="66bba-107">Si [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] detecta que el sistema está ocupado, el grado de paralelismo de la operación de índice se reduce automáticamente antes de comenzar la ejecución de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="66bba-107">If the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] detects that the system is busy, the degree of parallelism of the index operation is automatically reduced before statement execution starts.</span></span> <span data-ttu-id="66bba-108">[!INCLUDE[ssDE](../../includes/ssde-md.md)] también puede reducir el grado de paralelismo si la columna de clave inicial de un índice sin particiones tiene un número limitado de valores distintos o la frecuencia de cada valor distinto varía significativamente.</span><span class="sxs-lookup"><span data-stu-id="66bba-108">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] can also reduce the degree of parallelism if the leading key column of a non-partitioned index has a limited number of distinct values or the frequency of each distinct value varies significantly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="66bba-109">Las operaciones de índices en paralelo no están disponibles en todas las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66bba-109">Parallel index operations are not available in every [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition.</span></span> <span data-ttu-id="66bba-110">Para obtener más información, vea [características compatibles con las ediciones de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="66bba-110">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
 <span data-ttu-id="66bba-111">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="66bba-111">**In This Topic**</span></span>  
  
-   <span data-ttu-id="66bba-112">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="66bba-112">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="66bba-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="66bba-113">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="66bba-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="66bba-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="66bba-115">**Para establecer el grado máximo de paralelismo, usando:**</span><span class="sxs-lookup"><span data-stu-id="66bba-115">**To set the max degree of parallelism, using:**</span></span>  
  
     [<span data-ttu-id="66bba-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="66bba-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="66bba-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="66bba-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="66bba-118">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="66bba-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="66bba-119">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="66bba-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="66bba-120">El número de procesadores que utiliza el optimizador de consultas suele proporcionar un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="66bba-120">The number of processors that are used by the query optimizer typically provides optimal performance.</span></span> <span data-ttu-id="66bba-121">No obstante, las operaciones como la creación, reconstrucción o eliminación de índices de gran tamaño utilizan una gran cantidad de recursos y pueden provocar la falta de recursos para otras aplicaciones y operaciones de base de datos durante la operación de índice.</span><span class="sxs-lookup"><span data-stu-id="66bba-121">However, operations such as creating, rebuilding, or dropping very large indexes are resource intensive and can cause insufficient resources for other applications and database operations for the duration of the index operation.</span></span> <span data-ttu-id="66bba-122">Cuando se produce este problema, se puede configurar manualmente el número máximo de procesadores que se emplean para ejecutar la instrucción de índice limitando el número de procesadores que se usarán para la operación de índice.</span><span class="sxs-lookup"><span data-stu-id="66bba-122">When this problem occurs, you can manually configure the maximum number of processors that are used to run the index statement by limiting the number of processors to use for the index operation.</span></span>  
  
-   <span data-ttu-id="66bba-123">La opción de índice MAXDOP reemplaza la opción de configuración max degree of parallelism solo para la consulta que especifica esta opción.</span><span class="sxs-lookup"><span data-stu-id="66bba-123">The MAXDOP index option overrides the max degree of parallelism configuration option only for the query specifying this option.</span></span> <span data-ttu-id="66bba-124">En la tabla siguiente se muestran los valores enteros válidos que se pueden especificar con la opción de configuración max degree of parallelism y la opción de índice MAXDOP.</span><span class="sxs-lookup"><span data-stu-id="66bba-124">The following table lists the valid integer values that can be specified with the max degree of parallelism configuration option and the MAXDOP index option.</span></span>  
  
    |<span data-ttu-id="66bba-125">Value</span><span class="sxs-lookup"><span data-stu-id="66bba-125">Value</span></span>|<span data-ttu-id="66bba-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="66bba-126">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="66bba-127">0</span><span class="sxs-lookup"><span data-stu-id="66bba-127">0</span></span>|<span data-ttu-id="66bba-128">Especifica que el servidor determina el número de CPU que se usan, según la carga de trabajo del sistema actual.</span><span class="sxs-lookup"><span data-stu-id="66bba-128">Specifies that the server determines the number of CPUs that are used, depending on the current system workload.</span></span> <span data-ttu-id="66bba-129">Éste es el valor predeterminado y recomendado.</span><span class="sxs-lookup"><span data-stu-id="66bba-129">This is the default value and recommended setting.</span></span>|  
    |<span data-ttu-id="66bba-130">1</span><span class="sxs-lookup"><span data-stu-id="66bba-130">1</span></span>|<span data-ttu-id="66bba-131">Suprime la generación de planes paralelos.</span><span class="sxs-lookup"><span data-stu-id="66bba-131">Suppresses parallel plan generation.</span></span> <span data-ttu-id="66bba-132">La operación se ejecutará en serie.</span><span class="sxs-lookup"><span data-stu-id="66bba-132">The operation will be executed serially.</span></span>|  
    |<span data-ttu-id="66bba-133">2-64</span><span class="sxs-lookup"><span data-stu-id="66bba-133">2-64</span></span>|<span data-ttu-id="66bba-134">Limita el número de procesadores al valor especificado.</span><span class="sxs-lookup"><span data-stu-id="66bba-134">Limits the number of processors to the specified value.</span></span> <span data-ttu-id="66bba-135">Puede que se utilicen menos procesadores, dependiendo de la carga de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="66bba-135">Fewer processors may be used depending on the current workload.</span></span> <span data-ttu-id="66bba-136">Si especifica un valor superior al número de CPU disponibles, se utilizará el número real de CPU disponibles.</span><span class="sxs-lookup"><span data-stu-id="66bba-136">If a value larger than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>|  
  
-   <span data-ttu-id="66bba-137">La ejecución de índices en paralelo y la opción de índice MAXDOP se aplican a las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] siguientes:</span><span class="sxs-lookup"><span data-stu-id="66bba-137">Parallel index execution and the MAXDOP index option apply to the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    -   <span data-ttu-id="66bba-138">CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="66bba-138">CREATE INDEX</span></span>  
  
    -   <span data-ttu-id="66bba-139">ALTER INDEX REBUILD</span><span class="sxs-lookup"><span data-stu-id="66bba-139">ALTER INDEX REBUILD</span></span>  
  
    -   <span data-ttu-id="66bba-140">DROP INDEX (esta opción solo se aplica a los clúster)</span><span class="sxs-lookup"><span data-stu-id="66bba-140">DROP INDEX (This applies to clustered indexes only.)</span></span>  
  
    -   <span data-ttu-id="66bba-141">ALTER TABLE ADD (índice) CONSTRAINT</span><span class="sxs-lookup"><span data-stu-id="66bba-141">ALTER TABLE ADD (index) CONSTRAINT</span></span>  
  
    -   <span data-ttu-id="66bba-142">ALTER TABLE DROP (índice clúster) CONSTRAINT</span><span class="sxs-lookup"><span data-stu-id="66bba-142">ALTER TABLE DROP (clustered index) CONSTRAINT</span></span>  
  
-   <span data-ttu-id="66bba-143">La opción de índice MAXDOP no se puede especificar en la instrucción ALTER INDEX REORGANIZE.</span><span class="sxs-lookup"><span data-stu-id="66bba-143">The MAXDOP index option cannot be specified in the ALTER INDEX REORGANIZE statement.</span></span>  
  
-   <span data-ttu-id="66bba-144">Los requisitos de memoria de las operaciones de índices con particiones que requieren ordenación pueden ser mayores si el optimizador de consultas aplica grados de paralelismo a la operación de generación.</span><span class="sxs-lookup"><span data-stu-id="66bba-144">Memory requirements for partitioned index operations that require sorting can be greater if the query optimizer applies degrees of parallelism to the build operation.</span></span> <span data-ttu-id="66bba-145">Cuanto mayores sean los grados de paralelismo, mayor será el requisito de memoria.</span><span class="sxs-lookup"><span data-stu-id="66bba-145">The higher the degrees of parallelism, the greater the memory requirement is.</span></span> <span data-ttu-id="66bba-146">Para obtener más información, vea [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="66bba-146">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="66bba-147">Seguridad</span><span class="sxs-lookup"><span data-stu-id="66bba-147">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="66bba-148">Permisos</span><span class="sxs-lookup"><span data-stu-id="66bba-148">Permissions</span></span>  
 <span data-ttu-id="66bba-149">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="66bba-149">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="66bba-150">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="66bba-150">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-max-degree-of-parallelism-on-an-index"></a><span data-ttu-id="66bba-151">Para establecer el grado máximo de paralelismo en un índice</span><span class="sxs-lookup"><span data-stu-id="66bba-151">To set max degree of parallelism on an index</span></span>  
  
1.  <span data-ttu-id="66bba-152">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que desea establecer el grado máximo de paralelismo para un índice.</span><span class="sxs-lookup"><span data-stu-id="66bba-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to set max degree of parallelism for an index.</span></span>  
  
2.  <span data-ttu-id="66bba-153">Expanda la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="66bba-153">Expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="66bba-154">Haga clic en el signo más para expandir la tabla en la que desea establecer el grado máximo de paralelismo para un índice.</span><span class="sxs-lookup"><span data-stu-id="66bba-154">Click the plus sign to expand the table on which you want to set max degree of parallelism for an index.</span></span>  
  
4.  <span data-ttu-id="66bba-155">Expanda la carpeta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="66bba-155">Expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="66bba-156">Haga clic con el botón derecho en el índice para el que quiere establecer el grado máximo de paralelismo y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="66bba-156">Right-click the index for which you want to set the max degree of parallelism and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="66bba-157">Debajo de **Seleccionar una página**, seleccione **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="66bba-157">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="66bba-158">Seleccione **Grado máximo de paralelismo**y, a continuación, escriba un valor entre 1 y 64.</span><span class="sxs-lookup"><span data-stu-id="66bba-158">Select **Maximum degree of parallelism**, and then enter some value between 1 and 64.</span></span>  
  
8.  <span data-ttu-id="66bba-159">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="66bba-159">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="66bba-160">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="66bba-160">Using Transact-SQL</span></span>  
  
#### <a name="to-set-max-degree-of-parallelism-on-an-existing-index"></a><span data-ttu-id="66bba-161">Para establecer el grado máximo de paralelismo en un índice existente</span><span class="sxs-lookup"><span data-stu-id="66bba-161">To set max degree of parallelism on an existing index</span></span>  
  
1.  <span data-ttu-id="66bba-162">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66bba-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="66bba-163">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="66bba-163">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="66bba-164">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="66bba-164">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    /*Alters the IX_ProductVendor_VendorID index on the Purchasing.ProductVendor table so that, if the server has eight or more processors, the Database Engine will limit the execution of the index operation to eight or fewer processors.  
    */  
    ALTER INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor  
    REBUILD WITH (MAXDOP=8);   
    GO  
    ```  
  
 <span data-ttu-id="66bba-165">Para obtener más información, vea [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="66bba-165">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
#### <a name="set-max-degree-of-parallelism-on-a-new-index"></a><span data-ttu-id="66bba-166">Establecer el grado máximo de paralelismo en un nuevo índice</span><span class="sxs-lookup"><span data-stu-id="66bba-166">Set max degree of parallelism on a new index</span></span>  
  
1.  <span data-ttu-id="66bba-167">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="66bba-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="66bba-168">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="66bba-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="66bba-169">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="66bba-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE INDEX IX_ProductVendor_NewVendorID   
    ON Purchasing.ProductVendor (BusinessEntityID)  
    WITH (MAXDOP=8);  
    GO  
    ```  
  
 <span data-ttu-id="66bba-170">Para obtener más información, vea [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="66bba-170">For more information, see [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
  
