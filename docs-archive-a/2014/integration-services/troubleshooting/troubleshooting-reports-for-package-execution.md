---
title: Solucionar problemas de informes para la ejecución de paquetes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8fc476ac-bd69-434e-9636-70776e0b3b6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b20d9c9c02af3f3df96e2ef46a7b25251793fa55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674896"
---
# <a name="troubleshooting-reports-for-package-execution"></a><span data-ttu-id="37b72-102">Solucionar problemas de informes para la ejecución de paquetes</span><span class="sxs-lookup"><span data-stu-id="37b72-102">Troubleshooting Reports for Package Execution</span></span>
  <span data-ttu-id="37b72-103">En la versión actual de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], existen informes estándar en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para ayudarlo a supervisar y solucionar problemas relacionados con los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que se han implementado en el catálogo de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37b72-103">In the current release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], standard reports are available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to help you monitor and troubleshoot [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that have been deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] catalog.</span></span> <span data-ttu-id="37b72-104">En concreto, dos de estos informes le ayudarán a ver el estado de ejecución de los paquetes e identificar la causa de los errores de ejecución.</span><span class="sxs-lookup"><span data-stu-id="37b72-104">Two of these package reports in particular help you to view package execution status and identify the cause of execution failures.</span></span>  
  
-   <span data-ttu-id="37b72-105">**Panel de Integration Services** : este informe proporciona información general sobre todas las ejecuciones de paquetes de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en las últimas 24 horas.</span><span class="sxs-lookup"><span data-stu-id="37b72-105">**Integration Services Dashboard** - This report provides an overview of all the package executions on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance in the past 24 hours.</span></span> <span data-ttu-id="37b72-106">El informe muestra información sobre el estado, tipo de operación, nombre del paquete, etc., para cada paquete.</span><span class="sxs-lookup"><span data-stu-id="37b72-106">The report displays information such as Status, Operation Type, Package Name, etc., for each package.</span></span>  
  
     <span data-ttu-id="37b72-107">La Hora de inicio, la Hora de finalización y la Duración se pueden interpretar de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="37b72-107">The Start Time, End Time, and Duration can be interpreted as follows:</span></span>  
  
    -   <span data-ttu-id="37b72-108">Si el paquete se sigue ejecutando: Duración = hora actual - Hora de inicio</span><span class="sxs-lookup"><span data-stu-id="37b72-108">If the package is still running, then Duration = current time - Start Time</span></span>  
  
    -   <span data-ttu-id="37b72-109">Si el paquete se ha completado: Duración = Hora de finalización - Hora de inicio</span><span class="sxs-lookup"><span data-stu-id="37b72-109">If the package has completed, then Duration = End Time - Start Time</span></span>  
  
     <span data-ttu-id="37b72-110">Para cada paquete que se ha ejecutado en el servidor, el panel le permite 'acercar' para buscar detalles específicos sobre los errores que podrían haberse producido durante la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="37b72-110">For each package that has run on the server, the dashboard allows you to "zoom in" to find specific details on package execution errors that may have occurred.</span></span> <span data-ttu-id="37b72-111">Por ejemplo, haga clic en **Información general** para mostrar información general de alto nivel sobre el estado de las tareas durante la ejecución o haga clic en **Todos los mensajes** para mostrar los mensajes detallados que se capturaron como parte de la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="37b72-111">For example, click **Overview** to display a high-level overview of the status of the tasks in the execution, or **All Messages** to display the detailed messages that were captured as part of the package execution.</span></span>  
  
     <span data-ttu-id="37b72-112">Puede filtrar la tabla que se muestra en cualquier página si hace clic en **Filtro** y selecciona los criterios deseados en el cuadro de diálogo **Configuración de filtro** .</span><span class="sxs-lookup"><span data-stu-id="37b72-112">You can filter the table displayed on any page by clicking **Filter** and then selecting criteria in the **Filter Settings** dialog.</span></span> <span data-ttu-id="37b72-113">Los criterios de filtro disponibles dependen de los datos que se muestran.</span><span class="sxs-lookup"><span data-stu-id="37b72-113">The filter criteria available depends on the data being displayed.</span></span> <span data-ttu-id="37b72-114">Puede cambiar el criterio de ordenación del informe haciendo clic en el icono de ordenación del cuadro de diálogo **Configuración de filtro** .</span><span class="sxs-lookup"><span data-stu-id="37b72-114">You can change the sort order of the report by clicking the sort icon in the **Filter Settings** dialog.</span></span>  
  
-   <span data-ttu-id="37b72-115">**Informe “Actividad: todas las ejecuciones”** : en este informe, se muestra un resumen de todas las ejecuciones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] realizadas en el servidor.</span><span class="sxs-lookup"><span data-stu-id="37b72-115">**Activity - All Executions Report** - This report displays a summary of all [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] executions that have been performed on the server.</span></span> <span data-ttu-id="37b72-116">El resumen muestra información para cada ejecución, como el estado, la hora de inicio y la hora de finalización.</span><span class="sxs-lookup"><span data-stu-id="37b72-116">The summary displays information for each execution such as status, start time, and end time.</span></span> <span data-ttu-id="37b72-117">Cada entrada de resumen incluye vínculos a más información acerca de la ejecución, incluidos los mensajes generados durante la ejecución y los datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="37b72-117">Each summary entry includes links to more information about the execution including messages generated during execution and performance data.</span></span> <span data-ttu-id="37b72-118">Al igual que con el Panel de Integration Services, puede aplicar un filtro a la tabla para reducir la información mostrada.</span><span class="sxs-lookup"><span data-stu-id="37b72-118">As with the Integration Services Dashboard, you can apply a filter to the table to narrow down the information displayed.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="37b72-119">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="37b72-119">Related Tasks</span></span>  
 [<span data-ttu-id="37b72-120">Ver informes del servidor de Integration Services</span><span class="sxs-lookup"><span data-stu-id="37b72-120">View Reports for the Integration Services Server</span></span>](../view-reports-for-the-integration-services-server.md)  
  
## <a name="related-content"></a><span data-ttu-id="37b72-121">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="37b72-121">Related Content</span></span>  
 [<span data-ttu-id="37b72-122">Informes para el servidor de Integration Services</span><span class="sxs-lookup"><span data-stu-id="37b72-122">Reports for the Integration Services Server</span></span>](../reports-for-the-integration-services-server.md)  
  
 [<span data-ttu-id="37b72-123">Herramientas para solucionar problemas de la ejecución de paquetes</span><span class="sxs-lookup"><span data-stu-id="37b72-123">Troubleshooting Tools for Package Execution</span></span>](troubleshooting-tools-for-package-execution.md)  
  
  
