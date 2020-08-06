---
title: Agregar nuevos elementos a un proyecto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], item additions
- adding project items
ms.assetid: 76af8692-324f-4f5e-b1a0-d72ca8a107e3
author: stevestein
ms.author: sstein
ms.openlocfilehash: c73c58952c7801b3a0e2c86652feb461292cf37c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677323"
---
# <a name="add-new-items-to-a-project"></a><span data-ttu-id="b138e-102">Agregar nuevos elementos a un proyecto</span><span class="sxs-lookup"><span data-stu-id="b138e-102">Add New Items to a Project</span></span>
  <span data-ttu-id="b138e-103">Agregue elementos nuevos a un proyecto para ampliar la funcionalidad de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b138e-103">Add new items to a project to extend application functionality.</span></span> <span data-ttu-id="b138e-104">Un elemento nuevo puede ser una consulta o una conexión.</span><span class="sxs-lookup"><span data-stu-id="b138e-104">A new item can be a query or a connection.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="b138e-105">tiene dos tipos de proyectos: proyecto de script de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y proyecto de script de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="b138e-105">has two project types: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script Project, and Analysis Services Script Project.</span></span> <span data-ttu-id="b138e-106">El tipo de proyecto determina los elementos que se pueden agregar al proyecto.</span><span class="sxs-lookup"><span data-stu-id="b138e-106">The project type determines the items that you can add to the project.</span></span> <span data-ttu-id="b138e-107">Por ejemplo, se puede agregar una consulta [!INCLUDE[tsql](../../includes/tsql-md.md)] (un archivo con una extensión .sql) a un proyecto de script de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , pero no a un proyecto de script de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="b138e-107">For example, you can add a [!INCLUDE[tsql](../../includes/tsql-md.md)] query (a file with a .sql extension) to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script project, but you cannot add it to an Analysis Services Script Project.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="b138e-108">no permite crear carpetas dentro de los proyectos.</span><span class="sxs-lookup"><span data-stu-id="b138e-108">does not allow you to create folders within projects.</span></span> <span data-ttu-id="b138e-109">Para organizar el trabajo, cree varios proyectos dentro de la solución.</span><span class="sxs-lookup"><span data-stu-id="b138e-109">To organize your work, create multiple projects within the solution.</span></span>  
  
### <a name="to-add-a-new-query-to-an-existing-project"></a><span data-ttu-id="b138e-110">Para agregar una consulta nueva a un proyecto existente</span><span class="sxs-lookup"><span data-stu-id="b138e-110">To add a new query to an existing project</span></span>  
  
1.  <span data-ttu-id="b138e-111">En el Explorador de soluciones, seleccione el proyecto de destino.</span><span class="sxs-lookup"><span data-stu-id="b138e-111">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="b138e-112">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b138e-112">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="b138e-113">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione una categoría en el panel de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="b138e-113">In the **Add New Item** dialog box, select a category in the left pane.</span></span>  
  
4.  <span data-ttu-id="b138e-114">Seleccione una plantilla de consulta en el panel de la derecha y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b138e-114">Select a query template in the right pane, and then click **Add**.</span></span> <span data-ttu-id="b138e-115">La consulta nueva se agrega a la carpeta **Consultas** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b138e-115">The new query is added in the **Queries** folder of the project.</span></span>  
  
5.  <span data-ttu-id="b138e-116">En el cuadro de diálogo **Conectar al motor de base de datos** , especifique una conexión para la consulta nueva y haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="b138e-116">In the **Connect to Database Engine** dialog box, specify a connection for the new query, and then click **Connect**.</span></span> <span data-ttu-id="b138e-117">Si no desea asociar una conexión a la consulta nueva, puede hacer clic en **Cancelar** en el cuadro de diálogo de conexión.</span><span class="sxs-lookup"><span data-stu-id="b138e-117">You can click **Cancel** on the connection dialog if you do not want to associate a connection to the new query.</span></span>  
  
6.  <span data-ttu-id="b138e-118">Si lo desea, cambie el nombre de la consulta en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="b138e-118">Rename the query in Solution Explorer if you wish.</span></span>  
  
### <a name="to-add-a-new-connection-to-an-existing-project"></a><span data-ttu-id="b138e-119">Para agregar una conexión nueva a un proyecto existente</span><span class="sxs-lookup"><span data-stu-id="b138e-119">To add a new connection to an existing project</span></span>  
  
1.  <span data-ttu-id="b138e-120">En el Explorador de soluciones, seleccione el proyecto de destino.</span><span class="sxs-lookup"><span data-stu-id="b138e-120">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="b138e-121">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="b138e-121">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="b138e-122">Seleccione **Conexión** en el panel de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="b138e-122">Select **Connection** in the left pane.</span></span>  
  
4.  <span data-ttu-id="b138e-123">Seleccione **Nueva conexión** en el panel de la derecha y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b138e-123">Select **New Connection** in the right pane, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="b138e-124">En el cuadro de diálogo **Conectar al motor de base de datos** , especifique una conexión para la consulta nueva y haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="b138e-124">In the **Connect to Database Engine** dialog box, specify a connection for the new query, and then click **Connect**.</span></span> <span data-ttu-id="b138e-125">La conexión nueva se agrega a la carpeta **Conexiones** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b138e-125">The new connection gets added in the **Connections** folder of the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b138e-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b138e-126">See Also</span></span>  
 <span data-ttu-id="b138e-127">[Explorador de soluciones](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="b138e-127">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="b138e-128">[Asociar extensiones de archivo a un editor de código](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md) </span><span class="sxs-lookup"><span data-stu-id="b138e-128">[Associate File Extensions to a Code Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md) </span></span>  
 <span data-ttu-id="b138e-129">[Agregar elementos existentes a un proyecto](add-existing-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="b138e-129">[Add Existing Items to a Project](add-existing-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="b138e-130">Quitar o eliminar un elemento o un proyecto</span><span class="sxs-lookup"><span data-stu-id="b138e-130">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)  
  
  
