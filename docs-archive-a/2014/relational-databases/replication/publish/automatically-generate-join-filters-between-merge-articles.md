---
title: Generar automáticamente un conjunto de filtros de combinación entre artículos de mezcla (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- automatic join filter generation
- join filters
ms.assetid: 7ef419f4-c17f-42a5-9068-174a3ec08941
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4bfdbf93aad134e4da873a6aade307754a2637e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661908"
---
# <a name="automatically-generate-a-set-of-join-filters-between-merge-articles-sql-server-management-studio"></a><span data-ttu-id="76d6b-102">Generar automáticamente un conjunto de filtros de combinación entre artículos de mezcla (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="76d6b-102">Automatically Generate a Set of Join Filters Between Merge Articles (SQL Server Management Studio)</span></span>
  <span data-ttu-id="76d6b-103">Genere automáticamente un conjunto de filtros de combinación en la página **Filtrar filas de tabla** del Asistente para nueva publicación o en la página **Filtrar filas** del cuadro de diálogo **Propiedades de la publicación: \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="76d6b-103">Automatically generate a set of join filters on the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="76d6b-104">Para obtener más información sobre el uso del asistente y el acceso al cuadro de diálogo, consulte [Create a Publication](create-a-publication.md) (Crear una publicación) y [Ver y modificar propiedades de publicación](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="76d6b-104">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76d6b-105">Si genera automáticamente un conjunto de filtros de combinación en el cuadro de diálogo **Propiedades de la publicación: \<Publication>** después de haber inicializado las suscripciones para la publicación, deberá generar una nueva instantánea y volver a inicializar todas las suscripciones una vez realizado el cambio.</span><span class="sxs-lookup"><span data-stu-id="76d6b-105">If you automatically generate a set of join filters in the **Publication Properties - \<Publication>** dialog box after subscriptions to the publication have been initialized, you must generate a new snapshot and reinitialize all subscriptions after making the change.</span></span> <span data-ttu-id="76d6b-106">Para obtener más información sobre los requisitos para los cambios de propiedad, consulte [Cambiar las propiedades de la publicación y de los artículos](change-publication-and-article-properties.md) (Cambiar las propiedades de la publicación y de los artículos).</span><span class="sxs-lookup"><span data-stu-id="76d6b-106">For more information about requirements for property changes, see [Change Publication and Article Properties](change-publication-and-article-properties.md).</span></span>  
  
 <span data-ttu-id="76d6b-107">Es posible crear filtros de combinación para un conjunto de tablas de forma manual, o bien la replicación puede generar los filtros de forma automática en función de las relaciones de clave clave externa a clave principal definidas en las tablas.</span><span class="sxs-lookup"><span data-stu-id="76d6b-107">Join filters can be created manually for a set of tables, or replication can generate the filters automatically based on the foreign key to primary key relationships defined on the tables.</span></span> <span data-ttu-id="76d6b-108">Para obtener más información sobre cómo crear filtros de combinación manualmente, consulte [Define and Modify a Join Filter Between Merge Articles](define-and-modify-a-join-filter-between-merge-articles.md) (Definir y modificar un filtro de combinación entre artículos de mezcla).</span><span class="sxs-lookup"><span data-stu-id="76d6b-108">For more information about creating join filters manually, see [Define and Modify a Join Filter Between Merge Articles](define-and-modify-a-join-filter-between-merge-articles.md).</span></span>  
  
### <a name="to-automatically-generate-a-set-of-join-filters-between-merge-articles"></a><span data-ttu-id="76d6b-109">Para generar automáticamente un conjunto de filtros de combinación entre artículos de mezcla</span><span class="sxs-lookup"><span data-stu-id="76d6b-109">To automatically generate a set of join filters between merge articles</span></span>  
  
1.  <span data-ttu-id="76d6b-110">En la página **Filtrar filas de tabla** del Asistente para nueva publicación o la página **Filtrar filas** del cuadro de diálogo **Propiedades de la publicación: \<Publication>** , haga clic en **Agregar** y luego en **Generar filtros automáticamente**.</span><span class="sxs-lookup"><span data-stu-id="76d6b-110">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, click **Add**, and then click **Automatically Generate Filters**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="76d6b-111">Al generar filtros automáticamente, se eliminan los filtros de fila o los filtros de combinación existentes en la publicación.</span><span class="sxs-lookup"><span data-stu-id="76d6b-111">Automatically generating filters deletes any existing row filters or join filters in the publication.</span></span> <span data-ttu-id="76d6b-112">Es posible agregar filtros después de haber generado automáticamente un conjunto de filtros.</span><span class="sxs-lookup"><span data-stu-id="76d6b-112">You can add filters after automatically generating a set of filters.</span></span>  
  
2.  <span data-ttu-id="76d6b-113">Siga el proceso del cuadro de diálogo **Generar filtros** para crear un filtro de fila.</span><span class="sxs-lookup"><span data-stu-id="76d6b-113">Follow the process in the **Generate Filters** dialog box to create a row filter.</span></span> <span data-ttu-id="76d6b-114">A continuación, el filtro de fila se amplía a las tablas relacionadas con la tabla filtrada por medio de las relaciones de clave principal y clave externa.</span><span class="sxs-lookup"><span data-stu-id="76d6b-114">The row filter is then extended to the tables related to the filtered table through primary key and foreign key relationships.</span></span>  
  
    1.  <span data-ttu-id="76d6b-115">Seleccione una tabla para filtrar en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="76d6b-115">Select a table to filter from the drop-down list box.</span></span>  
  
    2.  <span data-ttu-id="76d6b-116">Cree una instrucción para el filtro en el cuadro de texto **Instrucción de filtro** .</span><span class="sxs-lookup"><span data-stu-id="76d6b-116">Create a filter statement in the **Filter statement** text box.</span></span> <span data-ttu-id="76d6b-117">Puede escribir directamente en el área de texto o puede arrastrar y colocar columnas del cuadro de lista **Columnas** .</span><span class="sxs-lookup"><span data-stu-id="76d6b-117">You can type directly in the text area, and you can also drag and drop columns from the **Columns** list box.</span></span>  
  
         <span data-ttu-id="76d6b-118">El área de texto **Instrucción de filtro** incluye el texto predeterminado, que tiene este formato:</span><span class="sxs-lookup"><span data-stu-id="76d6b-118">The **Filter statement** text area includes the default text, which is in the form of:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [tableowner].[tablename] WHERE  
        ```  
  
         <span data-ttu-id="76d6b-119">El texto predeterminado no se puede modificar; escriba la cláusula de filtro para un filtro de fila estático o un filtro de fila con parámetros después de la palabra clave WHERE mediante la sintaxis SQL estándar.</span><span class="sxs-lookup"><span data-stu-id="76d6b-119">The default text cannot be changed; type the filter clause for a static row filter or a parameterized row filter after the WHERE keyword using standard SQL syntax.</span></span> <span data-ttu-id="76d6b-120">La cláusula de filtro completa para un filtro de fila con parámetros sería similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="76d6b-120">The complete filter clause for a parameterized row filter would look like:</span></span>  
  
        ```  
        SELECT <published_columns> FROM [HumanResources].[Employee] WHERE LoginID = SUSER_SNAME()  
        ```  
  
         <span data-ttu-id="76d6b-121">La cláusula WHERE debe usar nombres de dos partes; los nombres de tres y cuatro partes no se admiten.</span><span class="sxs-lookup"><span data-stu-id="76d6b-121">The WHERE clause should use two-part naming; three-part naming and four-part naming are not supported.</span></span>  
  
    3.  <span data-ttu-id="76d6b-122">Especifique las opciones del filtro.</span><span class="sxs-lookup"><span data-stu-id="76d6b-122">Specify filter options.</span></span>  
  
         <span data-ttu-id="76d6b-123">Seleccione la opción que indique cómo se van a compartir los datos entre los suscriptores: **Una fila de esta tabla irá a varias suscripciones** o **Una fila de esta tabla irá a una sola suscripción**.</span><span class="sxs-lookup"><span data-stu-id="76d6b-123">Select the option that matches how data will be shared among Subscribers: **A row from this table will go to multiple subscriptions** or **A row from this table will go to only one subscription**.</span></span> <span data-ttu-id="76d6b-124">Si selecciona **Una fila de esta tabla irá a una sola suscripción**, la replicación de mezcla puede optimizar el rendimiento almacenando y procesando menos metadatos.</span><span class="sxs-lookup"><span data-stu-id="76d6b-124">If you select **A row from this table will go to only one subscription**, merge replication can optimize performance by storing and processing less metadata.</span></span> <span data-ttu-id="76d6b-125">No obstante, debe asegurarse de que los datos se particionan de forma que una fila no se pueda replicar en más de un suscriptor.</span><span class="sxs-lookup"><span data-stu-id="76d6b-125">However, you must ensure that the data is partitioned in such a way that a row cannot be replicated to more than one Subscriber.</span></span> <span data-ttu-id="76d6b-126">Para obtener más información, vea la sección sobre cómo configurar opciones de partición en el tema [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="76d6b-126">For more information, see the section "Setting 'partition options'" in the topic [Parameterized Row Filters](../merge/parameterized-filters-parameterized-row-filters.md).</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="76d6b-127">El filtro que ha especificado se analiza y se ejecuta según la tabla de la cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="76d6b-127">The filter you specified is parsed and run against the table in the SELECT clause.</span></span> <span data-ttu-id="76d6b-128">Si la instrucción de filtro contiene errores de sintaxis u otros problemas, se le notificará y podrá modificar dicha instrucción.</span><span class="sxs-lookup"><span data-stu-id="76d6b-128">If the filter statement contains syntax errors or other problems, you will be notified and will be able to edit the filter statement.</span></span>  
  
     <span data-ttu-id="76d6b-129">Una vez analizada la instrucción, la replicación crea los filtros de combinación necesarios y los muestra en el panel **Tablas filtradas** de la página **Filtrar filas de tabla** o **Filtrar filas** .</span><span class="sxs-lookup"><span data-stu-id="76d6b-129">After the statement is parsed, replication creates the necessary join filters and displays them in the **Filtered Tables** pane on the **Filter Table Rows** or **Filter Rows** page.</span></span> <span data-ttu-id="76d6b-130">Si genera filtros desde el Asistente para nueva publicación y aún no ha configurado el distribuidor para el publicador en el que se ejecuta este asistente, se le pedirá que lo haga.</span><span class="sxs-lookup"><span data-stu-id="76d6b-130">If you are generating filters from the New Publication Wizard and have not yet configured the Distributor for the Publisher against which this wizard is running, you are prompted to configure it.</span></span>  
  
4.  <span data-ttu-id="76d6b-131">Si está en el cuadro de diálogo **Propiedades de la publicación: \<Publication>** , haga clic en **Aceptar** para guardar y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="76d6b-131">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
### <a name="to-modify-a-filter-that-was-automatically-generated"></a><span data-ttu-id="76d6b-132">Para modificar un filtro generado automáticamente</span><span class="sxs-lookup"><span data-stu-id="76d6b-132">To modify a filter that was automatically generated</span></span>  
  
1.  <span data-ttu-id="76d6b-133">En la página **Filtrar filas de tabla** del Asistente para nueva publicación o en la página **Filtrar filas** de **Propiedades de la publicación: \<Publication>** , seleccione un filtro en el panel **Tablas filtradas** y luego haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="76d6b-133">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Edit**.</span></span>  
  
2.  <span data-ttu-id="76d6b-134">En el cuadro de diálogo **Editar filtro** o **Editar combinación** , modifique el filtro.</span><span class="sxs-lookup"><span data-stu-id="76d6b-134">In the **Edit Filter** or **Edit Join** dialog box, modify the filter.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-filter-that-was-automatically-generated"></a><span data-ttu-id="76d6b-135">Para eliminar un filtro generado automáticamente</span><span class="sxs-lookup"><span data-stu-id="76d6b-135">To delete a filter that was automatically generated</span></span>  
  
1.  <span data-ttu-id="76d6b-136">En la página **Filtrar filas de tabla** del Asistente para nueva publicación o en la página **Filtrar filas** de **Propiedades de la publicación: \<Publication>** , seleccione un filtro en el panel **Tablas filtradas** y luego haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="76d6b-136">On the **Filter Table Rows** page of the New Publication Wizard or the **Filter Rows** page of the **Publication Properties - \<Publication>**, select a filter in the **Filtered Tables** pane, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76d6b-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76d6b-137">See Also</span></span>  
 <span data-ttu-id="76d6b-138">[Join Filters](../merge/join-filters.md) </span><span class="sxs-lookup"><span data-stu-id="76d6b-138">[Join Filters](../merge/join-filters.md) </span></span>  
 [<span data-ttu-id="76d6b-139">Filtros de fila con parámetros</span><span class="sxs-lookup"><span data-stu-id="76d6b-139">Parameterized Row Filters</span></span>](../merge/parameterized-filters-parameterized-row-filters.md)  
  
  
