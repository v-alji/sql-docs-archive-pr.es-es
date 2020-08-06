---
title: Controlar la distribución de informes | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], report distribution
- subscriptions [Reporting Services], e-mail
- subscriptions [Reporting Services], file share delivery
- file share delivery [Reporting Services]
- e-mail [Reporting Services]
- subscriptions [Reporting Services], security
- mail [Reporting Services]
ms.assetid: 8f15e2c6-a647-4b05-a519-1743b5d8654c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: de8a27801ef89f10bf303cee17d1c2d0e1081c5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661816"
---
# <a name="control-report-distribution"></a><span data-ttu-id="648f9-102">Controlar la distribución de informes</span><span class="sxs-lookup"><span data-stu-id="648f9-102">Control Report Distribution</span></span>
  <span data-ttu-id="648f9-103">Puede configurar un servidor de informes para reducir los riesgos de seguridad asociados a la distribución por correo electrónico y a recursos compartidos de archivos.</span><span class="sxs-lookup"><span data-stu-id="648f9-103">You can configure a report server to reduce the security risks associated with e-mail and file share distribution.</span></span>  
  
## <a name="securing-reports"></a><span data-ttu-id="648f9-104">Proteger informes</span><span class="sxs-lookup"><span data-stu-id="648f9-104">Securing Reports</span></span>  
 <span data-ttu-id="648f9-105">El primer paso para controlar la distribución de informes consiste en proteger el informe contra accesos no autorizados.</span><span class="sxs-lookup"><span data-stu-id="648f9-105">The first step in controlling report distribution is to secure the report against unauthorized access.</span></span> <span data-ttu-id="648f9-106">Para poder utilizarse en una suscripción, el informe debe utilizar un conjunto almacenado de credenciales que no varíen para las entregas individuales.</span><span class="sxs-lookup"><span data-stu-id="648f9-106">To be used in a subscription, a report must use a stored set of credentials that do not vary for individual deliveries.</span></span> <span data-ttu-id="648f9-107">Cualquier usuario con acceso al informe en el servidor de informes puede ejecutarlo y posiblemente distribuirlo.</span><span class="sxs-lookup"><span data-stu-id="648f9-107">Any user who can access the report on the report server can run it and possibly distribute it.</span></span> <span data-ttu-id="648f9-108">Para impedir que esto ocurra, debe limitar el acceso al informe únicamente a aquellos usuarios que lo necesiten.</span><span class="sxs-lookup"><span data-stu-id="648f9-108">To prevent this from occurring, you must limit report access to only those users who require it.</span></span> <span data-ttu-id="648f9-109">Para obtener más información, consulte [proteger informes y recursos](security/secure-reports-and-resources.md) y [carpetas seguras](security/secure-folders.md).</span><span class="sxs-lookup"><span data-stu-id="648f9-109">For more information, see [Secure Reports and Resources](security/secure-reports-and-resources.md) and [Secure Folders](security/secure-folders.md).</span></span>  
  
 <span data-ttu-id="648f9-110">Los informes extremadamente confidenciales que utilicen la seguridad de base de datos para autorizar el acceso no pueden distribuirse mediante una suscripción.</span><span class="sxs-lookup"><span data-stu-id="648f9-110">Highly confidential reports that use database security to authorize access cannot be distributed by way of subscription.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="648f9-111">Los informes se transportan como archivos.</span><span class="sxs-lookup"><span data-stu-id="648f9-111">Reports are transported as files.</span></span> <span data-ttu-id="648f9-112">Los riesgos y las medidas de seguridad que se aplican a los archivos se aplican igualmente a los informes que se guardan en disco o se envían como datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="648f9-112">The risks and safeguards that apply to files apply equally to reports that are saved to disk or sent as attachments.</span></span> <span data-ttu-id="648f9-113">Cualquier usuario con acceso a un archivo puede distribuirlo o utilizarlo como desee.</span><span class="sxs-lookup"><span data-stu-id="648f9-113">Any user who has access to a file can distribute or use the file at his or her discretion.</span></span>  
  
## <a name="controlling-e-mail-delivery"></a><span data-ttu-id="648f9-114">Controlar la entrega por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="648f9-114">Controlling E-Mail Delivery</span></span>  
 <span data-ttu-id="648f9-115">Puede configurar un servidor de informes para limitar la distribución por correo electrónico a dominios de host específicos.</span><span class="sxs-lookup"><span data-stu-id="648f9-115">You can configure a report server to limit e-mail distribution to specific host domains.</span></span> <span data-ttu-id="648f9-116">Por ejemplo, puede evitar que un servidor de informes entregue un informe a todos los dominios, excepto a los que figuran en el archivo de configuración RSReportServer.</span><span class="sxs-lookup"><span data-stu-id="648f9-116">For example, you can prevent a report server from delivering a report to all domains except those listed in the RSReportServer configuration file.</span></span>  
  
 <span data-ttu-id="648f9-117">También puede establecer los parámetros de configuración para ocultar el campo **Para** en una suscripción.</span><span class="sxs-lookup"><span data-stu-id="648f9-117">You can also set configuration settings to hide the **To** field in a subscription.</span></span> <span data-ttu-id="648f9-118">En este caso, los informes solo se entregan al usuario que haya definido la suscripción.</span><span class="sxs-lookup"><span data-stu-id="648f9-118">In this case, reports are delivered only to the user defining the subscription.</span></span> <span data-ttu-id="648f9-119">No obstante, una vez que se envíe un informe a un usuario, no puede impedir explícitamente que se reenvíe.</span><span class="sxs-lookup"><span data-stu-id="648f9-119">However, after a report is sent to a user, you cannot explicitly prevent it from being forwarded.</span></span>  
  
 <span data-ttu-id="648f9-120">El método más eficaz de controlar la distribución de informes consiste en configurar el servidor de informes para que solo envíe una dirección URL de servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="648f9-120">The most effective way to control report distribution is to configure a report server to send only a report server URL.</span></span> <span data-ttu-id="648f9-121">El servidor de informes utiliza Autenticación de Windows y un modelo de autorización basada en roles para controlar el acceso a un informe.</span><span class="sxs-lookup"><span data-stu-id="648f9-121">The report server uses Windows Authentication and a role-based authorization model to control access to a report.</span></span> <span data-ttu-id="648f9-122">Si un usuario recibe accidentalmente mediante el correo electrónico un informe que no está autorizado para ver, el servidor de informes no lo mostrará.</span><span class="sxs-lookup"><span data-stu-id="648f9-122">If a user accidentally receives through e-mail a report that he or she is not authorized to view, the report server will not display the report.</span></span>  
  
## <a name="controlling-file-share-delivery"></a><span data-ttu-id="648f9-123">Controlar la entrega a recursos compartidos de archivos</span><span class="sxs-lookup"><span data-stu-id="648f9-123">Controlling File Share Delivery</span></span>  
 <span data-ttu-id="648f9-124">La entrega a recursos compartidos de archivos se utiliza para enviar un informe a un archivo de un disco duro.</span><span class="sxs-lookup"><span data-stu-id="648f9-124">File share delivery is used to send a report to a file on a hard disk.</span></span> <span data-ttu-id="648f9-125">Una vez que el archivo se ha guardado en un disco, ya no está sujeto al modelo de seguridad basada en roles que utiliza el servidor de informes para controlar el acceso de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="648f9-125">After the file has been saved to disk, it is no longer subject to the role-based security model that the report server uses to control user access.</span></span> <span data-ttu-id="648f9-126">Para proteger un informe que se haya entregado a un disco, puede utilizar listas de control de acceso (ACL) en el archivo en sí o en la carpeta que lo contenga.</span><span class="sxs-lookup"><span data-stu-id="648f9-126">To secure a report that has been delivered to disk, you can place Access Control Lists (ACLs) on the file itself or on the folder that contains it.</span></span> <span data-ttu-id="648f9-127">Según el sistema operativo que utilice, es posible que existan opciones de seguridad adicionales.</span><span class="sxs-lookup"><span data-stu-id="648f9-127">Additional security options might be available, depending on your operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="648f9-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="648f9-128">See Also</span></span>  
 <span data-ttu-id="648f9-129">[Configurar un servidor de informes para la entrega por correo electrónico &#40;SSRS Configuration Manager&#41;](../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="648f9-129">[Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="648f9-130">[Suscripciones y entrega &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="648f9-130">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 [<span data-ttu-id="648f9-131">Creación y administración de suscripciones para servidores de informes en modo nativo</span><span class="sxs-lookup"><span data-stu-id="648f9-131">Create and Manage Subscriptions for Native Mode Report Servers</span></span>](../../2014/reporting-services/create-manage-subscriptions-native-mode-report-servers.md)  
  
  
