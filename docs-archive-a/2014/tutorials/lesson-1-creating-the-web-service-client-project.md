---
title: 'Lección 1: crear el proyecto de cliente de servicio Web | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0070daa6-56b0-4663-83b2-44c96acafad8
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: eda9413867c4ca6d44a5cf98b82be9bddc04d0f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747313"
---
# <a name="lesson-1-creating-the-web-service-client-project"></a><span data-ttu-id="ce5e4-102">Lección 1: Creación del proyecto cliente del servicio web</span><span class="sxs-lookup"><span data-stu-id="ce5e4-102">Lesson 1: Creating the Web Service Client Project</span></span>
  <span data-ttu-id="ce5e4-103">Para esta visita guiada, creará una aplicación de consola sencilla con acceso al servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="ce5e4-103">For this walkthrough, you will create a simple console application that accesses the Report Server Web service.</span></span> <span data-ttu-id="ce5e4-104">En este tutorial se da por supuesto que la programación se realiza con [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce5e4-104">This walkthrough assumes you are developing in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
### <a name="to-create-a-console-application"></a><span data-ttu-id="ce5e4-105">Crear una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="ce5e4-105">To create a console application</span></span>  
  
1.  <span data-ttu-id="ce5e4-106">En el menú **archivo** , seleccione **nuevo**y, a continuación, haga clic en **proyecto** para abrir el cuadro de diálogo **nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="ce5e4-106">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="ce5e4-107">En el panel izquierdo, en **plantillas instaladas**, haga clic en **Visual Basic** o en el nodo **Visual C#** y seleccione una categoría de tipos de proyecto en la lista expandida.</span><span class="sxs-lookup"><span data-stu-id="ce5e4-107">In the left pane, under **Installed Templates**, click either **Visual Basic** or the **Visual C#** node, and select a category of project types from the expanded list.</span></span>  
  
3.  <span data-ttu-id="ce5e4-108">Elija el tipo de proyecto **aplicación de consola** .</span><span class="sxs-lookup"><span data-stu-id="ce5e4-108">Choose the **Console Application** project type.</span></span>  
  
4.  <span data-ttu-id="ce5e4-109">En el cuadro **nombre** , escriba un nombre para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ce5e4-109">In the **Name** box, enter a name for your project.</span></span> <span data-ttu-id="ce5e4-110">Escriba el nombre `GetPropertiesSample` .</span><span class="sxs-lookup"><span data-stu-id="ce5e4-110">Type the name `GetPropertiesSample`.</span></span>  
  
5.  <span data-ttu-id="ce5e4-111">En el cuadro **Ubicación** , escriba la ruta de acceso donde desea guardar el proyecto o haga clic en **examinar** para navegar hasta la carpeta.</span><span class="sxs-lookup"><span data-stu-id="ce5e4-111">In the **Location** box, enter the path where you want to save your project, or click **Browse** to navigate to the folder.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="ce5e4-112">En Explorador de soluciones se muestra una vista contraída del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ce5e4-112">A collapsed view of your project appears in Solution Explorer.</span></span>  
  
     <span data-ttu-id="ce5e4-113">Expanda el nodo del proyecto en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="ce5e4-113">In Solution Explorer, expand the project node.</span></span> <span data-ttu-id="ce5e4-114">Se ha agregado al proyecto un archivo con el nombre predeterminado Program.cs (Module1. VB para [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="ce5e4-114">A file with the default name of Program.cs (Module1.vb for [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) has been added to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce5e4-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce5e4-115">See Also</span></span>  
 <span data-ttu-id="ce5e4-116">[Lección 2: agregar una referencia Web](../../2014/tutorials/lesson-2-adding-a-web-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ce5e4-116">[Lesson 2: Adding a Web Reference](../../2014/tutorials/lesson-2-adding-a-web-reference.md) </span></span>  
 [<span data-ttu-id="ce5e4-117">Obtener acceso al servicio Web del servidor de informes mediante el tutorial de Visual Basic o Visual C&#35; &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ce5e4-117">Accessing the Report Server Web Service Using Visual Basic or Visual C&#35; &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/access-report-server-web-service-vb-vcsharp-ssrs-tutorial.md)  
  
  
