---
title: Especificar el factor de relleno para un índice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- fill factor [SQL Server]
- page splits [SQL Server]
ms.assetid: 237a577e-b42b-4adb-90cf-aa7fb174f3ab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ac54f2b22de55ed74c4635ec0f86d008c7624a42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749302"
---
# <a name="specify-fill-factor-for-an-index"></a><span data-ttu-id="89fd3-102">Especificar el factor de relleno para un índice</span><span class="sxs-lookup"><span data-stu-id="89fd3-102">Specify Fill Factor for an Index</span></span>
  <span data-ttu-id="89fd3-103">Este tema describe qué es el factor de relleno y cómo especificar un valor de factor de relleno en un índice de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89fd3-103">This topic describes what fill factor is and how to specify a fill factor value on an index in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="89fd3-104">La opción de factor de relleno permite optimizar el almacenamiento y rendimiento de los datos de índice.</span><span class="sxs-lookup"><span data-stu-id="89fd3-104">The fill-factor option is provided for fine-tuning index data storage and performance.</span></span> <span data-ttu-id="89fd3-105">Cuando se crea o se vuelve a generar un índice, el valor de factor de relleno determina el porcentaje de espacio en cada página de nivel de hoja que se tiene que rellenar con datos, por lo que se reserva el resto de cada página como espacio disponible para seguir creciendo.</span><span class="sxs-lookup"><span data-stu-id="89fd3-105">When an index is created or rebuilt, the fill-factor value determines the percentage of space on each leaf-level page to be filled with data, reserving the remainder on each page as free space for future growth.</span></span> <span data-ttu-id="89fd3-106">Por ejemplo, si se especifica un valor de factor de relleno de 80, significa que el 20 por ciento de cada página de nivel de hoja se dejará vacío para proporcionar espacio para la expansión del índice a medida que se agreguen datos a la tabla subyacente.</span><span class="sxs-lookup"><span data-stu-id="89fd3-106">For example, specifying a fill-factor value of 80 means that 20 percent of each leaf-level page will be left empty, providing space for index expansion as data is added to the underlying table.</span></span> <span data-ttu-id="89fd3-107">El espacio vacío se reserva entre las filas de índice en lugar de al final del índice.</span><span class="sxs-lookup"><span data-stu-id="89fd3-107">The empty space is reserved between the index rows rather than at the end of the index.</span></span>  
  
 <span data-ttu-id="89fd3-108">El valor de factor de relleno es un porcentaje entre 1 y 100, y el valor predeterminado en el servidor es 0, lo que significa que las páginas de nivel de hoja se rellenan al máximo de su capacidad.</span><span class="sxs-lookup"><span data-stu-id="89fd3-108">The fill-factor value is a percentage from 1 to 100, and the server-wide default is 0 which means that the leaf-level pages are filled to capacity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89fd3-109">Los valores del factor de relleno 0 y 100 son idénticos.</span><span class="sxs-lookup"><span data-stu-id="89fd3-109">Fill-factor values 0 and 100 are the same in all respects.</span></span>  
  
 <span data-ttu-id="89fd3-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="89fd3-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="89fd3-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="89fd3-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="89fd3-112">Consideraciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="89fd3-112">Performance Considerations</span></span>](#Performance)  
  
     [<span data-ttu-id="89fd3-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="89fd3-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="89fd3-114">**Para especificar un factor de relleno en un índice, use:**</span><span class="sxs-lookup"><span data-stu-id="89fd3-114">**To specify a fill factor in an index, using:**</span></span>  
  
     [<span data-ttu-id="89fd3-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="89fd3-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="89fd3-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="89fd3-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="89fd3-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="89fd3-117">Before You Begin</span></span>  
  
###  <a name="performance-considerations"></a><a name="Performance"></a> <span data-ttu-id="89fd3-118">Consideraciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="89fd3-118">Performance Considerations</span></span>  
  
#### <a name="page-splits"></a><span data-ttu-id="89fd3-119">Divisiones de páginas</span><span class="sxs-lookup"><span data-stu-id="89fd3-119">Page Splits</span></span>  
 <span data-ttu-id="89fd3-120">Si el valor de factor de relleno se elige correctamente, se pueden reducir las posibles divisiones de página al proporcionarse espacio suficiente para la expansión del índice a medida que se agregan datos a la tabla subyacente. Cuando se agrega una fila nueva a una página de índice llena, el [!INCLUDE[ssDE](../../includes/ssde-md.md)] mueve aproximadamente la mitad de las filas a una página nueva con el fin de hacer espacio para la nueva fila.</span><span class="sxs-lookup"><span data-stu-id="89fd3-120">A correctly chosen fill-factor value can reduce potential page splits by providing enough space for index expansion as data is added to the underlying table.When a new row is added to a full index page, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] moves approximately half the rows to a new page to make room for the new row.</span></span> <span data-ttu-id="89fd3-121">Esta reorganización se denomina división de página.</span><span class="sxs-lookup"><span data-stu-id="89fd3-121">This reorganization is known as a page split.</span></span> <span data-ttu-id="89fd3-122">Una división de página genera espacio para los nuevos registros, pero puede tardar en realizarse y es una operación que consume muchos recursos.</span><span class="sxs-lookup"><span data-stu-id="89fd3-122">A page split makes room for new records, but can take time to perform and is a resource intensive operation.</span></span> <span data-ttu-id="89fd3-123">Además, puede causar fragmentación que, a su vez, causa más operaciones de E/S.</span><span class="sxs-lookup"><span data-stu-id="89fd3-123">Also, it can cause fragmentation that causes increased I/O operations.</span></span> <span data-ttu-id="89fd3-124">Cuando se llevan a cabo divisiones de páginas con frecuencia, el índice se puede volver a generar utilizando un valor de factor de relleno nuevo o existente para redistribuir los datos.</span><span class="sxs-lookup"><span data-stu-id="89fd3-124">When frequent page splits occur, the index can be rebuilt by using a new or existing fill-factor value to redistribute the data.</span></span> <span data-ttu-id="89fd3-125">Para obtener más información, vea [Reorganizar y volver a generar índices](reorganize-and-rebuild-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="89fd3-125">For more information, see [Reorganize and Rebuild Indexes](reorganize-and-rebuild-indexes.md).</span></span>  
  
 <span data-ttu-id="89fd3-126">Aunque si el valor del factor de relleno es bajo y distinto de cero, se puede reducir el requisito de dividir páginas a medida que crezca el índice, éste necesitará más espacio de almacenamiento y puede reducir el rendimiento de la lectura.</span><span class="sxs-lookup"><span data-stu-id="89fd3-126">Although a low, nonzero fill-factor value may reduce the requirement to split pages as the index grows, the index will require more storage space and can decrease read performance.</span></span> <span data-ttu-id="89fd3-127">Incluso en el caso de una aplicación pensada para realizar muchas operaciones de inserción y actualización, el número de lecturas de base de datos suele superar a las escrituras en un factor de 5 a 10.</span><span class="sxs-lookup"><span data-stu-id="89fd3-127">Even for an application oriented for many insert and update operations, the number of database reads typically outnumber database writes by a factor of 5 to 10.</span></span> <span data-ttu-id="89fd3-128">Por lo tanto, al especificar un factor de relleno distinto del predeterminado, se puede disminuir el rendimiento de las lecturas de base de datos en una cantidad inversamente proporcional al valor del factor de relleno.</span><span class="sxs-lookup"><span data-stu-id="89fd3-128">Therefore, specifying a fill factor other than the default can decrease database read performance by an amount inversely proportional to the fill-factor setting.</span></span> <span data-ttu-id="89fd3-129">Por ejemplo, un valor de factor de relleno igual a 50 puede hacer que el rendimiento de las lecturas de base de datos se reduzca a la mitad.</span><span class="sxs-lookup"><span data-stu-id="89fd3-129">For example, a fill-factor value of 50 can cause database read performance to decrease by two times.</span></span> <span data-ttu-id="89fd3-130">El rendimiento de las lecturas se reduce porque el índice contiene más páginas, con lo que se aumentan las operaciones de E/S de disco necesarias para recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="89fd3-130">Read performance is decreased because the index contains more pages, therefore increasing the disk IO operations required to retrieve the data.</span></span>  
  
#### <a name="adding-data-to-the-end-of-the-table"></a><span data-ttu-id="89fd3-131">Agregar datos al final de la tabla</span><span class="sxs-lookup"><span data-stu-id="89fd3-131">Adding Data to the End of the Table</span></span>  
 <span data-ttu-id="89fd3-132">Un factor de relleno distinto de cero o de cien puede ser conveniente para el rendimiento si los datos nuevos se distribuyen uniformemente en toda la tabla.</span><span class="sxs-lookup"><span data-stu-id="89fd3-132">A nonzero fill factor other than 0 or 100 can be good for performance if the new data is evenly distributed throughout the table.</span></span> <span data-ttu-id="89fd3-133">Sin embargo, si todos los datos se agregan al final de la tabla, el espacio vacío en las páginas de índice no se rellenará.</span><span class="sxs-lookup"><span data-stu-id="89fd3-133">However, if all the data is added to the end of the table, the empty space in the index pages will not be filled.</span></span> <span data-ttu-id="89fd3-134">Por ejemplo, si la columna de clave de índice es una columna IDENTITY, la clave de las nuevas filas siempre aumenta y las filas de índice se agregan lógicamente al final del índice.</span><span class="sxs-lookup"><span data-stu-id="89fd3-134">For example, if the index key column is an IDENTITY column, the key for new rows is always increasing and the index rows are logically added to the end of the index.</span></span> <span data-ttu-id="89fd3-135">Si las filas existentes se van a actualizar con datos que hacen aumentar el tamaño de las filas, use un factor de relleno menor que 100.</span><span class="sxs-lookup"><span data-stu-id="89fd3-135">If existing rows will be updated with data that lengthens the size of the rows, use a fill factor of less than 100.</span></span> <span data-ttu-id="89fd3-136">Los bytes adicionales en cada página ayudarán a reducir las divisiones de página ocasionadas por la longitud extra de las filas.</span><span class="sxs-lookup"><span data-stu-id="89fd3-136">The extra bytes on each page will help to minimize page splits caused by extra length in the rows.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="89fd3-137">Seguridad</span><span class="sxs-lookup"><span data-stu-id="89fd3-137">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="89fd3-138">Permisos</span><span class="sxs-lookup"><span data-stu-id="89fd3-138">Permissions</span></span>  
 <span data-ttu-id="89fd3-139">Requiere el permiso ALTER en la tabla o la vista.</span><span class="sxs-lookup"><span data-stu-id="89fd3-139">Requires ALTER permission on the table or view.</span></span> <span data-ttu-id="89fd3-140">El usuario debe ser miembro del rol fijo de servidor **sysadmin** o de los roles fijos de base de datos **db_ddladmin** y **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="89fd3-140">User must be a member of the **sysadmin** fixed server role or the **db_ddladmin** and **db_owner** fixed database roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="89fd3-141">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="89fd3-141">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-fill-factor-by-using-table-designer"></a><span data-ttu-id="89fd3-142">Para especificar un factor de relleno con el Diseñador de tablas</span><span class="sxs-lookup"><span data-stu-id="89fd3-142">To specify a fill factor by using Table Designer</span></span>  
  
1.  <span data-ttu-id="89fd3-143">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que quiera especificar el factor de relleno de un índice.</span><span class="sxs-lookup"><span data-stu-id="89fd3-143">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to specify an index's fill factor.</span></span>  
  
2.  <span data-ttu-id="89fd3-144">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="89fd3-144">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="89fd3-145">Haga clic con el botón derecho en la tabla en la que quiere especificar el factor de relleno de un índice y seleccione **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="89fd3-145">Right-click the table on which you want to specify an index's fill factor and select **Design**.</span></span>  
  
4.  <span data-ttu-id="89fd3-146">En el menú **Diseñador de tablas** , haga clic en **Índices o claves**.</span><span class="sxs-lookup"><span data-stu-id="89fd3-146">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
5.  <span data-ttu-id="89fd3-147">Seleccione el índice con el factor de relleno que desea especificar.</span><span class="sxs-lookup"><span data-stu-id="89fd3-147">Select the index with the fill factor that you want to specify.</span></span>  
  
6.  <span data-ttu-id="89fd3-148">Expanda **Especificación de relleno**, seleccione la fila **Factor de relleno** y escriba el factor de relleno que desee en la fila.</span><span class="sxs-lookup"><span data-stu-id="89fd3-148">Expand **Fill Specification**, select the **Fill Factor** row and enter the fill factor you want in the row.</span></span>  
  
7.  <span data-ttu-id="89fd3-149">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="89fd3-149">Click **Close**.</span></span>  
  
8.  <span data-ttu-id="89fd3-150">En el menú **Archivo** , seleccione **Guardar**_nombre_tabla_.</span><span class="sxs-lookup"><span data-stu-id="89fd3-150">On the **File** menu, select **Save**_table_name_.</span></span>  
  
#### <a name="to-specify-a-fill-factor-in-an-index-by-using-object-explorer"></a><span data-ttu-id="89fd3-151">Para especificar un factor de relleno en un índice mediante el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="89fd3-151">To specify a fill factor in an index by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="89fd3-152">En el Explorador de objetos, haga clic en el signo más para expandir la base de datos que contiene la tabla en la que quiera especificar el factor de relleno de un índice.</span><span class="sxs-lookup"><span data-stu-id="89fd3-152">In Object Explorer, click the plus sign to expand the database that contains the table on which you want to specify an index's fill factor.</span></span>  
  
2.  <span data-ttu-id="89fd3-153">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="89fd3-153">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="89fd3-154">Haga clic en el signo más para expandir la tabla en la que quiere especificar el factor de relleno de un índice.</span><span class="sxs-lookup"><span data-stu-id="89fd3-154">Click the plus sign to expand the table on which you want to specify an index's fill factor.</span></span>  
  
4.  <span data-ttu-id="89fd3-155">Haga clic en el signo más para expandir la carpeta **Índices** .</span><span class="sxs-lookup"><span data-stu-id="89fd3-155">Click the plus sign to expand the **Indexes** folder.</span></span>  
  
5.  <span data-ttu-id="89fd3-156">Haga clic con el botón derecho en el índice con el factor de relleno que quiere especificar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="89fd3-156">Right-click the index with the fill factor that you want to specify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="89fd3-157">Debajo de **Seleccionar una página**, seleccione **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="89fd3-157">Under **Select a page**, select **Options**.</span></span>  
  
7.  <span data-ttu-id="89fd3-158">En la fila **Factor de relleno** , escriba el factor de relleno que desee.</span><span class="sxs-lookup"><span data-stu-id="89fd3-158">In the **Fill factor** row, enter the fill factor that you want.</span></span>  
  
8.  <span data-ttu-id="89fd3-159">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="89fd3-159">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="89fd3-160">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="89fd3-160">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-fill-factor-in-an-existing-index"></a><span data-ttu-id="89fd3-161">Para especificar un factor de relleno en un índice existente</span><span class="sxs-lookup"><span data-stu-id="89fd3-161">To specify a fill factor in an existing index</span></span>  
  
1.  <span data-ttu-id="89fd3-162">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89fd3-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="89fd3-163">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="89fd3-163">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="89fd3-164">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="89fd3-164">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="89fd3-165">En el ejemplo se vuelve a generar un índice existente y se aplica el factor de relleno especificado durante la operación de nueva generación.</span><span class="sxs-lookup"><span data-stu-id="89fd3-165">The example rebuilds an existing index and applies the specified fill factor during the rebuild operation.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Rebuilds the IX_Employee_OrganizationLevel_OrganizationNode index   
    -- with a fill factor of 80 on the HumanResources.Employee table.  
  
    ALTER INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
    REBUILD WITH (FILLFACTOR = 80);   
    GO  
    ```  
  
#### <a name="another-way-to-specify-a-fill-factor-in-an-index"></a><span data-ttu-id="89fd3-166">Otra manera de especificar un factor de relleno de un índice</span><span class="sxs-lookup"><span data-stu-id="89fd3-166">Another way to specify a fill factor in an index</span></span>  
  
1.  <span data-ttu-id="89fd3-167">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89fd3-167">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="89fd3-168">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="89fd3-168">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="89fd3-169">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="89fd3-169">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    /* Drops and re-creates the IX_Employee_OrganizationLevel_OrganizationNode index on the HumanResources.Employee table with a fill factor of 80.  
    */  
  
    CREATE INDEX IX_Employee_OrganizationLevel_OrganizationNode ON HumanResources.Employee  
       (OrganizationLevel, OrganizationNode)   
    WITH (DROP_EXISTING = ON, FILLFACTOR = 80);   
    GO  
    ```  
  
 <span data-ttu-id="89fd3-170">Para obtener más información, vea [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="89fd3-170">For more information, see [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql).</span></span>  
  
  
