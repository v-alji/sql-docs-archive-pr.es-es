---
title: Agregar un informe personalizado a Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: 3cf8d726-0a90-4f80-98d0-352a2a59be0f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07263edfb9b255257e0c79733c2c34b279b61cd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661783"
---
# <a name="add-a-custom-report-to-management-studio"></a><span data-ttu-id="c1c6d-102">agregar un informe personalizado a Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1c6d-102">Add a Custom Report to Management Studio</span></span>
  <span data-ttu-id="c1c6d-103">En este tema se describe cómo se crea un informe sencillo de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que se guarda como archivo .rdl y, a continuación, cómo se agrega dicho archivo a [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] como informe personalizado.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-103">This topic describes how to create a simple [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report that is saved as an .rdl file, and then add that rdl file to [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] as a custom report.</span></span> [!INCLUDE[ssRS](../../includes/ssrs.md)] <span data-ttu-id="c1c6d-104">puede crear una gran variedad de informes complejos.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-104">can create a wide variety of sophisticated reports.</span></span> <span data-ttu-id="c1c6d-105">Para crear un informe siguiendo las instrucciones de este tema, debe tener instalado [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-105">To create a report by using this topic, you must have [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] installed on the computer.</span></span> <span data-ttu-id="c1c6d-106">No es necesario instalar [!INCLUDE[ssRS](../../includes/ssrs.md)] en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ejecutar un informe personalizado mediante [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1c6d-106">You do not have to install [!INCLUDE[ssRS](../../includes/ssrs.md)] on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to run a custom report using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
  
### <a name="to-create-a-simple-report-saved-as-an-rdl-file"></a><span data-ttu-id="c1c6d-107">Para crear un informe simple guardado como un archivo .rdl</span><span class="sxs-lookup"><span data-stu-id="c1c6d-107">To create a simple report saved as an .rdl file</span></span>  
  
1.  <span data-ttu-id="c1c6d-108">Haga clic en **Inicio**, seleccione **Programas**, **Microsoft SQL Server**y, luego, haga clic en **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-108">Click **Start**, point to **Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="c1c6d-109">En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-109">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="c1c6d-110">En la lista **Tipos de proyecto** , haga clic en **Proyectos de Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-110">In the **Project Types** list, click **Business Intelligence Projects**.</span></span>  
  
4.  <span data-ttu-id="c1c6d-111">En la lista **Plantillas** , haga clic en **Asistente de proyectos de servidor de informes**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-111">In the **Templates** list, click **Report Server Project Wizard**.</span></span>  
  
5.  <span data-ttu-id="c1c6d-112">En **Nombre**, escriba **ConnectionsReport**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-112">In **Name**, type **ConnectionsReport**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="c1c6d-113">En la página de introducción del **Asistente para informes** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-113">On the **Report Wizard** introduction page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="c1c6d-114">En la página **Seleccionar el origen de datos** , en el cuadro Nombre, escriba un nombre para esta conexión a [!INCLUDE[ssDE](../../includes/ssde-md.md)]y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-114">On the **Select the Data Source** page, in the Name box type a name for this connection to your [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Edit**.</span></span>  
  
8.  <span data-ttu-id="c1c6d-115">En el cuadro de diálogo **Propiedades de conexión** , en el cuadro **Nombre del servidor** , escriba el nombre de la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1c6d-115">In the **Connection Properties** dialog box, in the **Server name** box, type the name of your instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
9. <span data-ttu-id="c1c6d-116">En el cuadro **Seleccione o escriba un nombre de base de datos** , escriba el nombre de cualquier base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], como [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-116">In the **Select or enter a database name** box, type the name of any database on your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **OK**.</span></span>  
  
10. <span data-ttu-id="c1c6d-117">En la página **Seleccionar el origen de datos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-117">On the **Select the Data Source** page, click **Next**.</span></span>  
  
11. <span data-ttu-id="c1c6d-118">En la página **Diseñar la consulta** , en el cuadro **Cadena de consulta** , escriba la siguiente instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] que muestra las conexiones actuales a [!INCLUDE[ssDE](../../includes/ssde-md.md)]y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-118">On the **Design the Query** page, in the **Query string** box, type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that lists the current connections to your [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Next**.</span></span> <span data-ttu-id="c1c6d-119">El cuadro Cadena de consulta del Asistente para informes no aceptará parámetros de informe.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-119">The Report Wizard Query string box will not accept report parameters.</span></span> <span data-ttu-id="c1c6d-120">Los informes personalizados más complejos deben crearse manualmente.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-120">More complex custom reports must be created manually.</span></span>  
  
     `SELECT session_id, net_transport FROM sys.dm_exec_connections;`  
  
12. <span data-ttu-id="c1c6d-121">En la página **Seleccionar el tipo de informe** , seleccione **Tabular**y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-121">On the **Select the Report Type** page, select **Tabular**, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="c1c6d-122">En la página **Finalización del asistente** , en el cuadro **Nombre del informe** , escriba **ConnectionsReport**y, a continuación, haga clic en **Finalizar** para crear y guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-122">On the **Completing the Wizard** page, in the **Report name** box, type **ConnectionsReport**, and then click **Finish** to create and save the report.</span></span>  
  
14. <span data-ttu-id="c1c6d-123">Cierre [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1c6d-123">Close [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
15. <span data-ttu-id="c1c6d-124">Copie **ConnectionsReport.rdl** en una carpeta que haya creado en el servidor de bases de datos para los informes personalizados.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-124">Copy **ConnectionsReport.rdl** to a folder that you created on the database server for custom reports.</span></span>  
  
### <a name="to-add-a-report-to-management-studio"></a><span data-ttu-id="c1c6d-125">Para agregar un informe a Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1c6d-125">To add a report to Management Studio</span></span>  
  
-   <span data-ttu-id="c1c6d-126">En [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], haga clic con el botón derecho en un nodo del Explorador de objetos, seleccione **Informes**y haga clic en **Informes personalizados**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-126">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click a node in Object Explorer, point to **Reports**, click **Custom Reports**.</span></span> <span data-ttu-id="c1c6d-127">En el cuadro de diálogo **Abrir archivo** , busque la carpeta de informes personalizados, seleccione el archivo **ConnectionsReport.rdl** y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-127">In the **Open File** dialog box, locate the custom reports folder and select the **ConnectionsReport.rdl** file, and then click **Open**.</span></span>  
  
     <span data-ttu-id="c1c6d-128">La primera vez que se abre un nuevo informe personalizado desde un nodo del Explorador de objetos, el informe personalizado se agrega a la lista de **Informes personalizados** usados más recientemente en el menú contextual de dicho nodo.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-128">When a new custom report is first opened from an Object Explorer node, the custom report is added to the most recently used list under **Custom Reports** on the shortcut menu of that node.</span></span> <span data-ttu-id="c1c6d-129">Al abrir un informe estándar por primera vez, aparece además en la lista de informes usados más recientemente en **Informes personalizados**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-129">When a standard report is opened for the first time, it will also appear on the most recently used list under **Custom Reports**.</span></span> <span data-ttu-id="c1c6d-130">Si se elimina un archivo de informe personalizado, la próxima vez que se seleccione el elemento aparecerá un mensaje que le indicará que elimine el elemento de la lista de informes usados más recientemente.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-130">If a custom report file is deleted, the next time that the item is selected, a prompt will appear to delete the item from the most recently used list.</span></span>  
  
    1.  <span data-ttu-id="c1c6d-131">Para cambiar el número de archivos que se muestran en esta lista, en el menú **Herramientas** , haga clic en **Opciones** , expanda la carpeta **Entorno** y, a continuación, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-131">To change the number of files that are displayed on the recently used list, on the **Tools** menu, click **Options,** expand the **Environment** folder, and then click **General**.</span></span>  
  
    2.  <span data-ttu-id="c1c6d-132">Ajuste el número de **Mostrar archivos de la lista de archivos recientes**.</span><span class="sxs-lookup"><span data-stu-id="c1c6d-132">Adjust the number for **Display files in recently used list**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c6d-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1c6d-133">See Also</span></span>  
 <span data-ttu-id="c1c6d-134">[Informes personalizados en Management Studio](custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="c1c6d-134">[Custom Reports in Management Studio](custom-reports-in-management-studio.md) </span></span>  
 <span data-ttu-id="c1c6d-135">[Usar informes personalizados con propiedades de nodo de Explorador de objetos](use-custom-reports-with-object-explorer-node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c1c6d-135">[Use Custom Reports with Object Explorer Node Properties](use-custom-reports-with-object-explorer-node-properties.md) </span></span>  
 <span data-ttu-id="c1c6d-136">[No suprimir advertencias de ejecutar informe personalizado](unsuppress-run-custom-report-warnings.md) </span><span class="sxs-lookup"><span data-stu-id="c1c6d-136">[Unsuppress Run Custom Report Warnings](unsuppress-run-custom-report-warnings.md) </span></span>  
 [<span data-ttu-id="c1c6d-137">Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c1c6d-137">Reporting Services &#40;SSRS&#41;</span></span>](../../reporting-services/create-deploy-and-manage-mobile-and-paginated-reports.md)  
  
  
