---
title: Cambiar el nombre de una base de datos multidimensional (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- renaming databases
ms.assetid: 15fdaec7-f3e4-44d9-9b78-1a1d78c484e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3974e7671aff5d1cba22b10563bbc85a129a1dff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674399"
---
# <a name="rename-a-multidimensional-database-analysis-services"></a><span data-ttu-id="4a6ac-102">Cambie el nombre de una base de datos multidimensional (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="4a6ac-102">Rename a Multidimensional Database (Analysis Services)</span></span>
  <span data-ttu-id="4a6ac-103">La manera en la que se cambia el nombre de una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de datos depende de cómo se conecte a la [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="4a6ac-103">The manner in which you change the name of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database depends upon how you connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="4a6ac-104">Para cambiar el nombre de una base de datos existente, debe conectarse en el modo en línea.</span><span class="sxs-lookup"><span data-stu-id="4a6ac-104">To change the name of an existing database, you must connect in online mode.</span></span> <span data-ttu-id="4a6ac-105">Para cambiar el nombre de la base de datos a la que se conectan los objetos de un proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , debe conectarse en el modo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="4a6ac-105">To change the name of the database into which objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project will be instantiated, you must connect in project mode.</span></span>  
  
### <a name="to-change-the-database-name-in-online-mode"></a><span data-ttu-id="4a6ac-106">Para cambiar el nombre de la base de datos en el modo en línea</span><span class="sxs-lookup"><span data-stu-id="4a6ac-106">To change the database name in online mode</span></span>  
  
1.  <span data-ttu-id="4a6ac-107">Con [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], conéctese directamente a la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4a6ac-107">Using [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], connect directly to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="4a6ac-108">En el Explorador de soluciones, haga clic con el botón derecho en la base de datos y, después, haga clic en **Editar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="4a6ac-108">In Solution Explorer, right-click the database and then click **Edit Database**.</span></span>  
  
3.  <span data-ttu-id="4a6ac-109">En el cuadro de texto **Nombre de la base de datos** , cambie el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4a6ac-109">In the **Database name** text box, change the database name.</span></span>  
  
4.  <span data-ttu-id="4a6ac-110">Haga clic en **Guardar** o en **Guardar todo** en la barra de herramientas, haga clic en **Guardar los elementos seleccionados** o en **Guardar todo** en el menú **Archivo** , o cierre el **Diseñador de bases de datos** y, a continuación, haga clic en **Guardar** cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="4a6ac-110">Click **Save** or **Save All** on the toolbar, click **Save Selected Items** or **Save All** on the **File** menu, or close the **Database Designer** and then click **Save** when prompted.</span></span>  
  
     <span data-ttu-id="4a6ac-111">El nombre de la base de datos se actualiza en la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y el objeto de base de datos se actualiza en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="4a6ac-111">The database name is updated in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and the database object in Solution Explorer is refreshed.</span></span>  
  
### <a name="to-change-the-database-name-in-project-mode"></a><span data-ttu-id="4a6ac-112">Para cambiar el nombre de la base de datos en el modo de proyecto</span><span class="sxs-lookup"><span data-stu-id="4a6ac-112">To change the database name in project mode</span></span>  
  
1.  <span data-ttu-id="4a6ac-113">Abra el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4a6ac-113">Open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="4a6ac-114">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y, después, elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4a6ac-114">In Solution Explorer, right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="4a6ac-115">En el cuadro de diálogo **Páginas de propiedades** , haga clic en **Implementación** en la sección **Propiedades de configuración** .</span><span class="sxs-lookup"><span data-stu-id="4a6ac-115">In the **Property Pages** dialog box, click **Deployment** in the **Configuration Properties** section.</span></span>  
  
4.  <span data-ttu-id="4a6ac-116">Cambie la propiedad **Database** al nuevo nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4a6ac-116">Change the **Database** property to the new database name.</span></span>  
  
     <span data-ttu-id="4a6ac-117">La próxima vez que se implemente el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , se hará con este nuevo nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4a6ac-117">The next time the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project is deployed, it will be deployed to this new database name.</span></span> <span data-ttu-id="4a6ac-118">Si esta base de datos ya existe, se sobrescribirá.</span><span class="sxs-lookup"><span data-stu-id="4a6ac-118">If this database already exists, it will be overwritten.</span></span>  
  
### <a name="to-change-the-database-name-using-sql-server-management-studio"></a><span data-ttu-id="4a6ac-119">Para cambiar el nombre de la base de datos con SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="4a6ac-119">To change the database name using SQL Server Management Studio</span></span>  
  
-   <span data-ttu-id="4a6ac-120">Haga clic con el botón derecho en la base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y edite la propiedad Name.</span><span class="sxs-lookup"><span data-stu-id="4a6ac-120">Right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database and edit the Name property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6ac-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a6ac-121">See Also</span></span>  
 <span data-ttu-id="4a6ac-122">[Configurar las propiedades del servidor en Analysis Services](../server-properties/server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="4a6ac-122">[Configure Server Properties in Analysis Services](../server-properties/server-properties-in-analysis-services.md) </span></span>  
 <span data-ttu-id="4a6ac-123">[Establecer propiedades de bases de datos multidimensionales &#40;Analysis Services&#41;](set-multidimensional-database-properties-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="4a6ac-123">[Set Multidimensional Database Properties &#40;Analysis Services&#41;](set-multidimensional-database-properties-analysis-services.md) </span></span>  
 <span data-ttu-id="4a6ac-124">[Configurar las propiedades del proyecto Analysis Services &#40;SSDT&#41;](configure-analysis-services-project-properties-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="4a6ac-124">[Configure Analysis Services Project Properties &#40;SSDT&#41;](configure-analysis-services-project-properties-ssdt.md) </span></span>  
 [<span data-ttu-id="4a6ac-125">Implementar proyectos de Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="4a6ac-125">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](deploy-analysis-services-projects-ssdt.md)  
  
  
