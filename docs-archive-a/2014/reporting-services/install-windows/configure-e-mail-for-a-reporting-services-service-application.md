---
title: Configurar el correo electrónico para una aplicación de servicio de Reporting Services (SharePoint 2010 y SharePoint 2013) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 38fc34a6-aae7-4dde-9ad2-f1eee0c42a9f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 628122289f8a9d83a307d70a369ab51f8f571c04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674626"
---
# <a name="configure-e-mail-for-a-reporting-services-service-application-sharepoint-2010-and-sharepoint-2013"></a><span data-ttu-id="9b4bf-102">Configurar el correo electrónico para una aplicación de servicio de Reporting Services (SharePoint 2010 y SharePoint 2013)</span><span class="sxs-lookup"><span data-stu-id="9b4bf-102">Configure E-mail for a Reporting Services Service Application (SharePoint 2010 and SharePoint 2013)</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="9b4bf-103">la alerta de datos envía las alertas en mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9b4bf-103">data alerting sends alerts in e-mail messages.</span></span> <span data-ttu-id="9b4bf-104">Para enviar correo electrónico, quizás tenga que configurar la aplicación de servicio de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y modificar la extensión de entrega de correo electrónico para ella.</span><span class="sxs-lookup"><span data-stu-id="9b4bf-104">To send e-mail you may need to configure your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application and you may need to modify the e-mail delivery extension for the service application.</span></span> <span data-ttu-id="9b4bf-105">También se requiere la configuración del correo electrónico si piensa utilizar la extensión de entrega por correo electrónico para la característica de suscripción de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b4bf-105">The e-mail settings are also required if you plan to use the e-mail delivery extension for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] subscription feature.</span></span>  
  
||  
|-|  
|[!INCLUDE[applies](../../includes/applies-md.md)]<span data-ttu-id="9b4bf-106">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo de sharepoint &#124; sharepoint 2010 y sharepoint 2013.</span><span class="sxs-lookup"><span data-stu-id="9b4bf-106">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode &#124; SharePoint 2010 and SharePoint 2013.</span></span>|  
  
### <a name="to-configure-e-mail-for-the-shared-service"></a><span data-ttu-id="9b4bf-107">Para configurar el correo electrónico para el servicio compartido</span><span class="sxs-lookup"><span data-stu-id="9b4bf-107">To configure e-mail for the shared service</span></span>  
  
1.  <span data-ttu-id="9b4bf-108">En Administración central de SharePoint, haga clic en **Administración de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="9b4bf-108">In SharePoint Central Administration, click the **Application Management**.</span></span>  
  
2.  <span data-ttu-id="9b4bf-109">En el grupo **Aplicaciones de servicio** , haga clic en **Administrar aplicaciones de servicio**.</span><span class="sxs-lookup"><span data-stu-id="9b4bf-109">In the **Service Applications** group, click **Manage service applications**.</span></span>  
  
3.  <span data-ttu-id="9b4bf-110">En la lista **Nombre** , haga clic en el nombre de su aplicación de servicio de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b4bf-110">In the **Name** list, click the name of your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
4.  <span data-ttu-id="9b4bf-111">Haga clic en **Configuración de correo electrónico** en la página **Administrar la aplicación de Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="9b4bf-111">Click **E-mail Settings** on the **Manage Reporting Services Application** page.</span></span>  
  
5.  <span data-ttu-id="9b4bf-112">Seleccione **Utilizar servidor SMTP**.</span><span class="sxs-lookup"><span data-stu-id="9b4bf-112">Select **Use SMTP server**.</span></span>  
  
6.  <span data-ttu-id="9b4bf-113">En el cuadro **Servidor SMTP saliente** , escriba el nombre de un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="9b4bf-113">In the **Outbound SMTP server** box, type the name of an SMTP server.</span></span>  
  
7.  <span data-ttu-id="9b4bf-114">En el cuadro **De la dirección** , escriba una dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9b4bf-114">In the **From address** box, type an e-mail address.</span></span>  
  
     <span data-ttu-id="9b4bf-115">Esta dirección es el remitente de todos los mensajes de correo electrónico alertas.</span><span class="sxs-lookup"><span data-stu-id="9b4bf-115">This address is the sender of all alert e-mail messages.</span></span>  
  
     <span data-ttu-id="9b4bf-116">La cuenta del usuario especificada en **De la dirección** debe ser una cuenta administrada que especificó cuando configuró el grupo de aplicaciones para la aplicación de servicio de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b4bf-116">The account of the user specified in **From address** must be a managed account that you specified when you configured the application pool for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="9b4bf-117">Si tiene permiso, puede ver una lista de las cuentas administradas que existen en la página Cuentas de servicio de Administración central de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9b4bf-117">If you have permission, you can view a list of existing managed accounts on the Service Accounts page in SharePoint Central Administration.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="ntlm-authentication"></a><span data-ttu-id="9b4bf-118">Autenticación NTLM</span><span class="sxs-lookup"><span data-stu-id="9b4bf-118">NTLM Authentication</span></span>  
  
1.  <span data-ttu-id="9b4bf-119">Si el entorno de correo electrónico requiere la autenticación NTLM y no permite el acceso anónimo, necesita modificar la configuración de la extensión de entrega por correo electrónico para las aplicaciones de servicio de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b4bf-119">If your email environment requires NTLM authentication and does not allow anonymous access, you need to modify the e-mail delivery extension configuration for your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service applications.</span></span> <span data-ttu-id="9b4bf-120">Cambie **smtpauthenticate** para que use un valor de "2".</span><span class="sxs-lookup"><span data-stu-id="9b4bf-120">Change the **SMTPAuthenticate** to use a value of "2".</span></span> <span data-ttu-id="9b4bf-121">Este valor no se puede cambiar desde la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="9b4bf-121">This value cannot be changed from the user interface.</span></span> <span data-ttu-id="9b4bf-122">En el ejemplo de script de PowerShell siguiente se actualiza la configuración completa de la extensión de entrega por correo electrónico del servidor de informes para la aplicación de servicio denominada "SSRS_TESTAPPLICATION".</span><span class="sxs-lookup"><span data-stu-id="9b4bf-122">The following PowerShell script example, updates the full configuration for the report server e-mail delivery extension for the service application named "SSRS_TESTAPPLICATION".</span></span> <span data-ttu-id="9b4bf-123">Tenga en cuenta que algunos de los nodos enumerados en el script también se pueden establecer desde la interfaz de usuario, por ejemplo la dirección "De".</span><span class="sxs-lookup"><span data-stu-id="9b4bf-123">Note some of the nodes listed in the script can also be set from the user interface, for example the "From" address.</span></span>  
  
    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -like "SSRS_TESTAPPLICATION *"}  
    $emailCfg = Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml
    $emailXml = [xml]$emailCfg
    $emailXml.SelectSingleNode("//SMTPServer").InnerText = "your email server name"  
    $emailXml.SelectSingleNode("//SendUsing").InnerText = "2"  
    $emailXml.SelectSingleNode("//SMTPAuthenticate").InnerText = "2"  
    $emailXml.SelectSingleNode("//From").InnerText = "your FROM email address"  
    Set-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" -ExtensionConfiguration $emailXml.OuterXml  
    ```  
  
2.  <span data-ttu-id="9b4bf-124">Si necesita comprobar el nombre de la aplicación de servicio, ejecute el cmdlet **Get-SPRSServiceApplication** .</span><span class="sxs-lookup"><span data-stu-id="9b4bf-124">If you need to verify the name of your service application, run the **Get-SPRSServiceApplication** cmdlet.</span></span>  
  
    ```powershell
    Get-SPRSServiceApplication  
    ```  
  
3.  <span data-ttu-id="9b4bf-125">En el ejemplo siguiente se devolverán los valores actuales de la extensión de correo electrónico para la aplicación de servicio denominada "SSRS_TESTAPPLICATION".</span><span class="sxs-lookup"><span data-stu-id="9b4bf-125">The following example will return the current values of the e-mail extension for the service application named "SSRS_TESTAPPLICATION".</span></span>  
  
    ```powershell
    $app = get-sprsserviceapplication | Where {$_.name -like "SSRSTEST_APPLICATION*"}  
    Get-SPRSExtension -Identity $app -ExtensionType "Delivery" -Name "Report Server Email" | Select -ExpandProperty ConfigurationXml  
    ```  
  
4.  <span data-ttu-id="9b4bf-126">En el ejemplo siguiente se creará un archivo denominado "emailconfig.txt" con los valores actuales de la extensión de correo electrónico para la aplicación de servicio denominada "SSRS_TESTAPPLICATION".</span><span class="sxs-lookup"><span data-stu-id="9b4bf-126">The following example will create a new file named "emailconfig.txt" with the current values of the e-mail extension for the service application named "SSRS_TESTAPPLICATION"</span></span>  
  
    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -like "SSRS_TESTAPPLICATION*"}  
    Get-SPRSExtension -identity $app -ExtensionType "Delivery" -name "Report Server Email" | Select -ExpandProperty ConfigurationXml | Out-File c:\emailconfig.txt  
    ```
