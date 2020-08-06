---
title: Importar informes desde Microsoft Access (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Access reports [Reporting Services]
- importing reports
ms.assetid: 4f29d5b8-b77d-4714-a84a-05523df55646
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 862d8b90f3c91dffda35971677db7fdc231c1b63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675747"
---
# <a name="import-reports-from-microsoft-access-reporting-services"></a><span data-ttu-id="c8d42-102">Importar informes desde Microsoft Access (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="c8d42-102">Import Reports from Microsoft Access (Reporting Services)</span></span>
  <span data-ttu-id="c8d42-103">En Diseñador de informes, puede importar informes desde una [!INCLUDE[msCoName](../includes/msconame-md.md)] base de datos o un proyecto de Access.</span><span class="sxs-lookup"><span data-stu-id="c8d42-103">In Report Designer, you can import reports from a [!INCLUDE[msCoName](../includes/msconame-md.md)] Access database or project.</span></span> <span data-ttu-id="c8d42-104">Deberá instalar Access 2002 o una versión posterior en el mismo equipo en el que está instalado el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="c8d42-104">Access 2002 or a later version must be installed on the same computer on which Report Designer is installed.</span></span>  
  
 <span data-ttu-id="c8d42-105">Cuando se usa la característica de importación, se importan todos los informes de la base de datos o del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c8d42-105">When you use the import feature, all reports in the database or project file are imported.</span></span> <span data-ttu-id="c8d42-106">Si el archivo de Access contiene muchos informes, es recomendable crear un proyecto de informes diferente para importarlos y, después, abrir los archivos RDL individuales en el proyecto de informes principal.</span><span class="sxs-lookup"><span data-stu-id="c8d42-106">If your Access file contains many reports, you may want to create a separate report project into which to import the reports, and then open the individual RDL files in your main report project.</span></span> <span data-ttu-id="c8d42-107">Puede modificar los informes después de importarlos al Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="c8d42-107">You can edit the reports after they are imported into Report Designer.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="c8d42-108">no admite todos los objetos de informe de Access.</span><span class="sxs-lookup"><span data-stu-id="c8d42-108">does not support all Access report objects.</span></span> <span data-ttu-id="c8d42-109">Los elementos que no se convierten se muestran en la ventana **lista de tareas** .</span><span class="sxs-lookup"><span data-stu-id="c8d42-109">Items that are not converted are displayed in the **Task List** window.</span></span> <span data-ttu-id="c8d42-110">Para obtener más información, vea [características de informes de Access admitidas &#40;SSRS&#41;](../../2014/reporting-services/supported-access-report-features-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c8d42-110">For more information, see [Supported Access Report Features &#40;SSRS&#41;](../../2014/reporting-services/supported-access-report-features-ssrs.md).</span></span>  
  
### <a name="to-import-reports-from-microsoft-access"></a><span data-ttu-id="c8d42-111">Para importar informes desde Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="c8d42-111">To import reports from Microsoft Access</span></span>  
  
1.  <span data-ttu-id="c8d42-112">Abra o cree el proyecto al que desea importar los informes.</span><span class="sxs-lookup"><span data-stu-id="c8d42-112">Open or create a project into which to import the reports.</span></span>  
  
2.  <span data-ttu-id="c8d42-113">En el menú **proyecto** , elija **importar informes**y, a continuación, haga clic en **Microsoft Access**.</span><span class="sxs-lookup"><span data-stu-id="c8d42-113">On the **Project** menu, point to **Import Reports**, and then click **Microsoft Access**.</span></span> <span data-ttu-id="c8d42-114">O bien, haga clic con el botón derecho en el proyecto en Explorador de soluciones, elija **importar informes**y, a continuación, haga clic en **Microsoft Access**.</span><span class="sxs-lookup"><span data-stu-id="c8d42-114">Alternatively, right-click the project in Solution Explorer, point to **Import Reports**, and then click **Microsoft Access**.</span></span>  
  
3.  <span data-ttu-id="c8d42-115">En el cuadro de diálogo **abrir** , seleccione la base de datos de Access (. mdb,. accdb) o el proyecto (. ADP) que contiene los informes y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="c8d42-115">In the **Open** dialog box, select the Access database (.mdb, .accdb) or project (.adp) that contains the reports, and then click **Open**.</span></span> <span data-ttu-id="c8d42-116">Todos los informes existentes en el archivo de base de datos o de proyecto se importan y se especifican en la carpeta de informes en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="c8d42-116">All the reports in the database or project file are imported and listed in the Reports folder in Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="c8d42-117">Compruebe si hay errores de compilación en la ventana **lista de tareas** .</span><span class="sxs-lookup"><span data-stu-id="c8d42-117">Check the **Task List** window for build errors.</span></span> <span data-ttu-id="c8d42-118">Para ver la ventana de **lista de tareas** , abra el menú **Ver** , seleccione **otras ventanas**y, a continuación, haga clic en **lista de tareas**.</span><span class="sxs-lookup"><span data-stu-id="c8d42-118">To view the **Task List** window, open the **View** menu, point to **Other Windows**, and then click **Task List**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d42-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8d42-119">See Also</span></span>  
 [<span data-ttu-id="c8d42-120">Diseñar informes con el Diseñador de informes &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c8d42-120">Design Reports with Report Designer &#40;SSRS&#41;</span></span>](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md)  
  
  
