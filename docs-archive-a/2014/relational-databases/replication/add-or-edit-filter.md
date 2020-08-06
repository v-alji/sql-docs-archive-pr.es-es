---
title: Agregar o editar filtro | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.addeditfilter.f1
ms.assetid: bdd7c71d-1c59-4044-bfe8-c85f908345bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 54dcb1ea0b7bf10f51659a14b9d0cc5eb7991769
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663429"
---
# <a name="add-or-edit-filter"></a><span data-ttu-id="e77b7-102">Agregar filtro o Editar filtro</span><span class="sxs-lookup"><span data-stu-id="e77b7-102">Add or Edit Filter</span></span>
  <span data-ttu-id="e77b7-103">Los cuadros de diálogo **Agregar filtro** y **Editar filtro** le permiten agregar y editar filtros de filas estáticos y filtros de filas con parámetros.</span><span class="sxs-lookup"><span data-stu-id="e77b7-103">The **Add Filter** and **Edit Filter** dialog boxes allow you to add and edit static row filters and parameterized row filters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e77b7-104">La edición de un filtro en una publicación existente requiere una nueva instantánea para la publicación.</span><span class="sxs-lookup"><span data-stu-id="e77b7-104">Editing a filter in an existing publication requires a new snapshot for the publication.</span></span> <span data-ttu-id="e77b7-105">Si una publicación tiene suscripciones, es necesario reinicializar las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="e77b7-105">If a publication has subscriptions, the subscriptions must be reinitialized.</span></span> <span data-ttu-id="e77b7-106">Para obtener más información sobre los cambios de propiedad, consulte [Cambiar las propiedades de la publicación y de los artículos](publish/change-publication-and-article-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e77b7-106">For more information about property changes, see [Change Publication and Article Properties](publish/change-publication-and-article-properties.md).</span></span>  
  
 <span data-ttu-id="e77b7-107">Todos los tipos de publicaciones pueden incluir filtros estáticos; las publicaciones de combinación también pueden incluir filtros con parámetros.</span><span class="sxs-lookup"><span data-stu-id="e77b7-107">All publication types can include static filters; merge publications can also include parameterized filters.</span></span> <span data-ttu-id="e77b7-108">Se evalúa un filtro estático cuando se crea la publicación: todos los Suscriptores a la publicación reciben los mismos datos.</span><span class="sxs-lookup"><span data-stu-id="e77b7-108">A static filter is evaluated when the publication is created: all Subscribers to the publication receive the same data.</span></span> <span data-ttu-id="e77b7-109">Un filtro parametrizado se evalúa durante la sincronización de la replicación: Suscriptores diferentes pueden recibir particiones distintas de datos según el inicio de sesión o nombre de equipo de cada Suscriptor.</span><span class="sxs-lookup"><span data-stu-id="e77b7-109">A parameterized filter is evaluated during replication synchronization: different Subscribers can receive different partitions of data based on the login or computer name of each Subscriber.</span></span> <span data-ttu-id="e77b7-110">Haga clic en el vínculo **Instrucciones de ejemplo** del cuadro de diálogo para ver ejemplos de cada tipo de filtro.</span><span class="sxs-lookup"><span data-stu-id="e77b7-110">Click the **Example statements** link in the dialog box to see examples of each type of filter.</span></span> <span data-ttu-id="e77b7-111">Para obtener más información sobre las opciones de filtrado, vea [Filtrar datos publicados](publish/filter-published-data.md).</span><span class="sxs-lookup"><span data-stu-id="e77b7-111">For more information about filtering options, see [Filter Published Data](publish/filter-published-data.md).</span></span>  
  
 <span data-ttu-id="e77b7-112">Mediante los filtros de fila, puede especificar un subconjunto de filas de la tabla que desea publicar.</span><span class="sxs-lookup"><span data-stu-id="e77b7-112">Using row filters, you can specify a subset of rows to be published from a table.</span></span> <span data-ttu-id="e77b7-113">Puede utilizar filtros de filas para eliminar filas que no necesitan ver los usuarios (como las filas que contienen información importante o confidencial) o crear distintas particiones de datos que se enviarán a distintos suscriptores.</span><span class="sxs-lookup"><span data-stu-id="e77b7-113">Row filters can be used to eliminate rows that users do not need to see (such as rows that contain sensitive or confidential information), or to create different partitions of data that are sent to different Subscribers.</span></span> <span data-ttu-id="e77b7-114">La publicación de distintas particiones de datos para distintos suscriptores también puede ayudar a evitar conflictos que podrían causar la actualización simultánea de los mismos datos realizada por varios suscriptores.</span><span class="sxs-lookup"><span data-stu-id="e77b7-114">Publishing different partitions of data to different Subscribers can also help avoid conflicts that would otherwise be caused by multiple Subscribers updating the same data.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e77b7-115">Opciones</span><span class="sxs-lookup"><span data-stu-id="e77b7-115">Options</span></span>  
 <span data-ttu-id="e77b7-116">Este cuadro de diálogo incluye un proceso de dos pasos para las publicaciones transaccionales y de instantáneas y un proceso de tres pasos para las publicaciones de combinación.</span><span class="sxs-lookup"><span data-stu-id="e77b7-116">This dialog box involves a two-step process for transactional and snapshot publications and a three-step process for merge publications.</span></span> <span data-ttu-id="e77b7-117">Todos los tipos de publicaciones requieren que seleccione la tabla que desea filtrar y una o más columnas que se incluirán en el filtro, en donde el filtro se define como una cláusula WHERE estándar.</span><span class="sxs-lookup"><span data-stu-id="e77b7-117">All publication types require you to select a table to be filtered and one or more columns to be included in the filter; the filter is defined as a standard WHERE clause.</span></span>  
  
1.  <span data-ttu-id="e77b7-118">**Seleccione la tabla que desea filtrar**</span><span class="sxs-lookup"><span data-stu-id="e77b7-118">**Select the table to filter**</span></span>  
  
     <span data-ttu-id="e77b7-119">Si va a editar un filtro existente, no se puede cambiar la selección de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e77b7-119">If you are editing an existing filter, the table selection cannot be changed.</span></span> <span data-ttu-id="e77b7-120">Si va a agregar un nuevo filtro, seleccione una tabla del cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e77b7-120">If you are adding a new filter, select a table from the drop-down list box.</span></span> <span data-ttu-id="e77b7-121">Las tablas solo se mostrarán en el cuadro de lista si se han seleccionado en la página **Artículos** y no presentan un filtro de fila.</span><span class="sxs-lookup"><span data-stu-id="e77b7-121">Tables appear in the list box only if they were selected on the **Articles** page and do not already have a row filter.</span></span> <span data-ttu-id="e77b7-122">Si la tabla presenta un filtro de fila y desea definir uno nuevo:</span><span class="sxs-lookup"><span data-stu-id="e77b7-122">If a table has a row filter and you want to define a new one:</span></span>  
  
    1.  <span data-ttu-id="e77b7-123">Haga clic en **Cancelar** en el cuadro de diálogo **Agregar filtro** .</span><span class="sxs-lookup"><span data-stu-id="e77b7-123">Click **Cancel** on the **Add Filter** dialog box.</span></span>  
  
    2.  <span data-ttu-id="e77b7-124">Seleccione la tabla en el panel de filtros de la página **Filtrar filas de tabla** y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e77b7-124">Select the table in the filter pane on the **Filter Table Rows** page and click **Edit**.</span></span>  
  
    3.  <span data-ttu-id="e77b7-125">Edite un filtro existente en el cuadro de diálogo **Editar filtro** .</span><span class="sxs-lookup"><span data-stu-id="e77b7-125">Edit an existing filter in the **Edit Filter** dialog box.</span></span>  
  
2.  <span data-ttu-id="e77b7-126">**Complete la instrucción de filtro para identificar las filas de la tabla que recibirán los suscriptores**</span><span class="sxs-lookup"><span data-stu-id="e77b7-126">**Complete the filter statement to identify which table rows Subscribers will receive**</span></span>  
  
     <span data-ttu-id="e77b7-127">Defina una nueva instrucción de filtro o edite una existente.</span><span class="sxs-lookup"><span data-stu-id="e77b7-127">Define a new filter statement or edit an existing one.</span></span> <span data-ttu-id="e77b7-128">El cuadro de lista **Columnas** muestra todas las columnas que va a publicar en la tabla seleccionada en **Seleccione la tabla que desea filtrar**.</span><span class="sxs-lookup"><span data-stu-id="e77b7-128">The **Columns** list box lists all the columns that you are publishing from the table you selected in **Select the table to filter**.</span></span> <span data-ttu-id="e77b7-129">El área de texto **Instrucción de filtro** incluye el texto predeterminado, que tiene este formato:</span><span class="sxs-lookup"><span data-stu-id="e77b7-129">The **Filter statement** text area includes the default text, which is in the form of:</span></span>  
  
     `SELECT <published_columns> FROM [schema].[tablename] WHERE`  
  
     <span data-ttu-id="e77b7-130">No se puede cambiar este texto; escriba la cláusula de filtro después de la palabra clave WHERE utilizando sintaxis estándar [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e77b7-130">This text cannot be changed; type the filter clause after the WHERE keyword using standard [!INCLUDE[tsql](../../includes/tsql-md.md)] syntax.</span></span> <span data-ttu-id="e77b7-131">Si el publicador es un publicador de Oracle, la cláusula WHERE debe seguir la sintaxis de consultas de Oracle.</span><span class="sxs-lookup"><span data-stu-id="e77b7-131">If the Publisher is an Oracle Publisher, the WHERE clause must be compliant with Oracle query syntax.</span></span> <span data-ttu-id="e77b7-132">Evite utilizar filtros complejos en la medida de lo posible.</span><span class="sxs-lookup"><span data-stu-id="e77b7-132">Avoid using complex filters when possible.</span></span> <span data-ttu-id="e77b7-133">Tanto los filtros estáticos como los que utilizan parámetros aumentan el tiempo de procesamiento de las publicaciones, por lo que deberá escribir las instrucciones de filtro de la forma más sencilla posible.</span><span class="sxs-lookup"><span data-stu-id="e77b7-133">Both static and parameterized filters increase processing time for publications; therefore you should keep filter statements as simple as possible.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e77b7-134">Por motivos de rendimiento, se recomienda no aplicar funciones a los nombres de columna en las cláusulas de los filtros de fila con parámetros, como `LEFT([MyColumn]) = SUSER_SNAME()`.</span><span class="sxs-lookup"><span data-stu-id="e77b7-134">For performance reasons, we recommended that you not apply functions to column names in parameterized row filter clauses for merge publications, such as `LEFT([MyColumn]) = SUSER_SNAME()`.</span></span> <span data-ttu-id="e77b7-135">Si utiliza HOST_NAME en una cláusula de filtro y reemplaza el valor HOST_NAME, puede que sea necesario convertir los tipos de datos utilizando CONVERT.</span><span class="sxs-lookup"><span data-stu-id="e77b7-135">If you use HOST_NAME in a filter clause and override the HOST_NAME value, it might be necessary to convert data types using CONVERT.</span></span> <span data-ttu-id="e77b7-136">Para obtener más información acerca de las prácticas recomendadas para este caso, vea la sección "Reemplazar el valor de HOST_NAME()" del tema [Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="e77b7-136">For more information about best practices for this case, see the section "Overriding the HOST_NAME() Value" in the topic [Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
3.  <span data-ttu-id="e77b7-137">**Especifique cuántas suscripciones recibirán datos de esta tabla**</span><span class="sxs-lookup"><span data-stu-id="e77b7-137">**Specify how many subscriptions will receive data from this table**</span></span>  
  
     [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="e77b7-138">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores únicamente; solo replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="e77b7-138">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only; merge replication only.</span></span> <span data-ttu-id="e77b7-139">La replicación de mezcla le permite especificar el tipo de partición más adecuado para sus datos y aplicación.</span><span class="sxs-lookup"><span data-stu-id="e77b7-139">Merge replication allows you to specify the type of partitions that are best suited to your data and application.</span></span> <span data-ttu-id="e77b7-140">Si selecciona **Una fila de esta tabla irá a una sola suscripción**, la replicación de mezcla establece la opción de particiones no superpuestas.</span><span class="sxs-lookup"><span data-stu-id="e77b7-140">If you select **A row from this table will go to only one subscription**, merge replication sets the nonoverlapping partitions option.</span></span> <span data-ttu-id="e77b7-141">Las particiones no superpuestas funcionan junto con las particiones precalculadas para aumentar el rendimiento: la finalidad de las particiones no superpuestas es minimizar el costo de carga asociado a las particiones precalculadas.</span><span class="sxs-lookup"><span data-stu-id="e77b7-141">Nonoverlapping partitions work in conjunction with precomputed partitions to improve performance, with nonoverlapping partitions minimizing the upload cost associated with precomputed partitions.</span></span> <span data-ttu-id="e77b7-142">La ventaja en el rendimiento de las particiones no superpuestas es más evidente cuando los filtros con parámetros y de combinación utilizados son más complejos.</span><span class="sxs-lookup"><span data-stu-id="e77b7-142">The performance benefit of nonoverlapping partitions is more noticeable when the parameterized filters and join filters used are more complex.</span></span> <span data-ttu-id="e77b7-143">Si selecciona esta opción, debe asegurarse de que los datos se dividen en particiones de forma que una fila no se pueda replicar en más de un suscriptor.</span><span class="sxs-lookup"><span data-stu-id="e77b7-143">If you select this option, you must ensure that the data is partitioned in such a way that a row cannot be replicated to more than one Subscriber.</span></span> <span data-ttu-id="e77b7-144">Para obtener más información, vea la sección sobre cómo configurar opciones de partición en el tema [Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="e77b7-144">For more information, see the section "Setting 'partition options'" in the topic [Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 <span data-ttu-id="e77b7-145">Una vez agregado o editado un filtro, haga clic en **Aceptar** para guardar los cambios y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e77b7-145">After you have added or edited a filter, click **OK** to save changes and close the dialog box.</span></span> <span data-ttu-id="e77b7-146">El filtro que ha especificado se analiza y se ejecuta según la tabla de la cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="e77b7-146">The filter you specified is parsed and run against the table in the SELECT clause.</span></span> <span data-ttu-id="e77b7-147">Si la instrucción de filtro contiene errores de sintaxis u otros problemas, se le notificará para que pueda editar la instrucción de filtro.</span><span class="sxs-lookup"><span data-stu-id="e77b7-147">If the filter statement contains syntax errors or other problems, you are notified and are able to edit the filter statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77b7-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e77b7-148">See Also</span></span>  
 <span data-ttu-id="e77b7-149">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="e77b7-149">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="e77b7-150">[Ver y modificar propiedades de publicación](publish/view-and-modify-publication-properties.md) </span><span class="sxs-lookup"><span data-stu-id="e77b7-150">[View and Modify Publication Properties](publish/view-and-modify-publication-properties.md) </span></span>  
 <span data-ttu-id="e77b7-151">[Filtrar datos publicados](publish/filter-published-data.md) </span><span class="sxs-lookup"><span data-stu-id="e77b7-151">[Filter Published Data](publish/filter-published-data.md) </span></span>  
 <span data-ttu-id="e77b7-152">[Join Filters](merge/join-filters.md) </span><span class="sxs-lookup"><span data-stu-id="e77b7-152">[Join Filters](merge/join-filters.md) </span></span>  
 <span data-ttu-id="e77b7-153">[Filtros de fila con parámetros](merge/parameterized-filters-parameterized-row-filters.md) </span><span class="sxs-lookup"><span data-stu-id="e77b7-153">[Parameterized Row Filters](merge/parameterized-filters-parameterized-row-filters.md) </span></span>  
 [<span data-ttu-id="e77b7-154">Publicar datos y objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="e77b7-154">Publish Data and Database Objects</span></span>](publish/publish-data-and-database-objects.md)  
  
  