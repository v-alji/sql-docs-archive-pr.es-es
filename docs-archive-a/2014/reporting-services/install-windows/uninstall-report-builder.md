---
title: Desinstalar la versión independiente de Generador de informes (Generador de informes) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 009538c6-4941-4393-b14b-9144cffdbdaf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cda13248d1aa14ee3d57a951872d3ad8ded17da9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675737"
---
# <a name="uninstall-the-stand-alone-version-of-report-builder-report-builder"></a><span data-ttu-id="28a55-102">Desinstalar la versión independiente del Generador de informes (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="28a55-102">Uninstall the Stand-Alone Version of Report Builder (Report Builder)</span></span>
  <span data-ttu-id="28a55-103">Podrá desinstalar la versión independiente del Generador de informes desde el panel de control o la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="28a55-103">You can uninstall the stand-alone version of Report Builder from the control panel or the command line.</span></span> <span data-ttu-id="28a55-104">No podrá desinstalar la versión [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)] del Generador de informes sin desinstalar [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28a55-104">You cannot uninstall the [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)] version of Report Builder without uninstalling [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="28a55-105">La desinstalación del Generador de informes desde la línea de comandos utiliza una sintaxis que es idéntica a la que se utiliza para instalar el Generador de informes, excepto en que se usa la opción /x en lugar de la opción /i.</span><span class="sxs-lookup"><span data-stu-id="28a55-105">Uninstalling Report Builder from the command line uses syntax that is identical to the syntax you use to install Report Builder, except you use the /x option instead of the /i option.</span></span> <span data-ttu-id="28a55-106">Las líneas de comandos para desinstalar también pueden incluir la opción /quiet y otras opciones estándar.</span><span class="sxs-lookup"><span data-stu-id="28a55-106">Command lines for uninstalling can also include the /quiet option and other standard options.</span></span> <span data-ttu-id="28a55-107">Si se ha quitado el paquete de Windows Installer para el Generador de informes (ReportBuilder3_x86.msi), no podrá utilizar con facilidad la línea de comandos para desinstalar el Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="28a55-107">If the Report Builder Windows Installer Package (ReportBuilder3_x86.msi) has been removed, you cannot use the command line easily to uninstall Report Builder.</span></span> <span data-ttu-id="28a55-108">Para obtener información acerca de cómo quitar el Generador de informes utilizando su GUID, consulte la documentación del programa msiexec en la biblioteca de MDSN.</span><span class="sxs-lookup"><span data-stu-id="28a55-108">To learn more about how you might be able to remove Report Builder by using its GUID, see the documentation for the msiexec program in the msdn library.</span></span>  
  
 <span data-ttu-id="28a55-109">Si las carpetas utilizadas por el Generador de informes incluyen archivos personalizados, las carpetas y archivos se conservan cuando se quita el Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="28a55-109">If folders used by Report Builder include custom files, the folders and the files are preserved when Report Builder is removed.</span></span> <span data-ttu-id="28a55-110">Solamente se quitan los archivos del Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="28a55-110">Only the Report Builder files are removed.</span></span>  
  
### <a name="to-uninstall-report-builder-from-the-control-panel"></a><span data-ttu-id="28a55-111">Para desinstalar el Generador de informes desde el panel de control</span><span class="sxs-lookup"><span data-stu-id="28a55-111">To uninstall Report Builder from the control panel</span></span>  
  
1.  <span data-ttu-id="28a55-112">En el menú **Inicio** , haga clic en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="28a55-112">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="28a55-113">En el Panel de control, haga clic en **Programas y características**.</span><span class="sxs-lookup"><span data-stu-id="28a55-113">In the Control Panel, click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="28a55-114">Busque Generador de informes de  en la lista Nombre y haga clic en él.</span><span class="sxs-lookup"><span data-stu-id="28a55-114">Locate [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Builder in the **Name** list and click it.</span></span>  
  
4.  <span data-ttu-id="28a55-115">Haga clic en **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="28a55-115">Click **Uninstall**.</span></span>  
  
5.  <span data-ttu-id="28a55-116">Si se le solicita que confirme la desinstalación del Generador de informes, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="28a55-116">If prompted to confirm the uninstall of Report Builder, click **Yes**.</span></span>  
  
### <a name="to-uninstall-report-builder-from-the-command-line"></a><span data-ttu-id="28a55-117">Para desinstalar el Generador de informes desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="28a55-117">To uninstall Report Builder from the command line</span></span>  
  
1.  <span data-ttu-id="28a55-118">En el menú **Inicio** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="28a55-118">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="28a55-119">En el cuadro de texto **abrir** , escriba`cmd.`</span><span class="sxs-lookup"><span data-stu-id="28a55-119">In the **Open** text box, type `cmd.`</span></span>  
  
3.  <span data-ttu-id="28a55-120">En la ventana del símbolo del sistema, navegue hasta la carpeta con ReportBuilder3_x86.msi.</span><span class="sxs-lookup"><span data-stu-id="28a55-120">In the command prompt window, navigate to the folder with ReportBuilder3_x86.msi.</span></span>  
  
4.  <span data-ttu-id="28a55-121">Escriba una línea de comandos básica similar a esta:</span><span class="sxs-lookup"><span data-stu-id="28a55-121">Type a basic command line such as the following:</span></span>  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v install.log`  
  
 <span data-ttu-id="28a55-122">Si puede, utilice una línea de comandos como la siguiente para incluir el registro:</span><span class="sxs-lookup"><span data-stu-id="28a55-122">If you can to include logging, use a command line such as the following:</span></span>  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v c:\junk\install.log`  
  
1.  <span data-ttu-id="28a55-123">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="28a55-123">Press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a55-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28a55-124">See Also</span></span>  
 <span data-ttu-id="28a55-125">[Instalación, desinstalación y compatibilidad Generador de informes](../install-uninstall-and-report-builder-support.md) </span><span class="sxs-lookup"><span data-stu-id="28a55-125">[Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md) </span></span>  
 [<span data-ttu-id="28a55-126">Instale la versión independiente de Generador de informes &#40;Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="28a55-126">Install the Stand-Alone Version of Report Builder &#40;Report Builder&#41;</span></span>](install-report-builder.md)  
  
  
