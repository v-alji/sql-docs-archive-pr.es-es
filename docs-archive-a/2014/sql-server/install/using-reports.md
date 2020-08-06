---
title: Uso de informes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- displaying reports
- overriding reports
- Upgrade Advisor Report Viewer
- reports [Upgrade Advisor], about reports
- formatting reports
- resolved issues [Upgrade Advisor]
- distributing reports [Reporting Services]
- filtering reports [Reporting Services]
- removing report items
- viewing reports
- rerunning analysis
- information issues [Upgrade Advisor]
- deleting report items
- icons [Upgrade Advisor]
- Upgrade Advisor [SQL Server], reports
- sending reports
- blocking issues [Upgrade Advisor]
- sharing reports
- reports [Upgrade Advisor]
- SQL Server Upgrade Advisor, reports
- modifying reports
- distributing reports [Reporting Services], about report distribution
- warnings [Upgrade Advisor]
- analyzing system [Upgrade Advisor], reports
ms.assetid: 4a3cb94a-a7ac-4cec-94c7-db26fcf6d161
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f52afcfdaa7de33d83d64a049f9a350f0463b4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751654"
---
# <a name="using-reports"></a><span data-ttu-id="168e5-102">Utilizar los informes</span><span class="sxs-lookup"><span data-stu-id="168e5-102">Using Reports</span></span>
  <span data-ttu-id="168e5-103">Se genera un informe independiente para cada componente y, cuando es necesario, para cada instancia, los cuales analiza el Asistente para análisis del Asesor de actualizaciones en un servidor.</span><span class="sxs-lookup"><span data-stu-id="168e5-103">A separate report is generated for each component, and, where necessary, each instance, that the Upgrade Advisor Analysis Wizard analyzes on a server.</span></span> <span data-ttu-id="168e5-104">El informe proporciona detalles sobre los problemas conocidos que afectan a una actualización.</span><span class="sxs-lookup"><span data-stu-id="168e5-104">The report provides details about known issues that affect an upgrade.</span></span> <span data-ttu-id="168e5-105">También se proporcionan vínculos a información y acciones sugeridas para solucionar los problemas identificados.</span><span class="sxs-lookup"><span data-stu-id="168e5-105">It also provides links to information and suggested actions for addressing the identified issues.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="168e5-106">Si el visor de informes del Asesor de actualizaciones no encuentra ningún informe en el directorio de informes predeterminado, puede cargar un informe desde un directorio diferente mediante el vínculo **abrir Informe** .</span><span class="sxs-lookup"><span data-stu-id="168e5-106">If the Upgrade Advisor Report Viewer does not find any reports in the default reports directory, you can load a report from a different directory by using the **Open Report** link.</span></span>  
  
## <a name="viewing-reports"></a><span data-ttu-id="168e5-107">Ver informes</span><span class="sxs-lookup"><span data-stu-id="168e5-107">Viewing Reports</span></span>  
 <span data-ttu-id="168e5-108">Puede usar el Visor de informes del Asesor de actualizaciones para ver los informes del Asesor de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="168e5-108">You use the Upgrade Advisor Report Viewer to view Upgrade Advisor reports.</span></span> <span data-ttu-id="168e5-109">Para ver informes, en la página de inicio del Asesor de actualizaciones, haga clic en **iniciar el visor de informes del Asesor de actualizaciones**.</span><span class="sxs-lookup"><span data-stu-id="168e5-109">To view reports, on the Upgrade Advisor start page, click **Launch Upgrade Advisor Report Viewer**.</span></span>  
  
 <span data-ttu-id="168e5-110">Después de cargar un informe de un servidor, puede seleccionar un componente cuyos problemas de actualización desee ver.</span><span class="sxs-lookup"><span data-stu-id="168e5-110">After you load a report for a server, you can select a component for which you want to see upgrade issues.</span></span> <span data-ttu-id="168e5-111">Puede aplicar un filtro desde el cuadro **filtrar por** para ver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="168e5-111">You can apply a filter from the **Filter By** box to see the following:</span></span>  
  
-   <span data-ttu-id="168e5-112">Todos los problemas</span><span class="sxs-lookup"><span data-stu-id="168e5-112">All issues</span></span>  
  
-   <span data-ttu-id="168e5-113">Todos los problemas de actualización</span><span class="sxs-lookup"><span data-stu-id="168e5-113">All upgrade issues</span></span>  
  
-   <span data-ttu-id="168e5-114">Problemas anteriores a la actualización</span><span class="sxs-lookup"><span data-stu-id="168e5-114">Pre-upgrade issues</span></span>  
  
-   <span data-ttu-id="168e5-115">Todos los problemas de migración</span><span class="sxs-lookup"><span data-stu-id="168e5-115">All migration issues</span></span>  
  
-   <span data-ttu-id="168e5-116">Problemas resueltos</span><span class="sxs-lookup"><span data-stu-id="168e5-116">Resolved issues</span></span>  
  
-   <span data-ttu-id="168e5-117">Problemas sin resolver</span><span class="sxs-lookup"><span data-stu-id="168e5-117">Unresolved issues</span></span>  
  
 <span data-ttu-id="168e5-118">Si el informe tiene más de 20 problemas, puede pasar al grupo siguiente o anterior de problemas haciendo clic en **siguiente 20** o en el **20 anterior** en la parte superior o inferior de la lista de problemas.</span><span class="sxs-lookup"><span data-stu-id="168e5-118">If your report has more than 20 issues, you can move to the next or previous group of issues by clicking **Next 20** or **Previous 20** at the top or bottom of the issues list.</span></span>  
  
 <span data-ttu-id="168e5-119">Puede ver hasta cinco informes guardados si selecciona los informes en el cuadro de lista desplegable **Informe** .</span><span class="sxs-lookup"><span data-stu-id="168e5-119">You can view up to five saved reports by selecting the reports from the **Report** drop-down list box.</span></span> <span data-ttu-id="168e5-120">Los informes se enumeran según la marca de tiempo establecida durante su generación.</span><span class="sxs-lookup"><span data-stu-id="168e5-120">The reports are listed by the timestamp from when they were generated.</span></span>  
  
## <a name="report-format"></a><span data-ttu-id="168e5-121">Formato de informe</span><span class="sxs-lookup"><span data-stu-id="168e5-121">Report Format</span></span>  
 <span data-ttu-id="168e5-122">El Visor de informes muestra los problemas del informe en tres columnas.</span><span class="sxs-lookup"><span data-stu-id="168e5-122">The report viewer displays report issues in three columns.</span></span> <span data-ttu-id="168e5-123">Cada problema se puede contraer, de forma que puede ocultar la descripción y ver únicamente la información más importante.</span><span class="sxs-lookup"><span data-stu-id="168e5-123">Each issue is collapsible so that you can hide the description and view only the key information.</span></span>  
  
 <span data-ttu-id="168e5-124">La primera columna es la columna de **importancia** .</span><span class="sxs-lookup"><span data-stu-id="168e5-124">The first column is the **Importance** column.</span></span> <span data-ttu-id="168e5-125">Los iconos indican la importancia de cada problema, mostrando un círculo rojo con una X para aquellos problemas importantes o un triángulo amarillo con un signo de admiración para problemas de tipo advertencia o que proporcionan información.</span><span class="sxs-lookup"><span data-stu-id="168e5-125">Icons indicate the importance for each issue by displaying either a red circle with an X for blocking or important issues or a yellow triangle with an exclamation mark for Warning and Information issues.</span></span> <span data-ttu-id="168e5-126">La segunda columna, **Cuándo corregir**, indica cuándo debe resolverse el problema.</span><span class="sxs-lookup"><span data-stu-id="168e5-126">The second column, **When to fix**, indicates when you must resolve the issue.</span></span> <span data-ttu-id="168e5-127">Puede ordenar el informe según la columna **importancia** o **al corregir** .</span><span class="sxs-lookup"><span data-stu-id="168e5-127">You can sort the report on either the **Importance** or **When to fix** column.</span></span> <span data-ttu-id="168e5-128">La tercera columna, **Description**, muestra el título del problema.</span><span class="sxs-lookup"><span data-stu-id="168e5-128">The third column, **Description**, lists the title of the issue.</span></span>  
  
 <span data-ttu-id="168e5-129">Puede expandir un problema para ver información adicional, un vínculo a información detallada acerca de cómo resolver el problema y un vínculo para mostrar los detalles del problema.</span><span class="sxs-lookup"><span data-stu-id="168e5-129">You can expand an issue to display additional information, a link to detailed information about resolving the issue, and a link to show issue details.</span></span> <span data-ttu-id="168e5-130">Al hacer clic en el vínculo para obtener información detallada acerca del problema, se muestra un tema de ayuda con información detallada acerca del problema, así como instrucciones específicas acerca de cómo solucionarlo.</span><span class="sxs-lookup"><span data-stu-id="168e5-130">When you click the link to get detailed information for the issue, a Help topic with information about the issue and instructions for addressing the issue is displayed.</span></span> <span data-ttu-id="168e5-131">Una vez corregido el problema, o para administrar los elementos de acción, puede marcar los problemas como completos activando la casilla **este problema** se ha resuelto.</span><span class="sxs-lookup"><span data-stu-id="168e5-131">After you have fixed an issue, or to manage your action items, you can mark issues as complete by selecting the **This issue has been resolved** check box.</span></span> <span data-ttu-id="168e5-132">Si desea quitar los problemas resueltos de la lista de problemas de actualización, haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="168e5-132">If you want to remove the resolved issues from the list of upgrade issues, click **Refresh**.</span></span> <span data-ttu-id="168e5-133">El problema no se mostrará de nuevo hasta que ejecute el Asistente para análisis del Asesor de actualizaciones en el mismo componente o aplique el filtro **problemas resueltos** de la opción **filtrar por** .</span><span class="sxs-lookup"><span data-stu-id="168e5-133">The issue is not displayed again until you either run the Upgrade Advisor Analysis Wizard against the same component or apply the **Resolved Issues** filter from the **Filter By** option.</span></span>  
  
## <a name="report-files"></a><span data-ttu-id="168e5-134">Archivos de informe</span><span class="sxs-lookup"><span data-stu-id="168e5-134">Report Files</span></span>  
 <span data-ttu-id="168e5-135">El Asistente para análisis del Asesor de actualizaciones crea los informes en el directorio mis documentos \\ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade Advisor\110\Reports y crea un subdirectorio para cada servidor que analice.</span><span class="sxs-lookup"><span data-stu-id="168e5-135">The Upgrade Advisor Analysis Wizard creates reports in the My Documents\\[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports directory and creates a subdirectory for each server that you analyze.</span></span> <span data-ttu-id="168e5-136">Los archivos de informe son archivos XML que siguen una convención de nomenclatura concreta.</span><span class="sxs-lookup"><span data-stu-id="168e5-136">The report files are XML files that follow a specific naming convention.</span></span> <span data-ttu-id="168e5-137">Al iniciar el Visor de informes del Asistente de actualizaciones, se muestran los archivos de informe del directorio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="168e5-137">When you launch the Upgrade Advisor Report Viewer, the report files in the default directory are displayed.</span></span> <span data-ttu-id="168e5-138">Si copia los archivos de informe en esta carpeta, deben cumplir la convención de nomenclatura o el Visor de informes no los mostrará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="168e5-138">If you copy report files into this folder, they must adhere to the naming convention or the report viewer will not display them automatically.</span></span>  
  
 <span data-ttu-id="168e5-139">Si desea compartir la información con otras personas, puede enviarles el informe XML.</span><span class="sxs-lookup"><span data-stu-id="168e5-139">If you want to share the information with other people, you can send them the XML report.</span></span> <span data-ttu-id="168e5-140">O, si desea utilizar otra aplicación, puede exportar el informe en un archivo de valores separados por comas que puede utilizar para crear una hoja de cálculo, un archivo de texto o un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="168e5-140">Or, if you want to use another application, you can export the report into a comma-separated value file that you can use to create a spreadsheet, text file, or e-mail message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="168e5-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="168e5-141">See Also</span></span>  
 <span data-ttu-id="168e5-142">[Cómo ver un informe del Asesor de actualizaciones](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md) </span><span class="sxs-lookup"><span data-stu-id="168e5-142">[How to: View an Upgrade Advisor Report](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md) </span></span>  
 <span data-ttu-id="168e5-143">[Cómo: exportar informes](../../../2014/sql-server/install/how-to-export-reports.md) </span><span class="sxs-lookup"><span data-stu-id="168e5-143">[How to: Export Reports](../../../2014/sql-server/install/how-to-export-reports.md) </span></span>  
 <span data-ttu-id="168e5-144">[Cómo: filtrar informes](../../../2014/sql-server/install/how-to-filter-reports.md) </span><span class="sxs-lookup"><span data-stu-id="168e5-144">[How to: Filter Reports](../../../2014/sql-server/install/how-to-filter-reports.md) </span></span>  
 <span data-ttu-id="168e5-145">[Resolver problemas de actualización](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="168e5-145">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="168e5-146">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="168e5-146">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
