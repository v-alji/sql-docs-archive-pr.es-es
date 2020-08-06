---
title: Importar un proyecto de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3301c328-b0f5-4517-915c-93713413e453
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a98219f3a04d11e086957d64a62e7c64cd51418
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663597"
---
# <a name="import-an-integration-services-project"></a><span data-ttu-id="2eed7-102">Importar un proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="2eed7-102">Import an Integration Services Project</span></span>
  <span data-ttu-id="2eed7-103">Use el **Asistente para importar proyectos** de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para crear un proyecto a partir de un archivo de implementación (.ispac) existente o de un proyecto implementado en el catálogo de Integration Services.</span><span class="sxs-lookup"><span data-stu-id="2eed7-103">Use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]**Import Project Wizard** to create a project from an existing deployment file (.ispac) or from a project deployed to Integration services catalog.</span></span> <span data-ttu-id="2eed7-104">Esta característica resulta especialmente útil si no tiene la copia original del proyecto, pero desea crear uno a partir de un archivo .ispac o un catálogo de SSISDB.</span><span class="sxs-lookup"><span data-stu-id="2eed7-104">This feature is especially useful when you do not have the original copy of the project but you want to create one from an .ispac file or SSISDB catalog.</span></span>  
  
### <a name="to-import-a-project"></a><span data-ttu-id="2eed7-105">Para importar un proyecto</span><span class="sxs-lookup"><span data-stu-id="2eed7-105">To Import a Project</span></span>  
  
1.  <span data-ttu-id="2eed7-106">En [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , haga clic en **nuevo**  >  **proyecto** en el menú **archivo** .</span><span class="sxs-lookup"><span data-stu-id="2eed7-106">In [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], click **New** > **Project** on the **File** menu.</span></span>  
  
2.  <span data-ttu-id="2eed7-107">En el área **Plantillas instaladas** de la ventana **Nuevo proyecto** , expanda **Business Intelligence**y haga clic en **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="2eed7-107">In the **Installed Templates** area of the **New Project** window, expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="2eed7-108">Seleccione **Asistente para importar proyectos de Integration Services** de la lista de tipos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="2eed7-108">Select **Integration Services Import Project Wizard** from the project types list.</span></span>  
  
4.  <span data-ttu-id="2eed7-109">Escriba un nombre para el proyecto que va a crear en el cuadro de texto **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="2eed7-109">Type a name for the new project to be created in the **Name** text box.</span></span>  
  
5.  <span data-ttu-id="2eed7-110">Escriba la ruta de acceso o la ubicación del proyecto en el cuadro de texto **Ubicación** o haga clic en **Examinar** para seleccionar uno.</span><span class="sxs-lookup"><span data-stu-id="2eed7-110">Type the path or location for the project in the **Location** text box, or click **Browse** to select one.</span></span>  
  
6.  <span data-ttu-id="2eed7-111">Escriba un nombre para la solución en el cuadro de texto **Nombre de solución** .</span><span class="sxs-lookup"><span data-stu-id="2eed7-111">Type a name for the solution in the **Solution name** text box.</span></span>  
  
7.  <span data-ttu-id="2eed7-112">Haga clic en **Aceptar** para iniciar el cuadro de diálogo **Asistente para importar proyectos de Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="2eed7-112">Click **OK** to launch the **Integration Services Import Project Wizard** dialog box.</span></span>  
  
8.  <span data-ttu-id="2eed7-113">Haga clic en **Siguiente** para cambiar a la página **Seleccionar origen** .</span><span class="sxs-lookup"><span data-stu-id="2eed7-113">Click **Next** to switch to the **Select Source** page.</span></span>  
  
9. <span data-ttu-id="2eed7-114">Si va a importar desde un archivo **.ispac** , escriba la ruta de acceso con el nombre de archivo incluido en el cuadro de texto **Ruta de acceso** .</span><span class="sxs-lookup"><span data-stu-id="2eed7-114">If you are importing from an **.ispac** file, type the path including file name in the **Path** text box.</span></span> <span data-ttu-id="2eed7-115">Haga clic en **Examinar** para navegar hasta la carpeta donde desea almacenar la solución, escriba el nombre del archivo en el cuadro de texto **Nombre de archivo** y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="2eed7-115">Click **Browse** to navigate to the folder where you want the solution to be stored and type file name in the **File name** text box, and click **Open**.</span></span>  
  
     <span data-ttu-id="2eed7-116">Si está efectuando una importación desde un **Catálogo de Integration Services**, escriba el nombre de la instancia de base de datos en el cuadro de texto **Nombre del servidor** o haga clic en **Examinar** y seleccione la instancia de base de datos que contiene el catálogo.</span><span class="sxs-lookup"><span data-stu-id="2eed7-116">If you are importing from an **Integration Services Catalog**, type the database instance name in the **Server name** text box or click **Browse** and select the database instance that contains the catalog.</span></span>  
  
     <span data-ttu-id="2eed7-117">Haga clic en **Examinar** junto al cuadro de texto **Ruta de acceso** , expanda la carpeta del catálogo, seleccione el proyecto que desea importar y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2eed7-117">Click **Browse** next to **Path** text box, expand folder in the catalog, select the project you want to import, and click **OK**.</span></span>  
  
     <span data-ttu-id="2eed7-118">Haga clic en **Siguiente** para pasar a la página **Revisión** .</span><span class="sxs-lookup"><span data-stu-id="2eed7-118">Click **Next** to switch to the **Review** page.</span></span>  
  
10. <span data-ttu-id="2eed7-119">Revise la información y haga clic en **Importar** para crear un proyecto basado en el proyecto existente que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2eed7-119">Review the information and click **Import** to create a project based on the existing project you selected.</span></span>  
  
11. <span data-ttu-id="2eed7-120">Opcional: haga clic en **Guardar informe** para guardar los resultados en un archivo</span><span class="sxs-lookup"><span data-stu-id="2eed7-120">Optional: click **Save Report** to save the results to a file</span></span>  
  
12. <span data-ttu-id="2eed7-121">Haga clic en **Cerrar** para cerrar el cuadro de diálogo **Asistente para importar proyectos de Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="2eed7-121">Click **Close** to close the **Integration Services Import Project Wizard** dialog box.</span></span>  
  
  
