---
title: Editor de transformación búsqueda aproximada (pestaña tabla de referencia) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.referencetable.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: 451f4e7d-1c8e-4784-b540-df0806509bf1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ce51dd64c9c5807ab23ac645694cfec29a36d52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663596"
---
# <a name="fuzzy-lookup-transformation-editor-reference-table-tab"></a><span data-ttu-id="62ad2-102">Editor de transformación Búsqueda aproximada (pestaña Tabla de referencia)</span><span class="sxs-lookup"><span data-stu-id="62ad2-102">Fuzzy Lookup Transformation Editor (Reference Table Tab)</span></span>
  <span data-ttu-id="62ad2-103">Use la pestaña **Tabla de referencia** del cuadro de diálogo **Editor de transformación Búsqueda aproximada** para especificar la tabla de origen y el índice que se van a usar para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="62ad2-103">Use the **Reference Table** tab of the **Fuzzy Lookup Transformation Editor** dialog box to specify the source table and the index to use for the lookup.</span></span> <span data-ttu-id="62ad2-104">El origen de los datos de referencia debe ser una tabla de una base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62ad2-104">The reference data source must be a table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62ad2-105">La transformación Búsqueda aproximada crea una copia de trabajo de la tabla de referencia.</span><span class="sxs-lookup"><span data-stu-id="62ad2-105">The Fuzzy Lookup transformation creates a working copy of the reference table.</span></span> <span data-ttu-id="62ad2-106">Los índices descritos a continuación se crean en esta tabla de trabajo mediante una tabla especial, no un índice normal de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="62ad2-106">The indexes described below are created on this working table by using a special table, not an ordinary [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] index.</span></span> <span data-ttu-id="62ad2-107">La transformación no modifica las tablas de origen existentes a menos que se seleccione **Mantener el índice almacenado**.</span><span class="sxs-lookup"><span data-stu-id="62ad2-107">The transformation does not modify the existing source tables unless you select **Maintain stored index**.</span></span> <span data-ttu-id="62ad2-108">En este caso, se crea un desencadenador en la tabla de referencia que actualiza la tabla de trabajo y la tabla del índice de búsqueda basándose en los cambios en la tabla de referencia.</span><span class="sxs-lookup"><span data-stu-id="62ad2-108">In this case, it creates a trigger on the reference table that updates the working table and the lookup index table based on changes to the reference table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62ad2-109">Las `Exhaustive` propiedades y `MaxMemoryUsage` de la transformación búsqueda aproximada no están disponibles en el **Editor de transformación búsqueda aproximada**, pero se pueden establecer mediante el **editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="62ad2-109">The `Exhaustive` and the `MaxMemoryUsage` properties of the Fuzzy Lookup transformation are not available in the **Fuzzy Lookup Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="62ad2-110">Además, solo se puede especificar un valor mayor que 100 para `MaxOutputMatchesPerInput` en el **editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="62ad2-110">In addition, a value greater than 100 for `MaxOutputMatchesPerInput` can be specified only in the **Advanced Editor**.</span></span> <span data-ttu-id="62ad2-111">Para obtener más información acerca de estas propiedades, vea la sección sobre la transformación Búsqueda aproximada en [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="62ad2-111">For more information on these properties, see the Fuzzy Lookup Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="62ad2-112">Para obtener más información acerca de la transformación Búsqueda aproximada, vea [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="62ad2-112">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="62ad2-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="62ad2-113">Options</span></span>  
 <span data-ttu-id="62ad2-114">**Administrador de conexiones OLE DB**</span><span class="sxs-lookup"><span data-stu-id="62ad2-114">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="62ad2-115">Seleccione un administrador de conexiones OLE DB de la lista o cree una conexión haciendo clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="62ad2-115">Select an existing OLE DB connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="62ad2-116">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="62ad2-116">**New**</span></span>  
 <span data-ttu-id="62ad2-117">Cree una conexión mediante el cuadro de diálogo **Configurar el administrador de conexiones OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="62ad2-117">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="62ad2-118">**Generar índice nuevo**</span><span class="sxs-lookup"><span data-stu-id="62ad2-118">**Generate new index**</span></span>  
 <span data-ttu-id="62ad2-119">Especifique que la transformación debe crear un nuevo índice que se utilizará en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="62ad2-119">Specify that the transformation should create a new index to use for the lookup.</span></span>  
  
 <span data-ttu-id="62ad2-120">**Nombre de la tabla de referencia**</span><span class="sxs-lookup"><span data-stu-id="62ad2-120">**Reference table name**</span></span>  
 <span data-ttu-id="62ad2-121">Seleccione la tabla existente que se utilizará como tabla de referencia (búsqueda).</span><span class="sxs-lookup"><span data-stu-id="62ad2-121">Select the existing table to use as the reference (lookup) table.</span></span>  
  
 <span data-ttu-id="62ad2-122">**Almacenar el nuevo índice**</span><span class="sxs-lookup"><span data-stu-id="62ad2-122">**Store new index**</span></span>  
 <span data-ttu-id="62ad2-123">Seleccione esta opción si desea guardar el nuevo índice de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="62ad2-123">Select this option if you want to save the new lookup index.</span></span>  
  
 <span data-ttu-id="62ad2-124">**Nombre del índice nuevo**</span><span class="sxs-lookup"><span data-stu-id="62ad2-124">**New index name**</span></span>  
 <span data-ttu-id="62ad2-125">Si ha elegido guardar el índice de búsqueda nuevo, escriba un nombre descriptivo para el índice.</span><span class="sxs-lookup"><span data-stu-id="62ad2-125">If you have chosen to save the new lookup index, type a descriptive name for the index.</span></span>  
  
 <span data-ttu-id="62ad2-126">**Mantener el índice almacenado**</span><span class="sxs-lookup"><span data-stu-id="62ad2-126">**Maintain stored index**</span></span>  
 <span data-ttu-id="62ad2-127">Si ha elegido guardar el índice de búsqueda nuevo, especifique si también desea que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] mantenga el índice.</span><span class="sxs-lookup"><span data-stu-id="62ad2-127">If you have chosen to save the new lookup index, specify whether you also want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to maintain the index.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="62ad2-128">Al seleccionar **Mantener el índice almacenado** en la pestaña **Tabla de referencia** del **Editor de transformación Búsqueda aproximada**, la transformación utiliza los procedimientos almacenados administrados para mantener el índice.</span><span class="sxs-lookup"><span data-stu-id="62ad2-128">When you select **Maintain stored index** on the **Reference Table** tab of the **Fuzzy Lookup Transformation Editor**, the transformation uses managed stored procedures to maintain the index.</span></span> <span data-ttu-id="62ad2-129">Estos procedimientos almacenados administrados usan la característica de integración de Common Language Runtime (CLR) en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62ad2-129">These managed stored procedures use the common language runtime (CLR) integration feature in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="62ad2-130">De forma predeterminada, la integración de CLR en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="62ad2-130">By default, CLR integration in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is not enabled.</span></span> <span data-ttu-id="62ad2-131">Para utilizar la funcionalidad **Mantener el índice almacenado** , debe habilitar la integración de CLR.</span><span class="sxs-lookup"><span data-stu-id="62ad2-131">To use the **Maintain stored index** functionality, you must enable CLR integration.</span></span> <span data-ttu-id="62ad2-132">Para más información, consulte [Enabling CLR Integration](../relational-databases/clr-integration/clr-integration-enabling.md).</span><span class="sxs-lookup"><span data-stu-id="62ad2-132">For more information, see [Enabling CLR Integration](../relational-databases/clr-integration/clr-integration-enabling.md).</span></span>  
>   
>  <span data-ttu-id="62ad2-133">Dado que la opción **Mantener el índice almacenado** requiere la integración con CLR, esta característica solo funciona al seleccionar una tabla de referencia en una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] donde se habilite la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="62ad2-133">Because the **Maintain stored index** option requires CLR integration, this feature works only when you select a reference table on an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] where CLR integration is enabled.</span></span>  
  
 <span data-ttu-id="62ad2-134">**Usar índice existente**</span><span class="sxs-lookup"><span data-stu-id="62ad2-134">**Use existing index**</span></span>  
 <span data-ttu-id="62ad2-135">Especifique que la transformación debe utilizar un índice existente para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="62ad2-135">Specify that the transformation should use an existing index for the lookup.</span></span>  
  
 <span data-ttu-id="62ad2-136">**Nombre de un índice existente**</span><span class="sxs-lookup"><span data-stu-id="62ad2-136">**Name of an existing index**</span></span>  
 <span data-ttu-id="62ad2-137">Seleccione de la lista un índice de búsqueda creado previamente.</span><span class="sxs-lookup"><span data-stu-id="62ad2-137">Select a previously created lookup index from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ad2-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62ad2-138">See Also</span></span>  
 <span data-ttu-id="62ad2-139">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="62ad2-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="62ad2-140">[Editor de transformación búsqueda aproximada &#40;pestaña columnas&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md) </span><span class="sxs-lookup"><span data-stu-id="62ad2-140">[Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md) </span></span>  
 [<span data-ttu-id="62ad2-141">Editor de transformación Búsqueda aproximada &#40;pestaña Avanzadas&#41;</span><span class="sxs-lookup"><span data-stu-id="62ad2-141">Fuzzy Lookup Transformation Editor &#40;Advanced Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-advanced-tab.md)  
  
  
