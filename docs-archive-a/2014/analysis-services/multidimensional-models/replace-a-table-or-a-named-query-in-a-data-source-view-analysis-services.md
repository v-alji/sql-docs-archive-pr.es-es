---
title: Reemplazar una tabla o una consulta con nombre en una vista del origen de datos (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- replacing tables
- data source views [Analysis Services], tables
- named queries [Analysis Services], replacing tables
- tables [Analysis Services], data source views
- partitions [Analysis Services], named queries
ms.assetid: 60c2a018-1299-4915-b60e-e73316524def
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b5055de60ba757c9dcfa118e4e2c4748c6534e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674398"
---
# <a name="replace-a-table-or-a-named-query-in-a-data-source-view-analysis-services"></a><span data-ttu-id="db917-102">Reemplazar una tabla o una consulta con nombre en una vista del origen de datos (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="db917-102">Replace a Table or a Named Query in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="db917-103">En el Diseñador de vistas del origen de datos, puede reemplazar una tabla, una vista o una consulta con nombre de una vista del origen de datos (DSV) por una vista o tabla diferente del mismo origen de datos o de otro, o por una consulta con nombre definida en la DSV.</span><span class="sxs-lookup"><span data-stu-id="db917-103">In Data Source View Designer, you can replace a table, view, or named query in a data source view (DSV) with a different table or view from the same or a different data source, or with a named query defined in the DSV.</span></span> <span data-ttu-id="db917-104">Cuando se reemplaza una tabla, los demás objetos de la base de datos o proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contienen referencias a dicha tabla continúan haciendo referencia a ella, ya que el identificador de objeto de la tabla no cambia en la DSV.</span><span class="sxs-lookup"><span data-stu-id="db917-104">When you replace a table, all other objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or project that have references to the table continue to reference the table because the object ID for the table in the DSV does not change.</span></span> <span data-ttu-id="db917-105">Se conservan todas las relaciones que siguen siendo pertinentes (basadas en la coincidencia de nombre y tipo de columna).</span><span class="sxs-lookup"><span data-stu-id="db917-105">Any relationships that are still relevant (based on name and column-type matching) are retained.</span></span> <span data-ttu-id="db917-106">Por el contrario, si elimina y luego agrega una tabla, las referencias y relaciones se pierden y se tienen que volver a crear.</span><span class="sxs-lookup"><span data-stu-id="db917-106">In contrast, if you delete and then add a table, references and relationships are lost and must be recreated.</span></span>  
  
 <span data-ttu-id="db917-107">Para reemplazar una tabla por otra tabla, debe tener una conexión activa a los datos de origen en el Diseñador de vistas del origen de datos en el modo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="db917-107">To replace a table with another table, you must have an active connection to the source data in Data Source View Designer in project mode.</span></span>  
  
 <span data-ttu-id="db917-108">La mayoría de las veces, reemplaza una tabla de la vista del origen de datos por otra tabla del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="db917-108">You most frequently replace a table in the data source view with another table in the data source.</span></span> <span data-ttu-id="db917-109">No obstante, también puede reemplazar una consulta con nombre por una tabla.</span><span class="sxs-lookup"><span data-stu-id="db917-109">However, you can also replace a named query with a table.</span></span> <span data-ttu-id="db917-110">Por ejemplo, ha reemplazado una tabla por una consulta con nombre y ahora desea revertir a la tabla.</span><span class="sxs-lookup"><span data-stu-id="db917-110">For example, you previously replaced a table with a named query, and now want to revert to a table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="db917-111">Si cambia el nombre de una tabla en un origen de datos, siga los pasos para reemplazar una tabla y especifique la tabla cuyo nombre acaba de cambiar como el origen de la tabla correspondiente en la DSV antes de actualizar una DSV.</span><span class="sxs-lookup"><span data-stu-id="db917-111">If you rename a table in a data source, follow the steps for replacing a table and specify the renamed table as the source of the corresponding table in the DSV before you refresh a DSV.</span></span> <span data-ttu-id="db917-112">Si se completa el proceso de reemplazo y cambio de nombre de la tabla, se conservan la tabla, las referencias de la tabla y las relaciones de la tabla en la DSV.</span><span class="sxs-lookup"><span data-stu-id="db917-112">Completing the replacement and renaming process preserves the table, the table's references, and the table's relationships in the DSV.</span></span> <span data-ttu-id="db917-113">En caso contrario, cuando actualice la DSV, se interpretará que se ha eliminado la tabla a la que se ha cambiado el nombre en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="db917-113">Otherwise, when you refresh the DSV, a renamed table in data source is interpreted as being deleted.</span></span> <span data-ttu-id="db917-114">Para obtener más información, vea [Actualizar el esquema de una vista del origen de datos &#40;Analysis Services&#41;](refresh-the-schema-in-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="db917-114">For more information, see [Refresh the Schema in a Data Source View &#40;Analysis Services&#41;](refresh-the-schema-in-a-data-source-view-analysis-services.md).</span></span>  
  
##  <a name="replace-a-table-with-a-named-query"></a><a name="bkmk_nq"></a> <span data-ttu-id="db917-115">Reemplazar una tabla por una consulta con nombre</span><span class="sxs-lookup"><span data-stu-id="db917-115">Replace a table with a named query</span></span>  
  
1.  <span data-ttu-id="db917-116">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto o conéctese a la base de datos que contiene la vista del origen de datos en la que desea reemplazar una tabla o una consulta con nombre.</span><span class="sxs-lookup"><span data-stu-id="db917-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to replace a table or a named query.</span></span>  
  
2.  <span data-ttu-id="db917-117">En el Explorador de soluciones, expanda la carpeta **Vistas del origen de datos** y, después, haga doble clic en la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="db917-117">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="db917-118">Abra el cuadro de diálogo **Crear consulta con nombre** .</span><span class="sxs-lookup"><span data-stu-id="db917-118">Open the **Create Named Query** dialog box.</span></span> <span data-ttu-id="db917-119">En el panel **Tablas** o **Diagrama** , haga clic con el botón derecho en la tabla que quiere reemplazar, seleccione **Reemplazar tabla** y, después, haga clic en **Con nueva consulta con nombre**.</span><span class="sxs-lookup"><span data-stu-id="db917-119">In either **Tables** or **Diagram** pane, right-click the table that you wish to replace, point to **Replace Table** and then click **With New Named Query**.</span></span>  
  
4.  <span data-ttu-id="db917-120">En el cuadro de diálogo **Crear consulta con nombre** , defina la consulta con nombre y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db917-120">In the **Create Named Query** dialog box, define the named query and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="db917-121">Guarde la vista del origen de datos modificada.</span><span class="sxs-lookup"><span data-stu-id="db917-121">Save the modified data source view.</span></span>  
  
## <a name="replace-a-table-or-named-query-with-a-table"></a><span data-ttu-id="db917-122">Reemplazar una tabla o una consulta con nombre por una tabla</span><span class="sxs-lookup"><span data-stu-id="db917-122">Replace a table or named query with a table</span></span>  
  
1.  <span data-ttu-id="db917-123">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto o conéctese a la base de datos que contiene la vista del origen de datos en la que desea reemplazar una tabla o una consulta con nombre.</span><span class="sxs-lookup"><span data-stu-id="db917-123">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to replace a table or a named query.</span></span>  
  
2.  <span data-ttu-id="db917-124">En el Explorador de soluciones, expanda la carpeta **Vistas del origen de datos** y, después, haga doble clic en la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="db917-124">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="db917-125">Abra el cuadro de diálogo **Reemplazar tabla por otra tabla** .</span><span class="sxs-lookup"><span data-stu-id="db917-125">Open the **Replace Table with Other Table** dialog box.</span></span> <span data-ttu-id="db917-126">En el panel **Tablas** o **Diagrama** , haga clic con el botón derecho en la tabla o la consulta con nombre que quiere reemplazar, seleccione **Reemplazar tabla** y, después, haga clic en **Con otra tabla**.</span><span class="sxs-lookup"><span data-stu-id="db917-126">In either **Tables** or **Diagram** pane, right-click the table or named query that you wish to replace, point to **Replace Table** and then click **With Other Table**.</span></span>  
  
4.  <span data-ttu-id="db917-127">En el cuadro de diálogo **Reemplazar tabla por otra tabla** :</span><span class="sxs-lookup"><span data-stu-id="db917-127">In the **Replace Table with Other Table** dialog box:</span></span>  
  
    1.  <span data-ttu-id="db917-128">En la lista desplegable **Origen de datos** , seleccione el origen de datos que quiera.</span><span class="sxs-lookup"><span data-stu-id="db917-128">In the **DataSource** drop-down list box, select the desired data source</span></span>  
  
    2.  <span data-ttu-id="db917-129">Seleccione la tabla por la que desea reemplazar la tabla o consulta con nombre.</span><span class="sxs-lookup"><span data-stu-id="db917-129">Select the table with which you wish to replace the table or named query</span></span>  
  
5.  <span data-ttu-id="db917-130">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="db917-130">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="db917-131">Guarde la vista del origen de datos modificada.</span><span class="sxs-lookup"><span data-stu-id="db917-131">Save the modified data source view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db917-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db917-132">See Also</span></span>  
 [<span data-ttu-id="db917-133">Vistas del origen de datos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="db917-133">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
