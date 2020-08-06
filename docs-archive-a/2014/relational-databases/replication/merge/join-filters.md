---
title: Filtros de combinación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server replication], join
- publications [SQL Server replication], join filters
- merge replication join filters [SQL Server replication]
- join filters
ms.assetid: dd78fd8f-56e3-4582-9abd-6bc25c91e075
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b97e7d7b53e6a3fdb242d1272e013bbd45f0ed17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661956"
---
# <a name="join-filters"></a><span data-ttu-id="2eae5-102">filtros de combinación</span><span class="sxs-lookup"><span data-stu-id="2eae5-102">Join Filters</span></span>
  <span data-ttu-id="2eae5-103">Un filtro de combinación permite filtrar una tabla en función de cómo se haya filtrado una tabla relacionada en la publicación.</span><span class="sxs-lookup"><span data-stu-id="2eae5-103">A join filter allows a table to be filtered based on how a related table in the publication is filtered.</span></span> <span data-ttu-id="2eae5-104">Normalmente, una tabla primaria se filtra utilizando un filtro con parámetros; por tanto, los filtros de combinación se definen de manera muy similar a como se define una combinación entre tablas.</span><span class="sxs-lookup"><span data-stu-id="2eae5-104">Typically a parent table is filtered using a parameterized filter; then one or more join filters are defined in much the same way that you define a join between tables.</span></span> <span data-ttu-id="2eae5-105">Los filtros de combinación amplían el filtro con parámetros de modo que los datos de las tablas relacionadas solo se replican si coinciden con la cláusula del filtro de combinación.</span><span class="sxs-lookup"><span data-stu-id="2eae5-105">The join filters extend the parameterized filter so that the data in the related tables is only replicated if it matches the join filter clause.</span></span>  
  
 <span data-ttu-id="2eae5-106">Normalmente, los filtros de combinación siguen las relaciones entre clave principal y clave externa definidas para las tablas en las que se aplican, aunque no se limitan estrictamente a dichas relaciones.</span><span class="sxs-lookup"><span data-stu-id="2eae5-106">Join filters typically follow the primary key/foreign key relationships defined for the tables to which they are applied, but they are not limited strictly to primary key/foreign key relationships.</span></span> <span data-ttu-id="2eae5-107">Un filtro de combinación puede estar basado en cualquier lógica que compare datos relacionados en dos tablas.</span><span class="sxs-lookup"><span data-stu-id="2eae5-107">The join filter can be based on any logic that compares related data in two tables.</span></span>  
  
 <span data-ttu-id="2eae5-108">Considere las siguientes tablas de la base de datos de ejemplo [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] , que tienen relaciones de clave principal a clave externa:</span><span class="sxs-lookup"><span data-stu-id="2eae5-108">Consider the following tables in the [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] sample database, which are related through primary key to foreign key relationships:</span></span>  
  
-   <span data-ttu-id="2eae5-109">**HumanResources.Employee**</span><span class="sxs-lookup"><span data-stu-id="2eae5-109">**HumanResources.Employee**</span></span>  
  
-   <span data-ttu-id="2eae5-110">**Sales.SalesOrderHeader**</span><span class="sxs-lookup"><span data-stu-id="2eae5-110">**Sales.SalesOrderHeader**</span></span>  
  
-   <span data-ttu-id="2eae5-111">**Sales.SalesOrderDetail**</span><span class="sxs-lookup"><span data-stu-id="2eae5-111">**Sales.SalesOrderDetail**</span></span>  
  
 <span data-ttu-id="2eae5-112">Estas tablas se podrían utilizar en una aplicación para dar apoyo al personal de ventas móvil, pero es necesario filtrarlas para que cada una de las personas de la tabla **HumanResources.Employee** reciba solo los datos de los pedidos de sus clientes.</span><span class="sxs-lookup"><span data-stu-id="2eae5-112">These tables could be used in an application to support a mobile sales force, but they must be filtered so that each sales person in the **HumanResources.Employee** table receives only the data relevant to their customers' orders.</span></span>  
  
 <span data-ttu-id="2eae5-113">El primer paso es definir un filtro con parámetros en la tabla primaria, que en este ejemplo es la tabla **HumanResources.Employee** .</span><span class="sxs-lookup"><span data-stu-id="2eae5-113">The first step is to define a parameterized filter on the parent table, which in this example is the **HumanResources.Employee** table.</span></span> <span data-ttu-id="2eae5-114">Esta tabla incluye la columna **LoginID**, que contiene el inicio de sesión de cada empleado en la forma *dominio\inicioDeSesión*.</span><span class="sxs-lookup"><span data-stu-id="2eae5-114">This table includes the column **LoginID**, which contains the login for each employee in the form *domain\login*.</span></span> <span data-ttu-id="2eae5-115">Para filtrar esta tabla con el objeto de que cada empleado reciba únicamente los datos pertinentes, especifique la siguiente cláusula de filtro:</span><span class="sxs-lookup"><span data-stu-id="2eae5-115">To filter this table so that each employee receives only the data related to them, specify a parameterized filter clause of:</span></span>  
  
```  
LoginID = SUSER_SNAME()  
```  
  
 <span data-ttu-id="2eae5-116">Este filtro asegura que cada suscripción de empleado contenga solamente los datos de la tabla **HumanResources.Employee** que sean relevantes para dicho empleado (que en este caso es una sola fila).</span><span class="sxs-lookup"><span data-stu-id="2eae5-116">This filter ensures that each employee's subscription only contains data from the **HumanResources.Employee** table that is relevant to that employee (which in this case is a single row).</span></span> <span data-ttu-id="2eae5-117">Para obtener más información, consulte [Filtros de fila con parámetros](parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="2eae5-117">For more information, see [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 <span data-ttu-id="2eae5-118">El siguiente paso es extender este filtro a cada una de las tablas relacionadas, utilizando una sintaxis similar a la que se utiliza para especificar una combinación entre dos tablas.</span><span class="sxs-lookup"><span data-stu-id="2eae5-118">The next step is to extend this filter to each of the related tables, using syntax similar to that used to specify a join between two tables.</span></span> <span data-ttu-id="2eae5-119">La cláusula de este primer filtro de combinación es:</span><span class="sxs-lookup"><span data-stu-id="2eae5-119">The first join filter clause is:</span></span>  
  
```  
Employee.EmployeeID = SalesOrderHeader.SalesPersonID  
```  
  
 <span data-ttu-id="2eae5-120">Esto asegura que la suscripción contenga solo los datos relevantes para cada vendedor.</span><span class="sxs-lookup"><span data-stu-id="2eae5-120">This ensures the subscription contains only the order data relevant to each sales person.</span></span> <span data-ttu-id="2eae5-121">La cláusula del segundo filtro de combinación es:</span><span class="sxs-lookup"><span data-stu-id="2eae5-121">The second join filter clause is:</span></span>  
  
```  
SalesOrderHeader.SalesOrderID = SalesOrderDetail.SalesOrderID  
```  
  
 <span data-ttu-id="2eae5-122">Esto asegura que la suscripción contenga solo los datos detallados relacionados con los datos del pedido de cada vendedor.</span><span class="sxs-lookup"><span data-stu-id="2eae5-122">This ensures the subscription contains only the detail data related to the order data for each sales person.</span></span> <span data-ttu-id="2eae5-123">En este ejemplo se muestra una única tabla que se ha combinado en cada punto; también es posible combinar más de una tabla en cada punto.</span><span class="sxs-lookup"><span data-stu-id="2eae5-123">This example shows a single table being joined at each point; it is also possible to join more than one table at each point.</span></span>  
  
 <span data-ttu-id="2eae5-124">Los filtros de combinación se pueden agregar de uno en uno mediante el Asistente para nueva publicación y el cuadro de diálogo **Propiedades de la publicación** , y también mediante programación.</span><span class="sxs-lookup"><span data-stu-id="2eae5-124">Join filters can be added one at a time through the New Publication Wizard and the **Publication Properties** dialog box, or they can be added programmatically.</span></span> <span data-ttu-id="2eae5-125">También se pueden generar automáticamente a través del Asistente para nueva publicación: se especifica un filtro de fila para una tabla y los filtros de combinación se aplican a todas las tablas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="2eae5-125">They can also be generated automatically through the New Publication Wizard: you specify a row filter for a table and join filters are applied to all related tables.</span></span> <span data-ttu-id="2eae5-126">Para obtener más información, vea [Definir y modificar un filtro de combinación entre artículos de mezcla](../publish/define-and-modify-a-join-filter-between-merge-articles.md), [Generar automáticamente un conjunto de filtros de combinación entre artículos de mezcla &#40;SQL Server Management Studio&#41;](../publish/automatically-generate-join-filters-between-merge-articles.md) y [Definir un artículo](../publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="2eae5-126">For more information, see [Define and Modify a Join Filter Between Merge Articles](../publish/define-and-modify-a-join-filter-between-merge-articles.md), [Automatically Generate a Set of Join Filters Between Merge Articles &#40;SQL Server Management Studio&#41;](../publish/automatically-generate-join-filters-between-merge-articles.md), and [Define an Article](../publish/define-an-article.md).</span></span>  
  
## <a name="optimizing-join-filter-performance"></a><span data-ttu-id="2eae5-127">Optimizar el rendimiento de los filtros de combinación</span><span class="sxs-lookup"><span data-stu-id="2eae5-127">Optimizing Join Filter Performance</span></span>  
 <span data-ttu-id="2eae5-128">El rendimiento de los filtros de combinación se puede optimizar siguiendo estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="2eae5-128">Join filter performance can be optimized by following these guidelines:</span></span>  
  
-   <span data-ttu-id="2eae5-129">Limite el número de tablas de la jerarquía del filtro de combinación.</span><span class="sxs-lookup"><span data-stu-id="2eae5-129">Limit the number of tables in the join filter hierarchy.</span></span>  
  
     <span data-ttu-id="2eae5-130">Los filtros de combinación pueden implicar un número ilimitado de tablas, pero los filtros con un gran número de tablas pueden producir un efecto significativo en el rendimiento durante el proceso de mezcla.</span><span class="sxs-lookup"><span data-stu-id="2eae5-130">Join Filters can involve an unlimited number of tables, but filters with a large number of tables can significantly impact performance during merge processing.</span></span> <span data-ttu-id="2eae5-131">Si va a generar filtros de combinación de cinco tablas o más, considere otras soluciones, como no filtrar tablas pequeñas, que no estén sometidas a cambios o que sean principalmente tablas de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2eae5-131">If you are generating join filters of five or more tables, consider other solutions: do not filter tables that are small, not subject to change, or are primarily lookup tables.</span></span> <span data-ttu-id="2eae5-132">Utilice filtros combinados solo entre tablas que deben particionarse entre las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="2eae5-132">Use join filters only between tables that must be partitioned among subscriptions.</span></span>  
  
-   <span data-ttu-id="2eae5-133">Establezca la opción **join unique key** en **True** donde corresponda.</span><span class="sxs-lookup"><span data-stu-id="2eae5-133">Set the **join unique key** option to **True** where appropriate.</span></span>  
  
     <span data-ttu-id="2eae5-134">El proceso de mezcla dispone de optimizaciones de rendimiento especiales si la columna combinada en el elemento primario es única.</span><span class="sxs-lookup"><span data-stu-id="2eae5-134">The merge process has special performance optimizations available if the joined column in the parent is unique.</span></span> <span data-ttu-id="2eae5-135">Si la condición de combinación se basa en una columna única, establezca la opción **join unique key** para el filtro de combinación.</span><span class="sxs-lookup"><span data-stu-id="2eae5-135">If the join condition is based on a unique column, set the **join unique key** option for the join filter.</span></span> <span data-ttu-id="2eae5-136">Para obtener información sobre el modo de establecer esta opción, vea los temas de procedimientos enumerados en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="2eae5-136">For information about setting this option, see the how-to topics listed in the previous section.</span></span>  
  
-   <span data-ttu-id="2eae5-137">Asegúrese de que las columnas a las que se hace referencia en los filtros de combinación están indizadas.</span><span class="sxs-lookup"><span data-stu-id="2eae5-137">Ensure that the columns referenced in join filters are indexed.</span></span>  
  
     <span data-ttu-id="2eae5-138">Si las columnas a las que se hace referencia en el filtro están indizadas, la replicación podrá procesar los filtros con más eficacia.</span><span class="sxs-lookup"><span data-stu-id="2eae5-138">If the columns referenced in the filter are indexed, replication can process the filters more efficiently.</span></span>  
  
-   <span data-ttu-id="2eae5-139">No cree filtros de fila que se comporten como filtros de combinación.</span><span class="sxs-lookup"><span data-stu-id="2eae5-139">Do not create row filters that mimic join filters.</span></span>  
  
     <span data-ttu-id="2eae5-140">Es posible crear filtros de fila que se comporten como filtros de combinación utilizando una subconsulta en una cláusula WHERE como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="2eae5-140">It is possible to create row filters that mimic join filters by using a subquery in a WHERE clause, such as:</span></span>  
  
    ```  
    WHERE Customer.SalesPersonID IN (SELECT EmployeeID FROM Employee WHERE LoginID = SUSER_SNAME())   
    ```  
  
     <span data-ttu-id="2eae5-141">Se recomienda encarecidamente que todas las lógicas similares se expresen en un filtro de combinación en lugar de una subconsulta.</span><span class="sxs-lookup"><span data-stu-id="2eae5-141">It is strongly recommended that all such logic be expressed in a join filter rather than a subquery.</span></span> <span data-ttu-id="2eae5-142">Si la aplicación requiere que un filtro de fila utilice una subconsulta, asegúrese de que la subconsulta solo hace referencia a los datos de búsqueda que no cambian.</span><span class="sxs-lookup"><span data-stu-id="2eae5-142">If your application requires a row filter to use a subsquery, ensure that the subquery only references lookup data that does not change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eae5-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2eae5-143">See Also</span></span>  
 <span data-ttu-id="2eae5-144">[Filtrar datos publicados para la replicación de mezcla](filter-published-data-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="2eae5-144">[Filter Published Data for Merge Replication](filter-published-data-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="2eae5-145">Filtros de fila con parámetros</span><span class="sxs-lookup"><span data-stu-id="2eae5-145">Parameterized Row Filters</span></span>](parameterized-filters-parameterized-row-filters.md)  
  
  
