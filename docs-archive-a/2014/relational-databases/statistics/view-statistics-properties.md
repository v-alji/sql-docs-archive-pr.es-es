---
title: Ver propiedades de estadísticas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.statistics.details.f1
helpviewer_keywords:
- viewing statistics properties
- statistics [SQL Server], viewing properties
ms.assetid: 0eaa2101-006e-4015-9979-3468b50e0aaa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 63cabc5d8844982604993acac6a791317ee36925
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676399"
---
# <a name="view-statistics-properties"></a><span data-ttu-id="9ee86-102">Ver propiedades de estadísticas</span><span class="sxs-lookup"><span data-stu-id="9ee86-102">View Statistics Properties</span></span>
  <span data-ttu-id="9ee86-103">Puede mostrar las estadísticas de optimización de consultas actuales para una tabla o vista indizada en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ee86-103">You can display current query optimization statistics for a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9ee86-104">Los objetos de estadísticas incluyen un encabezado con metadatos sobre las estadísticas, un histograma con la distribución de valores de la primera columna de clave del objeto de estadísticas y un vector de la densidad para medir la correlación entre las columnas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-104">Statistics objects include a header with metadata about the statistics, a histogram with the distribution of values in the first key column of the statistics object, and a density vector to measure cross-column correlation.</span></span> <span data-ttu-id="9ee86-105">Para obtener más información sobre histogramas y vectores de densidad, vea [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9ee86-105">For more information about histograms and density vectors, see [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql)</span></span>  
  
 <span data-ttu-id="9ee86-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="9ee86-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9ee86-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="9ee86-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9ee86-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9ee86-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9ee86-109">**Para ver propiedades de estadísticas, mediante:**</span><span class="sxs-lookup"><span data-stu-id="9ee86-109">**To view statistics properties, using:**</span></span>  
  
     [<span data-ttu-id="9ee86-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ee86-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9ee86-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ee86-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9ee86-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="9ee86-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9ee86-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9ee86-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9ee86-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="9ee86-114">Permissions</span></span>  
 <span data-ttu-id="9ee86-115">Para ver el objeto de estadísticas, el usuario debe ser propietario de la tabla o miembro del rol fijo de servidor `sysadmin`, del rol fijo de base de datos `db_owner` o del rol fijo de base de datos `db_ddladmin`.</span><span class="sxs-lookup"><span data-stu-id="9ee86-115">In order to view the statistics object, the user must own the table or the user must be a member of the `sysadmin` fixed server role, the `db_owner` fixed database role, or the `db_ddladmin` fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9ee86-116">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9ee86-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-statistics-properties"></a><span data-ttu-id="9ee86-117">Para ver las propiedades de estadísticas</span><span class="sxs-lookup"><span data-stu-id="9ee86-117">To view statistics properties</span></span>  
  
1.  <span data-ttu-id="9ee86-118">En el **Explorador de objetos**, haga clic en el signo más para expandir la base de datos en la que desea crear una nueva estadística.</span><span class="sxs-lookup"><span data-stu-id="9ee86-118">In **Object Explorer**, click the plus sign to expand the database in which you want to create a new statistic.</span></span>  
  
2.  <span data-ttu-id="9ee86-119">Haga clic en el signo más para expandir la carpeta **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="9ee86-119">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="9ee86-120">Haga clic en el signo más para expandir la tabla en la que quiere ver las propiedades de las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-120">Click the plus sign to expand the table in which you want to view the statistic's properties.</span></span>  
  
4.  <span data-ttu-id="9ee86-121">Haga clic en el signo más para expandir la carpeta **Estadísticas** .</span><span class="sxs-lookup"><span data-stu-id="9ee86-121">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="9ee86-122">Haga clic con el botón derecho en el objeto Estadísticas cuyas propiedades quiere ver y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9ee86-122">Right-click the Statistics object of which you want to view the properties and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="9ee86-123">En el cuadro de diálogo **Propiedades de estadísticas -** _nombre de estadísticas_, en el panel **Seleccionar una página**, seleccione **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="9ee86-123">In the **Statistics Properties -** _statistics_name_ dialog box, in the **Select a page** pane, select **Details**.</span></span>  
  
     <span data-ttu-id="9ee86-124">Las propiedades siguientes se muestran en la página **Detalles** del cuadro de diálogo **Propiedades de estadísticas -** _nombre de estadísticas_.</span><span class="sxs-lookup"><span data-stu-id="9ee86-124">The following properties show on the **Details** page in the **Statistics Properties -** _statistics_name_ dialog box.</span></span>  
  
     <span data-ttu-id="9ee86-125">**Nombre de tabla**</span><span class="sxs-lookup"><span data-stu-id="9ee86-125">**Table Name**</span></span>  
     <span data-ttu-id="9ee86-126">Muestra el nombre de la tabla descrita por las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-126">Displays the name of the table described by the statistics.</span></span>  
  
     <span data-ttu-id="9ee86-127">**Nombre de las estadísticas**</span><span class="sxs-lookup"><span data-stu-id="9ee86-127">**Statistics Name**</span></span>  
     <span data-ttu-id="9ee86-128">Muestra el nombre del objeto de base de datos donde se almacenan las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-128">Displays the name of the database object where the statistics are stored.</span></span>  
  
     <span data-ttu-id="9ee86-129">**Estadísticas para INDEXnombre_de_estadísticas**</span><span class="sxs-lookup"><span data-stu-id="9ee86-129">**Statistics for INDEXstatistics_name**</span></span>  
     <span data-ttu-id="9ee86-130">Este cuadro de texto muestra las propiedades devueltas del objeto de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-130">This text box shows the properties returned from the statistics object.</span></span> <span data-ttu-id="9ee86-131">Estas propiedades se dividen en tres secciones: Encabezado de estadísticas, Vector de densidad e Histograma.</span><span class="sxs-lookup"><span data-stu-id="9ee86-131">This properties are divided into three sections: Stats Header, Density Vector, and Histogram.</span></span>  
  
     <span data-ttu-id="9ee86-132">La siguiente información se describen las columnas devueltas en el conjunto de resultados para el encabezado de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-132">The following information describes the columns returned in the result set for the Stats Header.</span></span>  
  
     <span data-ttu-id="9ee86-133">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9ee86-133">**Name**</span></span>  
     <span data-ttu-id="9ee86-134">Nombre del objeto de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-134">Name of the statistics object.</span></span>  
  
     <span data-ttu-id="9ee86-135">**Updated**</span><span class="sxs-lookup"><span data-stu-id="9ee86-135">**Updated**</span></span>  
     <span data-ttu-id="9ee86-136">Fecha y hora de la última actualización de las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-136">Date and time the statistics were last updated.</span></span>  
  
     <span data-ttu-id="9ee86-137">**Filas**</span><span class="sxs-lookup"><span data-stu-id="9ee86-137">**Rows**</span></span>  
     <span data-ttu-id="9ee86-138">Número total de filas que tenía la tabla o vista indizada la última vez que se actualizaron las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-138">Total number of rows in the table or indexed view when the statistics were last updated.</span></span> <span data-ttu-id="9ee86-139">Si las estadísticas se filtran o corresponden a un índice filtrado, el número de filas puede ser inferior al número de filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9ee86-139">If the statistics are filtered or correspond to a filtered index, the number of rows might be less than the number of rows in the table.</span></span>  
  
     <span data-ttu-id="9ee86-140">**Rows Sampled**</span><span class="sxs-lookup"><span data-stu-id="9ee86-140">**Rows Sampled**</span></span>  
     <span data-ttu-id="9ee86-141">Número total de filas muestreadas para cálculos de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-141">Total number of rows sampled for statistics calculations.</span></span> <span data-ttu-id="9ee86-142">Si Rows Sampled < Rows, el histograma y los resultados de la densidad que se muestren serán estimaciones extraídas de las filas muestreadas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-142">If Rows Sampled < Rows, the displayed histogram and density results are estimates based on the sampled rows.</span></span>  
  
     <span data-ttu-id="9ee86-143">**Pasos**</span><span class="sxs-lookup"><span data-stu-id="9ee86-143">**Steps**</span></span>  
     <span data-ttu-id="9ee86-144">Número de pasos del histograma.</span><span class="sxs-lookup"><span data-stu-id="9ee86-144">Number of steps in the histogram.</span></span> <span data-ttu-id="9ee86-145">Cada paso abarca un intervalo de valores de columna seguido de un valor de columna límite superior.</span><span class="sxs-lookup"><span data-stu-id="9ee86-145">Each step spans a range of column values followed by an upper bound column value.</span></span> <span data-ttu-id="9ee86-146">Los pasos del histograma se definen en la primera columna de clave de las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-146">The histogram steps are defined on the first key column in the statistics.</span></span> <span data-ttu-id="9ee86-147">El número máximo de pasos es 200.</span><span class="sxs-lookup"><span data-stu-id="9ee86-147">The maximum number of steps is 200.</span></span>  
  
     <span data-ttu-id="9ee86-148">**Densidad**</span><span class="sxs-lookup"><span data-stu-id="9ee86-148">**Density**</span></span>  
     <span data-ttu-id="9ee86-149">Se calcula como 1 / *valores distintos* en todos los valores de la primera columna de clave del objeto de estadísticas, excepto en los valores límite del histograma.</span><span class="sxs-lookup"><span data-stu-id="9ee86-149">Calculated as 1 / *distinct values* for all values in the first key column of the statistics object, excluding the histogram boundary values.</span></span> <span data-ttu-id="9ee86-150">El optimizador de consultas no usa este valor de densidad y solo se muestra por motivos de compatibilidad con versiones anteriores a SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="9ee86-150">This Density value is not used by the query optimizer and is displayed for backward compatibility with versions before SQL Server 2008.</span></span>  
  
     <span data-ttu-id="9ee86-151">**Promedio de longitud de clave**</span><span class="sxs-lookup"><span data-stu-id="9ee86-151">**Average Key Length**</span></span>  
     <span data-ttu-id="9ee86-152">Número promedio de bytes por cada uno de los valores de las columnas de clave del objeto de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-152">Average number of bytes per value for all of the key columns in the statistics object.</span></span>  
  
     <span data-ttu-id="9ee86-153">**String Index**</span><span class="sxs-lookup"><span data-stu-id="9ee86-153">**String Index**</span></span>  
     <span data-ttu-id="9ee86-154">Sí indica que el objeto de estadísticas contiene estadísticas de resumen de las cadenas para mejorar los cálculos de cardinalidad de los predicados de consulta que utilizan el operador LIKE; por ejemplo, `WHERE ProductName LIKE '%Bike'`.</span><span class="sxs-lookup"><span data-stu-id="9ee86-154">Yes indicates the statistics object contains string summary statistics to improve the cardinality estimates for query predicates that use the LIKE operator; for example, `WHERE ProductName LIKE '%Bike'`.</span></span> <span data-ttu-id="9ee86-155">Las estadísticas de resumen de cadenas se almacenan de forma independiente del histograma y se crean en la primera columna de clave del objeto de estadísticas cuando es de tipo **char**, **varchar**, **nchar**, **nvarchar**, **varchar(max)** , **nvarchar(max)** , **text**o **ntext**.</span><span class="sxs-lookup"><span data-stu-id="9ee86-155">String summary statistics are stored separately from the histogram and are created on the first key column of the statistics object when it is of type **char**, **varchar**, **nchar**, **nvarchar**, **varchar(max)**, **nvarchar(max)**, **text**, or **ntext**.</span></span>  
  
     <span data-ttu-id="9ee86-156">**Expresión de filtro**</span><span class="sxs-lookup"><span data-stu-id="9ee86-156">**Filter Expression**</span></span>  
     <span data-ttu-id="9ee86-157">Predicado del subconjunto de filas de la tabla incluido en el objeto de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-157">Predicate for the subset of table rows included in the statistics object.</span></span> <span data-ttu-id="9ee86-158">NULL = Estadísticas no filtradas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-158">NULL = non-filtered statistics.</span></span>  
  
     <span data-ttu-id="9ee86-159">**Filas sin filtrar**</span><span class="sxs-lookup"><span data-stu-id="9ee86-159">**Unfiltered Rows**</span></span>  
     <span data-ttu-id="9ee86-160">Número total de filas de la tabla antes de aplicar la expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="9ee86-160">Total number of rows in the table before applying the filter expression.</span></span> <span data-ttu-id="9ee86-161">Si Expresión de filtro es NULL, las Filas sin filtrar son iguales a Filas.</span><span class="sxs-lookup"><span data-stu-id="9ee86-161">If Filter Expression is NULL, Unfiltered Rows is equal to Rows.</span></span>  
  
     <span data-ttu-id="9ee86-162">La siguiente información describe las columnas devueltas en el conjunto de resultados del vector de densidad.</span><span class="sxs-lookup"><span data-stu-id="9ee86-162">The following information describes the columns returned in the result set for the Density Vector.</span></span>  
  
     <span data-ttu-id="9ee86-163">**Toda la densidad**</span><span class="sxs-lookup"><span data-stu-id="9ee86-163">**All Density**</span></span>  
     <span data-ttu-id="9ee86-164">La densidad es 1 / *valores distintos*.</span><span class="sxs-lookup"><span data-stu-id="9ee86-164">Density is 1 / *distinct values*.</span></span> <span data-ttu-id="9ee86-165">Los resultados muestran la densidad de cada prefijo de columnas del objeto de estadísticas (una fila por cada densidad).</span><span class="sxs-lookup"><span data-stu-id="9ee86-165">Results display density for each prefix of columns in the statistics object, one row per density.</span></span> <span data-ttu-id="9ee86-166">Un valor distinto es una lista Distinct de los valores de columna de cada fila y prefijo de columna.</span><span class="sxs-lookup"><span data-stu-id="9ee86-166">A distinct value is a distinct list of the column values per row and per columns prefix.</span></span> <span data-ttu-id="9ee86-167">Por ejemplo, si el objeto de estadísticas contiene las columnas de clave (A, B, C), los resultados indican la densidad de las listas de valores distintos de cada uno de estos prefijos de columna: (A), (A,B) y (A, B, C).</span><span class="sxs-lookup"><span data-stu-id="9ee86-167">For example, if the statistics object contains key columns (A, B, C), the results report the density of the distinct lists of values in each of these column prefixes: (A), (A,B), and (A, B, C).</span></span> <span data-ttu-id="9ee86-168">Si se usa el prefijo (A, B, C), cada una de estas listas es una lista de valores distintos: (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7).</span><span class="sxs-lookup"><span data-stu-id="9ee86-168">Using the prefix (A, B, C), each of these lists is a distinct value list: (3, 5, 6), (4, 4, 6), (4, 5, 6), (4, 5, 7).</span></span> <span data-ttu-id="9ee86-169">Si se usa el prefijo (A, B) los valores de la misma columna tendrán estas listas de valores distintos: (3, 5), (4, 4) y (4, 5).</span><span class="sxs-lookup"><span data-stu-id="9ee86-169">Using the prefix (A, B) the same column values have these distinct value lists: (3, 5), (4, 4), and (4, 5).</span></span>  
  
     <span data-ttu-id="9ee86-170">**Promedio de longitud**</span><span class="sxs-lookup"><span data-stu-id="9ee86-170">**Average Length**</span></span>  
     <span data-ttu-id="9ee86-171">Promedio de longitud, en bytes, para almacenar una lista de los valores de columna del prefijo de columna.</span><span class="sxs-lookup"><span data-stu-id="9ee86-171">Average length, in bytes, to store a list of the column values for the column prefix.</span></span> <span data-ttu-id="9ee86-172">Por ejemplo, si cada valor de la lista (3, 5, 6) necesita 4 bytes, la longitud es 12 bytes.</span><span class="sxs-lookup"><span data-stu-id="9ee86-172">For example, if the values in the list (3, 5, 6) each require 4 bytes the length is 12 bytes.</span></span>  
  
     <span data-ttu-id="9ee86-173">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="9ee86-173">**Columns**</span></span>  
     <span data-ttu-id="9ee86-174">Nombres de las columnas en el prefijo para las que se muestran Toda la densidad y Promedio de longitud.</span><span class="sxs-lookup"><span data-stu-id="9ee86-174">Names of columns in the prefix for which All density and Average length are displayed.</span></span>  
  
     <span data-ttu-id="9ee86-175">La siguiente información describe las columnas devueltas en el conjunto de resultados del histograma.</span><span class="sxs-lookup"><span data-stu-id="9ee86-175">The following information describes the columns returned in the result set for the Histogram.</span></span>  
  
     <span data-ttu-id="9ee86-176">**RANGE_HI_KEY**</span><span class="sxs-lookup"><span data-stu-id="9ee86-176">**RANGE_HI_KEY**</span></span>  
     <span data-ttu-id="9ee86-177">Valor de columna límite superior de un paso del histograma.</span><span class="sxs-lookup"><span data-stu-id="9ee86-177">Upper bound column value for a histogram step.</span></span> <span data-ttu-id="9ee86-178">El valor de columna también se denomina valor de clave.</span><span class="sxs-lookup"><span data-stu-id="9ee86-178">The column value is also called a key value.</span></span>  
  
     <span data-ttu-id="9ee86-179">**RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="9ee86-179">**RANGE_ROWS**</span></span>  
     <span data-ttu-id="9ee86-180">Número calculado de filas cuyo valor de columna está comprendido en un paso del histograma, sin incluir el límite superior.</span><span class="sxs-lookup"><span data-stu-id="9ee86-180">Estimated number of rows whose column value falls within a histogram step, excluding the upper bound.</span></span>  
  
     <span data-ttu-id="9ee86-181">**EQ_ROWS**</span><span class="sxs-lookup"><span data-stu-id="9ee86-181">**EQ_ROWS**</span></span>  
     <span data-ttu-id="9ee86-182">Número calculado de filas cuyo valor de columna es igual al límite superior del paso del histograma.</span><span class="sxs-lookup"><span data-stu-id="9ee86-182">Estimated number of rows whose column value equals the upper bound of the histogram step.</span></span>  
  
     <span data-ttu-id="9ee86-183">**DISTINCT_RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="9ee86-183">**DISTINCT_RANGE_ROWS**</span></span>  
     <span data-ttu-id="9ee86-184">Número calculado de filas que tienen un valor de columna distinto en un paso del histograma, sin incluir el límite superior.</span><span class="sxs-lookup"><span data-stu-id="9ee86-184">Estimated number of rows with a distinct column value within a histogram step, excluding the upper bound.</span></span>  
  
     <span data-ttu-id="9ee86-185">**AVG_RANGE_ROWS**</span><span class="sxs-lookup"><span data-stu-id="9ee86-185">**AVG_RANGE_ROWS**</span></span>  
     <span data-ttu-id="9ee86-186">Número medio de filas que tienen valores de columna duplicados en un paso del histograma, sin incluir el límite superior (RANGE_ROWS/DISTINCT_RANGE_ROWS para DISTINCT_RANGE_ROWS > 0).</span><span class="sxs-lookup"><span data-stu-id="9ee86-186">Average number of rows with duplicate column values within a histogram step, excluding the upper bound (RANGE_ROWS / DISTINCT_RANGE_ROWS for DISTINCT_RANGE_ROWS > 0).</span></span>  
  
7.  <span data-ttu-id="9ee86-187">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ee86-187">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9ee86-188">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9ee86-188">Using Transact-SQL</span></span>  
  
#### <a name="to-view-statistics-properties"></a><span data-ttu-id="9ee86-189">Para ver las propiedades de estadísticas</span><span class="sxs-lookup"><span data-stu-id="9ee86-189">To view statistics properties</span></span>  
  
1.  <span data-ttu-id="9ee86-190">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ee86-190">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9ee86-191">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="9ee86-191">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9ee86-192">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="9ee86-192">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- The following example displays all statistics information for the AK_Address_rowguid index of the Person.Address table.   
    DBCC SHOW_STATISTICS ("Person.Address", AK_Address_rowguid);   
    GO  
    ```  
  
 <span data-ttu-id="9ee86-193">Para obtener más información, vea [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9ee86-193">For more information, see [DBCC SHOW_STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-show-statistics-transact-sql).</span></span>  
  
#### <a name="to-find-all-of-the-statistics-on-a-table-or-view"></a><span data-ttu-id="9ee86-194">Para buscar todas las estadísticas de una tabla o vista</span><span class="sxs-lookup"><span data-stu-id="9ee86-194">To find all of the statistics on a table or view</span></span>  
  
1.  <span data-ttu-id="9ee86-195">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ee86-195">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9ee86-196">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="9ee86-196">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9ee86-197">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="9ee86-197">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    /*Gets the following information: name and ID of the statistics, whether the statistics were created automatically or by the user, whether the statistics were created with the NORECOMPUTE option, and whether the statistics have a filter and, if so, what that filter is.  
    */  
    SELECT name AS statistics_name  
        ,stats_id  
        ,auto_created  
        ,user_created  
        ,no_recompute  
        ,has_filter  
        ,filter_definition  
    -- using the sys.stats catalog view  
    FROM sys.stats  
    -- for the Sales.SpecialOffer table  
    WHERE object_id = OBJECT_ID('Sales.SpecialOffer');  
    GO  
    ```  
  
 <span data-ttu-id="9ee86-198">Para obtener más información, vea [sys.stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9ee86-198">For more information, see [sys.stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-stats-transact-sql).</span></span>  
  
  
