---
title: 'Paso 2: Crear el proyecto de implementación | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 59990fe2-7036-4e9c-8efc-6ece9e66eda7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ebfce8796f98628c2832c5ab7f4be665c7915d10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673135"
---
# <a name="step-2-creating-the-deployment-project"></a><span data-ttu-id="e9457-102">Paso 2: Creación del proyecto de implementación</span><span class="sxs-lookup"><span data-stu-id="e9457-102">Step 2: Creating the Deployment Project</span></span>
  <span data-ttu-id="e9457-103">En [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], la unidad que se puede implementar es un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9457-103">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the deployable unit is an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span> <span data-ttu-id="e9457-104">Antes de que pueda implementar paquetes, debe crear un nuevo proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] y agregar todos los paquetes y archivos auxiliares que desee implementar con los paquetes en ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="e9457-104">Before you can deploy packages, you must create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and add all the packages and any ancillary files that you want to deploy with the packages to that project.</span></span>  
  
### <a name="to-create-the-integration-services-project"></a><span data-ttu-id="e9457-105">Para crear el proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="e9457-105">To create the Integration Services project</span></span>  
  
1.  <span data-ttu-id="e9457-106">Haga clic en **Inicio**, seleccione **Todos los programas**, **Microsoft SQL Server**y, después, haga clic en **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="e9457-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **SQL ServerSQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="e9457-107">En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto** para crear un proyecto nuevo de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9457-107">On the **File** menu, point to **New**, and then click **Project** to create a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
3.  <span data-ttu-id="e9457-108">En el cuadro de diálogo **Nuevo proyecto** , seleccione **Proyecto de Integration Services** en el panel **Plantillas** .</span><span class="sxs-lookup"><span data-stu-id="e9457-108">In the **New Project** dialog box, select **Integration Services Project** in the **Templates** pane.</span></span>  
  
4.  <span data-ttu-id="e9457-109">En el cuadro **Nombre** , cambie el nombre predeterminado por **Deployment Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="e9457-109">In the **Name** box, change the default name to **Deployment Tutorial**.</span></span> <span data-ttu-id="e9457-110">Opcionalmente, desactive la casilla **Crear directorio para la solución** .</span><span class="sxs-lookup"><span data-stu-id="e9457-110">Optionally, clear the **Create directory for solution** check box.</span></span>  
  
5.  <span data-ttu-id="e9457-111">Acepte la ubicación predeterminada o haga clic en **Examinar** para buscar la carpeta que quiere usar.</span><span class="sxs-lookup"><span data-stu-id="e9457-111">Accept the default location, or click **Browse** to locate the folder you want to use.</span></span>  
  
6.  <span data-ttu-id="e9457-112">En el cuadro de diálogo **Ubicación del proyecto** , haga clic en la carpeta y, después, en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e9457-112">In the **Project Location** dialog box, click the folder, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="e9457-113">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9457-113">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="e9457-114">De forma predeterminada, se crea un paquete vacío, denominado Package.dtsx, que se agrega al nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="e9457-114">By default, an empty package, named Package.dtsx, is created and added to your project.</span></span> <span data-ttu-id="e9457-115">Sin embargo, no utilizará este paquete; en su lugar, agregará paquetes existentes al proyecto.</span><span class="sxs-lookup"><span data-stu-id="e9457-115">However, you will not use this package; instead, you will add existing packages to the project.</span></span> <span data-ttu-id="e9457-116">Puesto que todos los paquetes de un proyecto se incluirán en la implementación, deber eliminar Package.dtsx.</span><span class="sxs-lookup"><span data-stu-id="e9457-116">Because all the packages in a project will be included in the deployment, you should delete Package.dtsx.</span></span> <span data-ttu-id="e9457-117">Para eliminarlo, haga clic con el botón derecho en el paquete y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e9457-117">To delete it, right-click it, and then click **Delete**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e9457-118">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="e9457-118">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e9457-119">Paso 3: Agregar paquetes y otros archivos</span><span class="sxs-lookup"><span data-stu-id="e9457-119">Step 3: Adding Packages and Other Files</span></span>](../integration-services/lesson-1-3-adding-packages-and-other-files.md)  
  
<span data-ttu-id="e9457-120">![Integration Services icono (pequeño)](media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="e9457-120">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e9457-121">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="e9457-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e9457-122">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="e9457-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e9457-123">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="e9457-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9457-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9457-124">See Also</span></span>  
 [<span data-ttu-id="e9457-125">Proyectos de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e9457-125">Integration Services &#40;SSIS&#41; Projects</span></span>](integration-services-ssis-projects-and-solutions.md)  
  
  
