---
title: Instalar la versión independiente de Generador de informes (Generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6b2291bb-1d20-4d08-81cb-a16dd8e01faf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2ba8c132125f56ad833a71a1c82221e2bf28d13e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674625"
---
# <a name="install-the-stand-alone-version-of-report-builder-report-builder"></a><span data-ttu-id="b225a-102">Instalar la versión independiente del Generador de informes (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="b225a-102">Install the Stand-Alone Version of Report Builder (Report Builder)</span></span>
  <span data-ttu-id="b225a-103">Puede instalar Generador de informes del [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack en el centro de [descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53613) o en una ubicación como una carpeta pública en la que se haya descargado el ReportBuilder3_x86.msi, el paquete de Windows Installer para generador de informes.</span><span class="sxs-lookup"><span data-stu-id="b225a-103">You can install Report Builder from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] feature pack on the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53613) or a location such as public folder to which the ReportBuilder3_x86.msi, the Windows Installer Package for Report Builder, has been downloaded.</span></span>  
  
 <span data-ttu-id="b225a-104">También puede realizar una instalación de línea de comandos del Generador de informes y especificar argumentos para personalizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="b225a-104">You can also perform a command line installation of Report Builder and provide arguments to customize the installation.</span></span> <span data-ttu-id="b225a-105">Además de los parámetros estándar intrínsecos de MSI, puede usar los parámetros personalizados que proporciona el Generador de informes: RBINSTALLDIR y REPORTSERVERURL.</span><span class="sxs-lookup"><span data-stu-id="b225a-105">In addition to the standard MSI intrinsic parameters, you can use the custom parameters that Report Builder provides: RBINSTALLDIR and REPORTSERVERURL.</span></span> <span data-ttu-id="b225a-106">RBINSTALLDIR especifica la carpeta de instalación raíz para el Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="b225a-106">RBINSTALLDIR specifies the root installation folder for Report Builder.</span></span> <span data-ttu-id="b225a-107">REPORTSERVERURL especifica el servidor de informes predeterminado que usa el Generador de informes para guardar los informes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b225a-107">REPORTSERVERURL specifies the default report server that Report Builder uses to save reports on the server.</span></span>  
  
 <span data-ttu-id="b225a-108">Si quiere realizar una instalación completamente silenciosa, sin ninguna interacción con la interfaz de usuario, especifique la opción **/quiet** .</span><span class="sxs-lookup"><span data-stu-id="b225a-108">If you want a completely silent installation, with no user interface interaction at all, specify the **/quiet** option.</span></span> <span data-ttu-id="b225a-109">Por diseño, la marca de la opción quiet suprime los errores de instalación.</span><span class="sxs-lookup"><span data-stu-id="b225a-109">By design, the quiet option flag suppresses installation errors.</span></span> <span data-ttu-id="b225a-110">Por lo tanto, es recomendable que, cuando use la opción quiet, incluya la opción **/l** que especifica el registro.</span><span class="sxs-lookup"><span data-stu-id="b225a-110">It is therefore recommended that you include the **/l** option, which specifies logging, when you use the quiet option.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b225a-111">Las características de seguridad de Windows Vista y Windows 7 exigen permisos elevados para ejecutar operaciones de línea de comandos y solicitarán permiso para ejecutar la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b225a-111">Windows Vista and Windows 7 security features require elevated permissions to run command line operations and will prompt for permission to run the command line.</span></span> <span data-ttu-id="b225a-112">La instalación no es silenciosa.</span><span class="sxs-lookup"><span data-stu-id="b225a-112">The installation is not silent.</span></span> <span data-ttu-id="b225a-113">Para que la instalación sea silenciosa, es necesario ejecutar la línea de comandos como administrador.</span><span class="sxs-lookup"><span data-stu-id="b225a-113">To make the installation silent, you need to run the command line as an administrator.</span></span>  
  
### <a name="to-install-report-builder-from-the-download-site"></a><span data-ttu-id="b225a-114">Instalar Generador de informes desde el sitio de descarga</span><span class="sxs-lookup"><span data-stu-id="b225a-114">To install Report Builder from the download site</span></span>  
  
1.  <span data-ttu-id="b225a-115">Vaya a [Microsoft SQL Server 2012 generador de informes](https://go.microsoft.com/fwlink/?LinkID=219138) y busque la sección generador de informes de la Página Web.</span><span class="sxs-lookup"><span data-stu-id="b225a-115">Go to [Microsoft SQL Server 2012 Report Builder](https://go.microsoft.com/fwlink/?LinkID=219138) and locate the Report Builder section of the Web page.</span></span>  
  
2.  <span data-ttu-id="b225a-116">Haga clic en **paquete x86**.</span><span class="sxs-lookup"><span data-stu-id="b225a-116">Click **X86 Package**.</span></span>  
  
3.  <span data-ttu-id="b225a-117">En el cuadro de diálogo **descarga de archivos** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b225a-117">In the **File Download** dialog box, click **Run**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b225a-118">Descargue solo archivos de fuentes de confianza.</span><span class="sxs-lookup"><span data-stu-id="b225a-118">Download only files from trusted sources.</span></span>  
  
4.  <span data-ttu-id="b225a-119">En el cuadro de diálogo Internet Explorer, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b225a-119">In the Internet Explorer dialog box, click **Run**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b225a-120">Ejecute solo archivos de fuentes de confianza.</span><span class="sxs-lookup"><span data-stu-id="b225a-120">Run only files from trusted sources.</span></span>  
  
5.  <span data-ttu-id="b225a-121">Se iniciará el Asistente del Generador de informes de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b225a-121">The Microsoft SQL Server Report Builder Wizard is launched.</span></span>  
  
6.  <span data-ttu-id="b225a-122">En la página **Bienvenido al Asistente para la instalación** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b225a-122">On the **Welcome to the Installation Wizard** page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="b225a-123">En la página **contrato de licencia** , lea el contrato y, a continuación, seleccione la opción acepto **los términos del contrato de licencia** .</span><span class="sxs-lookup"><span data-stu-id="b225a-123">On the **License Agreement** page, read the agreement and then select the **I accept the terms in the license agreement** option.</span></span> <span data-ttu-id="b225a-124">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b225a-124">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="b225a-125">Especifique su nombre y el nombre de su compañía.</span><span class="sxs-lookup"><span data-stu-id="b225a-125">Provide your personal name and company name.</span></span> <span data-ttu-id="b225a-126">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b225a-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="b225a-127">En la página **selección de características** , puede hacer clic en **examinar** o en el costo del **disco**.</span><span class="sxs-lookup"><span data-stu-id="b225a-127">On the **Feature Selection** page, optionally click **Browse** or **Disk Cost**.</span></span> <span data-ttu-id="b225a-128">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b225a-128">Click **Next**.</span></span>  
  
    -   <span data-ttu-id="b225a-129">Haga clic en **examinar** para ver la ubicación predeterminada de generador de informes y actualizarla.</span><span class="sxs-lookup"><span data-stu-id="b225a-129">Click **Browse** to see the default location of Report Builder and update it.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b225a-130">La carpeta de instalación predeterminada para Generador de informes es \<drive> archivos de programa\microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b225a-130">The default installation folder for Report Builder is \<drive>Program Files\Microsoft SQL Server.</span></span>  
  
    -   <span data-ttu-id="b225a-131">Haga clic en **costo del disco** para obtener información sobre el espacio en disco que consume generador de informes.</span><span class="sxs-lookup"><span data-stu-id="b225a-131">Click **Disk Cost** to learn how much disk space Report Builder consumes.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b225a-132">Si un volumen no tiene suficiente espacio disponible en disco, se muestra resaltado.</span><span class="sxs-lookup"><span data-stu-id="b225a-132">If a volume does not have sufficient amount of free disk space, the volume is highlighted.</span></span>  
  
10. <span data-ttu-id="b225a-133">En la página **Servidor de destino predeterminado** , puede especificar la dirección URL al servidor de informes de destino si difiere del valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b225a-133">On the **Default Target Server** page, optionally provide the URL to the target report server if it is different from the default.</span></span> <span data-ttu-id="b225a-134">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b225a-134">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b225a-135">Si tiene previsto trabajar con el Generador de informes cuando esté conectado a un servidor de informes, conviene que especifique en este momento la dirección URL al servidor.</span><span class="sxs-lookup"><span data-stu-id="b225a-135">If you plan to work with Report Builder when it is connected to a report server, it is convenient to provide the URL to the server at this time.</span></span> <span data-ttu-id="b225a-136">Sin embargo, también puede hacerlo desde el cuadro de diálogo **Opciones** cuando esté trabajando en generador de informes.</span><span class="sxs-lookup"><span data-stu-id="b225a-136">However, you can also do this from the **Options** dialog box when you are working in Report Builder.</span></span>  
  
11. <span data-ttu-id="b225a-137">Haga clic en **instalar** para completar la instalación de generador de informes.</span><span class="sxs-lookup"><span data-stu-id="b225a-137">Click **Install** to complete the installation of Report Builder.</span></span>  
  
### <a name="to-install-report-builder-from-a-share"></a><span data-ttu-id="b225a-138">Instalar el Generador de informes desde un recurso compartido</span><span class="sxs-lookup"><span data-stu-id="b225a-138">To install Report Builder from a share</span></span>  
  
1.  <span data-ttu-id="b225a-139">Póngase en contacto con el administrador para obtener información sobre la ubicación del archivo ReportBuilder3_x86.msi.msi que necesitará ejecutar para instalar el Generador de informes en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="b225a-139">Contact your administrator for the location of ReportBuilder3_x86.msi.msi that you run to install Report Builder on your local computer.</span></span>  
  
2.  <span data-ttu-id="b225a-140">Busque el archivo ReportBuilder3_x86.msi.msi, que es el paquete de Windows Installer (MSI) para el Generador de informes, y haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="b225a-140">Browse to locate the ReportBuilder3_x86.msi.msi, the Windows Installer Package (MSI) for Report Builder, and click it.</span></span>  
  
     <span data-ttu-id="b225a-141">Se iniciará el Asistente del Generador de informes de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b225a-141">The Microsoft SQL Server Report Builder Wizard is launched.</span></span>  
  
3.  <span data-ttu-id="b225a-142">En la página **Bienvenido al Asistente para la instalación** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b225a-142">On the **Welcome to the Installation Wizard** page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="b225a-143">En la página **contrato de licencia** , lea el contrato y, a continuación, seleccione la opción acepto **los términos del contrato de licencia** .</span><span class="sxs-lookup"><span data-stu-id="b225a-143">On the **License Agreement** page, read the agreement and then select the **I accept the terms in the license agreement** option.</span></span> <span data-ttu-id="b225a-144">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b225a-144">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="b225a-145">Especifique su nombre y el nombre de su compañía.</span><span class="sxs-lookup"><span data-stu-id="b225a-145">Provide your personal name and company name.</span></span> <span data-ttu-id="b225a-146">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b225a-146">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="b225a-147">En la página **selección de características** , puede hacer clic en **examinar** o en el costo del **disco**.</span><span class="sxs-lookup"><span data-stu-id="b225a-147">On the **Feature Selection** page, optionally click **Browse** or **Disk Cost**.</span></span> <span data-ttu-id="b225a-148">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b225a-148">Click **Next**.</span></span>  
  
    -   <span data-ttu-id="b225a-149">Haga clic en **examinar** para ver la ubicación predeterminada de generador de informes y actualizarla.</span><span class="sxs-lookup"><span data-stu-id="b225a-149">Click **Browse** to see the default location of Report Builder and update it.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b225a-150">La carpeta de instalación predeterminada para Generador de informes es \<drive> archivos de programa\microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b225a-150">The default installation folder for Report Builder is \<drive>Program Files\Microsoft SQL Server.</span></span>  
  
    -   <span data-ttu-id="b225a-151">Haga clic en **costo del disco** para obtener información sobre el espacio en disco que consume generador de informes.</span><span class="sxs-lookup"><span data-stu-id="b225a-151">Click **Disk Cost** to learn how much disk space Report Builder consumes.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b225a-152">Si un volumen no tiene suficiente espacio disponible en disco, se muestra resaltado.</span><span class="sxs-lookup"><span data-stu-id="b225a-152">If a volume does not have sufficient amount of free disk space, the volume is highlighted.</span></span>  
  
7.  <span data-ttu-id="b225a-153">En la página **Servidor de destino predeterminado** , puede especificar la dirección URL al servidor de informes de destino si difiere del valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b225a-153">On the **Default Target Server** page, optionally provide the URL to the target report server if it is different from the default.</span></span> <span data-ttu-id="b225a-154">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="b225a-154">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b225a-155">Si tiene previsto trabajar con el Generador de informes cuando esté conectado a un servidor de informes, conviene que especifique en este momento la dirección URL al servidor.</span><span class="sxs-lookup"><span data-stu-id="b225a-155">If you plan to work with Report Builder when it is connected to a report server, it is convenient to provide the URL to the server at this time.</span></span> <span data-ttu-id="b225a-156">Sin embargo, también puede hacerlo desde el cuadro de diálogo **Opciones** cuando esté trabajando en generador de informes.</span><span class="sxs-lookup"><span data-stu-id="b225a-156">However, you can also do this from the **Options** dialog box when you are working in Report Builder.</span></span>  
  
8.  <span data-ttu-id="b225a-157">Haga clic en **instalar** para completar la instalación de generador de informes.</span><span class="sxs-lookup"><span data-stu-id="b225a-157">Click **Install** to complete the installation of Report Builder.</span></span>  
  
### <a name="to-install-report-builder-from-the-command-line"></a><span data-ttu-id="b225a-158">Instalar el Generador de informes desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b225a-158">To install Report Builder from the command line</span></span>  
  
1.  <span data-ttu-id="b225a-159">Vaya a [Microsoft SQL Server 2012 generador de informes](https://go.microsoft.com/fwlink/?LinkID=219138) y busque la sección generador de informes.</span><span class="sxs-lookup"><span data-stu-id="b225a-159">Go to [Microsoft SQL Server 2012 Report Builder](https://go.microsoft.com/fwlink/?LinkID=219138) and locate the Report Builder section.</span></span>  
  
2.  <span data-ttu-id="b225a-160">Haga clic en **paquete x86**.</span><span class="sxs-lookup"><span data-stu-id="b225a-160">Click **X86 Package**.</span></span>  
  
3.  <span data-ttu-id="b225a-161">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b225a-161">Click Save.</span></span>  
  
4.  <span data-ttu-id="b225a-162">Opcionalmente, vaya a la ubicación en la que se va a guardar, compruebe que la opción **Guardar como** está **Windows Installer paquete**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b225a-162">Optionally, browse to the location to save to, verify the **Save as** option is **Windows Installer Package**, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="b225a-163">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b225a-163">On the **Start** menu, click **Run**.</span></span>  
  
6.  <span data-ttu-id="b225a-164">En el cuadro de texto Abrir, escriba `cmd.`</span><span class="sxs-lookup"><span data-stu-id="b225a-164">In the Open text box, type `cmd.`</span></span>  
  
7.  <span data-ttu-id="b225a-165">En la ventana del Símbolo del sistema, navegue hasta la carpeta en la que guardó ReportBuilder3_x86.msi.</span><span class="sxs-lookup"><span data-stu-id="b225a-165">In the Command Prompt window, navigate to the folder where you saved ReportBuilder3_x86.msi.</span></span>  
  
8.  <span data-ttu-id="b225a-166">Escriba un comando con el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="b225a-166">Type a command with the following format:</span></span>  
  
     `msiexec/i ReportBuilder3_.msi /option [value] [/option [value]]`  
  
     <span data-ttu-id="b225a-167">Las dos opciones específicas para la instalación del Generador de informes son: RBINSTALLDIR y REPORTSERVERURL.</span><span class="sxs-lookup"><span data-stu-id="b225a-167">The two options specific to installing Report Builder are: RBINSTALLDIR and REPORTSERVERURL.</span></span> <span data-ttu-id="b225a-168">No se requiere que incluya estos argumentos en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b225a-168">It not required that you include these arguments in the command line.</span></span> <span data-ttu-id="b225a-169">El siguiente es el comando de línea base:</span><span class="sxs-lookup"><span data-stu-id="b225a-169">The following is the baseline command:</span></span>  
  
     `msiexec /i ReportBuilder3_x86.msi /quiet`  
  
9. <span data-ttu-id="b225a-170">Para ejecutar el comando, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="b225a-170">To run the command, press Enter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b225a-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b225a-171">See Also</span></span>  
 <span data-ttu-id="b225a-172">[Instalación, desinstalación y compatibilidad Generador de informes](../install-uninstall-and-report-builder-support.md) </span><span class="sxs-lookup"><span data-stu-id="b225a-172">[Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md) </span></span>  
 [<span data-ttu-id="b225a-173">Desinstale la versión independiente de Generador de informes &#40;Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="b225a-173">Uninstall the Stand-Alone Version of Report Builder &#40;Report Builder&#41;</span></span>](install-report-builder.md)  
  
  
