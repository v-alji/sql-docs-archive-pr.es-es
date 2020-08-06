---
title: Ver eventos para el servicio de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- events [Integration Services]
- service [Integration Services], events
- Integration Services service, events
ms.assetid: 37e23946-10d1-4116-8568-8fd24067102e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a513c8fc917da2987f3619c8eb9011e1170f7dcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676049"
---
# <a name="view-events-for-the-integration-services-service"></a><span data-ttu-id="08ec0-102">Ver los eventos para el servicio Integration Services</span><span class="sxs-lookup"><span data-stu-id="08ec0-102">View Events for the Integration Services Service</span></span>
  <span data-ttu-id="08ec0-103">Hay dos herramientas en las que puede ver los eventos para el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="08ec0-103">There are two tools in which you can view events for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service:</span></span>  
  
-   <span data-ttu-id="08ec0-104">El cuadro de diálogo **Visor del archivo de registros** en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08ec0-104">The **Log File Viewer** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="08ec0-105">El cuadro de diálogo **Visor del archivo de registros** incluye opciones para exportar, filtrar y buscar en el registro.</span><span class="sxs-lookup"><span data-stu-id="08ec0-105">The **Log File Viewer** dialog box includes options to export, filter, and search the log.</span></span> <span data-ttu-id="08ec0-106">Para obtener más información sobre las opciones del **Visor del archivo de registro**, vea [Ayuda F1 del Visor de archivos de registro](../relational-databases/logs/log-file-viewer-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="08ec0-106">For more information about the options in the **Log File Viewer**, see [Log File Viewer F1 Help](../relational-databases/logs/log-file-viewer-f1-help.md).</span></span>  
  
-   <span data-ttu-id="08ec0-107">El Visor de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="08ec0-107">The Windows Event Viewer.</span></span>  
  
 <span data-ttu-id="08ec0-108">Para obtener descripciones de los eventos registrados por el servicio de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , vea [Eventos registrados por el servicio Integration Services](service/events-logged-by-the-integration-services-service.md).</span><span class="sxs-lookup"><span data-stu-id="08ec0-108">For descriptions of the events logged by the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, see [Events Logged by the Integration Services Service](service/events-logged-by-the-integration-services-service.md).</span></span>  
  
### <a name="to-view-service-events-for-integration-services-in-sql-server-management-studio"></a><span data-ttu-id="08ec0-109">Para ver los eventos del servicio para Integration Services en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="08ec0-109">To view service events for Integration Services in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="08ec0-110">Abra [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08ec0-110">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="08ec0-111">En el menú **Archivo** , haga clic en **Conectar Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="08ec0-111">On the **File** menu, click **Connect Object Explorer**.</span></span>  
  
3.  <span data-ttu-id="08ec0-112">En el cuadro de diálogo **Conectar al servidor** , seleccione el tipo de servidor [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , seleccione o localice el servidor al que desea conectarse y haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="08ec0-112">In the **Connect to Server** dialog box, select the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server type, select or locate the server to connect to, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="08ec0-113">En el Explorador de objetos, haga clic con el botón derecho en [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] y, después, haga clic en **Ver registros**.</span><span class="sxs-lookup"><span data-stu-id="08ec0-113">In Object Explorer, right-click [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and click **View Logs**.</span></span>  
  
5.  <span data-ttu-id="08ec0-114">Para ver los eventos de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , seleccione **SQL Server Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="08ec0-114">To view [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] events, select **SQL Server Integration Services**.</span></span> <span data-ttu-id="08ec0-115">La opción **Eventos NT** se selecciona automáticamente y se borra con la opción **SQL Server Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="08ec0-115">The **NT Events** option is automatically selected and cleared with the **SQL Server Integration Services** option.</span></span>  
  
### <a name="to-view-service-events-for-integration-services-in-windows-event-viewer"></a><span data-ttu-id="08ec0-116">Para ver los registros de eventos para Integration Services en el Visor de eventos de Windows</span><span class="sxs-lookup"><span data-stu-id="08ec0-116">To view service events for Integration Services in Windows Event Viewer</span></span>  
  
1.  <span data-ttu-id="08ec0-117">En el **Panel de control**, si utiliza la Vista clásica, haga clic en **Herramientas administrativas**o bien, si utiliza la Vista por categorías, haga clic en **Rendimiento y mantenimiento** y, a continuación, en **Herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="08ec0-117">In **Control Panel**, if you are using Classic View, click **Administrative Tools**, or, if you are using Category View, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="08ec0-118">Haga clic en **Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="08ec0-118">Click **Event Viewer**.</span></span>  
  
3.  <span data-ttu-id="08ec0-119">En el cuadro de diálogo **Visor de eventos** , haga clic en **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="08ec0-119">In the **Event Viewer** dialog box, click **Application**.</span></span>  
  
4.  <span data-ttu-id="08ec0-120">En el complemento **Aplicación** , localice una entrada en la columna **Origen** que contenga el valor **SQLISService**, haga clic con el botón derecho en la entrada y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="08ec0-120">In the **Application** snap-in, locate an entry in the **Source** column that has the value **SQLISService**, right-click the entry, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="08ec0-121">O bien, haga clic en la flecha arriba o abajo para ver el evento anterior o el siguiente.</span><span class="sxs-lookup"><span data-stu-id="08ec0-121">Optionally, click the up or down arrow to show the previous or next event.</span></span>  
  
6.  <span data-ttu-id="08ec0-122">Si lo desea, puede hacer clic en el icono Copiar al Portapapeles para copiar la información del evento.</span><span class="sxs-lookup"><span data-stu-id="08ec0-122">Optionally, click the Copy to Clipboard icon to copy the event information.</span></span>  
  
7.  <span data-ttu-id="08ec0-123">Elija si desea ver los datos del evento en bytes o en palabras.</span><span class="sxs-lookup"><span data-stu-id="08ec0-123">Choose to display event data using bytes or words.</span></span>  
  
8.  <span data-ttu-id="08ec0-124">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="08ec0-124">Click **OK**.</span></span>  
  
9. <span data-ttu-id="08ec0-125">En el menú **Archivo** , haga clic en **Salir** para salir del cuadro de diálogo **Visor de eventos** .</span><span class="sxs-lookup"><span data-stu-id="08ec0-125">On the **File** menu, click **Exit** to close the **Event Viewer** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08ec0-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08ec0-126">See Also</span></span>  
 <span data-ttu-id="08ec0-127">[Administrar el servicio de Integration Services](../../2014/integration-services/manage-the-integration-services-service.md) </span><span class="sxs-lookup"><span data-stu-id="08ec0-127">[Manage the Integration Services Service](../../2014/integration-services/manage-the-integration-services-service.md) </span></span>  
 [<span data-ttu-id="08ec0-128">Agregar un registro para los contadores de rendimiento del flujo de datos</span><span class="sxs-lookup"><span data-stu-id="08ec0-128">Add a Log for Data Flow Performance Counters</span></span>](performance/performance-counters.md)  
  
  
