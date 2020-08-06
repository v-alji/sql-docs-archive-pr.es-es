---
title: Definición y modificación de un filtro de fila con parámetros para un artículo de mezcla | Microsoft Docs
ms.custom: ''
ms.date: 06/02/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- parameterized filters [SQL Server replication], defining
- parameterized filters [SQL Server replication], modifying
- merge replication [SQL Server replication], dynamic filters
- merge replication parameterized filters [SQL Server replication]
- filters [SQL Server replication], parameterized
- modifying filters, parameterized row
- dynamic filters [SQL Server replication]
ms.assetid: de0482a2-3cc8-4030-8a4a-14364549ac9f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d80ad53661aced22795220507398e2fcc510edd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748041"
---
# <a name="define-and-modify-a-parameterized-row-filter-for-a-merge-article"></a><span data-ttu-id="8d200-102">Definir y modificar un filtro de fila con parámetros para un artículo de mezcla</span><span class="sxs-lookup"><span data-stu-id="8d200-102">Define and Modify a Parameterized Row Filter for a Merge Article</span></span>
  <span data-ttu-id="8d200-103">En este tema se describe cómo definir y modificar un filtro de fila con parámetros en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d200-103">This topic describes how to define and modify a parameterized row filter in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="8d200-104">Al crear los artículos de la tabla, puede usar filtros de fila con parámetros.</span><span class="sxs-lookup"><span data-stu-id="8d200-104">When creating table articles, you can use parameterized row filters.</span></span> <span data-ttu-id="8d200-105">Estos filtros usan una cláusula [WHERE](/sql/t-sql/queries/where-transact-sql) para seleccionar los datos adecuados que se van a publicar.</span><span class="sxs-lookup"><span data-stu-id="8d200-105">These filters use a [WHERE](/sql/t-sql/queries/where-transact-sql) clause to select the appropriate data to be published.</span></span> <span data-ttu-id="8d200-106">En vez de especificar un valor literal en la cláusula (como ocurre con un filtro de fila estático), se especifica una o las dos funciones del sistema siguientes: [SUSER_SNAME](/sql/t-sql/functions/suser-sname-transact-sql) y [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8d200-106">Rather than specifying a literal value in the clause (as you do with a static row filter), you specify one or both of the following system functions: [SUSER_SNAME](/sql/t-sql/functions/suser-sname-transact-sql) and [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql).</span></span> <span data-ttu-id="8d200-107">Para obtener más información, consulte [Filtros de fila con parámetros](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="8d200-107">For more information, see [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8d200-108">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="8d200-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="8d200-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="8d200-109">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="8d200-110">Si agrega, modifica o elimina un filtro de fila con parámetros una vez inicializadas las suscripciones a la publicación, deberá generar una instantánea nueva y reinicializar todas las suscripciones después de realizar el cambio.</span><span class="sxs-lookup"><span data-stu-id="8d200-110">If you add, modify, or delete a parameterized row filter after subscriptions to the publication have been initialized, you must generate a new snapshot and reinitialize all subscriptions after making the change.</span></span> <span data-ttu-id="8d200-111">Para obtener más información sobre los requisitos para los cambios de propiedad, consulte [Cambiar las propiedades de la publicación y de los artículos](change-publication-and-article-properties.md) (Cambiar las propiedades de la publicación y de los artículos).</span><span class="sxs-lookup"><span data-stu-id="8d200-111">For more information about requirements for property changes, see [Change Publication and Article Properties](change-publication-and-article-properties.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="8d200-112">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="8d200-112">Recommendations</span></span>  
  
-   <span data-ttu-id="8d200-113">Por motivos de rendimiento, se recomienda no aplicar funciones a los nombres de columna en las cláusulas de filtro de fila con parámetros, como `LEFT([MyColumn]) = SUSER_SNAME()`.</span><span class="sxs-lookup"><span data-stu-id="8d200-113">For performance reasons, we recommend that you not apply functions to column names in parameterized row filter clauses, such as `LEFT([MyColumn]) = SUSER_SNAME()`.</span></span> <span data-ttu-id="8d200-114">Si utiliza HOST_NAME en una cláusula de filtro y reemplaza el valor HOST_NAME, puede que sea necesario convertir los tipos de datos utilizando CONVERT.</span><span class="sxs-lookup"><span data-stu-id="8d200-114">If you use HOST_NAME in a filter clause and override the HOST_NAME value, it might be necessary to convert data types using CONVERT.</span></span> <span data-ttu-id="8d200-115">Para obtener más información acerca de las prácticas recomendadas para este caso, vea la sección "Reemplazar el valor de HOST_NAME()" del tema [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="8d200-115">For more information about best practices for this case, see the section "Overriding the HOST_NAME() Value" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8d200-116">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8d200-116">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="8d200-117">Defina, modifique y elimine filtros de fila con parámetros en la página **Filtrar filas de tabla** del Asistente para nueva publicación o en la página **Filtrar filas** del cuadro de diálogo **Propiedades de la publicación: \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="8d200-117">Define, modify, and delete parameterized row filters on the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="8d200-118">Para obtener más información sobre el uso del asistente y el acceso al cuadro de diálogo, consulte [Create a Publication](create-a-publication.md) (Crear una publicación) y [Ver y modificar propiedades de publicación](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="8d200-118">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
#### <a name="to-define-a-parameterized-row-filter"></a><span data-ttu-id="8d200-119">Para definir un filtro de fila con parámetros</span><span class="sxs-lookup"><span data-stu-id="8d200-119">To define a parameterized row filter</span></span>  
  
1.  <span data-ttu-id="8d200-120">En la página **Filtrar filas de tabla** del Asistente para nueva publicación o la página **Filtrar filas** de **Propiedades de la publicación: \<Publication>** , haga clic en **Agregar** y en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="8d200-120">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, click **Add**, and then click **Add Filter**.</span></span>  
  
2.  <span data-ttu-id="8d200-121">En el cuadro de diálogo **Agregar filtro** , seleccione la tabla que va a filtrar en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8d200-121">In the **Add Filter** dialog box, select a table to filter from the drop-down list box.</span></span>  
  
3.  <span data-ttu-id="8d200-122">Cree una instrucción para el filtro en el cuadro de texto **Instrucción de filtro** .</span><span class="sxs-lookup"><span data-stu-id="8d200-122">Create a filter statement in the **Filter statement** text box.</span></span> <span data-ttu-id="8d200-123">Puede escribir directamente en el área de texto o puede arrastrar y colocar columnas del cuadro de lista **Columnas** .</span><span class="sxs-lookup"><span data-stu-id="8d200-123">You can type directly in the text area, and you can also drag and drop columns from the **Columns** list box.</span></span>  
  
    -   <span data-ttu-id="8d200-124">El área de texto **Instrucción de filtro** incluye el texto predeterminado, que tiene este formato:</span><span class="sxs-lookup"><span data-stu-id="8d200-124">The **Filter statement** text area includes the default text, which is in the form of:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [tableowner].[tablename] WHERE  
        ```  
  
    -   <span data-ttu-id="8d200-125">El texto predeterminado no se puede cambiar. Escriba la cláusula del filtro después de la palabra clave WHERE utilizando la sintaxis SQL estándar.</span><span class="sxs-lookup"><span data-stu-id="8d200-125">The default text cannot be changed; type the filter clause after the WHERE keyword using standard SQL syntax.</span></span> <span data-ttu-id="8d200-126">Un filtro con parámetros incluye una llamada a la función del sistema `HOST_NAME()` y/o `SUSER_SNAME()`, o una función definida por el usuario que hace referencia a una de estas funciones o a las dos.</span><span class="sxs-lookup"><span data-stu-id="8d200-126">A parameterized filter includes a call to the system function `HOST_NAME()` and/or `SUSER_SNAME()`, or a user-defined function that references one or both of these functions.</span></span> <span data-ttu-id="8d200-127">La línea siguiente es un ejemplo de una cláusula de filtro completa de un filtro de fila con parámetros:</span><span class="sxs-lookup"><span data-stu-id="8d200-127">The following is an example of a complete filter clause for a parameterized row filter:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [HumanResources].[Employee] WHERE LoginID = SUSER_SNAME()  
        ```  
  
         <span data-ttu-id="8d200-128">La cláusula WHERE debe usar nombres de dos partes; los nombres de tres y cuatro partes no se admiten.</span><span class="sxs-lookup"><span data-stu-id="8d200-128">The WHERE clause should use two-part naming; three-part naming and four-part naming are not supported.</span></span>  
  
4.  <span data-ttu-id="8d200-129">Seleccione la opción que indique cómo se van a compartir los datos entre los suscriptores:</span><span class="sxs-lookup"><span data-stu-id="8d200-129">Select the option that matches how data will be shared among Subscribers:</span></span>  
  
    -   <span data-ttu-id="8d200-130">**Una fila de esta tabla irá a varias suscripciones**</span><span class="sxs-lookup"><span data-stu-id="8d200-130">**A row from this table will go to multiple subscriptions**</span></span>  
  
    -   <span data-ttu-id="8d200-131">**Una fila de esta tabla irá a una sola suscripción**</span><span class="sxs-lookup"><span data-stu-id="8d200-131">**A row from this table will go to only one subscription**</span></span>  
  
     <span data-ttu-id="8d200-132">Si selecciona **Una fila de esta tabla irá a una sola suscripción**, la replicación de mezcla puede optimizar el rendimiento almacenando y procesando menos metadatos.</span><span class="sxs-lookup"><span data-stu-id="8d200-132">If you select **A row from this table will go to only one subscription**, merge replication can optimize performance by storing and processing less metadata.</span></span> <span data-ttu-id="8d200-133">No obstante, debe asegurarse de que los datos se particionan de forma que una fila no se pueda replicar en más de un suscriptor.</span><span class="sxs-lookup"><span data-stu-id="8d200-133">However, you must ensure that the data is partitioned in such a way that a row cannot be replicated to more than one Subscriber.</span></span> <span data-ttu-id="8d200-134">Para obtener más información, vea la sección sobre cómo configurar opciones de partición en el tema [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="8d200-134">For more information, see the section "Setting 'partition options'" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="8d200-135">Si está en el cuadro de diálogo **Propiedades de la publicación: \<Publication>** , haga clic en **Aceptar** para guardar y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8d200-135">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
#### <a name="to-modify-a-parameterized-row-filter"></a><span data-ttu-id="8d200-136">Para modificar un filtro de fila con parámetros</span><span class="sxs-lookup"><span data-stu-id="8d200-136">To modify a parameterized row filter</span></span>  
  
1.  <span data-ttu-id="8d200-137">En la página **Filtrar filas de tabla** del Asistente para nueva publicación o la página **Filtrar filas** de **Propiedades de la publicación: \<Publication>** , seleccione un filtro en el panel **Tablas filtradas** y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8d200-137">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="8d200-138">Modifique el filtro en el cuadro de diálogo **Editar filtro** .</span><span class="sxs-lookup"><span data-stu-id="8d200-138">In the **Edit Filter** dialog box, modify the filter.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-delete-a-parameterized-row-filter"></a><span data-ttu-id="8d200-139">Para eliminar un filtro de fila con parámetros</span><span class="sxs-lookup"><span data-stu-id="8d200-139">To delete a parameterized row filter</span></span>  
  
1.  <span data-ttu-id="8d200-140">En la página **Filtrar filas de tabla** del Asistente para nueva publicación o la página **Filtrar filas** de **Propiedades de la publicación: \<Publication>** , seleccione un filtro en el panel **Tablas filtradas** y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="8d200-140">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Delete**.</span></span>  
  

  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8d200-141">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8d200-141">Using Transact-SQL</span></span>  
 <span data-ttu-id="8d200-142">Los filtros de fila con parámetros se pueden crear y modificar mediante programación con los procedimientos almacenados de la replicación.</span><span class="sxs-lookup"><span data-stu-id="8d200-142">Parameterized row filters can be created and modified programmatically using replication stored procedures.</span></span>  
  
#### <a name="to-define-a-parameterized-row-filter-for-an-article-in-a-merge-publication"></a><span data-ttu-id="8d200-143">Para definir un filtro de fila con parámetros para un artículo en una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="8d200-143">To define a parameterized row filter for an article in a merge publication</span></span>  
  
1.  <span data-ttu-id="8d200-144">En la base de datos de publicación del publicador, ejecute [sp_addmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8d200-144">At the Publisher on the publication database, execute [sp_addmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql).</span></span> <span data-ttu-id="8d200-145">Especifique **@publication** un nombre para el artículo para **@article** , la tabla que se va a publicar para **@source_object** , la cláusula WHERE que define el filtro con parámetros para **@subset_filterclause** (sin incluir `WHERE` ) y uno de los siguientes valores para **@partition_options** , que describe el tipo de particionamiento que será el resultado del filtro de fila con parámetros:</span><span class="sxs-lookup"><span data-stu-id="8d200-145">Specify **@publication**, a name for the article for **@article**, the table being published for **@source_object**, the WHERE clause that defines the parameterized filter for **@subset_filterclause** (not including `WHERE`), and one of the following values for **@partition_options**, which describes the type of partitioning that will result from the parameterized row filter:</span></span>  
  
    -   <span data-ttu-id="8d200-146">**0** : El filtro del artículo es estático o no produce un subconjunto de datos único para cada partición (una partición "superpuesta").</span><span class="sxs-lookup"><span data-stu-id="8d200-146">**0** - Filtering for the article either is static or does not yield a unique subset of data for each partition (an "overlapping" partition).</span></span>  
  
    -   <span data-ttu-id="8d200-147">**1** : Las particiones resultantes son superpuestas y las actualizaciones realizadas en el suscriptor no pueden cambiar la partición a la que pertenece la fila.</span><span class="sxs-lookup"><span data-stu-id="8d200-147">**1** - Resulting partitions are overlapping, and updates made at the Subscriber cannot change the partition to which a row belongs.</span></span>  
  
    -   <span data-ttu-id="8d200-148">**2** : El filtro del artículo produce particiones no superpuestas, pero varios suscriptores pueden recibir la misma partición.</span><span class="sxs-lookup"><span data-stu-id="8d200-148">**2** - Filtering for the article yields nonoverlapping partitions, but multiple Subscribers can receive the same partition.</span></span>  
  
    -   <span data-ttu-id="8d200-149">**3** : El filtro del artículo produce particiones no superpuestas que son únicas para cada suscripción.</span><span class="sxs-lookup"><span data-stu-id="8d200-149">**3** - Filtering for the article yields nonoverlapping partitions that are unique for each subscription.</span></span>  
  
#### <a name="to-change-a-parameterized-row-filter-for-an-article-in-a-merge-publication"></a><span data-ttu-id="8d200-150">Para cambiar un filtro de fila con parámetros para un artículo en una publicación de combinación</span><span class="sxs-lookup"><span data-stu-id="8d200-150">To change a parameterized row filter for an article in a merge publication</span></span>  
  
1.  <span data-ttu-id="8d200-151">En la base de datos de publicación del publicador, ejecute [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8d200-151">At the Publisher on the publication database, execute [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql).</span></span> <span data-ttu-id="8d200-152">Especifique **@publication** , **@article** , un valor de `subset_filterclause` para **@property** , la expresión que define el filtro con parámetros para **@value** (sin incluir `WHERE` ) y un valor de **1** para **@force_invalidate_snapshot** y **@force_reinit_subscription** .</span><span class="sxs-lookup"><span data-stu-id="8d200-152">Specify **@publication**, **@article**, a value of `subset_filterclause` for **@property**, the expression that defines the parameterized filter for **@value** (not including `WHERE`), and a value of **1** for both **@force_invalidate_snapshot** and **@force_reinit_subscription**.</span></span>  
  
2.  <span data-ttu-id="8d200-153">Si este cambio produce un comportamiento de particionamiento diferente, a continuación, ejecute [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql) de nuevo.</span><span class="sxs-lookup"><span data-stu-id="8d200-153">If this change results in different partitioning behavior, then execute [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql) again.</span></span> <span data-ttu-id="8d200-154">Especifique **@publication** , **@article** , un valor de `partition_options` para **@property** y la opción de particionamiento más adecuada para **@value** , que puede ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="8d200-154">Specify **@publication**, **@article**, a value of `partition_options` for **@property**, and the most appropriate partitioning option for **@value**, which can be one of the following:</span></span>  
  
    -   <span data-ttu-id="8d200-155">**0** : El filtro del artículo es estático o no produce un subconjunto de datos único para cada partición (una partición "superpuesta").</span><span class="sxs-lookup"><span data-stu-id="8d200-155">**0** - Filtering for the article either is static or does not yield a unique subset of data for each partition (an "overlapping" partition).</span></span>  
  
    -   <span data-ttu-id="8d200-156">**1** : Las particiones resultantes son superpuestas y las actualizaciones realizadas en el suscriptor no pueden cambiar la partición a la que pertenece la fila.</span><span class="sxs-lookup"><span data-stu-id="8d200-156">**1** - Resulting partitions are overlapping, and updates made at the Subscriber cannot change the partition to which a row belongs.</span></span>  
  
    -   <span data-ttu-id="8d200-157">**2** : El filtro del artículo produce particiones no superpuestas, pero varios suscriptores pueden recibir la misma partición.</span><span class="sxs-lookup"><span data-stu-id="8d200-157">**2** - Filtering for the article yields nonoverlapping partitions, but multiple Subscribers can receive the same partition.</span></span>  
  
    -   <span data-ttu-id="8d200-158">**3** : El filtro del artículo produce particiones no superpuestas que son únicas para cada suscripción.</span><span class="sxs-lookup"><span data-stu-id="8d200-158">**3** - Filtering for the article yields nonoverlapping partitions that are unique for each subscription.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="8d200-159">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8d200-159">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="8d200-160">En este ejemplo se define un grupo de artículos en una publicación de mezcla, donde los artículos se filtran con una serie de filtros de combinación con la tabla `Employee` que a su vez se filtra mediante un filtro de fila con parámetros en la columna **LoginID** .</span><span class="sxs-lookup"><span data-stu-id="8d200-160">This example defines a group of articles in a merge publication where the articles are filtered with a series of join filters against the `Employee` table that is itself filtered using a parameterized row filter on the **LoginID** column.</span></span> <span data-ttu-id="8d200-161">Durante la sincronización, el valor devuelto por la función [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql) se invalida.</span><span class="sxs-lookup"><span data-stu-id="8d200-161">During synchronization, the value returned by the [HOST_NAME](/sql/t-sql/functions/host-name-transact-sql) function is overridden.</span></span> <span data-ttu-id="8d200-162">Para obtener más información, vea Invalidar el valor de HOST_NAME() en el tema [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="8d200-162">For more information, see Overriding the HOST_NAME() Value in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 [!code-sql[HowTo#sp_MergeDynamicPub1](../../../snippets/tsql/SQL15/replication/howto/tsql/createmergepubdynamic1.sql#sp_mergedynamicpub1)]  
  
  
## <a name="see-also"></a><span data-ttu-id="8d200-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d200-163">See Also</span></span>  
 <span data-ttu-id="8d200-164">[Definir y modificar un filtro de combinación entre artículos de mezcla](define-and-modify-a-join-filter-between-merge-articles.md) </span><span class="sxs-lookup"><span data-stu-id="8d200-164">[Define and Modify a Join Filter Between Merge Articles](define-and-modify-a-join-filter-between-merge-articles.md) </span></span>  
 <span data-ttu-id="8d200-165">[Cambiar las propiedades de la publicación y de los artículos](change-publication-and-article-properties.md) </span><span class="sxs-lookup"><span data-stu-id="8d200-165">[Change Publication and Article Properties](change-publication-and-article-properties.md) </span></span>  
 <span data-ttu-id="8d200-166">[Join Filters](../merge/join-filters.md) </span><span class="sxs-lookup"><span data-stu-id="8d200-166">[Join Filters](../merge/join-filters.md) </span></span>  
 [<span data-ttu-id="8d200-167">Filtros de fila con parámetros</span><span class="sxs-lookup"><span data-stu-id="8d200-167">Parameterized Row Filters</span></span>](../merge/parameterized-filters-parameterized-row-filters.md)  
  
  
