---
title: Cambiar el nombre de un equipo servidor de informes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- renaming report servers
ms.assetid: 82fc4ba2-291a-4939-a025-271b8d687c54
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fe8f699c17f9e5f1e11406ac6e5c161488767ed1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677427"
---
# <a name="rename-a-report-server-computer"></a><span data-ttu-id="15a85-102">Cambiar el nombre de un equipo que ejecuta un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="15a85-102">Rename a Report Server Computer</span></span>
  <span data-ttu-id="15a85-103">Al cambiar el nombre de un equipo, también se cambia el nombre correspondiente del servidor web y de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (si está en el mismo equipo).</span><span class="sxs-lookup"><span data-stu-id="15a85-103">Renaming a computer causes a corresponding name change for the Web server and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (if it is on the same computer).</span></span> <span data-ttu-id="15a85-104">En algunos casos, puede que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no esté accesible después de un cambio en el nombre de equipo.</span><span class="sxs-lookup"><span data-stu-id="15a85-104">In some cases, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] may not be accessible after a computer name change.</span></span> <span data-ttu-id="15a85-105">Siga los pasos que aparecen en este tema para volver a configurar un servidor de informes después de haber cambiado el nombre de un equipo.</span><span class="sxs-lookup"><span data-stu-id="15a85-105">Use the steps provided in this topic to reconfigure a report server after a computer name change.</span></span>  
  
## <a name="renaming-a-sql-server-database-engine"></a><span data-ttu-id="15a85-106">Cambiar el nombre de un motor de base de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="15a85-106">Renaming a SQL Server Database Engine</span></span>  
 <span data-ttu-id="15a85-107">Si cambia el nombre de la instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que ejecuta la base de datos del servidor de informes, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="15a85-107">If you rename the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance that runs the report server database, do the following:</span></span>  
  
1.  <span data-ttu-id="15a85-108">Inicie la herramienta de configuración de Reporting Services y conéctese al servidor de informes que utiliza la base de datos en el servidor de informes que ha cambiado de nombre.</span><span class="sxs-lookup"><span data-stu-id="15a85-108">Start the Reporting Services Configuration tool and connect to the report server that uses the report server database on the renamed server.</span></span>  
  
2.  <span data-ttu-id="15a85-109">Abra la página Instalación de base de datos.</span><span class="sxs-lookup"><span data-stu-id="15a85-109">Open the Database Setup page.</span></span>  
  
3.  <span data-ttu-id="15a85-110">En **Nombre del servidor**, escriba o seleccione el nombre de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y, a continuación, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="15a85-110">In **Server Name**, type or select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] name, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="15a85-111">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="15a85-111">Click **Apply**.</span></span>  
  
 <span data-ttu-id="15a85-112">Si el servidor de informes usa una instancia local de [!INCLUDE[ssDE](../../includes/ssde-md.md)] , puede usar *(local)* o *(local)\nombreDeInstancia* para especificar el servidor.</span><span class="sxs-lookup"><span data-stu-id="15a85-112">If the report server is using a local [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance, you can use *(local)* or *(local)\instancename* to specify the server.</span></span> <span data-ttu-id="15a85-113">Si usa *(local)* para referirse al servidor, puede cambiar el nombre del servidor y las conexiones continuarán funcionando.</span><span class="sxs-lookup"><span data-stu-id="15a85-113">If you use *(local)* to refer to the server, you can rename the server and the connections will continue to work.</span></span> <span data-ttu-id="15a85-114">Si usa un servidor remoto o se ha configurado [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] con el nombre del servidor, debe actualizar la información de conexión de la base de datos siempre que cambie el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="15a85-114">If you are using a remote server, or if [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is configured using the server name, you must update the database connection information whenever the server name is changed.</span></span>  
  
## <a name="renaming-a-report-server-computer"></a><span data-ttu-id="15a85-115">Cambiar el nombre de un equipo que ejecuta un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="15a85-115">Renaming a Report Server Computer</span></span>  
 <span data-ttu-id="15a85-116">Si cambia el nombre de un equipo que ejecuta un servidor de informes, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="15a85-116">If you rename a computer that runs a report server, do the following:</span></span>  
  
1.  <span data-ttu-id="15a85-117">Abra **RSReportServer.config** en un editor de texto y modifique la `UrlRoot` configuración para reflejar el nuevo nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="15a85-117">Open **RSReportServer.config** in a text editor and modify the `UrlRoot` setting to reflect the new server name.</span></span> <span data-ttu-id="15a85-118">La extensiones de entrega utilizan el valor `UrlRoot` para crear la dirección URL utilizada para obtener acceso a elementos almacenados en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="15a85-118">The `UrlRoot` setting is used by delivery extensions to compose the URL used to access items stored on the report server.</span></span> <span data-ttu-id="15a85-119">Cambiar la dirección URL del servidor requiere actualizar la configuración de `UrlRoot` para que las suscripciones sigan entregando informes correctamente.</span><span class="sxs-lookup"><span data-stu-id="15a85-119">Changing the report server URL address requires that you update the `UrlRoot` setting so that subscriptions continue to deliver reports as expected.</span></span>  
  
2.  <span data-ttu-id="15a85-120">En el mismo archivo, si se establece, modifique el valor `ReportServerUrl` para reflejar el nuevo nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="15a85-120">In the same file, if it is set, modify the `ReportServerUrl` setting to reflect the new server name.</span></span> <span data-ttu-id="15a85-121">Observe que esta configuración no se utiliza en todas las instalaciones.</span><span class="sxs-lookup"><span data-stu-id="15a85-121">Note that this setting is not used in every installation.</span></span> <span data-ttu-id="15a85-122">Si está en blanco, no haga nada.</span><span class="sxs-lookup"><span data-stu-id="15a85-122">If it is empty, do nothing.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="15a85-123">Si utiliza el Servicio de nombres Internet de Windows (WINS) en su red corporativa, el servidor de informes y el Administrador de informes continuarán estando disponibles con el nombre anterior durante algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="15a85-123">If you are using Windows Internet Naming Service (WINS) on your corporate network, the report server and Report Manager may continue to be available under the previous name for a period of time.</span></span> <span data-ttu-id="15a85-124">WINS asigna una dirección IP a cada uno de los equipos a los que sirve.</span><span class="sxs-lookup"><span data-stu-id="15a85-124">WINS maps an IP address to each computer it services.</span></span> <span data-ttu-id="15a85-125">Después de que WINS actualice la dirección IP para el equipo que ha cambiado de nombre, el nombre antiguo no podrá utilizarse para obtener acceso a un servidor de informes ni al Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="15a85-125">After WINS refreshes the IP address for the renamed computer, the old computer name can no longer be used to access a report server or Report Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15a85-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15a85-126">See Also</span></span>  
 <span data-ttu-id="15a85-127">[Archivo de configuración RSReportServer](rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="15a85-127">[RSReportServer Configuration File](rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="15a85-128">[Administrador de configuración de Reporting Services &#40;modo nativo&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="15a85-128">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="15a85-129">[Servidor de informes de Reporting Services &#40;modo nativo&#41;](reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="15a85-129">[Reporting Services Report Server &#40;Native Mode&#41;](reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="15a85-130">[Iniciar y detener el servicio del servidor de informes](start-and-stop-the-report-server-service.md) </span><span class="sxs-lookup"><span data-stu-id="15a85-130">[Start and Stop the Report Server Service](start-and-stop-the-report-server-service.md) </span></span>  
 [<span data-ttu-id="15a85-131">rsconfig (utilidad) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="15a85-131">rsconfig Utility &#40;SSRS&#41;</span></span>](../tools/rsconfig-utility-ssrs.md)  
  
  
