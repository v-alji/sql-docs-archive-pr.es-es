---
title: Habilitar los errores remotos (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- remote data source [Reporting Services]
- EnableRemoteError server property
ms.assetid: 5f05022b-d557-43e0-b50a-f5e2a1846b83
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d2a7e7e0b38b38bf563dfc2a8cff65c897c5293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674571"
---
# <a name="enable-remote-errors-reporting-services"></a><span data-ttu-id="a7a31-102">Habilitar los errores remotos (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="a7a31-102">Enable Remote Errors (Reporting Services)</span></span>
  <span data-ttu-id="a7a31-103">Es posible establecer propiedades de servidor en un servidor de informes de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para devolver información adicional sobre condiciones de error que se produzcan en servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="a7a31-103">You can set server properties on a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server to return additional information about error conditions that occur on remote servers.</span></span> <span data-ttu-id="a7a31-104">Si un mensaje de error incluye el texto "Para obtener más información acerca de este error, navegue hasta el servidor de informes en el equipo del servidor local o habilite los errores remotos", puede establecer la propiedad `EnableRemoteErrors` para obtener información adicional que pueda ayudarle a solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="a7a31-104">If an error message contains the text "For more information about this error, navigate to the report server on the local server machine, or enable remote errors", you can set the `EnableRemoteErrors` property to access additional information that can help you troubleshoot the problem.</span></span> <span data-ttu-id="a7a31-105">Para obtener más información, vea [Propiedades del sistema del servidor de informes](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7a31-105">For more information, see [Report Server System Properties](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="a7a31-106">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="a7a31-106">**In this topic:**</span></span>  
  
-   [<span data-ttu-id="a7a31-107">Habilitar errores remotos para el modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="a7a31-107">Enable Remote Errors for SharePoint Mode</span></span>](#bkmk_sharepoint)  
  
-   [<span data-ttu-id="a7a31-108">Habilitar los errores remotos a través de SQL Server Management Studio (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="a7a31-108">Enable remote errors through SQL Server Management Studio (Native Mode)</span></span>](#bkmk_mgtStudio)  
  
-   [<span data-ttu-id="a7a31-109">Habilitar errores remotos mediante scripts (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="a7a31-109">Enable remote errors through script (Native Mode)</span></span>](#bkmk_script)  
  
-   [<span data-ttu-id="a7a31-110">Modificar la tabla ConfigurationInfo (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="a7a31-110">Modifying the ConfigurationInfo table (Native Mode)</span></span>](#bkmk_ConfigurationInfo)  
  
##  <a name="enable-remote-errors-for-sharepoint-mode"></a><a name="bkmk_sharepoint"></a> <span data-ttu-id="a7a31-111">Habilitar errores remotos para el modo de SharePoint</span><span class="sxs-lookup"><span data-stu-id="a7a31-111">Enable Remote Errors for SharePoint Mode</span></span>  
 <span data-ttu-id="a7a31-112">Hay diferentes procedimientos para habilitar errores remotos para el modo de SharePoint de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7a31-112">There are two different procedures for enabling remote errors for [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="a7a31-113">El procedimiento es distinto para las dos arquitecturas diferentes del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a7a31-113">The procedure is different for the two different report server architectures.</span></span> <span data-ttu-id="a7a31-114">El servicio de SharePoint más reciente basado en la arquitectura que se introdujo en la versión de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] usa un valor que se puede configurar para cada aplicación de servicio de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7a31-114">The newer SharePoint service based architecture that was introduced in the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] release, utilizes a setting that can be configured for each [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="a7a31-115">La arquitectura más antigua utiliza un solo valor de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="a7a31-115">The older architecture utilizes a single site level setting.</span></span>  
  
#### <a name="enable-remote-errors-for-a-reporting-services-service-application"></a><span data-ttu-id="a7a31-116">Habilitar errores remotos para una aplicación de servicio de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a7a31-116">Enable Remote errors for a Reporting Services Service Application</span></span>  
  
1.  <span data-ttu-id="a7a31-117">Para un servidor de informes en modo de SharePoint instalado con [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] o una versión más reciente de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], habilite la configuración de aplicación de servicio **Habilitar los errores remotos**.</span><span class="sxs-lookup"><span data-stu-id="a7a31-117">For a SharePoint mode report server installed with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] or a newer version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], enable the service application setting **Enable remote errors**.</span></span> <span data-ttu-id="a7a31-118">El valor se puede configurar para cada aplicación de servicio de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7a31-118">The setting can be configured for each [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
2.  <span data-ttu-id="a7a31-119">En Administración central de SharePoint, en el grupo **Administrar aplicaciones de servicio** , haga clic en **Administración de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="a7a31-119">In SharePoint Central Administration, click **Manage service applications** in the **Application Management** group.</span></span>  
  
3.  <span data-ttu-id="a7a31-120">Encuentre su aplicación de servicio de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y haga clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="a7a31-120">Find your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application and click the name of your service application.</span></span>  
  
4.  <span data-ttu-id="a7a31-121">Haga clic en **Configuración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="a7a31-121">Click **System Settings**.</span></span>  
  
5.  <span data-ttu-id="a7a31-122">Haga clic en **Habilitar errores remotos** en la sección **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="a7a31-122">Click **Enable Remote Errors** in the **Security** section.</span></span>  
  
6.  <span data-ttu-id="a7a31-123">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7a31-123">Click **OK**.</span></span>  
  
#### <a name="enable-remote-errors-for-a-sharepoint-site"></a><span data-ttu-id="a7a31-124">Habilitar errores remotos para un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="a7a31-124">Enable Remote Errors for a SharePoint Site</span></span>  
  
1.  <span data-ttu-id="a7a31-125">Para un servidor de informes en modo de SharePoint instalado con una versión de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] anterior a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], habilite la configuración del sitio **Habilitar los errores remotos en modo local**.</span><span class="sxs-lookup"><span data-stu-id="a7a31-125">For a SharePoint mode report server installed with a version of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] prior to [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], enable the site setting **Enable remote errors in local mode**.</span></span>  
  
2.  <span data-ttu-id="a7a31-126">En **Acciones de sitio** , haga clic en **Configuración del sitio** para el sitio desea modificar.</span><span class="sxs-lookup"><span data-stu-id="a7a31-126">In **Site Actions** click **Site Settings** for the site you want to modify.</span></span>  
  
3.  <span data-ttu-id="a7a31-127">Haga clic en **Configuración del sitio de Reporting Services** en el grupo **Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="a7a31-127">Click **Reporting Services Site Settings** in the **Reporting Services** group.</span></span>  
  
4.  <span data-ttu-id="a7a31-128">Haga clic en **Habilitar los errores remotos en modo local**.</span><span class="sxs-lookup"><span data-stu-id="a7a31-128">Click **Enable remote errors in local mode**.</span></span>  
  
5.  <span data-ttu-id="a7a31-129">Haga clic en **Aceptar**</span><span class="sxs-lookup"><span data-stu-id="a7a31-129">Click **OK**</span></span>  
  
##  <a name="enable-remote-errors-through-sql-server-management-studio-native-mode"></a><a name="bkmk_mgtStudio"></a> <span data-ttu-id="a7a31-130">Habilitar los errores remotos a través de SQL Server Management Studio (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="a7a31-130">Enable remote errors through SQL Server Management Studio (Native Mode)</span></span>  
  
1.  <span data-ttu-id="a7a31-131">Inicie Management Studio y conéctese a una instancia del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a7a31-131">Start Management Studio and connect to a report server instance.</span></span> <span data-ttu-id="a7a31-132">Para obtener más información, vea [Conectar con un servidor de informes en Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a7a31-132">For more information, see [Connect to a Report Server in Management Studio](../tools/connect-to-a-report-server-in-management-studio.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="a7a31-133">Haga clic con el botón derecho en el nodo de servidor de informes y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a7a31-133">Right-click the report server node, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="a7a31-134">Haga clic en **Avanzadas** para abrir la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="a7a31-134">Click **Advanced** to open the properties page.</span></span> <span data-ttu-id="a7a31-135">Para más información, vea [Propiedades del servidor &#40;página Avanzadas&#41;](../tools/server-properties-advanced-page-reporting-services.md) en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7a31-135">For more information, see [Server Properties &#40;Advanced Page&#41; - Reporting Services](../tools/server-properties-advanced-page-reporting-services.md)in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
4.  <span data-ttu-id="a7a31-136">En `EnableRemoteErrors` , seleccione `True` .</span><span class="sxs-lookup"><span data-stu-id="a7a31-136">In `EnableRemoteErrors`, select `True`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="enable-remote-errors-through-script-native-mode"></a><a name="bkmk_script"></a> <span data-ttu-id="a7a31-137">Habilitar errores remotos mediante scripts (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="a7a31-137">Enable remote errors through script (Native Mode)</span></span>  
  
1.  <span data-ttu-id="a7a31-138">Cree un archivo de texto y copie en él el script siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7a31-138">Create a text file and copy the following script into the file.</span></span>  
  
    ```  
    Public Sub Main()  
      Dim P As New [Property]()  
      P.Name = "EnableRemoteErrors"  
      P.Value = True  
      Dim Properties(0) As [Property]  
      Properties(0) = P  
      Try  
        rs.SetSystemProperties(Properties)  
        Console.WriteLine("Remote errors enabled.")  
      Catch SE As SoapException  
        Console.WriteLine(SE.Detail.OuterXml)  
      End Try  
    End Sub  
    ```  
  
2.  <span data-ttu-id="a7a31-139">Guarde el archivo como EnableRemoteErrors.rss.</span><span class="sxs-lookup"><span data-stu-id="a7a31-139">Save the file as EnableRemoteErrors.rss.</span></span>  
  
3.  <span data-ttu-id="a7a31-140">Haga clic en **Inicio**, seleccione **Ejecutar**, escriba **cmd**y haga clic en **Aceptar** para abrir una ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a7a31-140">Click **Start**, point to **Run**, type **cmd**, and click **OK** to open a command prompt window.</span></span>  
  
4.  <span data-ttu-id="a7a31-141">Navegue hasta el directorio en el que se encuentra el archivo .rss que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="a7a31-141">Navigate to the directory that contains the .rss file you just created.</span></span>  
  
5.  <span data-ttu-id="a7a31-142">Escriba la línea de comandos siguiente sustituyendo *servername* por el nombre real del servidor:</span><span class="sxs-lookup"><span data-stu-id="a7a31-142">Type the following command line, replacing *servername* with the actual name of your server:</span></span>  
  
    ```  
    rs -i EnableRemoteErrors.rss -s http://servername/ReportServer  
    ```  
  
6.  <span data-ttu-id="a7a31-143">Para obtener más información, vea [Utilidad RS.exe &#40;SSRS&#41;](../tools/rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a7a31-143">For more information, see [RS.exe Utility &#40;SSRS&#41;](../tools/rs-exe-utility-ssrs.md)</span></span>  
  
##  <a name="modifying-the-configurationinfo-table-native-mode"></a><a name="bkmk_ConfigurationInfo"></a> <span data-ttu-id="a7a31-144">Modificar la tabla ConfigurationInfo (modo nativo)</span><span class="sxs-lookup"><span data-stu-id="a7a31-144">Modifying the ConfigurationInfo table (Native Mode)</span></span>  
  
1.  > [!NOTE]  
    >  <span data-ttu-id="a7a31-145">Puede editar la tabla **ConfigurationInfo** en la base de datos del servidor de informes para establecer `EnableRemoteErrors` en `True` , pero si el servidor de informes se usa activamente, debe usar SQL Server Management Studio o script para modificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="a7a31-145">You can edit the **ConfigurationInfo** table in the report server database to set `EnableRemoteErrors` to `True`, but if the report server is actively used, you should use SQL Server Management Studio or script to modify the settings.</span></span> <span data-ttu-id="a7a31-146">Si modifica el valor de la base de datos, debe reiniciar el servicio de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="a7a31-146">If you modify the setting in the database, you need to restart the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service before the changes take effect.</span></span>  
  
  
