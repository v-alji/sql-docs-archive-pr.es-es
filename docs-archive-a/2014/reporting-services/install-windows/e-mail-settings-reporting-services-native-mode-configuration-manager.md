---
title: 'Configuración de correo electrónico: Configuration Manager (modo nativo de SSRS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.rsconfigtool.emailsettings.f1
helpviewer_keywords:
- SQL11.rsconfigtool.emailsettings.F1
ms.assetid: cdad1529-bfa6-41fb-9863-d9ff1b802577
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8c5f276f8d6566e052ee291118eb1d1c12fbddc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746177"
---
# <a name="e-mail-settings---configuration-manager-ssrs-native-mode"></a><span data-ttu-id="6bba7-102">Configuración de correo electrónico - Administrador de configuración (Modo nativo de SSRS)</span><span class="sxs-lookup"><span data-stu-id="6bba7-102">E-mail Settings - Configuration Manager (SSRS Native Mode)</span></span>
  <span data-ttu-id="6bba7-103">Utilice esta página para especificar la configuración del Protocolo simple de transferencia de correo (SMTP) que habilita la entrega de correo electrónico del servidor de informes desde este.</span><span class="sxs-lookup"><span data-stu-id="6bba7-103">Use this page to specify Simple Mail Transport Protocol (SMTP) settings that enable report server e-mail delivery from the report server.</span></span> <span data-ttu-id="6bba7-104">Puede utilizar la extensión de entrega por correo electrónico del servidor de informes para distribuir informes o notificaciones de procesamiento de informes a través de suscripciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6bba7-104">You can use the Report Server E-Mail delivery extension to distribute reports or report processing notifications through e-mail subscriptions.</span></span> <span data-ttu-id="6bba7-105">La extensión de entrega por correo electrónico del servidor de informes requiere un servidor SMTP y una dirección de correo electrónico para el campo De:.</span><span class="sxs-lookup"><span data-stu-id="6bba7-105">The Report Server E-Mail delivery extension requires an SMTP server and an e-mail address to use in the From: field.</span></span>  
  
 <span data-ttu-id="6bba7-106">Se pueden utilizar parámetros de configuración adicionales para personalizar suscripciones por correo electrónico, incluidos los parámetros que restrinjan la disponibilidad de extensiones de representación y hosts del servidor de correo.</span><span class="sxs-lookup"><span data-stu-id="6bba7-106">Additional configuration settings can be used to further customize e-mail subscriptions, including settings that restrict mail server hosts and rendering extension availability.</span></span> <span data-ttu-id="6bba7-107">No se puede especificar esta configuración en el Administrador de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6bba7-107">You cannot specify these settings in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="6bba7-108">Para configurar los parámetros adicionales, debe editar el archivo RSReportServer.config manualmente.</span><span class="sxs-lookup"><span data-stu-id="6bba7-108">To configure the additional settings, you must manually edit the RSReportServer.config file.</span></span> <span data-ttu-id="6bba7-109">Para obtener más información, vea [configurar un servidor de informes para la entrega por correo electrónico &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) y [Reporting Services archivos de configuración en los](../report-server/reporting-services-configuration-files.md) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] libros en pantalla de.</span><span class="sxs-lookup"><span data-stu-id="6bba7-109">For more information, see [Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) and [Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="6bba7-110">Para abrir esta página, inicie la Administrador de configuración de Reporting Services y haga clic en **configuración de correo electrónico** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="6bba7-110">To open this page, start the Reporting Services Configuration Manager and click **E-mail Settings** in the navigation pane.</span></span> <span data-ttu-id="6bba7-111">Para obtener más información, vea [Administrador de configuración de Reporting Services &#40;modo nativo&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="6bba7-111">For more information, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>  
  
 [!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="6bba7-112">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="6bba7-112">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6bba7-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="6bba7-113">Options</span></span>  
 <span data-ttu-id="6bba7-114">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="6bba7-114">**Sender Address**</span></span>  
 <span data-ttu-id="6bba7-115">Especifica la dirección de correo electrónico que se utiliza en el campo De: de un mensaje de correo electrónico generado.</span><span class="sxs-lookup"><span data-stu-id="6bba7-115">Specifies the e-mail address to use in the From: field of a generated e-mail.</span></span> <span data-ttu-id="6bba7-116">Debe especificar una cuenta de usuario que tenga permiso para enviar correo desde el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="6bba7-116">You must specify a user account that has permission to send mail from the SMTP server.</span></span>  
  
 <span data-ttu-id="6bba7-117">**Método de entrega SMTP actual**</span><span class="sxs-lookup"><span data-stu-id="6bba7-117">**Current SMTP Delivery Method**</span></span>  
 <span data-ttu-id="6bba7-118">Especifica que el correo electrónico del servidor de informes se enruta a través de un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="6bba7-118">Specifies that report server e-mail is routed through an SMTP server.</span></span> <span data-ttu-id="6bba7-119">Este es el único método de entrega que puede especificar en el Administrador de configuración de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="6bba7-119">This is the only delivery method that you can specify in the Reporting Services Configuration Manager.</span></span>  
  
 <span data-ttu-id="6bba7-120">Un método de entrega alternativo es utilizar un directorio de recogida del servicio SMTP local.</span><span class="sxs-lookup"><span data-stu-id="6bba7-120">An alternative delivery method is to use a local SMTP service pickup directory.</span></span> <span data-ttu-id="6bba7-121">Puede utilizar este método de entrega si no hay disponible un servicio SMTP de red.</span><span class="sxs-lookup"><span data-stu-id="6bba7-121">You can use this delivery method if a network SMTP service is not available.</span></span> <span data-ttu-id="6bba7-122">Para especificar un directorio de recogida del servicio SMTP local, debe editar el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="6bba7-122">To specify a local SMTP service pickup directory, you must edit the RSReportServer.config file.</span></span> <span data-ttu-id="6bba7-123">Si edita el archivo de configuración para usar un directorio de recogida del servicio SMTP local, el Administrador de configuración de Reporting Services establece la opción **Método de entrega** en *personalizado* para indicar que el método de entrega se especifica en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="6bba7-123">If you edit the configuration file to use a local SMTP service pickup directory, the Reporting Services Configuration Manager sets the **Delivery method** option to *custom* to indicate that the delivery method is specified in the configuration file.</span></span>  
  
 <span data-ttu-id="6bba7-124">En el archivo de configuración, el método de entrega se establece a través del parámetro de configuración `SendUsing`.</span><span class="sxs-lookup"><span data-stu-id="6bba7-124">In the configuration file, the delivery method is set through the `SendUsing` configuration setting.</span></span> <span data-ttu-id="6bba7-125">Para obtener más información sobre cómo especificar la `SendUsing` configuración, vea [configurar un servidor de informes para la entrega por correo electrónico &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6bba7-125">For more information about specifying the `SendUsing` setting, see [Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md).</span></span>  
  
 <span data-ttu-id="6bba7-126">**Servidor SMTP**</span><span class="sxs-lookup"><span data-stu-id="6bba7-126">**SMTP Server**</span></span>  
 <span data-ttu-id="6bba7-127">Especifique el servidor SMTP o la puerta de enlace que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="6bba7-127">Specify the SMTP server or gateway to use.</span></span> <span data-ttu-id="6bba7-128">Puede utilizar un servidor local o un servidor SMTP en la red.</span><span class="sxs-lookup"><span data-stu-id="6bba7-128">You can use a local server or an SMTP server on your network.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bba7-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6bba7-129">See Also</span></span>  
 <span data-ttu-id="6bba7-130">[Configurar un servidor de informes para la entrega por correo electrónico &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="6bba7-130">[Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="6bba7-131">Administrador de configuración de Reporting Services temas de la ayuda F1 &#40;el modo nativo de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6bba7-131">Reporting Services Configuration Manager F1 Help Topics &#40;SSRS Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-f1-help-topics-ssrs-native-mode.md)  
  
  