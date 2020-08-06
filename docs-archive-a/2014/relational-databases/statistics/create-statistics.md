---
title: Creación de estadísticas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.statistics.propertis.f1
- sql12.swb.statistics.filter.f1
- sql12.swb.stat.properties.f1
- sql12.swb.stat.columns.f1
helpviewer_keywords:
- creating statistics
- statistics [SQL Server], creating
ms.assetid: 95a455fb-664d-4c95-851e-c6b62d7ebe04
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 230bd4d840c3d59dc1267dd6801754b68386cb32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676413"
---
# <a name="create-statistics"></a><span data-ttu-id="529cf-102">Crear estadísticas</span><span class="sxs-lookup"><span data-stu-id="529cf-102">Create Statistics</span></span>
  <span data-ttu-id="529cf-103">Puede crear estadísticas de optimización de consultas en una o más columnas de una tabla o vista indizada en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="529cf-103">You can create query optimization statistics on one or more columns of a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="529cf-104">Para la mayoría de las consultas, el optimizador de consultas ya genera las estadísticas necesarias para un plan de consulta de alta calidad; en algunos casos, para obtener los mejores resultados es necesario crear estadísticas adicionales.</span><span class="sxs-lookup"><span data-stu-id="529cf-104">For most queries, the query optimizer already generates the necessary statistics for a high-quality query plan; in a few cases, you need to create additional statistics.</span></span>  
  
 <span data-ttu-id="529cf-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="529cf-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="529cf-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="529cf-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="529cf-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="529cf-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="529cf-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="529cf-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="529cf-109">**Para crear estadísticas con:**</span><span class="sxs-lookup"><span data-stu-id="529cf-109">**To create statistics, using:**</span></span>  
  
     [<span data-ttu-id="529cf-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="529cf-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="529cf-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="529cf-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="529cf-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="529cf-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="529cf-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="529cf-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="529cf-114">Antes de crear estadísticas con la instrucción CREATE STATISTICS, compruebe que la opción AUTO_CREATE_STATISTICS está establecida en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="529cf-114">Before creating statistics with the CREATE STATISTICS statement, verify that the AUTO_CREATE_STATISTICS option is set at the database level.</span></span> <span data-ttu-id="529cf-115">De este modo se asegurará de que el optimizador de consultas continúe creando rutinariamente estadísticas de una sola columna para las columnas del predicado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="529cf-115">This will ensure that the query optimizer continues to routinely create single-column statistics for query predicate columns.</span></span>  
  
-   <span data-ttu-id="529cf-116">Puede mostrar hasta 32 columnas por objeto de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-116">You can list up to 32 columns per statistics object.</span></span>  
  
-   <span data-ttu-id="529cf-117">No se puede quitar, modificar ni cambiar la definición de una columna de la tabla que se define en un predicado de estadísticas filtrado.</span><span class="sxs-lookup"><span data-stu-id="529cf-117">You cannot drop, rename, or alter the definition of a table column that is defined in a filtered statistics predicate.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="529cf-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="529cf-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="529cf-119">Permisos</span><span class="sxs-lookup"><span data-stu-id="529cf-119">Permissions</span></span>  
 <span data-ttu-id="529cf-120">Requiere que el usuario sea el propietario de la tabla o vista indexada o un miembro de uno de los roles siguientes: rol fijo de servidor **sysadmin** , rol fijo de base de datos **db_owner** o rol fijo de base de datos **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="529cf-120">Requires that the user be the table or indexed view owner, or a member of one of the following roles: **sysadmin** fixed server role, **db_owner** fixed database role, or the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="529cf-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="529cf-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-statistics"></a><span data-ttu-id="529cf-122">Para crear estadísticas</span><span class="sxs-lookup"><span data-stu-id="529cf-122">To create statistics</span></span>  
  
1.  <span data-ttu-id="529cf-123">En el **Explorador de objetos**, haga clic en el signo más para expandir la base de datos en la que desea crear una nueva estadística.</span><span class="sxs-lookup"><span data-stu-id="529cf-123">In **Object Explorer**, click the plus sign to expand the database in which you want to create a new statistic.</span></span>  
  
2.  <span data-ttu-id="529cf-124">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="529cf-124">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="529cf-125">Haga clic en el signo más para expandir la tabla en la que desea crear una nueva estadística.</span><span class="sxs-lookup"><span data-stu-id="529cf-125">Click the plus sign to expand the table in which you want to create a new statistic.</span></span>  
  
4.  <span data-ttu-id="529cf-126">Haga clic con el botón derecho en la carpeta **Estadísticas** y, después, seleccione **Nueva estadística...** .</span><span class="sxs-lookup"><span data-stu-id="529cf-126">Right-click the **Statistics** folder and select **New Statistics...**.</span></span>  
  
     <span data-ttu-id="529cf-127">Las siguientes propiedades se muestran en la página **General** del cuadro de diálogo **nuevas estadísticas de la tabla**_TABLE_NAME_ .</span><span class="sxs-lookup"><span data-stu-id="529cf-127">The following properties show on the **General** page in the **New Statistics on Table**_table_name_ dialog box.</span></span>  
  
     <span data-ttu-id="529cf-128">**Nombre de tabla**</span><span class="sxs-lookup"><span data-stu-id="529cf-128">**Table Name**</span></span>  
     <span data-ttu-id="529cf-129">Muestra el nombre de la tabla descrita por las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-129">Displays the name of the table described by the statistics.</span></span>  
  
     <span data-ttu-id="529cf-130">**Nombre de las estadísticas**</span><span class="sxs-lookup"><span data-stu-id="529cf-130">**Statistics Name**</span></span>  
     <span data-ttu-id="529cf-131">Muestra el nombre del objeto de base de datos donde se almacenan las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-131">Displays the name of the database object where the statistics are stored.</span></span>  
  
     <span data-ttu-id="529cf-132">**Columnas de estadísticas**</span><span class="sxs-lookup"><span data-stu-id="529cf-132">**Statistics Columns**</span></span>  
     <span data-ttu-id="529cf-133">Esta cuadrícula muestra las columnas descritas por este conjunto de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-133">This grid shows the columns described by this set of statistics.</span></span> <span data-ttu-id="529cf-134">Todos los valores de la cuadrícula son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="529cf-134">All values in the grid are read-only.</span></span>  
  
     <span data-ttu-id="529cf-135">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="529cf-135">**Name**</span></span>  
     <span data-ttu-id="529cf-136">Muestra el nombre de la columna descrita por las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-136">Displays the name of the column described by the statistics.</span></span> <span data-ttu-id="529cf-137">Puede ser una sola columna o una combinación de columnas de una sola tabla.</span><span class="sxs-lookup"><span data-stu-id="529cf-137">This can be a single column or a combination of columns in a single table.</span></span>  
  
     <span data-ttu-id="529cf-138">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="529cf-138">**Data Type**</span></span>  
     <span data-ttu-id="529cf-139">Indica el tipo de datos de las columnas descritas por las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-139">Indicates the data type of the columns described by the statistics.</span></span>  
  
     <span data-ttu-id="529cf-140">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="529cf-140">**Size**</span></span>  
     <span data-ttu-id="529cf-141">Muestra el tamaño del tipo de datos de cada columna.</span><span class="sxs-lookup"><span data-stu-id="529cf-141">Displays the size of the data type for each column.</span></span>  
  
     <span data-ttu-id="529cf-142">**Identidad**</span><span class="sxs-lookup"><span data-stu-id="529cf-142">**Identity**</span></span>  
     <span data-ttu-id="529cf-143">Cuando se activa, indica una columna de identidad.</span><span class="sxs-lookup"><span data-stu-id="529cf-143">Indicates an identity column when it is checked.</span></span>  
  
     <span data-ttu-id="529cf-144">**Permitir valores NULL**</span><span class="sxs-lookup"><span data-stu-id="529cf-144">**Allow Nulls**</span></span>  
     <span data-ttu-id="529cf-145">Indica si la columna acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="529cf-145">Indicates whether the column accepts NULL values.</span></span>  
  
     <span data-ttu-id="529cf-146">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="529cf-146">**Add**</span></span>  
     <span data-ttu-id="529cf-147">Agregue columnas adicionales de la tabla a la cuadrícula de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-147">Add additional columns from the table to the statistics grid.</span></span>  
  
     <span data-ttu-id="529cf-148">**Remove**</span><span class="sxs-lookup"><span data-stu-id="529cf-148">**Remove**</span></span>  
     <span data-ttu-id="529cf-149">Quita la columna seleccionada de la cuadrícula de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-149">Remove the selected column from the statistics grid.</span></span>  
  
     <span data-ttu-id="529cf-150">**Subir**</span><span class="sxs-lookup"><span data-stu-id="529cf-150">**Move Up**</span></span>  
     <span data-ttu-id="529cf-151">Desplaza la columna seleccionada a una ubicación anterior de la cuadrícula de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-151">Move the selected column to an earlier location in the statistics grid.</span></span> <span data-ttu-id="529cf-152">La ubicación en la cuadrícula puede afectar considerablemente a la utilidad de las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-152">The location in the grid can substantially impact the usefulness of the statistics.</span></span>  
  
     <span data-ttu-id="529cf-153">**Bajar**</span><span class="sxs-lookup"><span data-stu-id="529cf-153">**Move Down**</span></span>  
     <span data-ttu-id="529cf-154">Desplaza la columna seleccionada a una ubicación posterior de la cuadrícula de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-154">Move the selected column to a later location in the statistics grid.</span></span>  
  
     <span data-ttu-id="529cf-155">**Las estadísticas de estas columnas se actualizaron por última vez:**</span><span class="sxs-lookup"><span data-stu-id="529cf-155">**Statistics for these columns were last updated:**</span></span>  
     <span data-ttu-id="529cf-156">Indica la antigüedad de las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-156">Indicates how old the statistics are.</span></span> <span data-ttu-id="529cf-157">Las estadísticas actuales tienen mayor valor.</span><span class="sxs-lookup"><span data-stu-id="529cf-157">Statistics are more valuable when they are current.</span></span> <span data-ttu-id="529cf-158">Actualice las estadísticas después de realizar grandes cambios en los datos o después de agregar datos atípicos.</span><span class="sxs-lookup"><span data-stu-id="529cf-158">Update statistics after large changes to the data or after adding atypical data.</span></span> <span data-ttu-id="529cf-159">Las estadísticas de las tablas que tienen una distribución coherente de datos deben actualizarse con menor frecuencia.</span><span class="sxs-lookup"><span data-stu-id="529cf-159">Statistics for tables that have a consistent distribution of data need to be updated less frequently.</span></span>  
  
     <span data-ttu-id="529cf-160">**Actualizar estadísticas de estas columnas**</span><span class="sxs-lookup"><span data-stu-id="529cf-160">**Update statistics for these columns**</span></span>  
     <span data-ttu-id="529cf-161">Comprueba la actualización de las estadísticas cuando se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="529cf-161">Check to update the statistics when the dialog box is closed.</span></span>  
  
     <span data-ttu-id="529cf-162">La siguiente propiedad se muestra en la página **filtro** del cuadro de diálogo **nuevas estadísticas de la tabla**_TABLE_NAME_ .</span><span class="sxs-lookup"><span data-stu-id="529cf-162">The following property shows on the **Filter** page in the **New Statistics on Table**_table_name_ dialog box.</span></span>  
  
     <span data-ttu-id="529cf-163">**Expresión de filtro**</span><span class="sxs-lookup"><span data-stu-id="529cf-163">**Filter Expression**</span></span>  
     <span data-ttu-id="529cf-164">Define qué filas de datos se incluyen en las estadísticas filtradas.</span><span class="sxs-lookup"><span data-stu-id="529cf-164">Defines which data rows to include in the filtered statistics.</span></span> <span data-ttu-id="529cf-165">Por ejemplo: `Production.ProductSubcategoryID IN ( 1,2,3 )`</span><span class="sxs-lookup"><span data-stu-id="529cf-165">For example, `Production.ProductSubcategoryID IN ( 1,2,3 )`</span></span>  
  
5.  <span data-ttu-id="529cf-166">En el cuadro de diálogo **nuevas estadísticas de la tabla**_TABLE_NAME_ , en la página **General** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="529cf-166">In the **New Statistics on Table**_table_name_ dialog box, on the **General** page, click **Add**.</span></span>  
  
     <span data-ttu-id="529cf-167">Las propiedades siguientes se muestran en el cuadro de diálogo **Seleccionar columnas** .</span><span class="sxs-lookup"><span data-stu-id="529cf-167">The following properties show in the **Select Columns** dialog box.</span></span> <span data-ttu-id="529cf-168">Esta información es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="529cf-168">This information is read-only.</span></span>  
  
     <span data-ttu-id="529cf-169">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="529cf-169">**Name**</span></span>  
     <span data-ttu-id="529cf-170">Muestra el nombre de la columna descrita por las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-170">Displays the name of the column described by the statistics.</span></span> <span data-ttu-id="529cf-171">Puede ser una sola columna o una combinación de columnas de una sola tabla.</span><span class="sxs-lookup"><span data-stu-id="529cf-171">This can be a single column or a combination of columns in a single table.</span></span>  
  
     <span data-ttu-id="529cf-172">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="529cf-172">**Data Type**</span></span>  
     <span data-ttu-id="529cf-173">Indica el tipo de datos de las columnas descritas por las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="529cf-173">Indicates the data type of the columns described by the statistics.</span></span>  
  
     <span data-ttu-id="529cf-174">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="529cf-174">**Size**</span></span>  
     <span data-ttu-id="529cf-175">Muestra el tamaño del tipo de datos de cada columna.</span><span class="sxs-lookup"><span data-stu-id="529cf-175">Displays the size of the data type for each column.</span></span>  
  
     <span data-ttu-id="529cf-176">**Identidad**</span><span class="sxs-lookup"><span data-stu-id="529cf-176">**Identity**</span></span>  
     <span data-ttu-id="529cf-177">Cuando se activa, indica una columna de identidad.</span><span class="sxs-lookup"><span data-stu-id="529cf-177">Indicates an identity column when checked.</span></span>  
  
     <span data-ttu-id="529cf-178">**Permitir valores NULL**</span><span class="sxs-lookup"><span data-stu-id="529cf-178">**Allow NULLs**</span></span>  
     <span data-ttu-id="529cf-179">Indica si la columna acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="529cf-179">Indicates whether the column accepts NULL values.</span></span>  
  
6.  <span data-ttu-id="529cf-180">En el cuadro de diálogo **Seleccionar columnas** , active la casilla o casillas de cada columna para la que desee crear una estadística y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="529cf-180">In the **Select Columns** dialog box, select the check box or check boxes of each column for which you want to create a statistic and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="529cf-181">En el cuadro de diálogo **nuevas estadísticas de la tabla**_TABLE_NAME_ , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="529cf-181">In the **New Statistics on Table**_table_name_ dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="529cf-182">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="529cf-182">Using Transact-SQL</span></span>  
  
#### <a name="to-create-statistics"></a><span data-ttu-id="529cf-183">Para crear estadísticas</span><span class="sxs-lookup"><span data-stu-id="529cf-183">To create statistics</span></span>  
  
1.  <span data-ttu-id="529cf-184">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="529cf-184">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="529cf-185">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="529cf-185">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="529cf-186">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="529cf-186">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Create new statistic object called ContactMail1  
    -- on the BusinessEntityID and EmailPromotion columns in the Person.Person table.   
  
    CREATE STATISTICS ContactMail1  
        ON Person.Person (BusinessEntityID, EmailPromotion);   
    GO  
    ```  
  
4.  <span data-ttu-id="529cf-187">La estadística creada anteriormente puede mejorar los resultados de la consulta siguiente.</span><span class="sxs-lookup"><span data-stu-id="529cf-187">The statistic created above potentially improves the results for the following query.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT LastName, FirstName  
    FROM Person.Person  
    WHERE EmailPromotion = 2  
    ORDER BY LastName, FirstName;   
    GO  
    ```  
  
 <span data-ttu-id="529cf-188">Para obtener más información, vea [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="529cf-188">For more information, see [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span></span>  
  
  
