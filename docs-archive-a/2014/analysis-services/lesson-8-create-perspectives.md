---
title: 'Lección 9: crear perspectivas | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 55b0f0d0-1cdf-4876-9c3d-d0c848be3f5d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 417b6a4d3b16857f48bcc2f39dc8ec4c010a2b10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748999"
---
# <a name="lesson-9-create-perspectives"></a><span data-ttu-id="75626-102">Lección 9: Crear perspectivas</span><span class="sxs-lookup"><span data-stu-id="75626-102">Lesson 9: Create Perspectives</span></span>
  <span data-ttu-id="75626-103">En esta lección, creará una perspectiva Venta por Internet.</span><span class="sxs-lookup"><span data-stu-id="75626-103">In this lesson, you will create an Internet Sales perspective.</span></span> <span data-ttu-id="75626-104">Una perspectiva define un subconjunto visible de un modelo que ofrece puntos de vista centrados, específicos del negocio o específicos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75626-104">A perspective defines a viewable subset of a model that provides focused, business-specific, or application-specific viewpoints.</span></span> <span data-ttu-id="75626-105">Cuando un usuario se conecta a un modelo utilizando una perspectiva, solo ve los objetos del modelo (tablas, columnas, medidas, jerarquías y KPI) como campos definidos en esa perspectiva.</span><span class="sxs-lookup"><span data-stu-id="75626-105">When a user connects to a model using a perspective, they see only those model objects (tables, columns, measures, hierarchies, and KPIs) as fields defined in that perspective.</span></span>  
  
 <span data-ttu-id="75626-106">La perspectiva Venta por Internet que va a crear en esta lección excluirá el objeto de tabla Cliente.</span><span class="sxs-lookup"><span data-stu-id="75626-106">The Internet Sales perspective you create in this lesson will exclude the Customer table object.</span></span> <span data-ttu-id="75626-107">Al crear una perspectiva que excluye ciertos objetos en la vista, ese objeto todavía existe en el modelo; sin embargo, no está visible en una lista de campos del cliente de informe.</span><span class="sxs-lookup"><span data-stu-id="75626-107">When you create a perspective that excludes certain objects from view, that object still exists in the model; however, it is not visible in a reporting client field list.</span></span> <span data-ttu-id="75626-108">Las columnas calculadas y medidas se pueden incluir en una perspectiva o no pueden calcularse a partir de los datos del objeto excluido.</span><span class="sxs-lookup"><span data-stu-id="75626-108">Calculated columns and measures either included in a perspective or not can still calculate from object data that is excluded.</span></span>  
  
 <span data-ttu-id="75626-109">El propósito de esta lección es describir cómo se crean las perspectivas y permitir que se familiarice con las herramientas de creación de modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="75626-109">The purpose of this lesson is to describe how to create perspectives and become familiar with the tabular model authoring tools.</span></span> <span data-ttu-id="75626-110">Si posteriormente amplía el modelo para incluir tablas adicionales, puede crear otras perspectivas para definir puntos de vista diferentes del modelo, como Inventario y Personal de ventas.</span><span class="sxs-lookup"><span data-stu-id="75626-110">If you later expand this model to include additional tables, you can create additional perspectives to define different viewpoints of the model, for example, Inventory and Sales Force.</span></span>  
  
 <span data-ttu-id="75626-111">Para obtener más información, consulte [Perspectivas &#40;SSAS tabular&#41;](tabular-models/perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="75626-111">To learn more, see [Perspectives &#40;SSAS Tabular&#41;](tabular-models/perspectives-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="75626-112">Tiempo estimado para completar esta lección: **5 minutos**</span><span class="sxs-lookup"><span data-stu-id="75626-112">Estimated time to complete this lesson: **5 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="75626-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="75626-113">Prerequisites</span></span>  
 <span data-ttu-id="75626-114">Este tema forma parte de un tutorial de modelado tabular, que se debe completar en orden.</span><span class="sxs-lookup"><span data-stu-id="75626-114">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="75626-115">Antes de realizar las tareas de esta lección, debe haber completado la lección anterior: [Lección 8: Crear indicadores clave de rendimiento](lesson-7-create-key-performance-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="75626-115">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 8: Create Key Performance Indicators](lesson-7-create-key-performance-indicators.md).</span></span>  
  
## <a name="create-perspectives"></a><span data-ttu-id="75626-116">Crear perspectivas</span><span class="sxs-lookup"><span data-stu-id="75626-116">Create Perspectives</span></span>  
  
#### <a name="to-create-an-internet-sales-perspective"></a><span data-ttu-id="75626-117">Para crear una perspectiva Venta por Internet</span><span class="sxs-lookup"><span data-stu-id="75626-117">To create an Internet Sales perspective</span></span>  
  
1.  <span data-ttu-id="75626-118">En el diseñador de modelos, haga clic en el menú **modelo** y, a continuación, en **perspectivas**.</span><span class="sxs-lookup"><span data-stu-id="75626-118">In the model designer, click the **Model** menu, and then click **Perspectives**.</span></span>  
  
2.  <span data-ttu-id="75626-119">En el cuadro de diálogo **Perspectivas** , haga clic en **Nueva perspectiva**.</span><span class="sxs-lookup"><span data-stu-id="75626-119">In the **Perspectives** dialog box, click **New Perspective**.</span></span>  
  
3.  <span data-ttu-id="75626-120">Para cambiar el nombre de la perspectiva, haga doble clic en el encabezado de columna **nueva perspectiva 1** y, a continuación, escriba `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="75626-120">To rename the perspective, double-click the **New Perspective 1** column heading, and then type `Internet Sales`.</span></span>  
  
4.  <span data-ttu-id="75626-121">En **campos**, seleccione las tablas siguientes: **Date**, **Geography**, **Product**, **Product Category**, **Product**subcategory y `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="75626-121">In **Fields**, select the following tables **Date**, **Geography**, **Product**, **Product Category**, **Product Subcategory**, and `Internet Sales`.</span></span>  
  
     <span data-ttu-id="75626-122">Tenga en cuenta que excluyó la tabla Cliente y todas sus columnas de esta perspectiva.</span><span class="sxs-lookup"><span data-stu-id="75626-122">Notice you excluded the Customer table and all of its columns from this perspective.</span></span> <span data-ttu-id="75626-123">Más adelante, en la lección 12, utilizará la característica Analizar en Excel para probar esta perspectiva.</span><span class="sxs-lookup"><span data-stu-id="75626-123">Later, in Lesson 12, you will use the Analyze in Excel feature to test this perspective.</span></span> <span data-ttu-id="75626-124">La lista de campos de tabla dinámica de Excel incluirá todas las tablas, excepto la tabla Cliente.</span><span class="sxs-lookup"><span data-stu-id="75626-124">The Excel PivotTable Field List will include each table except the Customer table.</span></span>  
  
5.  <span data-ttu-id="75626-125">Compruebe sus selecciones, asegúrese de que no está marcada la tabla **Cliente** y, después, haga clic en **Aceptar**</span><span class="sxs-lookup"><span data-stu-id="75626-125">Verify your selections, making sure the **Customer** table is not checked, and then click **OK**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="75626-126">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="75626-126">Next Steps</span></span>  
 <span data-ttu-id="75626-127">Para continuar este tutorial, vaya a la lección siguiente: [Lección 10: Crear jerarquías](lesson-9-create-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="75626-127">To continue this tutorial, go to the next lesson: [Lesson 10: Create Hierarchies](lesson-9-create-hierarchies.md).</span></span>  
  
  
