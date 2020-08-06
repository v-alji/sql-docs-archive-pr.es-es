---
title: Definir un cubo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8aa4ac2d-857f-4048-baa0-0f314e207cf6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 354a05840dd2e091f956454858edd5c75c8c4bdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662296"
---
# <a name="defining-a-cube"></a><span data-ttu-id="86d40-102">Definir un cubo</span><span class="sxs-lookup"><span data-stu-id="86d40-102">Defining a Cube</span></span>
  <span data-ttu-id="86d40-103">El Asistente para cubos le ayuda a definir los grupos de medida y las dimensiones de un cubo.</span><span class="sxs-lookup"><span data-stu-id="86d40-103">The Cube Wizard helps you define the measure groups and dimensions for a cube.</span></span> <span data-ttu-id="86d40-104">En la tarea siguiente, usará el Asistente para cubos para generar un cubo.</span><span class="sxs-lookup"><span data-stu-id="86d40-104">In the following task, you will use the Cube Wizard to build a cube.</span></span>  
  
### <a name="to-define-a-cube-and-its-properties"></a><span data-ttu-id="86d40-105">Para definir un cubo y sus propiedades</span><span class="sxs-lookup"><span data-stu-id="86d40-105">To define a cube and its properties</span></span>  
  
1.  <span data-ttu-id="86d40-106">En el Explorador de soluciones, haga clic con el botón derecho en **Cubos**y, después, haga clic en **Nuevo cubo**.</span><span class="sxs-lookup"><span data-stu-id="86d40-106">In Solution Explorer, right-click **Cubes**, and then click **New Cube**.</span></span> <span data-ttu-id="86d40-107">Aparece el Asistente para cubos.</span><span class="sxs-lookup"><span data-stu-id="86d40-107">The Cube Wizard appears.</span></span>  
  
2.  <span data-ttu-id="86d40-108">En la página **Asistente para cubos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86d40-108">On the **Welcome to the Cube Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="86d40-109">En la página **Seleccionar método de creación** , compruebe que la opción **Usar tablas existentes** está seleccionada y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86d40-109">On the **Select Creation Method** page, verify that the **Use existing tables** option is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="86d40-110">En la página **Seleccionar tablas de grupo de medida** , compruebe que la vista del origen de datos **Adventure Works DW 2012** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="86d40-110">On the **Select Measure Group Tables** page, verify that the **Adventure Works DW 2012** data source view is selected.</span></span>  
  
5.  <span data-ttu-id="86d40-111">Haga clic en **Sugerir** para que el Asistente para cubos sugiera las tablas que se deben usar para crear los grupos de medida.</span><span class="sxs-lookup"><span data-stu-id="86d40-111">Click **Suggest** to have the cube wizard suggest tables to use to create measure groups.</span></span>  
  
     <span data-ttu-id="86d40-112">El asistente examinará las tablas y sugerirá **InternetSales** como tabla de grupos de medida.</span><span class="sxs-lookup"><span data-stu-id="86d40-112">The wizard examines the tables and suggests **InternetSales** as a measure group table.</span></span> <span data-ttu-id="86d40-113">Las tablas de grupos de medida, también denominadas tablas de hechos, contienen las medidas que son de su interés, como el número de unidades vendidas.</span><span class="sxs-lookup"><span data-stu-id="86d40-113">Measure group tables, also called fact tables, contain the measures you are interested in, such as the number of units sold.</span></span>  
  
6.  <span data-ttu-id="86d40-114">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="86d40-114">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="86d40-115">En la página **Seleccionar medidas** , revise las medidas seleccionadas en el grupo de medida **Internet Sales** y luego desactive las casillas de las medidas siguientes:</span><span class="sxs-lookup"><span data-stu-id="86d40-115">On the **Select Measures** page, review the selected measures in the **Internet Sales** measure group, and then clear the check boxes for the following measures:</span></span>  
  
    -   <span data-ttu-id="86d40-116">**Promotion Key**</span><span class="sxs-lookup"><span data-stu-id="86d40-116">**Promotion Key**</span></span>  
  
    -   <span data-ttu-id="86d40-117">**Currency Key**</span><span class="sxs-lookup"><span data-stu-id="86d40-117">**Currency Key**</span></span>  
  
    -   <span data-ttu-id="86d40-118">**Sales Territory Key**</span><span class="sxs-lookup"><span data-stu-id="86d40-118">**Sales Territory Key**</span></span>  
  
    -   <span data-ttu-id="86d40-119">**Revision Number**</span><span class="sxs-lookup"><span data-stu-id="86d40-119">**Revision Number**</span></span>  
  
     <span data-ttu-id="86d40-120">De forma predeterminada, el asistente selecciona como medidas todas las columnas numéricas de la tabla de hechos que no están vinculadas a dimensiones.</span><span class="sxs-lookup"><span data-stu-id="86d40-120">By default, the wizard selects as measures all numeric columns in the fact table that are not linked to dimensions.</span></span> <span data-ttu-id="86d40-121">No obstante, estas cuatro columnas no son miembros reales.</span><span class="sxs-lookup"><span data-stu-id="86d40-121">However, these four columns are not actual measures.</span></span> <span data-ttu-id="86d40-122">Las tres primeras son valores clave que vinculan la tabla de hechos con tablas de dimensiones que no se utilizan en la versión inicial de este cubo.</span><span class="sxs-lookup"><span data-stu-id="86d40-122">The first three are key values that link the fact table with dimension tables that are not used in the initial version of this cube.</span></span>  
  
8.  <span data-ttu-id="86d40-123">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="86d40-123">Click **Next**.</span></span>  
  
9. <span data-ttu-id="86d40-124">En la página **Seleccionar dimensiones existentes** , asegúrese de que la dimensión **Date** que ha creado anteriormente está seleccionada y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="86d40-124">On the **Select Existing Dimensions** page, make sure the **Date** dimension that you created earlier is selected, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="86d40-125">En la página **Seleccionar nuevas dimensiones** , seleccione las nuevas dimensiones que se van a crear.</span><span class="sxs-lookup"><span data-stu-id="86d40-125">On the **Select New Dimensions** page, select the new dimensions to be created.</span></span> <span data-ttu-id="86d40-126">Para ello, compruebe que las casillas **Customer**, **Geography**y **Product** están activadas y, después, desactive la casilla **InternetSales** .</span><span class="sxs-lookup"><span data-stu-id="86d40-126">To do this, verify that the **Customer**, **Geography**, and **Product** check boxes are selected, and then clear the **InternetSales** check box.</span></span>  
  
11. <span data-ttu-id="86d40-127">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="86d40-127">Click **Next**.</span></span>  
  
12. <span data-ttu-id="86d40-128">En la página **finalización del asistente** , cambie el nombre del cubo a `Analysis Services Tutorial` .</span><span class="sxs-lookup"><span data-stu-id="86d40-128">On the **Completing the Wizard** page, change the name of the cube to `Analysis Services Tutorial`.</span></span> <span data-ttu-id="86d40-129">En el panel de vista previa, puede ver el grupo de medida **InternetSales** y sus medidas.</span><span class="sxs-lookup"><span data-stu-id="86d40-129">In the Preview pane, you can see the **InternetSales** measure group and its measures.</span></span> <span data-ttu-id="86d40-130">También puede ver las dimensiones **Date**, **Customer** y **Product** .</span><span class="sxs-lookup"><span data-stu-id="86d40-130">You can also see the **Date**, **Customer,** and **Product** dimensions.</span></span>  
  
13. <span data-ttu-id="86d40-131">Haga clic en **Finalizar** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="86d40-131">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="86d40-132">En el Explorador de soluciones, en el proyecto Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] aparece en la carpeta **Cubos** , y las dimensiones de base de datos Customer y Product aparecen en la carpeta **Dimensiones** .</span><span class="sxs-lookup"><span data-stu-id="86d40-132">In Solution Explorer, in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube appears in the **Cubes** folder, and the Customer and Product database dimensions appear in the **Dimensions** folder.</span></span> <span data-ttu-id="86d40-133">Asimismo, en el centro del entorno de desarrollo, la pestaña Estructura de cubo muestra el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86d40-133">Additionally, in the center of the development environment, the Cube Structure tab displays the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
14. <span data-ttu-id="86d40-134">En la barra de herramientas de la pestaña Estructura de cubo, cambie el nivel de **Zoom** al 50 por ciento, de modo que pueda ver mejor las tablas de dimensiones y hechos del cubo.</span><span class="sxs-lookup"><span data-stu-id="86d40-134">On the toolbar of the Cube Structure tab, change the **Zoom** level to 50 percent, so that you can more easily see the dimensions and fact tables in the cube.</span></span> <span data-ttu-id="86d40-135">Observe que la tabla de hechos es amarilla y las tablas de dimensiones son azules.</span><span class="sxs-lookup"><span data-stu-id="86d40-135">Notice that the fact table is yellow and the dimension tables are blue.</span></span>  
  
15. <span data-ttu-id="86d40-136">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="86d40-136">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="86d40-137">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="86d40-137">Next Task in Lesson</span></span>  
 [<span data-ttu-id="86d40-138">Agregar atributos a dimensiones</span><span class="sxs-lookup"><span data-stu-id="86d40-138">Adding Attributes to Dimensions</span></span>](lesson-2-3-adding-attributes-to-dimensions.md)  
  
## <a name="see-also"></a><span data-ttu-id="86d40-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86d40-139">See Also</span></span>  
 <span data-ttu-id="86d40-140">[Cubos en modelos multidimensionales](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="86d40-140">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="86d40-141">Dimensiones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="86d40-141">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
