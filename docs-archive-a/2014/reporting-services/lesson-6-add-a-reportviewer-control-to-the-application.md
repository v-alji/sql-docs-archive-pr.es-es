---
title: 'Lección 6: Agregar un control ReportViewer a la aplicación | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f9492a97-5609-4059-ae76-0fba111d4968
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb04008fa47801f0500de711592a3cec45ca3dd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676872"
---
# <a name="lesson-6-add-a-reportviewer-control-to-the-application"></a><span data-ttu-id="ec817-102">Lección 6: agregar un control ReportViewer a la aplicación</span><span class="sxs-lookup"><span data-stu-id="ec817-102">Lesson 6: Add a ReportViewer Control to the Application</span></span>
  <span data-ttu-id="ec817-103">Después de diseñar el informe secundario con el Asistente de informes, el paso siguiente consiste en agregar un control ReportViewer a la aplicación del sitio Web.</span><span class="sxs-lookup"><span data-stu-id="ec817-103">After you design the child report by using the Report Wizard, your next step is to add a ReportViewer control to the website application.</span></span>  
  
### <a name="to-add-a-reportviewer-control-to-the-application"></a><span data-ttu-id="ec817-104">Para agregar un control ReportViewer a la aplicación</span><span class="sxs-lookup"><span data-stu-id="ec817-104">To add a ReportViewer control to the application</span></span>  
  
1.  <span data-ttu-id="ec817-105">En el **Explorador de soluciones**, haga clic con el botón derecho en **Default.aspx**y, después, haga clic en **Diseñador de vistas**.</span><span class="sxs-lookup"><span data-stu-id="ec817-105">In **Solution Explorer**, right-click **Default.aspx**, and then click **View Designer**.</span></span>  
  
2.  <span data-ttu-id="ec817-106">En el grupo **Extensiones AJAX** , en la ventana **Cuadro de herramientas** , arrastre un control **ScriptManager** a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="ec817-106">From the **AJAX Extensions** group in the **Toolbox** window, drag a **ScriptManager** control to the design surface.</span></span>  
  
3.  <span data-ttu-id="ec817-107">En el grupo **Reporting** , arrastre un control **ReportViewer** a la superficie de diseño debajo del control **ScriptManager** .</span><span class="sxs-lookup"><span data-stu-id="ec817-107">From the **Reporting** group, drag a **ReportViewer** control to the design surface below the **ScriptManager** control.</span></span>  
  
4.  <span data-ttu-id="ec817-108">Haga clic en la flecha de la esquina superior derecha del control **ReportViewer** para abrir la ventana **Tareas de ReportViewer** .</span><span class="sxs-lookup"><span data-stu-id="ec817-108">Open the **ReportViewer Tasks** window by clicking the arrow in the top right-hand corner of the **ReportViewer** control.</span></span>  
  
5.  <span data-ttu-id="ec817-109">En el cuadro **Elegir informe** , seleccione el informe primario que creó.</span><span class="sxs-lookup"><span data-stu-id="ec817-109">In the **Choose Report** box, select Parent report you created.</span></span>  
  
     <span data-ttu-id="ec817-110">Al seleccionar un informe, las instancias de los orígenes de datos usados en el informe se crean automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ec817-110">When you select a report, instances of data sources used in the report are created automatically.</span></span> <span data-ttu-id="ec817-111">El código se genera para crear una instancia de cada DataTable (y el contenedor [DataSet](https://msdn.microsoft.com/library/system.data.dataset\(v=vs.100\).aspx) ).</span><span class="sxs-lookup"><span data-stu-id="ec817-111">Code is generated to instantiate each DataTable (and its [DataSet](https://msdn.microsoft.com/library/system.data.dataset\(v=vs.100\).aspx) container).</span></span> <span data-ttu-id="ec817-112">Un control [ObjectDataSource](https://msdn.microsoft.com/library/system.web.ui.webcontrols.objectdatasource\(v=vs.100\).aspx) se agrega a la superficie de diseño, correspondiente a cada origen de datos usado en el informe.</span><span class="sxs-lookup"><span data-stu-id="ec817-112">An [ObjectDataSource](https://msdn.microsoft.com/library/system.web.ui.webcontrols.objectdatasource\(v=vs.100\).aspx) control is added to the design surface, corresponding to each data source used in the report.</span></span> <span data-ttu-id="ec817-113">Este control de origen de datos se configura automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ec817-113">This data source control is configured automatically.</span></span>  
  
     <span data-ttu-id="ec817-114">Si utiliza Microsoft Visual Studio 2012, asegúrese de que el control ObjectDataSource está enlazado a DataSet1 que está completo con el espacio de nombres del proyecto, si el nombre completo se muestra en el cuadro de lista desplegable **Elija el objeto comercial** (por ejemplo, Projectnamespace. DataSet1TableAdapters. ProductTableAdapter).</span><span class="sxs-lookup"><span data-stu-id="ec817-114">If you're using Microsoft Visual Studio 2012, make sure that the ObjectDataSource control is bound with DataSet1 that is fully qualified with the project namespace, if the fully qualified name is listed in the **Choose your business object** drop-down list box (for example, Projectnamespace.DataSet1TableAdapters.ProductTableAdapter).</span></span> <span data-ttu-id="ec817-115">Tiene acceso al cuadro de lista haciendo clic con el botón secundario en ObjectDataSource y, después, haciendo clic en **Configurar origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="ec817-115">You access the list box by right-clicking ObjectDataSource, and then clicking **Configure Data Source**.</span></span>  
  
6.  <span data-ttu-id="ec817-116">En el menú Compilar, haga clic en Compilar sitio Web.</span><span class="sxs-lookup"><span data-stu-id="ec817-116">On the Build menu, click Build website.</span></span>  
  
     <span data-ttu-id="ec817-117">Se compila el informe y errores como un error de sintaxis en una expresión de informe aparecen en el área de **Lista de errores** .</span><span class="sxs-lookup"><span data-stu-id="ec817-117">The report is compiled and any errors such as a syntax error in a report expression appear in the **Error List** area.</span></span> <span data-ttu-id="ec817-118">Haga clic en **Lista de errores** en la parte inferior de la ventana de Visual Studio para mostrar el área de **Lista de errores** .</span><span class="sxs-lookup"><span data-stu-id="ec817-118">Click **Error List** at the bottom of the Visual Studio window to display the **Error List** area.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="ec817-119">Tarea siguiente</span><span class="sxs-lookup"><span data-stu-id="ec817-119">Next Task</span></span>  
 <span data-ttu-id="ec817-120">Ha agregado correctamente un control ReportViewer a la aplicación del sitio Web.</span><span class="sxs-lookup"><span data-stu-id="ec817-120">You have successfully added a ReportViewer control to the website application.</span></span> <span data-ttu-id="ec817-121">Después, agregará una acción de obtención de detalles en el informe primario.</span><span class="sxs-lookup"><span data-stu-id="ec817-121">Next, you will add a drillthrough action on the parent report.</span></span>  
  
  
