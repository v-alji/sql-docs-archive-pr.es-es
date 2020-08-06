---
title: Crear un nuevo proyecto de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Integration Services], creating
- Integration Services projects, creating
- SQL Server Integration Services projects, creating
- SSIS projects, creating
ms.assetid: 1e23f259-0401-4333-ab4f-89809aae63b1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f62d3ac2d33bb51a0ccc3b77d9f8b5ec0f52b345
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671615"
---
# <a name="create-a-new-integration-services-project"></a><span data-ttu-id="423c0-102">Crear un proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="423c0-102">Create a New Integration Services Project</span></span>
  <span data-ttu-id="423c0-103">Este procedimiento crea un nuevo proyecto y una nueva solución de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="423c0-103">This procedure creates a new project and a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] solution.</span></span>  
  
### <a name="to-create-a-new-integration-services-project"></a><span data-ttu-id="423c0-104">Para crear un proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="423c0-104">To create a new Integration Services project</span></span>  
  
1.  <span data-ttu-id="423c0-105">Abra [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="423c0-105">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="423c0-106">En el menú **Archivo** , elija **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="423c0-106">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="423c0-107">En el cuadro de diálogo **Nuevo proyecto** , en el panel **Plantillas** , seleccione la plantilla **Proyecto de Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="423c0-107">In the **New Project** dialog box, in the **Templates** pane, select the **Integration Services Project** template.</span></span>  
  
     <span data-ttu-id="423c0-108">La plantilla **Proyecto de Integration Services** crea un proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene un único paquete vacío.</span><span class="sxs-lookup"><span data-stu-id="423c0-108">The **Integration Services Project** template creates an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains a single, empty package.</span></span>  
  
4.  <span data-ttu-id="423c0-109">Si lo desea, modifique el nombre y la ubicación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="423c0-109">(Optional) Edit the project name and the location.</span></span>  
  
     <span data-ttu-id="423c0-110">El nombre de la solución se actualiza automáticamente para que coincida con el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="423c0-110">The solution name is automatically updated to match the project name.</span></span>  
  
5.  <span data-ttu-id="423c0-111">Para crear una carpeta diferente para el archivo de solución, seleccione **Crear directorio para la solución**.</span><span class="sxs-lookup"><span data-stu-id="423c0-111">To create a separate folder for the solution file, select **Create directory for solution**.</span></span> <span data-ttu-id="423c0-112">Ésta es la opción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="423c0-112">This is the default option.</span></span>  
  
6.  <span data-ttu-id="423c0-113">Si en el equipo hay instalado software de control de código fuente, seleccione **Agregar al control de código fuente**  para asociar el proyecto con el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="423c0-113">If source control software is installed on the computer, select **Add to source control**  to associate the project with source control.</span></span>  
  
7.  <span data-ttu-id="423c0-114">Si el software de control de código fuente es [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, se abre el cuadro de diálogo **Inicio de sesión en Visual SourceSafe** .</span><span class="sxs-lookup"><span data-stu-id="423c0-114">If the source control software is [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, the **Visual SourceSafe Login** dialog box opens.</span></span> <span data-ttu-id="423c0-115">En **Inicio de sesión en Visual SourceSafe**, proporcione un nombre de usuario, una contraseña y el nombre de la base de datos de [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="423c0-115">In **Visual SourceSafe Login**, provide a user name, a password, and the name of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database.</span></span> <span data-ttu-id="423c0-116">Haga clic en **Examinar** para buscar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="423c0-116">Click **Browse** to locate the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="423c0-117">Para ver y cambiar el complemento de control de código fuente seleccionado y para configurar el entorno de control de código fuente, haga clic en **Opciones** en el menú **Herramientas** y, después, expanda el nodo **Control de código fuente**.</span><span class="sxs-lookup"><span data-stu-id="423c0-117">To view and change the selected source control plug-in and to configure the source control environment, click **Options** on the **Tools** menu, and then expand the **Source Control** node.</span></span>  
  
8.  <span data-ttu-id="423c0-118">Haga clic en **Aceptar** para agregar la solución a la solución **explorar**r y agregar el proyecto a la solución.</span><span class="sxs-lookup"><span data-stu-id="423c0-118">Click **OK** to add the solution to **Solution Explore**r and add the project to the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="423c0-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="423c0-119">See Also</span></span>  
 <span data-ttu-id="423c0-120">[Integration Services &#40;proyectos&#41; de SSIS](integration-services-ssis-projects-and-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="423c0-120">[Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md) </span></span>  
 [<span data-ttu-id="423c0-121">Agregar o quitar un proyecto de Integration Services en una solución</span><span class="sxs-lookup"><span data-stu-id="423c0-121">Add or Remove an Integration Services Project in a Solution</span></span>](../../2014/integration-services/add-or-remove-an-integration-services-project-in-a-solution.md)  
  
  
