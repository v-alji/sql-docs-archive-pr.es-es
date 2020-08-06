---
title: Habilitar y deshabilitar la impresión del lado cliente para Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0e709c96-7517-4547-8ef6-5632f8118524
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 031a7cd9b5da07b03b76b6bf49db63572a8fe546
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674573"
---
# <a name="enable-and-disable-client-side-printing-for-reporting-services"></a><span data-ttu-id="9974e-102">Habilitar y deshabilitar la impresión del lado cliente para Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9974e-102">Enable and Disable Client-Side Printing for Reporting Services</span></span>
  <span data-ttu-id="9974e-103">El [!INCLUDE[msCoName](../../includes/msconame-md.md)] control ActiveX, **RSClientPrint**, proporciona la impresión del lado cliente para los informes que se ven en un explorador.</span><span class="sxs-lookup"><span data-stu-id="9974e-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] ActiveX control, **RSClientPrint**, provides client-side printing for reports viewed in a browser.</span></span> <span data-ttu-id="9974e-104">El control muestra un cuadro de diálogo personalizado de impresión que admite características comunes a otros cuadros de diálogo de impresión.</span><span class="sxs-lookup"><span data-stu-id="9974e-104">The control displays a custom print dialog box that supports features common to other print dialog boxes.</span></span> <span data-ttu-id="9974e-105">Entre estas características se incluyen vista previa de impresión, selecciones de página para especificar páginas e intervalos específicos, márgenes de página y orientación.</span><span class="sxs-lookup"><span data-stu-id="9974e-105">The features include print preview, page selections for specifying specific pages and ranges, page margins, and orientation.</span></span> <span data-ttu-id="9974e-106">Aunque la impresión del lado cliente está habilitada de manera predeterminada, puede deshabilitar esta característica para impedir que sea utilizada.</span><span class="sxs-lookup"><span data-stu-id="9974e-106">Although client-side printing is enabled by default, you can disable the feature to prevent it from being used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9974e-107">Para descargar controles ActiveX se requieren permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="9974e-107">Downloading ActiveX controls requires administrator permissions.</span></span>  
  
## <a name="downloading-the-activex-control"></a><span data-ttu-id="9974e-108">Descargar el control ActiveX</span><span class="sxs-lookup"><span data-stu-id="9974e-108">Downloading the ActiveX Control</span></span>  
 <span data-ttu-id="9974e-109">Cada usuario que desee utilizar la función de impresión debe descargar e instalar el control ActiveX que ofrece la funcionalidad de impresión del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="9974e-109">Each user who wants to use the print feature must download and install the ActiveX control that provides client print functionality.</span></span> <span data-ttu-id="9974e-110">La primera vez que un usuario haga clic en el icono de la **impresora** en la barra de herramientas de informe, el control ActiveX de Microsoft se descargará en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9974e-110">The first time a user clicks the **Printer** icon on the report toolbar, the Microsoft ActiveX control is downloaded to the computer.</span></span> <span data-ttu-id="9974e-111">Una vez descargado el control, el cuadro de diálogo **Imprimir** aparece siempre que el usuario hace clic en el icono de la **impresora** .</span><span class="sxs-lookup"><span data-stu-id="9974e-111">After the control is downloaded, the **Print** dialog box displays whenever the user clicks the **Printer** icon.</span></span>  
  
 <span data-ttu-id="9974e-112">En función de la configuración del explorador, es posible que al usuario se le solicite instalar el control, se le impida instalar el control o se le obligue a instalar el control de un modo transparente en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="9974e-112">Depending on browser settings, the user may be prompted to install the control, be prevented from installing the control, or have the control install transparently in the background.</span></span>  
  
 <span data-ttu-id="9974e-113">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, la configuración que afecta a la descarga e instalación del control ActiveX se especifica a través del nodo **controles y** complementos de ActiveX de la página **configuración de seguridad** de la zona de contenido Web.</span><span class="sxs-lookup"><span data-stu-id="9974e-113">For [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, settings that affect ActiveX control download and installation are specified through the **ActiveX controls and plug-ins** node in the **Security Settings** page for the Web content zone.</span></span> <span data-ttu-id="9974e-114">La siguiente configuración determina si los usuarios pueden descargar y ejecutar el control de impresión en función de las preferencias de seguridad de la zona web:</span><span class="sxs-lookup"><span data-stu-id="9974e-114">The following settings determine whether users can download and run the print control, based on Web zone security preferences:</span></span>  
  
-   <span data-ttu-id="9974e-115">Descargar los controles ActiveX firmados.</span><span class="sxs-lookup"><span data-stu-id="9974e-115">Download signed ActiveX controls.</span></span>  
  
-   <span data-ttu-id="9974e-116">Activar script de los controles de ActiveX marcados como seguros.</span><span class="sxs-lookup"><span data-stu-id="9974e-116">Script ActiveX controls marked safe for scripting.</span></span>  
  
-   <span data-ttu-id="9974e-117">Ejecutar los controles y complementos para ActiveX.</span><span class="sxs-lookup"><span data-stu-id="9974e-117">Run ActiveX controls and plug-ins.</span></span>  
  
 <span data-ttu-id="9974e-118">Los usuarios que deseen usar **RSClientPrint** para realizar la impresión del lado cliente deben habilitar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9974e-118">Users who want to use **RSClientPrint** to perform client-side printing must enable the following:</span></span>  
  
-   <span data-ttu-id="9974e-119">**Descargar controles ActiveX firmados** y **crear scripts de control ActiveX marcados como seguros para el scripting** con fines de instalación.</span><span class="sxs-lookup"><span data-stu-id="9974e-119">**Download signed ActiveX controls** and **Script ActiveX control marked safe for scripting** for installation purposes.</span></span>  
  
-   <span data-ttu-id="9974e-120">**Ejecutar controles y complementos de ActiveX** para las operaciones de impresión en curso.</span><span class="sxs-lookup"><span data-stu-id="9974e-120">**Run ActiveX controls and plug-ins** for ongoing print operations.</span></span>  
  
 <span data-ttu-id="9974e-121">El control ActiveX **RSClientPrint** está firmado, lo que significa que contiene un certificado digital válido de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9974e-121">The **RSClientPrint** ActiveX control is signed, meaning it contains a valid digital certificate from [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span></span>  
  
## <a name="enabling-and-disabling-client-side-printing"></a><span data-ttu-id="9974e-122">Habilitar y deshabilitar la impresión de cliente</span><span class="sxs-lookup"><span data-stu-id="9974e-122">Enabling and Disabling Client-Side Printing</span></span>  
 <span data-ttu-id="9974e-123">Los administradores del servidor de informes tienen la opción de deshabilitar la característica de impresión estableciendo la propiedad del sistema del servidor de informes **EnableClientPrinting** en `false` .</span><span class="sxs-lookup"><span data-stu-id="9974e-123">Report server administrators have the option of disabling the print feature by setting the report server system property **EnableClientPrinting** to `false`.</span></span> <span data-ttu-id="9974e-124">De este modo se deshabilitará la impresión del lado cliente para todos los informes administrados por ese servidor.</span><span class="sxs-lookup"><span data-stu-id="9974e-124">This will disable client-side printing for all reports managed by that server.</span></span> <span data-ttu-id="9974e-125">De forma predeterminada, **EnableClientPrinting** se establece en `true` .</span><span class="sxs-lookup"><span data-stu-id="9974e-125">By default, **EnableClientPrinting** is set to `true`.</span></span> <span data-ttu-id="9974e-126">Puede deshabilitar la impresión del lado cliente de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="9974e-126">You can disable client-side printing in the following ways:</span></span>  
  
-   <span data-ttu-id="9974e-127">Para un **servidor de informes en modo nativo**:</span><span class="sxs-lookup"><span data-stu-id="9974e-127">For a **Native mode report server**:</span></span>  
  
    1.  <span data-ttu-id="9974e-128">Inicie [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="9974e-128">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
    2.  <span data-ttu-id="9974e-129">Conéctese a una instancia del servidor de informes en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9974e-129">Connect to a report server instance in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
    3.  <span data-ttu-id="9974e-130">Haga clic con el botón derecho en el nodo del servidor de informes y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9974e-130">Right-click the report server node, and then click **Properties**.</span></span> <span data-ttu-id="9974e-131">Si la opción **Propiedades** está deshabilitada, compruebe que inició [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="9974e-131">If the **Properties** option is disabled, verify you started [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] with administrative privileges.</span></span>  
  
    4.  <span data-ttu-id="9974e-132">Seleccione **Habilitar descarga para el control de impresión de ActiveX client**.</span><span class="sxs-lookup"><span data-stu-id="9974e-132">Select **Enable download for the ActiveX client print control**.</span></span>  
  
    5.  <span data-ttu-id="9974e-133">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="9974e-133">Click **OK**.</span></span>  
  
-   <span data-ttu-id="9974e-134">Para un **servidor de informes en modo de SharePoint**:</span><span class="sxs-lookup"><span data-stu-id="9974e-134">For a **SharePoint mode report server**:</span></span>  
  
    1.  <span data-ttu-id="9974e-135">En Administración central de SharePoint, haga clic en **Administración de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="9974e-135">In SharePoint Central Administration, click **Application Management**.</span></span>  
  
    2.  <span data-ttu-id="9974e-136">Haga clic en **Administrar aplicaciones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="9974e-136">Click **Manage service applications**.</span></span>  
  
    3.  <span data-ttu-id="9974e-137">Haga clic el nombre de la aplicación de servicio de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y, a continuación, haga clic en **Administrar** en la cinta de opciones de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9974e-137">Click the name of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application, and then click **Manage** in the SharePoint ribbon.</span></span>  
  
    4.  <span data-ttu-id="9974e-138">Haga clic en **Configuración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="9974e-138">Click **System Settings**.</span></span>  
  
    5.  <span data-ttu-id="9974e-139">Seleccione **Habilitar la impresión de cliente**.</span><span class="sxs-lookup"><span data-stu-id="9974e-139">Select **Enable Client Printing**.</span></span> <span data-ttu-id="9974e-140">La opción **Habilitar la impresión de cliente** está cerca de la parte inferior de la página.</span><span class="sxs-lookup"><span data-stu-id="9974e-140">The **Enable Client Printing** option is near the bottom of the page.</span></span>  
  
    6.  <span data-ttu-id="9974e-141">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="9974e-141">Click **OK**.</span></span>  
  
-   <span data-ttu-id="9974e-142">Escriba el script o el código para establecer la propiedad del sistema del servidor de informes **EnableClientPrinting** en`false.`</span><span class="sxs-lookup"><span data-stu-id="9974e-142">Write script or code to set the report server system property **EnableClientPrinting** to `false.`</span></span>  
  
 <span data-ttu-id="9974e-143">El siguiente script de ejemplo ilustra un enfoque válido para deshabilitar la impresión de lado cliente.</span><span class="sxs-lookup"><span data-stu-id="9974e-143">The following sample script illustrates one approach for disabling client-side printing.</span></span> <span data-ttu-id="9974e-144">Compile y ejecute el siguiente código de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] para establecer la propiedad **EnableClientPrinting** en **False**.</span><span class="sxs-lookup"><span data-stu-id="9974e-144">Compile and then run the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] code to set the **EnableClientPrinting** property to **False**.</span></span> <span data-ttu-id="9974e-145">Después de ejecutar el código, reinicie IIS.</span><span class="sxs-lookup"><span data-stu-id="9974e-145">After you run the code, restart IIS.</span></span>  
  
### <a name="sample-script"></a><span data-ttu-id="9974e-146">Script de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9974e-146">Sample Script</span></span>  
  
```  
Imports System  
Imports System.Web.Services.Protocols  
Class Sample  
   Public Shared Sub Main()  
Dim rs As New ReportingService()  
      rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
        Dim props(0) As [Property]  
        Dim setProp As New [Property]  
        setProp.Name = "EnableClientPrinting"  
        setProp.Value = "False"   
        props(0) = setProp  
        Try  
            rs.SetSystemProperties(props)  
        Catch ex As System.Web.Services.Protocols.SoapException  
            Console.Write(ex.Detail.InnerXml)  
        Catch e as Exception  
            Console.Write(e.Message)  
        End Try  
    End Sub 'Main  
End Class 'Sample  
```  
  
  
