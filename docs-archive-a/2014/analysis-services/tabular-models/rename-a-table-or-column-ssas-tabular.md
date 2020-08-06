---
title: Cambiar el nombre de una tabla o una columna (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.renametableorcolumn.f1
ms.assetid: 88061a39-c5aa-403d-a52b-7fdb365fc235
author: minewiskan
ms.author: owend
ms.openlocfilehash: d3a2e9a9f41434e64f9ec5ea2180861b459e8f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748942"
---
# <a name="rename-a-table-or-column-ssas-tabular"></a><span data-ttu-id="17691-102">Cambiar el nombre de una tabla o una columna (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="17691-102">Rename a Table or Column (SSAS Tabular)</span></span>
  <span data-ttu-id="17691-103">Puede cambiar el nombre de una tabla durante el proceso de importación si escribe un **Nombre descriptivo** en la página **Seleccionar tablas y vistas** del **Asistente para importación de tablas**.</span><span class="sxs-lookup"><span data-stu-id="17691-103">You can change the name of a table during the import process by typing a **Friendly Name** in the **Select Tables and Views** page of the **Table Import Wizard**.</span></span> <span data-ttu-id="17691-104">También puede cambiar los nombres de tabla y de columna si importa los datos especificando una consulta en la página **Especificar una consulta SQL** del **Asistente para la importación de tablas**.</span><span class="sxs-lookup"><span data-stu-id="17691-104">You can also change table and column names if you import data by specifying a query on the **Specify a SQL Query** page of the **Table Import Wizard**.</span></span>  
  
 <span data-ttu-id="17691-105">Después de haber agregado los datos al modelo, el nombre (o el título) de una tabla aparece en la pestaña de tabla, en la parte inferior del diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="17691-105">After you have added the data to the model, the name (or title) of a table appears on the table tab, at the bottom of the model designer.</span></span> <span data-ttu-id="17691-106">Puede cambiar el nombre de la tabla para darle otro más adecuado.</span><span class="sxs-lookup"><span data-stu-id="17691-106">You can change the name of your table to give it a more appropriate name.</span></span> <span data-ttu-id="17691-107">También puede cambiar el nombre de una columna una vez que los datos se hayan agregado al modelo.</span><span class="sxs-lookup"><span data-stu-id="17691-107">You can also rename a column after the data has been added to the model.</span></span> <span data-ttu-id="17691-108">Esta opción es especialmente importante si ha importado los datos de varios orígenes y desea asegurarse de que las columnas de tablas diferentes tengan nombres que son fáciles de distinguir.</span><span class="sxs-lookup"><span data-stu-id="17691-108">This option is especially important when you have imported data from multiple sources, and want to ensure that columns in different tables have names that are easy to distinguish.</span></span>  
  
### <a name="to-rename-a-table"></a><span data-ttu-id="17691-109">Para cambiar el nombre de una tabla</span><span class="sxs-lookup"><span data-stu-id="17691-109">To rename a table</span></span>  
  
1.  <span data-ttu-id="17691-110">En el diseñador de modelos, haga clic con el botón derecho en la pestaña que contenga la tabla cuyo nombre quiera cambiar y, después, haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="17691-110">In the model designer, right-click the tab that contains the table that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="17691-111">Escriba el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="17691-111">Type the new name.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="17691-112">Puede modificar otras propiedades de una tabla, como la información de conexión y las asignaciones de columnas, con el cuadro de diálogo **Editar propiedades de tabla** .</span><span class="sxs-lookup"><span data-stu-id="17691-112">You can edit other properties of a table, including the connection information and column mappings, by using the **Edit Table Properties** dialog box.</span></span> <span data-ttu-id="17691-113">Sin embargo, no puede cambiar el nombre en este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="17691-113">However, you cannot change the name in this dialog box.</span></span>  
  
### <a name="to-rename-a-column"></a><span data-ttu-id="17691-114">Para cambiar el nombre de una columna</span><span class="sxs-lookup"><span data-stu-id="17691-114">To rename a column</span></span>  
  
1.  <span data-ttu-id="17691-115">En el diseñador de modelos, haga doble clic en el encabezado de la columna cuyo nombre quiera cambiar, o bien haga clic con el botón derecho en el encabezado y seleccione **Cambiar el nombre de la columna** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="17691-115">In the model designer, double-click the header of the column that you want to rename, or right-click the header and select **Rename Column** from the context menu.</span></span>  
  
2.  <span data-ttu-id="17691-116">Escriba el nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="17691-116">Type the new name.</span></span>  
  
## <a name="naming-requirements-for-columns-and-tables"></a><span data-ttu-id="17691-117">Requisitos de los nombres de columnas y tablas</span><span class="sxs-lookup"><span data-stu-id="17691-117">Naming Requirements for Columns and Tables</span></span>  
 <span data-ttu-id="17691-118">Las palabras y caracteres siguientes no se pueden utilizar en el nombre de una tabla o columna:</span><span class="sxs-lookup"><span data-stu-id="17691-118">The following words and characters cannot be used in the name of a table or column:</span></span>  
  
-   <span data-ttu-id="17691-119">Espacios iniciales o finales</span><span class="sxs-lookup"><span data-stu-id="17691-119">Leading or trailing spaces</span></span>  
  
-   <span data-ttu-id="17691-120">Caracteres de control</span><span class="sxs-lookup"><span data-stu-id="17691-120">Control characters</span></span>  
  
-   <span data-ttu-id="17691-121">Los siguientes caracteres (que no son válidos en los nombres de objetos Analysis Services):.,; ':/ \\ \*|? &% $! + = () [] {}<></span><span class="sxs-lookup"><span data-stu-id="17691-121">The following characters (which are not valid in the names of Analysis Services objects): .,;':/\\*|?&%$!+=()[]{}<></span></span>  
  
-   <span data-ttu-id="17691-122">Palabras clave reservadas de Analysis Services, incluidos los nombres y operadores de funciones de las expresiones multidimensionales (MDX) y las extensiones de minería de datos (DMX).</span><span class="sxs-lookup"><span data-stu-id="17691-122">Analysis Services reserved keywords, including Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) function names and operators.</span></span>  
  
## <a name="effect-of-renaming-on-existing-tables-columns-and-calculations"></a><span data-ttu-id="17691-123">Efecto de cambiar el nombre en las tablas, columnas y cálculos existentes</span><span class="sxs-lookup"><span data-stu-id="17691-123">Effect of Renaming on Existing Tables, Columns, and Calculations</span></span>  
 <span data-ttu-id="17691-124">Siempre que cambia el nombre de una tabla, cambia el nombre del objeto de tabla subyacente, que puede contener varias columnas o medidas.</span><span class="sxs-lookup"><span data-stu-id="17691-124">Whenever you change the name of a table, you change the name of the underlying table object, which may contain multiple columns or measures.</span></span> <span data-ttu-id="17691-125">Por consiguiente, cualquier columna de la tabla, y cualquier relación que utilice las tabla, debe actualizarse para utilizar el nuevo nombre en sus definiciones.</span><span class="sxs-lookup"><span data-stu-id="17691-125">Therefore, any columns that are in the table, and any relationships that use the table, must be updated to use the new name in their definitions.</span></span> <span data-ttu-id="17691-126">Esta actualización tiene lugar automáticamente en algunos casos.</span><span class="sxs-lookup"><span data-stu-id="17691-126">This update happens automatically in some cases.</span></span> <span data-ttu-id="17691-127">Las medidas no se actualizan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="17691-127">Measures are not updated automatically.</span></span>  
  
 <span data-ttu-id="17691-128">Además, cualquier cálculo que utilice la tabla con el nombre cambiado o que use columnas de dicha tabla también debe actualizarse, así como los datos derivados de esos cálculos.</span><span class="sxs-lookup"><span data-stu-id="17691-128">Moreover, any calculations that use the renamed table, or that use columns from the renamed table, must also be updated, and the data derived from those calculations must be refreshed and recalculated.</span></span> <span data-ttu-id="17691-129">Esto puede tardar un tiempo que depende de cuántas tablas y cálculos se vean afectados.</span><span class="sxs-lookup"><span data-stu-id="17691-129">Depending on how many tables and calculations are affected, this can take some time to complete.</span></span> <span data-ttu-id="17691-130">Por consiguiente, el mejor momento para cambiar el nombre de las tablas es bien durante el proceso de importación o antes de empezar a generar relaciones y cálculos complejos.</span><span class="sxs-lookup"><span data-stu-id="17691-130">Therefore, the best time to rename tables is either during the import process, or before you start to build complex relationships and calculations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17691-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17691-131">See Also</span></span>  
 <span data-ttu-id="17691-132">[Tablas y columnas &#40;SSAS tabular&#41;](tables-and-columns-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="17691-132">[Tables and Columns &#40;SSAS Tabular&#41;](tables-and-columns-ssas-tabular.md) </span></span>  
 <span data-ttu-id="17691-133">[Importar desde PowerPivot &#40;SSAS tabular&#41;](import-from-power-pivot-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="17691-133">[Import from PowerPivot &#40;SSAS Tabular&#41;](import-from-power-pivot-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="17691-134">Importación desde Analysis Services &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="17691-134">Import from Analysis Services &#40;SSAS Tabular&#41;</span></span>](import-from-analysis-services-ssas-tabular.md)  
  
  
