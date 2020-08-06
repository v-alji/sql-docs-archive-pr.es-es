---
title: Guardar scripts como proyectos o soluciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 72dfd37f-dbe7-4d1d-bda6-7eb54c7922d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9fade3900c8859f211bb0c66820dc97792262481
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746656"
---
# <a name="save-scripts-as-projects-or-solutions"></a><span data-ttu-id="29292-102">Guardar scripts como proyectos o soluciones</span><span class="sxs-lookup"><span data-stu-id="29292-102">Save Scripts as Projects or Solutions</span></span>
  <span data-ttu-id="29292-103">Los desarrolladores que estén familiarizados con [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio acogerán con entusiasmo el Explorador de soluciones de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29292-103">Developers familiar with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio will welcome Solution Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="29292-104">Los scripts empleados en su empresa pueden agruparse en proyectos de script; estos proyectos pueden administrarse conjuntamente en forma de solución.</span><span class="sxs-lookup"><span data-stu-id="29292-104">The scripts that support your business can be grouped into script projects, and the script projects can be managed together as a solution.</span></span> <span data-ttu-id="29292-105">Cuando los scripts se colocan en soluciones y proyectos de script, pueden abrirse como un grupo o guardarse juntos en un producto de control de código fuente como Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="29292-105">When scripts are placed in script projects and solutions they can be opened together as a group, or saved together to a source control product such as Visual SourceSafe.</span></span> <span data-ttu-id="29292-106">Los proyectos de script incluyen información de conexión para que los scripts se ejecuten correctamente y pueden incluir archivos que no sean de script, por ejemplo, un archivo auxiliar de texto.</span><span class="sxs-lookup"><span data-stu-id="29292-106">Script projects include the connection information for the scripts to execute properly, and can include non-script files such as a supporting text file.</span></span>  
  
 <span data-ttu-id="29292-107">En la práctica siguiente, se crea un script breve que hace consultas a la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , ubicada en una solución y un proyecto de script.</span><span class="sxs-lookup"><span data-stu-id="29292-107">The following practice creates a short script that queries the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, placed in a script project and solution.</span></span>  
  
## <a name="using-script-projects-and-solutions"></a><span data-ttu-id="29292-108">Usar soluciones y proyectos de script</span><span class="sxs-lookup"><span data-stu-id="29292-108">Using Script Projects and Solutions</span></span>  
  
#### <a name="to-create-a-script-project-and-solution"></a><span data-ttu-id="29292-109">Para crear una solución y un proyecto de script</span><span class="sxs-lookup"><span data-stu-id="29292-109">To create a script project and solution</span></span>  
  
1.  <span data-ttu-id="29292-110">Abra [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]y conéctese a un servidor mediante el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="29292-110">Open [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and connect to a server with Object Explorer.</span></span>  
  
2.  <span data-ttu-id="29292-111">En el menú **Archivo** , elija **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="29292-111">On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="29292-112">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="29292-112">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="29292-113">En el cuadro de texto **Nombre** , escriba **StatusCheck**, haga clic en **Scripts de SQL Server** en **Plantillas**y, después, haga clic en **Aceptar** para abrir una solución y un proyecto de script nuevos.</span><span class="sxs-lookup"><span data-stu-id="29292-113">In the **Name** text box, type **StatusCheck**, click **SQL Server Scripts** in **Templates**, and then click **OK** to open a new solution and script project.</span></span>  
  
4.  <span data-ttu-id="29292-114">En el Explorador de soluciones, haga clic con el botón derecho en **Conexiones**y, después, en **Nueva conexión**.</span><span class="sxs-lookup"><span data-stu-id="29292-114">In Solution Explorer, right-click **Connections**, and then click **New Connection**.</span></span> <span data-ttu-id="29292-115">Se abre el cuadro de diálogo **Conectar al servidor** .</span><span class="sxs-lookup"><span data-stu-id="29292-115">The **Connect to Server** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="29292-116">En el cuadro de lista **Nombre del servidor** , escriba el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="29292-116">In the **Server name** list box, type the name of your server.</span></span>  
  
6.  <span data-ttu-id="29292-117">Haga clic en **Opciones**y, después, en la pestaña **Propiedades de conexión** .</span><span class="sxs-lookup"><span data-stu-id="29292-117">Click **Options**, and then click the **Connection Properties** tab.</span></span>  
  
7.  <span data-ttu-id="29292-118">En el cuadro **Conectar con base de datos** , examine el servidor, seleccione la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] y, después, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="29292-118">In the **Connect to database** box, browse the server, select the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, and then click **Connect**.</span></span> <span data-ttu-id="29292-119">La información de conexión que incluye la base de datos se agregará al proyecto.</span><span class="sxs-lookup"><span data-stu-id="29292-119">The connection information including the database is added to the project.</span></span>  
  
8.  <span data-ttu-id="29292-120">Si la ventana Propiedades no aparece, haga clic en la conexión nueva del Explorador de soluciones y, a continuación, presione F4.</span><span class="sxs-lookup"><span data-stu-id="29292-120">If the Properties window is not displayed, click the new connection in Solution Explorer, and then press F4.</span></span> <span data-ttu-id="29292-121">Las propiedades de la conexión aparecen y muestran información relativa a la conexión, incluida la **Base de datos inicial** como [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29292-121">The properties for the connection appear, and show information about the connection including the **Initial Database** as [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].</span></span>  
  
9. <span data-ttu-id="29292-122">En el Explorador de soluciones, haga clic con el botón derecho en la conexión y, después, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="29292-122">In Solution Explorer, right-click the connection, and then click **New Query**.</span></span> <span data-ttu-id="29292-123">Se crea una consulta denominada **SQLQuery1.sql** , que está conectada a la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] del servidor y se agrega al proyecto de script.</span><span class="sxs-lookup"><span data-stu-id="29292-123">A new query called **SQLQuery1.sql** is created, connected to the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database on your server, and added to your script project.</span></span>  
  
10. <span data-ttu-id="29292-124">En el Editor de consultas, escriba la consulta siguiente para determinar cuántas órdenes de trabajo tienen una fecha de vencimiento anterior a la fecha de inicio.</span><span class="sxs-lookup"><span data-stu-id="29292-124">In Query Editor, type the following query to determine how many work orders have due dates, before the work order starting dates.</span></span> <span data-ttu-id="29292-125">Puede copiar y pegar el código de la ventana del tutorial.</span><span class="sxs-lookup"><span data-stu-id="29292-125">(You can copy and paste the code from the Tutorial window.)</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT COUNT(WorkOrderID)  
    FROM Production.WorkOrder  
    WHERE DueDate < StartDate;  
  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="29292-126">Si necesita más espacio para escribir la consulta, presione MAYÚS+ALT+ENTRAR para cambiar al modo de pantalla completa.</span><span class="sxs-lookup"><span data-stu-id="29292-126">If you need more room to type your query, press SHIFT+ALT+ENTER, to switch to full-screen mode.</span></span>  
  
11. <span data-ttu-id="29292-127">En el Explorador de soluciones, haga clic con el botón derecho en **SQLQuery1**y, después, haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="29292-127">In Solution Explorer, right-click **SQLQuery1**, and then click **Rename**.</span></span> <span data-ttu-id="29292-128">Escriba **checkss. SQL** como el nuevo nombre de la consulta y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="29292-128">Type **Check Workorders.sql** as the new name for the query and press ENTER.</span></span>  
  
12. <span data-ttu-id="29292-129">Para guardar la solución y el proyecto de script, en el menú **Archivo** , haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="29292-129">To save your solution and script project, on the **File** menu, click **Save All**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="29292-130">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="29292-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="29292-131">Resumen: Soluciones y proyectos de scripts</span><span class="sxs-lookup"><span data-stu-id="29292-131">Summary: Solutions and Script Projects</span></span>](lesson-3-4-summary-solutions-and-script-projects.md)  
  
  
