---
title: Configurar la autenticación de formularios o personalizada en el servidor de informes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Forms authentication, configuring
- custom authentication [Reporting Services]
ms.assetid: e8601a8f-e66d-4649-8e4d-a46ca20ec7d0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1447e1e695f0e59dbc07b7e19f4df335a1220a97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670260"
---
# <a name="configure-custom-or-forms-authentication-on-the-report-server"></a><span data-ttu-id="9febb-102">Configurar la autenticación de formularios o personalizada en el servidor de informes</span><span class="sxs-lookup"><span data-stu-id="9febb-102">Configure Custom or Forms Authentication on the Report Server</span></span>
  <span data-ttu-id="9febb-103">Reporting Services proporciona una arquitectura extensible que permite conectar módulos de autenticación personalizados o basados en formularios.</span><span class="sxs-lookup"><span data-stu-id="9febb-103">Reporting Services provides an extensible architecture that allows you to plug in custom or forms-based authentication modules.</span></span> <span data-ttu-id="9febb-104">Podría considerar implementar una extensión de autenticación personalizada si los requisitos de implementación no incluyen la seguridad integrada de Windows o la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="9febb-104">You might consider implementing a custom authentication extension if deployment requirements do not include Windows integrated security or Basic authentication.</span></span> <span data-ttu-id="9febb-105">El escenario más común para utilizar la autenticación personalizada es admitir el acceso a una extranet o a Internet en una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="9febb-105">The most common scenario for using custom authentication is to support Internet or extranet access to a Web application.</span></span> <span data-ttu-id="9febb-106">Reemplazar la extensión de autenticación de Windows predeterminada con una extensión de autenticación personalizada le proporciona más control sobre cómo se concede acceso a los usuarios externos al servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9febb-106">Replacing the default Windows Authentication extension with a custom authentication extension gives you more control over how external users are granted access to the report server.</span></span>  
  
 <span data-ttu-id="9febb-107">En la práctica, implementar una extensión de autenticación personalizada requiere varios pasos que incluyen copiar los archivos de aplicación y ensamblados, modificar los archivos de configuración y realizar pruebas.</span><span class="sxs-lookup"><span data-stu-id="9febb-107">In practice, deploying a custom authentication extension requires multiple steps that include copying assemblies and application files, modifying configuration files, and testing.</span></span> <span data-ttu-id="9febb-108">Este tema se centra simplemente en la configuración de autenticación que se especifica en los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="9febb-108">This topic focuses on just the authentication settings that you specify in the configuration files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9febb-109">La creación de una extensión de autenticación personalizada requiere código personalizado y conocimientos sobre la seguridad de [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9febb-109">Creating a custom authentication extension requires custom code and expertise in [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] security.</span></span> <span data-ttu-id="9febb-110">Si no desea crear una extensión de autenticación personalizada, puede utilizar grupos y cuentas de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Active Directory, pero tendrá que reducir en gran parte el ámbito de implementación de un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9febb-110">If you do not want to create a custom authentication extension, you can use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Active Directory groups and accounts, but you should greatly reduce the scope of a report server deployment.</span></span> <span data-ttu-id="9febb-111">Para obtener más información sobre la autenticación personalizada, vea [Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md).</span><span class="sxs-lookup"><span data-stu-id="9febb-111">For more information about custom authentication, see [Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md).</span></span>  
  
 <span data-ttu-id="9febb-112">Además, si desea utilizar una extensión de la autenticación personalizada o de la autenticación de formularios en un entorno de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que esté integrado con un producto de SharePoint, debe configurar el sitio de SharePoint para utilizar el método de autenticación que elija.</span><span class="sxs-lookup"><span data-stu-id="9febb-112">Additionally, if you want to use Forms authentication or a custom authentication extension in a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] environment that is integrated with a SharePoint product, you must configure the SharePoint site to use the authentication method that you choose.</span></span> <span data-ttu-id="9febb-113">Para obtener más información sobre cómo configurar la autenticación en SharePoint, vea [Ejemplos de autenticación](https://go.microsoft.com/fwlink/?LinkId=115575) en [!INCLUDE[msCoName](../../includes/msconame-md.md)] Developer Network (MSDN).</span><span class="sxs-lookup"><span data-stu-id="9febb-113">For more information about configuring authentication in SharePoint, see [Authentication Samples](https://go.microsoft.com/fwlink/?LinkId=115575) on [!INCLUDE[msCoName](../../includes/msconame-md.md)] Developer Network (MSDN).</span></span>  
  
### <a name="to-configure-a-report-server-to-use-custom-authentication"></a><span data-ttu-id="9febb-114">Para configurar un servidor de informes de modo que use la autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="9febb-114">To configure a report server to use Custom authentication</span></span>  
  
1.  <span data-ttu-id="9febb-115">Abra RSReportServer.config en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="9febb-115">Open RSReportServer.config in a text editor.</span></span>  
  
2.  <span data-ttu-id="9febb-116">Busque <`Authentication`>.</span><span class="sxs-lookup"><span data-stu-id="9febb-116">Find <`Authentication`>.</span></span>  
  
3.  <span data-ttu-id="9febb-117">Copie la estructura XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="9febb-117">Copy the following XML structure:</span></span>  
  
    ```  
    <Authentication>  
          <AuthenticationTypes>  
                 <Custom />  
          </AuthenticationTypes>  
          <EnableAuthPersistence>true</EnableAuthPersistence>  
    </Authentication>  
    ```  
  
4.  <span data-ttu-id="9febb-118">Péguelo en las entradas existentes para <`Authentication`>.</span><span class="sxs-lookup"><span data-stu-id="9febb-118">Paste it over the existing entries for <`Authentication`>.</span></span>  
  
     <span data-ttu-id="9febb-119">Observe que no puede utilizar `Custom` con otros tipos de autenticación.</span><span class="sxs-lookup"><span data-stu-id="9febb-119">Note that you cannot use `Custom` with other authentication types.</span></span>  
  
5.  <span data-ttu-id="9febb-120">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="9febb-120">Save the file.</span></span>  
  
6.  <span data-ttu-id="9febb-121">Abra el archivo Web.config para el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9febb-121">Open the Web.config file for the report server.</span></span> <span data-ttu-id="9febb-122">De forma predeterminada, se encuentra en la carpeta \Archivos de programa\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="9febb-122">By default, it is located at \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportServer.</span></span>  
  
7.  <span data-ttu-id="9febb-123">Busque `authentication mode` y establézcalo `Forms` .</span><span class="sxs-lookup"><span data-stu-id="9febb-123">Find `authentication mode` and set it `Forms`.</span></span>  
  
    ```  
    <authentication mode = "Forms" />  
    ```  
  
8.  <span data-ttu-id="9febb-124">Busque `identity impersonate` y establézcalo en `False`.</span><span class="sxs-lookup"><span data-stu-id="9febb-124">Find `identity impersonate` and set it to `False`.</span></span>  
  
    ```  
    <identity impersonate = "false" />  
    ```  
  
9. <span data-ttu-id="9febb-125">Abra el archivo Web.config del Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="9febb-125">Open the Web.config file for Report Manager.</span></span> <span data-ttu-id="9febb-126">De forma predeterminada, se encuentra en la carpeta \Archivos de programa\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportManager.</span><span class="sxs-lookup"><span data-stu-id="9febb-126">By default, it is located at \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportManager.</span></span>  
  
10. <span data-ttu-id="9febb-127">Busque `authentication mode` y establézcalo `Forms` .</span><span class="sxs-lookup"><span data-stu-id="9febb-127">Find `authentication mode` and set it `Forms`.</span></span>  
  
    ```  
    <authentication mode = "Forms" />  
    ```  
  
11. <span data-ttu-id="9febb-128">Busque `identity impersonate` y establézcalo en `False`.</span><span class="sxs-lookup"><span data-stu-id="9febb-128">Find `identity impersonate` and set it to `False`.</span></span>  
  
    ```  
    <identity impersonate = "false" />  
    ```  
  
12. <span data-ttu-id="9febb-129">Agregue la estructura del elemento `PassThroughCookies` al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9febb-129">Add the `PassThroughCookies` element structure to the configuration file.</span></span> <span data-ttu-id="9febb-130">Para obtener más información, vea [Configurar el Administrador de informes para pasar cookies de autenticación personalizada](configure-the-web-portal-to-pass-custom-authentication-cookies.md).</span><span class="sxs-lookup"><span data-stu-id="9febb-130">For more information, see [Configure Report Manager to Pass Custom Authentication Cookies](configure-the-web-portal-to-pass-custom-authentication-cookies.md).</span></span>  
  
13. <span data-ttu-id="9febb-131">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="9febb-131">Save the file.</span></span>  
  
14. <span data-ttu-id="9febb-132">Si configuró una implementación escalada, repita todos los pasos anteriores con los demás servidores de informes de la implementación.</span><span class="sxs-lookup"><span data-stu-id="9febb-132">If you configured a scale-out deployment, repeat all of the previous steps for other report servers in the deployment.</span></span>  
  
15. <span data-ttu-id="9febb-133">Reinicie el servidor de informes para borrar las sesiones que estén abiertas en ese momento.</span><span class="sxs-lookup"><span data-stu-id="9febb-133">Restart the report server to clear any sessions that are currently open.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9febb-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9febb-134">See Also</span></span>  
 <span data-ttu-id="9febb-135">[Implementación de una extensión de seguridad](../extensions/security-extension/implementing-a-security-extension.md) </span><span class="sxs-lookup"><span data-stu-id="9febb-135">[Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md) </span></span>  
 <span data-ttu-id="9febb-136">[Autenticación con el servidor de informes](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="9febb-136">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 <span data-ttu-id="9febb-137">[Archivo de configuración RSReportServer](../report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="9febb-137">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="9febb-138">[Configurar la autenticación básica en el servidor de informes](configure-basic-authentication-on-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="9febb-138">[Configure Basic Authentication on the Report Server](configure-basic-authentication-on-the-report-server.md) </span></span>  
 [<span data-ttu-id="9febb-139">Configuración de la autenticación de Windows en el servidor de informes</span><span class="sxs-lookup"><span data-stu-id="9febb-139">Configure Windows Authentication on the Report Server</span></span>](configure-windows-authentication-on-the-report-server.md)  
  
  
