---
title: Crear y administrar particiones en la base de datos del área de trabajo (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.partitionmgr.f1
ms.assetid: 0b3027d6-652b-4eb3-a197-58b25df65218
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3824dd4763e516dc5e8e34a9ec815d3969f4eb79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671203"
---
# <a name="create-and-manage-partitions-in-the-workspace-database-ssas-tabular"></a><span data-ttu-id="bffd7-102">Crear y administrar particiones en la base de datos del área de trabajo (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="bffd7-102">Create and Manage Partitions in the Workspace Database (SSAS Tabular)</span></span>
  <span data-ttu-id="bffd7-103">Las particiones dividen una tabla en partes lógicas.</span><span class="sxs-lookup"><span data-stu-id="bffd7-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="bffd7-104">A continuación, cada partición se puede procesar (actualizar) de forma independiente o en paralelo con otras particiones.</span><span class="sxs-lookup"><span data-stu-id="bffd7-104">Each partition can then be processed (Refreshed) independently or in parallel with other partitions.</span></span> <span data-ttu-id="bffd7-105">Las particiones pueden mejorar la escalabilidad y facilitar el uso de bases de datos grandes.</span><span class="sxs-lookup"><span data-stu-id="bffd7-105">Partitions can improve scalability and manageability of large databases.</span></span> <span data-ttu-id="bffd7-106">De forma predeterminada, cada tabla tiene una partición que incluye todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="bffd7-106">By default, each table has one partition that includes all columns.</span></span> <span data-ttu-id="bffd7-107">En las tareas de este tema se describe cómo crear y administrar particiones en la base de datos del área de trabajo del modelo mediante el cuadro de diálogo **Administrador de particiones** de.[!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bffd7-107">Tasks in this topic describe how to create and manage partitions in the model workspace database by using the **Partition Manager** dialog box in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]</span></span>  
  
 <span data-ttu-id="bffd7-108">Una vez implementado un modelo en otra instancia de Analysis Services, los administradores de bases de datos pueden crear y administrar las particiones del modelo (implementado) mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bffd7-108">After a model has been deployed to another Analysis Services instance, database administrators can create and manage partitions in the (deployed) model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="bffd7-109">Para obtener más información, vea [Crear y administrar particiones de modelos tabulares &#40;SSAS tabular&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="bffd7-109">For more information, see [Create and Manage Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="bffd7-110">En este tema se incluyen las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="bffd7-110">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="bffd7-111">Para crear una partición</span><span class="sxs-lookup"><span data-stu-id="bffd7-111">To create a new partition</span></span>](#bkmk_create_new)  
  
-   [<span data-ttu-id="bffd7-112">Para copiar una partición</span><span class="sxs-lookup"><span data-stu-id="bffd7-112">To copy a partition</span></span>](#bkmk_copy)  
  
-   [<span data-ttu-id="bffd7-113">Para eliminar una partición</span><span class="sxs-lookup"><span data-stu-id="bffd7-113">To delete a partition</span></span>](#bkmk_delete)  
  
> [!NOTE]  
>  <span data-ttu-id="bffd7-114">No es posible mezclar particiones en la base de datos del área de trabajo del modelo usando el cuadro de diálogo Administrador de particiones.</span><span class="sxs-lookup"><span data-stu-id="bffd7-114">You cannot merge partitions in the model workspace database by using the Partition Manager dialog box.</span></span> <span data-ttu-id="bffd7-115">Solamente se pueden mezclar particiones en un modelo implementado mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bffd7-115">Partitions can be merged in a deployed model only by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="bffd7-116">Tareas</span><span class="sxs-lookup"><span data-stu-id="bffd7-116">Tasks</span></span>  
 <span data-ttu-id="bffd7-117">Para crear y administrar particiones, deberá usar el cuadro de diálogo **Administrador de particiones** .</span><span class="sxs-lookup"><span data-stu-id="bffd7-117">To create and manage partitions, you will use the **Partitions Manager** dialog box.</span></span> <span data-ttu-id="bffd7-118">Para ver el cuadro de diálogo **Administrador de particiones** , en [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], haga clic en el menú **Tabla** y en **Particiones**.</span><span class="sxs-lookup"><span data-stu-id="bffd7-118">To view the **Partitions Manager** dialog box, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Partitions**.</span></span>  
  
###  <a name="to-create-a-new-partition"></a><a name="bkmk_create_new"></a><span data-ttu-id="bffd7-119">Para crear una nueva partición</span><span class="sxs-lookup"><span data-stu-id="bffd7-119">To create a new partition</span></span>  
  
1.  <span data-ttu-id="bffd7-120">En el diseñador de modelos, seleccione la tabla en la que desea definir una partición.</span><span class="sxs-lookup"><span data-stu-id="bffd7-120">In the model designer, select the table for which you want to define a partition.</span></span>  
  
2.  <span data-ttu-id="bffd7-121">Haga clic en el menú **Tabla** y en **Particiones**.</span><span class="sxs-lookup"><span data-stu-id="bffd7-121">Click on the **Table** menu, and then click **Partitions**.</span></span>  
  
3.  <span data-ttu-id="bffd7-122">En **Administrador de particiones**, en el cuadro de lista **Tabla** , compruebe o seleccione la tabla en la que desea crear particiones y, a continuación, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="bffd7-122">In **Partition Manager**, in the **Table** listbox, verify or select the table you want to partition, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="bffd7-123">En **Nombre de partición**, escriba un nombre para la partición.</span><span class="sxs-lookup"><span data-stu-id="bffd7-123">In **Partition Name**, type a name for the partition.</span></span> <span data-ttu-id="bffd7-124">De forma predeterminada, el nombre de la partición predeterminada se incrementará numéricamente para cada nueva partición.</span><span class="sxs-lookup"><span data-stu-id="bffd7-124">By default, the name of the default partition will be incrementally numbered for each new partition.</span></span>  
  
5.  <span data-ttu-id="bffd7-125">Puede seleccionar las filas y las columnas que se incluirán en la partición mediante el modo de vista previa de tabla o mediante una consulta SQL creada con el Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="bffd7-125">You can select the rows and columns to be included in the partition by using Table Preview mode or by using a SQL query created using Query Editor mode.</span></span>  
  
     <span data-ttu-id="bffd7-126">Para usar el modo de vista previa de tabla (valor predeterminado), haga clic en el botón **Vista previa de tabla** cerca de la esquina superior derecha de la ventana de vista previa.</span><span class="sxs-lookup"><span data-stu-id="bffd7-126">To use Table Preview mode (default), click the **Table Preview** button near the upper-right corner of the preview window.</span></span> <span data-ttu-id="bffd7-127">Seleccione las columnas que desea incluir en la partición activando la casilla situada junto al nombre de cada columna.</span><span class="sxs-lookup"><span data-stu-id="bffd7-127">Select the columns you want to include in the partition by selecting the checkbox next to the column name.</span></span> <span data-ttu-id="bffd7-128">Para filtrar las filas, haga clic con el botón secundario en un valor de celda y, a continuación, haga clic en **Filtrar por valor de celda seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="bffd7-128">To filter rows, right click a cell value, and click **Filter by Selected Cell Value**.</span></span>  
  
     <span data-ttu-id="bffd7-129">Para usar una instrucción SQL, haga clic en el botón **Editor de consultas** cerca de la esquina superior derecha de la ventana de vista previa y, después, escriba o pegue una instrucción de consulta SQL en la ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="bffd7-129">To use a SQL statement, click the **Query Editor** button near the upper-right corner of the preview window, then type or paste a SQL query statement into the query window.</span></span> <span data-ttu-id="bffd7-130">Para validar la instrucción, haga clic **Validar**.</span><span class="sxs-lookup"><span data-stu-id="bffd7-130">To validate your statement, click **Validate**.</span></span> <span data-ttu-id="bffd7-131">Haga clic en **Diseño**para abrir el Diseñador de consultas.</span><span class="sxs-lookup"><span data-stu-id="bffd7-131">To use the Query Designer, click **Design**.</span></span>  
  
###  <a name="to-copy-a-partition"></a><a name="bkmk_copy"></a><span data-ttu-id="bffd7-132">Para copiar una partición</span><span class="sxs-lookup"><span data-stu-id="bffd7-132">To copy a partition</span></span>  
  
1.  <span data-ttu-id="bffd7-133">En **Administrador de particiones**, en el cuadro de lista **Tabla** , compruebe o seleccione la tabla que contiene la partición que desea copiar.</span><span class="sxs-lookup"><span data-stu-id="bffd7-133">In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to copy.</span></span>  
  
2.  <span data-ttu-id="bffd7-134">En la lista **Particiones** , seleccione la partición que desea copiar y haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="bffd7-134">In the **Partitions** list, select the partition you want to copy and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="bffd7-135">En **Nombre de partición**, escriba un nuevo nombre para la partición.</span><span class="sxs-lookup"><span data-stu-id="bffd7-135">In **Partition Name**, type a new name for the partition.</span></span>  
  
###  <a name="to-delete-a-partition"></a><a name="bkmk_delete"></a><span data-ttu-id="bffd7-136">Para eliminar una partición</span><span class="sxs-lookup"><span data-stu-id="bffd7-136">To delete a partition</span></span>  
  
1.  <span data-ttu-id="bffd7-137">En **Administrador de particiones**, en el cuadro de lista **Tabla** , compruebe o seleccione la tabla que contiene la partición que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="bffd7-137">In **Partition Manager**, in the **Table** listbox, verify or select the table that contains the partition you want to delete.</span></span>  
  
2.  <span data-ttu-id="bffd7-138">En la lista **Particiones** , seleccione la partición que desea eliminar y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="bffd7-138">In the **Partitions** list, select the partition you want to delete and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bffd7-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bffd7-139">See Also</span></span>  
 <span data-ttu-id="bffd7-140">[Particiones &#40;&#41;tabular de SSAS](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="bffd7-140">[Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="bffd7-141">Procesar particiones en la base de datos del área de trabajo &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="bffd7-141">Process Partitions in the Workspace Database &#40;SSAS Tabular&#41;</span></span>](process-partitions-in-the-workspace-database-ssas-tabular.md)  
  
  
