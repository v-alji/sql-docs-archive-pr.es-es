---
title: Establecer las propiedades del servicio Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, configuring
- Integration Services service, properties
ms.assetid: 3a8ad546-0f58-4b31-ab56-58d6313b1098
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 055eadd9a1d59c59dd40675b142eae480763f6f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751262"
---
# <a name="set-the-properties-of-the-integration-services-service"></a><span data-ttu-id="aaa82-102">Establecer las propiedades del servicio Integration Services</span><span class="sxs-lookup"><span data-stu-id="aaa82-102">Set the Properties of the Integration Services Service</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="aaa82-103">En este tema se describe el servicio de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un servicio Windows para administrar paquetes de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aaa82-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="aaa82-104">admite el servicio para mantener la compatibilidad con versiones anteriores de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aaa82-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="aaa82-105">A partir de [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], puede administrar objetos como paquetes en el servidor de Integration Services.</span><span class="sxs-lookup"><span data-stu-id="aaa82-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="aaa82-106">El servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] administra y supervisa los paquetes de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aaa82-106">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages and monitors packages in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="aaa82-107">La primera vez que se instala [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , el [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] servicio se inicia y el tipo de inicio del servicio se establece en automático.</span><span class="sxs-lookup"><span data-stu-id="aaa82-107">When you first install [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is started and the startup type of the service is set to automatic.</span></span>  
  
 <span data-ttu-id="aaa82-108">Una vez instalado el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , puede establecer sus propiedades mediante el Administrador de configuración de SQL Server o el complemento Servicios de componentes de MMC.</span><span class="sxs-lookup"><span data-stu-id="aaa82-108">After the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service has been installed, you can set the properties of the service by using either SQL Server Configuration Manager or the Services MMC snap-in.</span></span>  
  
 <span data-ttu-id="aaa82-109">Para configurar otras características importantes del servicio, incluidas las ubicaciones donde almacena y administra los paquetes, debe modificar el archivo de configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="aaa82-109">To configure other important features of the service, including the locations where it stores and manages packages, you must modify the configuration file of the service.</span></span> <span data-ttu-id="aaa82-110">Para obtener más información, vea [Configurar el servicio Integration Services &#40;servicio SSIS&#41;](service/integration-services-service-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="aaa82-110">For more information, see [Configuring the Integration Services Service &#40;SSIS Service&#41;](service/integration-services-service-ssis-service.md).</span></span>  
  
### <a name="to-set-properties-of-the-integration-services-service-by-using-sql-server-configuration-manager"></a><span data-ttu-id="aaa82-111">Para establecer las propiedades del servicio Integration Services con el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="aaa82-111">To set properties of the Integration Services service by using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="aaa82-112">En el menú **Inicio** , seleccione **Todos los programas**, **Microsoft SQL Server**, **Herramientas de configuración**y haga clic en **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="aaa82-112">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="aaa82-113">En el complemento **Administrador de configuración de SQL Server** , busque **SQL Server Integration Services** en la lista de servicios, haga clic con el botón derecho en **SQL Server Integration Services**y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="aaa82-113">In the **SQL Server Configuration Manager** snap-in, locate **SQL Server Integration Services** in the list of services, right-click **SQL Server Integration Services**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="aaa82-114">En el cuadro de diálogo **propiedades de SQL Server Integration Services** puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaa82-114">In the **SQL Server Integration Services Properties** dialog box you can do the following:</span></span>  
  
    -   <span data-ttu-id="aaa82-115">Haga clic en la pestaña **Iniciar sesión** para ver la información de inicio de sesión, como el nombre de cuenta.</span><span class="sxs-lookup"><span data-stu-id="aaa82-115">Click the **Log On** tab to view the logon information such as the account name.</span></span>  
  
    -   <span data-ttu-id="aaa82-116">Haga clic en la pestaña **Servicio** para ver información sobre el servicio, como el nombre del equipo host y para especificar el modo de inicio del servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aaa82-116">Click the **Service** tab to view information about the service such as the name of the host computer and to specify the start mode of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="aaa82-117">La pestaña **Avanzadas** no contiene información para el servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aaa82-117">The **Advanced** tab contains no information for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
4.  <span data-ttu-id="aaa82-118">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="aaa82-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="aaa82-119">En el menú **Archivo** , haga clic en **Salir** para cerrar el complemento **Administrador de configuración de SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="aaa82-119">On the **File** menu, click **Exit** to close the **SQL Server Configuration Manager** snap-in.</span></span>  
  
### <a name="to-set-properties-of-the-integration-services-service-by-using-services"></a><span data-ttu-id="aaa82-120">Para establecer las propiedades del servicio Integration Services con el complemento Servicios</span><span class="sxs-lookup"><span data-stu-id="aaa82-120">To set properties of the Integration Services service by using Services</span></span>  
  
1.  <span data-ttu-id="aaa82-121">En el **Panel de control**, si utiliza la Vista clásica, haga clic en **Herramientas administrativas**o bien, si utiliza la Vista por categorías, haga clic en **Rendimiento y mantenimiento** y, a continuación, en **Herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="aaa82-121">In **Control Panel**, if you are using Classic View, click **Administrative Tools**, or, if you are using Category View, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="aaa82-122">Haga clic en **Servicios**.</span><span class="sxs-lookup"><span data-stu-id="aaa82-122">Click **Services**.</span></span>  
  
3.  <span data-ttu-id="aaa82-123">En el complemento **Servicios** , localice **SQL Server Integration Services** en la lista de servicios, haga clic con el botón derecho en **SQL Server Integration Services**y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="aaa82-123">In the **Services** snap-in, locate **SQL Server Integration Services** in the list of services, right-click **SQL Server Integration Services**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="aaa82-124">En el cuadro de diálogo **Propiedades de SQL Server Integration Services** , puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaa82-124">In the **SQL Server Integration Services Properties** dialog box, you can do the following:</span></span>  
  
    -   <span data-ttu-id="aaa82-125">Haga clic en la pestaña **General** . Para habilitar el servicio, seleccione el tipo de inicio manual o automático.</span><span class="sxs-lookup"><span data-stu-id="aaa82-125">Click the **General** tab. To enable the service, select either the manual or automatic startup type.</span></span> <span data-ttu-id="aaa82-126">Para deshabilitar el servicio, seleccione Deshabilitar en el cuadro **Tipo de inicio** .</span><span class="sxs-lookup"><span data-stu-id="aaa82-126">To disable the service, select Disable in the **Startup type** box.</span></span> <span data-ttu-id="aaa82-127">Si el servicio se está ejecutando, no se detendrá al seleccionar Deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="aaa82-127">Selecting Disable does not stop the service if it is currently running.</span></span>  
  
         <span data-ttu-id="aaa82-128">Si el servicio ya está habilitado, puede hacer clic en **Detener** para detenerlo o en **Iniciar** para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="aaa82-128">If the service is already enabled, you can click **Stop** to stop the service, or click **Start** to start the service.</span></span>  
  
    -   <span data-ttu-id="aaa82-129">Haga clic en la pestaña **Iniciar sesión** para ver o editar la información de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="aaa82-129">Click the **Log On** tab to view or edit the logon information.</span></span>  
  
    -   <span data-ttu-id="aaa82-130">Haga clic en la pestaña **Recuperación** para ver las respuestas predeterminadas del equipo a un error en el servicio.</span><span class="sxs-lookup"><span data-stu-id="aaa82-130">Click the **Recovery** tab to view the default computer responses to service failure.</span></span> <span data-ttu-id="aaa82-131">Puede modificar estas opciones para adaptarlas a su entorno.</span><span class="sxs-lookup"><span data-stu-id="aaa82-131">You can modify these options to suit your environment.</span></span>  
  
    -   <span data-ttu-id="aaa82-132">Haga clic en la pestaña **Dependencias** para ver una lista de los servicios dependientes.</span><span class="sxs-lookup"><span data-stu-id="aaa82-132">Click the **Dependencies** tab to view a list of dependent services.</span></span> <span data-ttu-id="aaa82-133">El servicio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no tiene dependencias.</span><span class="sxs-lookup"><span data-stu-id="aaa82-133">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service has no dependencies.</span></span>  
  
5.  <span data-ttu-id="aaa82-134">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="aaa82-134">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="aaa82-135">Opcionalmente, si el tipo de inicio es Manual o Automático, puede hacer clic con el botón derecho en **SQL Server Integration Services** y hacer clic en **Iniciar, Detener o Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="aaa82-135">Optionally, if the startup type is Manual or Automatic, you can right-click **SQL Server Integration Services** and click **Start, Stop, or Restart**.</span></span>  
  
7.  <span data-ttu-id="aaa82-136">En el menú **Archivo** , haga clic en **Salir** para cerrar el complemento **Servicios** .</span><span class="sxs-lookup"><span data-stu-id="aaa82-136">On the **File** menu, click **Exit** to close the **Services** snap-in.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa82-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aaa82-137">See Also</span></span>  
 [<span data-ttu-id="aaa82-138">Administrar el servicio Integration Services</span><span class="sxs-lookup"><span data-stu-id="aaa82-138">Manage the Integration Services Service</span></span>](../../2014/integration-services/manage-the-integration-services-service.md)  
  
  
