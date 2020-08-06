---
title: Definir una dimensión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 112696db-3838-4b50-91bd-d2ce5fa04ee5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2eb7a695ffc2c0588396a4a9ea655983c26cc719
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662298"
---
# <a name="defining-a-dimension"></a><span data-ttu-id="60c0f-102">Definir una dimensión</span><span class="sxs-lookup"><span data-stu-id="60c0f-102">Defining a Dimension</span></span>
  <span data-ttu-id="60c0f-103">En la tarea siguiente, usará el Asistente para dimensiones con objeto de generar una dimensión Date.</span><span class="sxs-lookup"><span data-stu-id="60c0f-103">In the following task, you will use the Dimension Wizard to build a Date dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="60c0f-104">Para realizar esta lección es necesario haber completado todos los procedimientos de la lección 1.</span><span class="sxs-lookup"><span data-stu-id="60c0f-104">This lesson requires that you have completed all the procedures in Lesson 1.</span></span>  
  
### <a name="to-define-a-dimension"></a><span data-ttu-id="60c0f-105">Para definir una dimensión</span><span class="sxs-lookup"><span data-stu-id="60c0f-105">To define a dimension</span></span>  
  
1.  <span data-ttu-id="60c0f-106">En el Explorador de soluciones (en el margen derecho de Microsoft Visual Studio), haga clic con el botón derecho en **Dimensiones**y haga clic en **Nueva dimensión**.</span><span class="sxs-lookup"><span data-stu-id="60c0f-106">In Solution Explorer (on the right side of Microsoft Visual Studio), right-click **Dimensions**, and then click **New Dimension**.</span></span> <span data-ttu-id="60c0f-107">Aparece el Asistente para dimensiones.</span><span class="sxs-lookup"><span data-stu-id="60c0f-107">The Dimension Wizard appears.</span></span>  
  
2.  <span data-ttu-id="60c0f-108">En la página **Asistente para dimensiones** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="60c0f-108">On the **Welcome to the Dimension Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="60c0f-109">En la página **Seleccionar método de creación** , compruebe que la opción **Usar una tabla existente** está seleccionada y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="60c0f-109">On the **Select Creation Method** page, verify that the **Use an existing table** option is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="60c0f-110">En la página **Especificar información de origen** , compruebe que la vista del origen de datos **Adventure Works DW 2012** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="60c0f-110">On the **Specify Source Information** page, verify that the **Adventure Works DW 2012** data source view is selected.</span></span>  
  
5.  <span data-ttu-id="60c0f-111">En la lista **Tabla principal** , seleccione **Fecha**.</span><span class="sxs-lookup"><span data-stu-id="60c0f-111">In the **Main table** list, select **Date**.</span></span>  
  
6.  <span data-ttu-id="60c0f-112">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="60c0f-112">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="60c0f-113">En la página **Seleccionar los atributos de la dimensión** , active las casillas situadas junto a los siguientes atributos:</span><span class="sxs-lookup"><span data-stu-id="60c0f-113">On the **Select Dimension Attributes** page, select the check boxes next to the following attributes:</span></span>  
  
    -   <span data-ttu-id="60c0f-114">**Date Key**</span><span class="sxs-lookup"><span data-stu-id="60c0f-114">**Date Key**</span></span>  
  
    -   <span data-ttu-id="60c0f-115">**Full Date Alternate Key**</span><span class="sxs-lookup"><span data-stu-id="60c0f-115">**Full Date Alternate Key**</span></span>  
  
    -   <span data-ttu-id="60c0f-116">**Spanish Month Name**</span><span class="sxs-lookup"><span data-stu-id="60c0f-116">**English Month Name**</span></span>  
  
    -   <span data-ttu-id="60c0f-117">**Trimestre natural**</span><span class="sxs-lookup"><span data-stu-id="60c0f-117">**Calendar Quarter**</span></span>  
  
    -   <span data-ttu-id="60c0f-118">**Año natural**</span><span class="sxs-lookup"><span data-stu-id="60c0f-118">**Calendar Year**</span></span>  
  
    -   <span data-ttu-id="60c0f-119">**Semestre del calendario**</span><span class="sxs-lookup"><span data-stu-id="60c0f-119">**Calendar Semester**</span></span>  
  
8.  <span data-ttu-id="60c0f-120">Cambie el valor de la columna **Tipo de atributo** del atributo **Full Date Alternate Key** de **Normal** a **Fecha**.</span><span class="sxs-lookup"><span data-stu-id="60c0f-120">Change the setting of the **Full Date Alternate Key** attribute's **Attribute Type** column from **Regular** to **Date**.</span></span> <span data-ttu-id="60c0f-121">Para ello, haga clic en **Normal** en la columna **Tipo de atributo** .</span><span class="sxs-lookup"><span data-stu-id="60c0f-121">To do this, click **Regular** in the **Attribute Type** column.</span></span> <span data-ttu-id="60c0f-122">A continuación, haga clic en la flecha para expandir las opciones.</span><span class="sxs-lookup"><span data-stu-id="60c0f-122">Then click the arrow to expand the options.</span></span> <span data-ttu-id="60c0f-123">A continuación, **haga clic en fecha**  >  **calendario**  >  **fecha**.</span><span class="sxs-lookup"><span data-stu-id="60c0f-123">Next, click **Date** > **Calendar** > **Date**.</span></span> <span data-ttu-id="60c0f-124">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="60c0f-124">Click **OK**.</span></span> <span data-ttu-id="60c0f-125">Repita estos pasos para cambiar el tipo de atributo de los siguientes atributos como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="60c0f-125">Repeat these steps to change the attribute type of the attributes as follows:</span></span>  
  
    -   <span data-ttu-id="60c0f-126">**English Month Name** a **Month**</span><span class="sxs-lookup"><span data-stu-id="60c0f-126">**English Month Name** to **Month**</span></span>  
  
    -   <span data-ttu-id="60c0f-127">**Calendar Quarter** a **Quarter**</span><span class="sxs-lookup"><span data-stu-id="60c0f-127">**Calendar Quarter** to **Quarter**</span></span>  
  
    -   <span data-ttu-id="60c0f-128">**Calendar Year** a **Year**</span><span class="sxs-lookup"><span data-stu-id="60c0f-128">**Calendar Year** to **Year**</span></span>  
  
    -   <span data-ttu-id="60c0f-129">**Calendar Semester** a **Half Year**</span><span class="sxs-lookup"><span data-stu-id="60c0f-129">**Calendar Semester** to **Half Year**</span></span>  
  
9. <span data-ttu-id="60c0f-130">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="60c0f-130">Click **Next**.</span></span>  
  
10. <span data-ttu-id="60c0f-131">En la página **Finalización del asistente** , en el panel de vista previa, puede ver la dimensión **Fecha** y sus atributos.</span><span class="sxs-lookup"><span data-stu-id="60c0f-131">On the **Completing the Wizard** page, in the Preview pane, you can see the **Date** dimension and its attributes.</span></span>  
  
11. <span data-ttu-id="60c0f-132">Haga clic en **Finalizar** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="60c0f-132">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="60c0f-133">En el Explorador de soluciones, en el proyecto Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , la dimensión Fecha aparece en la carpeta **Dimensiones** .</span><span class="sxs-lookup"><span data-stu-id="60c0f-133">In Solution Explorer, in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, the Date dimension appears in the **Dimensions** folder.</span></span> <span data-ttu-id="60c0f-134">En el centro del entorno de desarrollo, el Diseñador de dimensiones muestra la dimensión Date.</span><span class="sxs-lookup"><span data-stu-id="60c0f-134">In the center of the development environment, Dimension Designer displays the Date dimension.</span></span>  
  
12. <span data-ttu-id="60c0f-135">En el menú **Archivo**, haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="60c0f-135">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="60c0f-136">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="60c0f-136">Next Task in Lesson</span></span>  
 [<span data-ttu-id="60c0f-137">Definir un cubo</span><span class="sxs-lookup"><span data-stu-id="60c0f-137">Defining a Cube</span></span>](lesson-2-2-defining-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="60c0f-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="60c0f-138">See Also</span></span>  
 <span data-ttu-id="60c0f-139">[Dimensiones en modelos multidimensionales](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="60c0f-139">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="60c0f-140">[Crear una dimensión usando una tabla existente](multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span><span class="sxs-lookup"><span data-stu-id="60c0f-140">[Create a Dimension by Using an Existing Table](multidimensional-models/create-a-dimension-by-using-an-existing-table.md) </span></span>  
 [<span data-ttu-id="60c0f-141">Crear una dimensión usando el Asistente para dimensiones</span><span class="sxs-lookup"><span data-stu-id="60c0f-141">Create a Dimension Using the Dimension Wizard</span></span>](multidimensional-models/create-a-dimension-using-the-dimension-wizard.md)  
  
  
