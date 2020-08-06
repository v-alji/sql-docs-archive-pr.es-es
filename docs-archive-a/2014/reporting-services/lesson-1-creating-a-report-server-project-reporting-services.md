---
title: 'Lección 1: Crear un proyecto de servidor de informes (Reporting Services) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 675671ca-e6c9-48a2-82e9-386778f3a49f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a708e5114344e87edd620ef58bc50594a9b9ef8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751813"
---
# <a name="lesson-1-creating-a-report-server-project-reporting-services"></a><span data-ttu-id="ab182-102">Lección 1: Crear un proyecto de servidor de informes (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="ab182-102">Lesson 1: Creating a Report Server Project (Reporting Services)</span></span>
  <span data-ttu-id="ab182-103">Para crear un informe en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], primero debe crear un proyecto de servidor de informes donde guardará el archivo de definición de informe (.rdl) y cualquier otro archivo de recursos que necesite para el informe.</span><span class="sxs-lookup"><span data-stu-id="ab182-103">To create a report in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you must first create a report server project where you will save your report definition (.rdl) file and any other resource files that you need for your report.</span></span> <span data-ttu-id="ab182-104">Luego creará el archivo de definición de informe real, definirá un origen de datos para el informe, definirá un conjunto de datos y establecerá el diseño del informe.</span><span class="sxs-lookup"><span data-stu-id="ab182-104">Then you will create the actual report definition file, define a data source for your report, define a dataset, and define the report layout.</span></span> <span data-ttu-id="ab182-105">Cuando ejecuta el informe, los datos reales se recuperan y combinan con el diseño y luego se representan en pantalla, desde donde se pueden exportar, imprimir o guardar.</span><span class="sxs-lookup"><span data-stu-id="ab182-105">When you run the report, the actual data is retrieved and combined with the layout, and then rendered on your screen, from where you can export it, print it, or save it.</span></span>  
  
 <span data-ttu-id="ab182-106">En esta lección aprenderá a crear un proyecto de servidor de informes en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab182-106">In this lesson, you will learn how to create a report server project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="ab182-107">Los proyectos de servidor de informes sirven para crear informes que se ejecutan en servidores de informes.</span><span class="sxs-lookup"><span data-stu-id="ab182-107">A report server project is used to create reports that run on a report server.</span></span>  
  
### <a name="to-create-a-report-server-project"></a><span data-ttu-id="ab182-108">Para crear un proyecto de servidor de informes</span><span class="sxs-lookup"><span data-stu-id="ab182-108">To create a report server project</span></span>  
  
1.  <span data-ttu-id="ab182-109">Haga clic en **Inicio**, seleccione **todos los programas**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] y, a continuación, haga clic en **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="ab182-109">Click **Start**, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)], and then click **SQL Server Data Tools**.</span></span> <span data-ttu-id="ab182-110">Si es la primera vez que se abre [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , haga clic en **configuración de Business Intelligence** para la configuración predeterminada del entorno.</span><span class="sxs-lookup"><span data-stu-id="ab182-110">If this is the first time you have opened [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Business Intelligence Settings** for the default environment settings.</span></span>  
  
2.  <span data-ttu-id="ab182-111">En el menú **Archivo** , elija **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="ab182-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="ab182-112">En la lista **Plantillas instaladas** , haga clic en **Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="ab182-112">In the **Installed Templates** list, click **Business Intelligence**.</span></span>  
  
4.  <span data-ttu-id="ab182-113">Haga clic en **proyecto de servidor de informes**.</span><span class="sxs-lookup"><span data-stu-id="ab182-113">Click **Report Server Project**.</span></span>  
  
5.  <span data-ttu-id="ab182-114">En **nombre**, escriba **tutorial**.</span><span class="sxs-lookup"><span data-stu-id="ab182-114">In **Name**, type **Tutorial**.</span></span>  
  
6.  <span data-ttu-id="ab182-115">Haga clic en **Aceptar** para crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ab182-115">Click **OK** to create the project.</span></span>  
  
     <span data-ttu-id="ab182-116">El proyecto Tutorial se muestra en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="ab182-116">The Tutorial project is displayed in Solution Explorer.</span></span>  
  
### <a name="to-create-a-new-report-definition-file"></a><span data-ttu-id="ab182-117">Para crear un nuevo archivo de definición de informe</span><span class="sxs-lookup"><span data-stu-id="ab182-117">To create a new report definition file</span></span>  
  
1.  <span data-ttu-id="ab182-118">En Explorador de soluciones, haga clic con el botón secundario en **informes**, seleccione **Agregar**y haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="ab182-118">In Solution Explorer, right-click **Reports**, point to **Add**, and click **New Item**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ab182-119">Si la ventana **Explorador de soluciones** no está visible, en el menú **Ver** , haga clic en **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="ab182-119">If the **Solution Explorer** window is not visible, from the **View** menu, click **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="ab182-120">En el cuadro de diálogo **Agregar nuevo elemento** , en **plantillas**, haga clic en **Informe**.</span><span class="sxs-lookup"><span data-stu-id="ab182-120">In the **Add New Item** dialog box, under **Templates**, click **Report**.</span></span>  
  
3.  <span data-ttu-id="ab182-121">En **Nombre**, escriba **Sales Orders.rdl** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ab182-121">In **Name**, type **Sales Orders.rdl** and then click **Add**.</span></span>  
  
     <span data-ttu-id="ab182-122">Se abrirá el Diseñador de informes y se mostrará el nuevo archivo .rdl en la vista Diseño.</span><span class="sxs-lookup"><span data-stu-id="ab182-122">Report Designer opens and displays the new .rdl file in Design view.</span></span>  
  
 <span data-ttu-id="ab182-123">El Diseñador de informes es un componente de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] que se ejecuta en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab182-123">Report Designer is a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] component that runs in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="ab182-124">Tiene dos vistas: **Diseño** y **Vista previa**.</span><span class="sxs-lookup"><span data-stu-id="ab182-124">It has two views: **Design** and **Preview**.</span></span> <span data-ttu-id="ab182-125">Haga clic en cada pestaña para cambiar las vistas.</span><span class="sxs-lookup"><span data-stu-id="ab182-125">Click each tab to change views.</span></span>  
  
 <span data-ttu-id="ab182-126">Los datos se definen en el panel **Datos de informe** .</span><span class="sxs-lookup"><span data-stu-id="ab182-126">You define your data in the **Report Data** pane.</span></span> <span data-ttu-id="ab182-127">El diseño del informe se define en la vista **Diseño** .</span><span class="sxs-lookup"><span data-stu-id="ab182-127">You define your report layout in **Design** view.</span></span> <span data-ttu-id="ab182-128">Puede ejecutar el informe y ver su aspecto en la vista **Vista previa** .</span><span class="sxs-lookup"><span data-stu-id="ab182-128">You can run the report and see what it looks like in **Preview** view.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="ab182-129">Tarea siguiente</span><span class="sxs-lookup"><span data-stu-id="ab182-129">Next Task</span></span>  
 <span data-ttu-id="ab182-130">Ha creado un proyecto de informe denominado "Tutorial" y ha agregado un archivo de definición de informe (.rdl) al proyecto del informe correctamente.</span><span class="sxs-lookup"><span data-stu-id="ab182-130">You have successfully created a report project called "Tutorial" and added a report definition (.rdl) file to the report project.</span></span> <span data-ttu-id="ab182-131">A continuación, debe especificar un origen de datos para utilizarlo con el informe.</span><span class="sxs-lookup"><span data-stu-id="ab182-131">Next, you will specify a data source to use for the report.</span></span> <span data-ttu-id="ab182-132">Vea [Lección 2: Especificar información de conexión &#40;Reporting Services&#41;](lesson-2-specifying-connection-information-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="ab182-132">See [Lesson 2: Specifying Connection Information &#40;Reporting Services&#41;](lesson-2-specifying-connection-information-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab182-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab182-133">See Also</span></span>  
 [<span data-ttu-id="ab182-134">Crear un informe de tabla básico &#40;Tutorial de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ab182-134">Create a Basic Table Report &#40;SSRS Tutorial&#41;</span></span>](create-a-basic-table-report-ssrs-tutorial.md)  
  
  
