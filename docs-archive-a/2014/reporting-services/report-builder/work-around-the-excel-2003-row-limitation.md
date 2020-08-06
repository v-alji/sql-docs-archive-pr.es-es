---
title: Solucionar el límite de filas de Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a4c8700b-bef5-4440-a99c-bba5dcc46bfd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 128f65cf09833d23234da10bf7744c6ce30065ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670307"
---
# <a name="work-around-the-excel-row-limitation"></a><span data-ttu-id="da3b9-102">Solución alternativa de la limitación de filas de Excel</span><span class="sxs-lookup"><span data-stu-id="da3b9-102">Work Around the Excel Row Limitation</span></span>
  <span data-ttu-id="da3b9-103">En este tema se explica cómo resolver la limitación de filas de Excel 2003 al exportar informes a Excel.</span><span class="sxs-lookup"><span data-stu-id="da3b9-103">This topic explains how to work around the Excel 2003 row limitation when you export reports to Excel.</span></span> <span data-ttu-id="da3b9-104">La solución alternativa es para un informe que solo contiene una tabla.</span><span class="sxs-lookup"><span data-stu-id="da3b9-104">The workaround is for a report that contains only a table.</span></span>  
  
 <span data-ttu-id="da3b9-105">Excel 2003 admite un máximo de 65.536 filas por hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="da3b9-105">Excel 2003 supports a maximum of 65,536 rows per worksheet.</span></span> <span data-ttu-id="da3b9-106">Puede evitar esta limitación si fuerza un salto de página explícito después de un número determinado de filas.</span><span class="sxs-lookup"><span data-stu-id="da3b9-106">You can work around this limitation by forcing an explicit page break after a certain number of rows.</span></span> <span data-ttu-id="da3b9-107">El representador de Excel crea una nueva hoja de cálculo por cada salto de página explícito.</span><span class="sxs-lookup"><span data-stu-id="da3b9-107">The Excel renderer creates a new worksheet for each explicit page break.</span></span>  
  
### <a name="to-create-an-explicit-page-break"></a><span data-ttu-id="da3b9-108">Para crear un salto de página explícito</span><span class="sxs-lookup"><span data-stu-id="da3b9-108">To create an explicit page break</span></span>  
  
1.  <span data-ttu-id="da3b9-109">Abra el informe en [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)] o en el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="da3b9-109">Open the report in [!INCLUDE[ss_dtbi](../../includes/ss-dtbi-md.md)] or Report Manager.</span></span>  
  
2.  <span data-ttu-id="da3b9-110">Haga clic con el botón secundario en la fila de datos de la tabla y, a continuación, haga clic en **Agregar**grupo  >  **primario** para agregar un grupo de tablas externo.</span><span class="sxs-lookup"><span data-stu-id="da3b9-110">Right click the Data row in the table, and then click **Add Group** > **Parent Group** to add an outer table group.</span></span>  
  
     <span data-ttu-id="da3b9-111">![Seleccionar el grupo primario](../media/datarow-selectparentgroup.png "Seleccionar el grupo primario")</span><span class="sxs-lookup"><span data-stu-id="da3b9-111">![Select the Parent Group](../media/datarow-selectparentgroup.png "Select the Parent Group")</span></span>  
  
3.  <span data-ttu-id="da3b9-112">Escriba la fórmula siguiente en el cuadro de expresión **Agrupar por** y, a continuación, haga clic en **Aceptar** para agregar el grupo primario.</span><span class="sxs-lookup"><span data-stu-id="da3b9-112">Enter the following formula in the **Group by** expression box, and then click **OK** to add the parent group.</span></span>  
  
     <span data-ttu-id="da3b9-113">=Int((RowNumber(Nothing)-1)/65000)</span><span class="sxs-lookup"><span data-stu-id="da3b9-113">=Int((RowNumber(Nothing)-1)/65000)</span></span>  
  
     <span data-ttu-id="da3b9-114">La fórmula asigna un número a cada conjunto de 65000 filas del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="da3b9-114">The formula assigns a number to each set of 65000 rows in the dataset.</span></span> <span data-ttu-id="da3b9-115">Cuando se define un salto de página para el grupo, la expresión produce un salto de página cada 65000 filas.</span><span class="sxs-lookup"><span data-stu-id="da3b9-115">When a page break is defined for the group, the expression results in a page break every 65000 rows.</span></span>  
  
     <span data-ttu-id="da3b9-116">Al agregar el grupo de tablas exterior agrega una columna de grupo al informe.</span><span class="sxs-lookup"><span data-stu-id="da3b9-116">Adding the outer table group adds a group column to the report.</span></span>  
  
4.  <span data-ttu-id="da3b9-117">Elimine la columna de grupo; para ello, haga clic con el botón derecho en el encabezado de columna, haga clic en **Eliminar columnas**, seleccione **Eliminar solo columnas**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="da3b9-117">Delete the group column by right-clicking on the column header, clicking **Delete Columns**, selecting **Delete columns only**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="da3b9-118">![Eliminar un grupo de columnas](../media/groupcolumn-delete-updated.png "Eliminar un grupo de columnas")</span><span class="sxs-lookup"><span data-stu-id="da3b9-118">![Delete a group column](../media/groupcolumn-delete-updated.png "Delete a group column")</span></span>  
  
5.  <span data-ttu-id="da3b9-119">Haga clic con el botón secundario en **Grupo 1** en la sección **Grupos de filas** y, a continuación, haga clic en **Propiedades de grupo**.</span><span class="sxs-lookup"><span data-stu-id="da3b9-119">Right click **Group 1** in the **Row Groups** section, and then click **Group Properties**.</span></span>  
  
     <span data-ttu-id="da3b9-120">![Ver propiedades de grupo](../media/groupproperties-updated.png "Ver propiedades de grupo")</span><span class="sxs-lookup"><span data-stu-id="da3b9-120">![View group properties](../media/groupproperties-updated.png "View group properties")</span></span>  
  
6.  <span data-ttu-id="da3b9-121">En la página **Ordenación** del cuadro de diálogo **Propiedades de grupo** , seleccione la opción de ordenación predeterminada y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="da3b9-121">On the **Sorting** page of the **Group Properties** dialog box, select the default sorting option and click **Delete**.</span></span>  
  
     <span data-ttu-id="da3b9-122">![Eliminar la ordenación predeterminada](../media/groupproperties-sorting-updated.png "Eliminar la ordenación predeterminada")</span><span class="sxs-lookup"><span data-stu-id="da3b9-122">![Delete default sorting](../media/groupproperties-sorting-updated.png "Delete default sorting")</span></span>  
  
7.  <span data-ttu-id="da3b9-123">En la página **Saltos de página** , haga clic en **Entre cada instancia de un grupo** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="da3b9-123">On the **Page Breaks** page, click **Between each instance of a group** and then click **OK**.</span></span>  
  
     <span data-ttu-id="da3b9-124">![Establecer saltos de página](../media/groupproperties-pagebreaks-updated.png "Establecer saltos de página")</span><span class="sxs-lookup"><span data-stu-id="da3b9-124">![Set page breaks](../media/groupproperties-pagebreaks-updated.png "Set page breaks")</span></span>  
  
8.  <span data-ttu-id="da3b9-125">Guarde el informe.</span><span class="sxs-lookup"><span data-stu-id="da3b9-125">Save the report.</span></span> <span data-ttu-id="da3b9-126">Cuando lo exporta a Excel, se exporta a varias hojas de cálculo y cada hoja de cálculo contiene un máximo de 65000 filas.</span><span class="sxs-lookup"><span data-stu-id="da3b9-126">When you export it to Excel, it exports to multiple worksheets and each worksheet contains a maximum of 65000 rows.</span></span>  
  
  
