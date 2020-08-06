---
title: 'Procedimientos: Depuración de ensamblados personalizados | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom assemblies [Reporting Services], debugging
- debugging custom assemblies [Reporting Services]
- troubleshooting [Reporting Services], custom assemblies
ms.assetid: 3a3215b3-548c-4474-81ba-3a98dd3912bf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1b5f9f5a4595d59cce98da4f753422cd07529926
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746790"
---
# <a name="how-to-debug-custom-assemblies"></a><span data-ttu-id="7aadd-102">Procedimientos: Depuración de ensamblados personalizados</span><span class="sxs-lookup"><span data-stu-id="7aadd-102">How to: Debug Custom Assemblies</span></span>
  <span data-ttu-id="7aadd-103">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Proporciona varias herramientas de depuración que pueden ayudarle a analizar el código de ensamblado personalizado y encontrar errores en él.</span><span class="sxs-lookup"><span data-stu-id="7aadd-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your custom assembly code and locate errors in it.</span></span> <span data-ttu-id="7aadd-104">La mejor herramienta para utilizar dependerá de lo que intente llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="7aadd-104">The best tool to use will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="7aadd-105">En este ejemplo se usa [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7aadd-105">This example uses [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span></span>  
  
 <span data-ttu-id="7aadd-106">La manera recomendada de diseñar, desarrollar y probar los ensamblados personalizados para [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] es crear una solución que contenga tanto los informes de prueba como el ensamblado personalizado.</span><span class="sxs-lookup"><span data-stu-id="7aadd-106">The recommended way to design, develop, and test custom assemblies for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is to create a solution that contains both your test reports and your custom assembly.</span></span>  
  
### <a name="to-debug-assemblies-using-a-single-instance-of-visual-studio"></a><span data-ttu-id="7aadd-107">Para depurar ensamblados con una única instancia de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7aadd-107">To debug assemblies using a single instance of Visual Studio</span></span>  
  
1.  <span data-ttu-id="7aadd-108">Cree un nuevo proyecto de informe mediante [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7aadd-108">Create a new report project using [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
     <span data-ttu-id="7aadd-109">Cuando se crea un proyecto de informe, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] también se crea una solución que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="7aadd-109">At the time you create a report project, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] also creates a solution to contain it.</span></span>  
  
2.  <span data-ttu-id="7aadd-110">Agregue un nuevo proyecto de biblioteca de clases a la solución existente.</span><span class="sxs-lookup"><span data-stu-id="7aadd-110">Add a new Class Library project to the existing solution.</span></span> <span data-ttu-id="7aadd-111">Asegúrese de que el proyecto de informe se establece como proyecto de inicio.</span><span class="sxs-lookup"><span data-stu-id="7aadd-111">Make sure that the report project is set as the startup project.</span></span> <span data-ttu-id="7aadd-112">Para obtener más información sobre cómo llevarlo a cabo, vea la documentación de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7aadd-112">For more information about how to accomplish this, see your [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] documentation.</span></span>  
  
3.  <span data-ttu-id="7aadd-113">En el Explorador de soluciones, seleccione la solución.</span><span class="sxs-lookup"><span data-stu-id="7aadd-113">In Solution Explorer, select the solution.</span></span>  
  
4.  <span data-ttu-id="7aadd-114">En el menú **Ver**, haga clic en **Páginas de propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-114">On the **View** menu, click **Property Pages**.</span></span>  
  
     <span data-ttu-id="7aadd-115">Se abre el cuadro de diálogo **Páginas de propiedades de la solución**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-115">The **Solution Property Pages** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="7aadd-116">En el panel izquierdo, expanda **Propiedades comunes** si fuera necesario y haga clic en **Dependencias del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-116">In the left pane, expand **Common Properties** if necessary, and click **Project Dependencies**.</span></span> <span data-ttu-id="7aadd-117">Seleccione el proyecto de informe en la lista desplegable **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-117">Select the report project from the **Project** drop-down list.</span></span> <span data-ttu-id="7aadd-118">Seleccione el proyecto de ensamblado en la lista **Depende de**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-118">Select your assembly project in the **Depends On** list.</span></span>  
  
6.  <span data-ttu-id="7aadd-119">Haga clic en **Aceptar** para guardar los cambios y cierre el cuadro de diálogo **Páginas de propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-119">Click **OK** to save the changes, and close the **Property Pages** dialog.</span></span>  
  
7.  <span data-ttu-id="7aadd-120">En el Explorador de soluciones, seleccione su proyecto de ensamblado personalizado.</span><span class="sxs-lookup"><span data-stu-id="7aadd-120">In Solution Explorer, select your custom assembly project.</span></span>  
  
8.  <span data-ttu-id="7aadd-121">En el menú **Ver**, haga clic en **Páginas de propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-121">On the **View** menu, click **Property Pages**.</span></span>  
  
     <span data-ttu-id="7aadd-122">Se abre el cuadro de diálogo **Páginas de propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-122">The **Project Property Pages** dialog box opens.</span></span>  
  
9. <span data-ttu-id="7aadd-123">Haga clic en la pestaña **Generar** si se encuentra en un proyecto C# o en la pestaña **Compilar** si se encuentra en un proyecto de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7aadd-123">Click the **Build** tab if you're in a C# project or the **Compile** tab if you're in a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] project.</span></span>  
  
10. <span data-ttu-id="7aadd-124">En la **Build** / página**compilar** compilación, escriba la ruta de acceso a la carpeta diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="7aadd-124">On the **Build**/**Compile** page, enter the path to the Report Designer folder.</span></span> <span data-ttu-id="7aadd-125">De forma predeterminada, es C:\Archivos de programa\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE en el cuadro de texto **Ruta de acceso de salida**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-125">By default, this is C:\Program Files\Microsoft SQL Server\100\Tools\Binn\VSShell\Common7\IDE) in the **Output Path** text box.</span></span> <span data-ttu-id="7aadd-126">De esta forma se genera e implementa directamente una versión actualizada del ensamblado personalizado para el Diseñador de informes antes de que se ejecute el informe.</span><span class="sxs-lookup"><span data-stu-id="7aadd-126">This builds and deploys an updated version of your custom assembly directly to Report Designer before your report is executed.</span></span>  
  
11. <span data-ttu-id="7aadd-127">Cuando haya diseñado el informe y desarrollado el ensamblado personalizado, establezca puntos de interrupción en el código de ensamblado personalizado.</span><span class="sxs-lookup"><span data-stu-id="7aadd-127">Once you have designed your report and developed your custom assembly, set breakpoints in your custom assembly code.</span></span>  
  
12. <span data-ttu-id="7aadd-128">Ejecute el informe en el modo **DebugLocal** al presionar tecla F5.</span><span class="sxs-lookup"><span data-stu-id="7aadd-128">Run the report under **DebugLocal** mode by pressing the F5 key.</span></span> <span data-ttu-id="7aadd-129">Cuando el informe se ejecuta en la ventana de la vista previa emergente, el depurador se para en los puntos de interrupción que se corresponden con el código ejecutable del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7aadd-129">When the report executes in the pop-up preview window, the debugger hits any breakpoints that correspond to executable code in your assembly.</span></span> <span data-ttu-id="7aadd-130">Utilice F11 para recorrer el código de ensamblado personalizado.</span><span class="sxs-lookup"><span data-stu-id="7aadd-130">Use F11 to step through your custom assembly code.</span></span>  
  
### <a name="to-debug-assemblies-using-two-instances-of-visual-studio"></a><span data-ttu-id="7aadd-131">Para depurar los ensamblados con dos instancias de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7aadd-131">To debug assemblies using two instances of Visual Studio</span></span>  
  
1.  <span data-ttu-id="7aadd-132">Inicie [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] y abra el proyecto de ensamblado personalizado.</span><span class="sxs-lookup"><span data-stu-id="7aadd-132">Start [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] and open your custom assembly project.</span></span>  
  
2.  <span data-ttu-id="7aadd-133">Genere el proyecto e implemente el ensamblado personalizado y el archivo .pdb acompañante para el Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="7aadd-133">Build the project, and deploy your custom assembly and the accompanying .pdb file to the Report Designer.</span></span> <span data-ttu-id="7aadd-134">Para más información sobre la implementación, vea [Implementar un ensamblado personalizado](deploying-a-custom-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="7aadd-134">For more information about deployment, see [Deploying a Custom Assembly](deploying-a-custom-assembly.md).</span></span>  
  
3.  <span data-ttu-id="7aadd-135">Abra un proyecto de informe que use el ensamblado personalizado mientras deja el código de ensamblado personalizado abierto en una instancia independiente de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7aadd-135">Open up a report project that uses your custom assembly while leaving your custom assembly code open in a separate instance of [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
4.  <span data-ttu-id="7aadd-136">Navegue a la instancia de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] que contiene el proyecto de ensamblado personalizado y establezca algunos puntos de interrupción en el código.</span><span class="sxs-lookup"><span data-stu-id="7aadd-136">Navigate to the instance of [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] that contains your custom assembly project and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="7aadd-137">Con el proyecto de ensamblado personalizado aún en la ventana activa, haga clic en **Asociar al proceso** en el menú **Depurar**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-137">With the custom assembly project still the active window, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="7aadd-138">Se abre el cuadro de diálogo **Asociar al proceso**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-138">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="7aadd-139">En la lista de procesos, seleccione el proceso devenv.exe que corresponda al proyecto de informe y haga clic en **Asociar**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-139">From the list of processes, select the devenv.exe process that corresponds to your Report Project and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="7aadd-140">Defina las expresiones que utilizará en el informe desde su ensamblado personalizado y diseñe el informe.</span><span class="sxs-lookup"><span data-stu-id="7aadd-140">Define the expressions that you will use in your report from your custom assembly and design your report.</span></span>  
  
8.  <span data-ttu-id="7aadd-141">Cuando termine de diseñar el informe, haga clic en la pestaña **Vista previa**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-141">When you are finished designing your report, click the **Preview** tab.</span></span>  
  
     <span data-ttu-id="7aadd-142">El informe se ejecuta y el código de ensamblado personalizado debería detenerse en los puntos de interrupción predefinidos.</span><span class="sxs-lookup"><span data-stu-id="7aadd-142">The report executes, and the custom assembly code should break at your predefined break points.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7aadd-143">El uso de la pestaña **Vista previa** no exige permisos de código para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7aadd-143">Using the **Preview** tab does not enforce code permissions for the assembly.</span></span> <span data-ttu-id="7aadd-144">Para realizar una prueba completa que incluya algún error de seguridad de acceso del código, inicie el proyecto de informe con la opción de configuración **DebugLocal**.</span><span class="sxs-lookup"><span data-stu-id="7aadd-144">For a complete test, which includes any code access security errors, start the report project under the **DebugLocal** configuration setting.</span></span>  
  
9. <span data-ttu-id="7aadd-145">Recorra el código con la tecla F11.</span><span class="sxs-lookup"><span data-stu-id="7aadd-145">Step through your code using the F11 key.</span></span> <span data-ttu-id="7aadd-146">Para obtener más información acerca de cómo depurar con [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], vea la documentación de [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7aadd-146">For more information about debugging using [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], see the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aadd-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7aadd-147">See Also</span></span>  
 [<span data-ttu-id="7aadd-148">Usar ensamblados personalizados con informes</span><span class="sxs-lookup"><span data-stu-id="7aadd-148">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
