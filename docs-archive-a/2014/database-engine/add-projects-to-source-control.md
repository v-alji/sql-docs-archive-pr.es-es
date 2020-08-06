---
title: Agregar proyectos al control de código fuente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- adding projects
- projects [SQL Server Management Studio], adding
ms.assetid: fd4616b2-a564-4a66-ac53-d1f5cba213c2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0afef4ef91e4d80db7e956d03a95a2ecffe1dc4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669838"
---
# <a name="add-projects-to-source-control"></a><span data-ttu-id="bdeed-102">Agregar proyectos al control de código fuente</span><span class="sxs-lookup"><span data-stu-id="bdeed-102">Add Projects to Source Control</span></span>
  <span data-ttu-id="bdeed-103">Las soluciones de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pueden contener varios proyectos de script.</span><span class="sxs-lookup"><span data-stu-id="bdeed-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] solutions can host multiple script projects.</span></span> <span data-ttu-id="bdeed-104">El modo en que se agregue un proyecto al control de código fuente depende de si la solución a la que pertenece el proyecto está bajo control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="bdeed-104">How you add a project to source control depends upon whether the solution to which the project belongs is under source control.</span></span> <span data-ttu-id="bdeed-105">Si la solución está bajo control de código fuente, al protegerla, se agrega automáticamente el proyecto al control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="bdeed-105">If the solution is under source control, checking in the solution automatically adds the project to source control.</span></span> <span data-ttu-id="bdeed-106">Para obtener más información acerca de la protección de soluciones, consulte [proteger archivos](../../2014/database-engine/check-in-files.md).</span><span class="sxs-lookup"><span data-stu-id="bdeed-106">For more information about checking in solutions, see [Check In Files](../../2014/database-engine/check-in-files.md).</span></span>  
  
 <span data-ttu-id="bdeed-107">Si la solución a la que pertenece el proyecto no está bajo control de código fuente, puede agregarla, con lo que se agregan automáticamente los proyectos de esa solución.</span><span class="sxs-lookup"><span data-stu-id="bdeed-107">If the solution that this project belongs to is not under source control, you can add that solution to source control, which then automatically adds the solution's projects.</span></span> <span data-ttu-id="bdeed-108">Para obtener más información sobre cómo agregar soluciones al control de código fuente, vea [Agregar soluciones al control de código fuente](../../2014/database-engine/add-solutions-to-source-control.md).</span><span class="sxs-lookup"><span data-stu-id="bdeed-108">For more information about adding solutions to source control, see [Add Solutions to Source Control](../../2014/database-engine/add-solutions-to-source-control.md).</span></span>  
  
 <span data-ttu-id="bdeed-109">Si no desea agregar la solución al control de código fuente, puede usar el comando **Agregar selección a control de código fuente** para agregar el proyecto manualmente.</span><span class="sxs-lookup"><span data-stu-id="bdeed-109">If you do not want to add the solution to source control, you can use the **Add Selection to Source Control** command to add the project manually.</span></span>  
  
 <span data-ttu-id="bdeed-110">El proveedor del control de código fuente no protege directamente los objetos de base de datos, pero puede crear scripts de los objetos de base de datos y guardarlos bajo el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="bdeed-110">Database objects are not directly protected by the source control provider, but you can create scripts of database objects and save the scripts under source control.</span></span>  
  
### <a name="to-add-a-project-to-source-control"></a><span data-ttu-id="bdeed-111">Para agregar un proyecto al control de código fuente</span><span class="sxs-lookup"><span data-stu-id="bdeed-111">To add a project to source control</span></span>  
  
1.  <span data-ttu-id="bdeed-112">En el Explorador de soluciones, seleccione un proyecto.</span><span class="sxs-lookup"><span data-stu-id="bdeed-112">In Solution Explorer, select a project.</span></span>  
  
2.  <span data-ttu-id="bdeed-113">En el menú **archivo** , seleccione **control de código fuente**y, a continuación, haga clic en **Agregar proyectos seleccionados al control de código fuente**.</span><span class="sxs-lookup"><span data-stu-id="bdeed-113">On the **File** menu, point to **Source Control**, and then click **Add Selected Projects to Source Control**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bdeed-114">Si usa el comando **Agregar proyectos seleccionados al control de código fuente** para agregar un proyecto que pertenece a una solución controlada por código fuente, se le preguntará si desea agregar el proyecto como una subcarpeta de la solución controlada por código fuente o agregar el proyecto como una carpeta independiente.</span><span class="sxs-lookup"><span data-stu-id="bdeed-114">If you use the **Add Selected Projects to Source Control** command to add a project that belongs to a source-controlled solution, you are prompted whether you want to add the project as a subfolder of the source-controlled solution or to add the project as a separate folder.</span></span>  
  
3.  <span data-ttu-id="bdeed-115">Si se le pide, inicie sesión en el proveedor de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="bdeed-115">If prompted, log on to your source control provider.</span></span>  
  
4.  <span data-ttu-id="bdeed-116">Aparecerá el cuadro de diálogo **Agregar a proyecto de SourceSafe** .</span><span class="sxs-lookup"><span data-stu-id="bdeed-116">The **Add to SourceSafe Project** dialog box appears.</span></span> <span data-ttu-id="bdeed-117">El nombre del proyecto aparece en el cuadro **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="bdeed-117">The name of your project appears in the **Project** box.</span></span>  
  
5.  <span data-ttu-id="bdeed-118">En la lista **carpetas** , abra la carpeta en la que desea colocar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="bdeed-118">In the **Folders** list, open the folder where you want to place your project.</span></span> <span data-ttu-id="bdeed-119">Como alternativa, puede hacer clic en **crear** para crear una carpeta con el nombre que se muestra en el cuadro **proyecto** .</span><span class="sxs-lookup"><span data-stu-id="bdeed-119">Alternatively, you can click **Create** to create a folder with the name displayed in the **Project** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdeed-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bdeed-120">See Also</span></span>  
 [<span data-ttu-id="bdeed-121">Agregar soluciones y proyectos al control de código fuente</span><span class="sxs-lookup"><span data-stu-id="bdeed-121">Add Solutions and Projects to Source Control</span></span>](../../2014/database-engine/add-solutions-and-projects-to-source-control.md)  
  
  
