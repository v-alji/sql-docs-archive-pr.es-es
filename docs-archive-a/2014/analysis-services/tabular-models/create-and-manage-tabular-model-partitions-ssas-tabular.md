---
title: Crear y administrar particiones de modelos tabulares (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: dab72cf0-95bc-4b63-95dc-505b5cd881c1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 58c408c712d6ac4b6bd590bd0f8c895dc1a88700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675520"
---
# <a name="create-and-manage-tabular-model-partitions-ssas-tabular"></a><span data-ttu-id="aff29-102">Crear y administrar particiones de modelos tabulares (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="aff29-102">Create and Manage Tabular Model Partitions (SSAS Tabular)</span></span>
  <span data-ttu-id="aff29-103">Las particiones dividen una tabla en partes lógicas.</span><span class="sxs-lookup"><span data-stu-id="aff29-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="aff29-104">A continuación, cada partición se puede procesar (actualizar) de forma independiente de las demás particiones.</span><span class="sxs-lookup"><span data-stu-id="aff29-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="aff29-105">Las particiones definidas para un modelo durante la creación de modelos se duplican en un modelo implementado.</span><span class="sxs-lookup"><span data-stu-id="aff29-105">Partitions defined for a model during model authoring are duplicated in a deployed model.</span></span> <span data-ttu-id="aff29-106">Una vez realizada la implementación, puede administrar esas particiones mediante el cuadro de diálogo **Particiones** de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o mediante un script.</span><span class="sxs-lookup"><span data-stu-id="aff29-106">Once deployed, you can manage those partitions by using the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or by using a script.</span></span> <span data-ttu-id="aff29-107">Las tareas proporcionadas en este tema describen cómo crear y administrar particiones en un modelo implementado.</span><span class="sxs-lookup"><span data-stu-id="aff29-107">Tasks provided in this topic describe how to create and manage partitions for a deployed model.</span></span>  
  
 <span data-ttu-id="aff29-108">En este tema se incluyen las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="aff29-108">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="aff29-109">Para crear una partición</span><span class="sxs-lookup"><span data-stu-id="aff29-109">To create a new partition</span></span>](#bkmk_create_new)  
  
-   [<span data-ttu-id="aff29-110">Para copiar una partición</span><span class="sxs-lookup"><span data-stu-id="aff29-110">To copy a partition</span></span>](#bkmk_copy)  
  
-   [<span data-ttu-id="aff29-111">Para combinar dos o más particiones</span><span class="sxs-lookup"><span data-stu-id="aff29-111">To merge two or more partitions</span></span>](#bkmk_merge)  
  
-   [<span data-ttu-id="aff29-112">Para eliminar una partición</span><span class="sxs-lookup"><span data-stu-id="aff29-112">To delete a partition</span></span>](#bkmk_delete)  
  
## <a name="tasks"></a><span data-ttu-id="aff29-113">Tareas</span><span class="sxs-lookup"><span data-stu-id="aff29-113">Tasks</span></span>  
 <span data-ttu-id="aff29-114">Para crear y administrar particiones en una base de datos de modelos tabulares implementada, usará el cuadro de diálogo **Particiones** de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aff29-114">To create and manage partitions for a deployed tabular model database, you will use the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="aff29-115">Para ver el cuadro de diálogo **Particiones** , en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], haga clic con el botón derecho en una tabla y, después, haga clic en **Particiones**.</span><span class="sxs-lookup"><span data-stu-id="aff29-115">To view the **Partitions** dialog box, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click on a table, and then click **Partitions**.</span></span>  
  
###  <a name="to-create-a-new-partition"></a><a name="bkmk_create_new"></a><span data-ttu-id="aff29-116">Para crear una nueva partición</span><span class="sxs-lookup"><span data-stu-id="aff29-116">To create a new partition</span></span>  
  
1.  <span data-ttu-id="aff29-117">En el cuadro de diálogo **Particiones** , haga clic en el botón **Nuevo** .</span><span class="sxs-lookup"><span data-stu-id="aff29-117">In the **Partitions** dialog box, click the **New** button.</span></span>  
  
2.  <span data-ttu-id="aff29-118">En **Nombre de partición**, escriba un nombre para la partición.</span><span class="sxs-lookup"><span data-stu-id="aff29-118">In **Partition Name**, type a name for the partition.</span></span> <span data-ttu-id="aff29-119">De forma predeterminada, el nombre de la partición predeterminada se incrementará numéricamente para cada nueva partición.</span><span class="sxs-lookup"><span data-stu-id="aff29-119">By default, the name of the default partition will be incrementally numbered for each new partition.</span></span>  
  
3.  <span data-ttu-id="aff29-120">En **Instrucción SQL**, escriba o pegue una instrucción de consulta SQL que defina las columnas y las cláusulas que desea incluir en la partición en la ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="aff29-120">In **SQL Statement**, type or paste a SQL query statement that defines the columns and any clauses you want to include in the partition into the query window.</span></span>  
  
4.  <span data-ttu-id="aff29-121">Para validar la instrucción, haga clic en **Comprobar sintaxis**.</span><span class="sxs-lookup"><span data-stu-id="aff29-121">To validate the statement, click **Check Syntax**.</span></span>  
  
###  <a name="to-copy-a-partition"></a><a name="bkmk_copy"></a><span data-ttu-id="aff29-122">Para copiar una partición</span><span class="sxs-lookup"><span data-stu-id="aff29-122">To copy a partition</span></span>  
  
1.  <span data-ttu-id="aff29-123">En el cuadro de diálogo **Particiones** , en la lista **Particiones** , seleccione la partición que desea copiar y, a continuación, haga clic en el botón **Copiar** .</span><span class="sxs-lookup"><span data-stu-id="aff29-123">In the **Partitions** dialog box, in the **Partitions** list, select the partition you want to copy, and then click the **Copy** button.</span></span>  
  
2.  <span data-ttu-id="aff29-124">En **Nombre de partición**, escriba un nuevo nombre para la partición.</span><span class="sxs-lookup"><span data-stu-id="aff29-124">In **Partition Name**, type a new name for the partition.</span></span>  
  
3.  <span data-ttu-id="aff29-125">En **Instrucción SQL**, edite la instrucción de consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="aff29-125">In **SQL Statement**, edit the SQL query statement.</span></span>  
  
###  <a name="to-merge-two-or-more-partitions"></a><a name="bkmk_merge"></a> <span data-ttu-id="aff29-126">Para combinar dos o más particiones</span><span class="sxs-lookup"><span data-stu-id="aff29-126">To merge two or more partitions</span></span>  
  
-   <span data-ttu-id="aff29-127">En el cuadro de diálogo **Particiones** , en la lista **Particiones** , use Ctrl+clic para seleccionar las particiones que quiere combinar y, después, haga clic en el botón **Combinar** .</span><span class="sxs-lookup"><span data-stu-id="aff29-127">In the **Partitions** dialog box, in the **Partitions** list, use Ctrl+click to select the partitions you want to merge, and then click the **Merge** button.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="aff29-128">Al combinar las particiones no se actualizan los metadatos de la partición.</span><span class="sxs-lookup"><span data-stu-id="aff29-128">Merging partitions does not update the partition metadata.</span></span> <span data-ttu-id="aff29-129">Los administradores deben modificar la instrucción SQL para la partición resultante a fin de asegurarse de que las operaciones de procesamiento procesan todos los datos de la partición combinada.</span><span class="sxs-lookup"><span data-stu-id="aff29-129">Administrators must alter the SQL Statement for the resulting partition to make sure processing operations process all data in the merged partition.</span></span>  
  
###  <a name="to-delete-a-partition"></a><a name="bkmk_delete"></a><span data-ttu-id="aff29-130">Para eliminar una partición</span><span class="sxs-lookup"><span data-stu-id="aff29-130">To delete a partition</span></span>  
  
-   <span data-ttu-id="aff29-131">En el cuadro de diálogo **Particiones** , en la lista **Particiones** , seleccione la partición que desea eliminar y, a continuación, haga clic en el botón **Eliminar** .</span><span class="sxs-lookup"><span data-stu-id="aff29-131">In the **Partitions** dialog box, in the **Partitions** list, select the partition you want to delete, and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff29-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aff29-132">See Also</span></span>  
 <span data-ttu-id="aff29-133">[Particiones de modelos tabulares &#40;SSAS tabular&#41;](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="aff29-133">[Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="aff29-134">Procesar particiones de modelos tabulares &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="aff29-134">Process Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](process-tabular-model-partitions-ssas-tabular.md)  
  
  
