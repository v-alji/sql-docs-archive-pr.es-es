---
title: Información general de extensiones de seguridad | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
ms.assetid: 24ccd795-6506-457c-93ac-6a9dd6bb9a46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9cd6c2a1518b724a7faafecdb2926505694e9707
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673504"
---
# <a name="security-extensions-overview"></a><span data-ttu-id="a5dba-102">Información general de extensiones de seguridad</span><span class="sxs-lookup"><span data-stu-id="a5dba-102">Security Extensions Overview</span></span>
  <span data-ttu-id="a5dba-103">Una extensión de seguridad [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] permite la autenticación y autorización de usuarios o grupos; es decir, les permite a usuarios diferentes iniciar sesión en un servidor de informes y, en función de sus identidades, realizar tareas u operaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="a5dba-103">A [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security extension enables the authentication and authorization of users or groups; that is, it enables different users to log on to a report server and, based on their identities, perform different tasks or operations.</span></span> <span data-ttu-id="a5dba-104">De forma predeterminada, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] utiliza una extensión de autenticación basada en Windows que utiliza los protocolos de cuenta de Windows para comprobar las identidades de los usuarios que indican que tienen cuentas en el sistema.</span><span class="sxs-lookup"><span data-stu-id="a5dba-104">By default, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a Windows-based authentication extension, which uses Windows account protocols to verify the identities of users who claim to have accounts on the system.</span></span> [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="a5dba-105">utiliza un sistema de seguridad basada en roles para autorizar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a5dba-105">uses a role-based security system to authorize users.</span></span> <span data-ttu-id="a5dba-106">El modelo de seguridad basado en roles [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] es similar a los modelos de seguridad basados en roles de otras tecnologías.</span><span class="sxs-lookup"><span data-stu-id="a5dba-106">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] role-based security model is similar to the role-based security models of other technologies.</span></span>

 <span data-ttu-id="a5dba-107">Dado que las extensiones de seguridad están basadas en una API abierta y extensible, puede crear nuevas extensiones de autenticación y de autorización en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5dba-107">Because security extensions are based on an open and extensible API, you can create new authentication and authorization extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="a5dba-108">El siguiente es un ejemplo de una implementación de extensión de seguridad típica que utiliza la autenticación y autorización basadas en formularios:</span><span class="sxs-lookup"><span data-stu-id="a5dba-108">The following is an example of a typical security extension implementation that uses Forms-based authentication and authorization:</span></span>

 <span data-ttu-id="a5dba-109">![Proceso de extensión de seguridad de Reporting Services](../../media/rosettasecurityextensionflow.gif "Proceso de extensión de seguridad de Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="a5dba-109">![Reporting Services security extension process](../../media/rosettasecurityextensionflow.gif "Reporting Services security extension process")</span></span>

 <span data-ttu-id="a5dba-110">Como se muestra en la ilustración, la autenticación y autorización se producen como sigue:</span><span class="sxs-lookup"><span data-stu-id="a5dba-110">As shown in the illustration, authentication and authorization occur as follows:</span></span>

1.  <span data-ttu-id="a5dba-111">Un usuario intenta tener acceso al Administrador de informes utilizando una URL y se le redirige a un formulario que recopila las credenciales del usuario para la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="a5dba-111">A user tries to access Report Manager by using a URL and is redirected to a form that collects user credentials for the client application.</span></span>

2.  <span data-ttu-id="a5dba-112">El usuario envía las credenciales al formulario.</span><span class="sxs-lookup"><span data-stu-id="a5dba-112">The user submits credentials to the form.</span></span>

3.  <span data-ttu-id="a5dba-113">Las credenciales del usuario se envían al servicio web de Reporting Services a través del método <xref:ReportService2010.ReportingService2010.LogonUser%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5dba-113">The user credentials are submitted to the Reporting Services Web service through the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method.</span></span>

4.  <span data-ttu-id="a5dba-114">El servicio web llama la extensión de seguridad proporcionada por el cliente y comprueba que el nombre de usuario y la contraseña existen en la entidad de seguridad personalizada.</span><span class="sxs-lookup"><span data-stu-id="a5dba-114">The Web service calls the customer-supplied security extension and verifies that the user name and password exist in the custom security authority.</span></span>

5.  <span data-ttu-id="a5dba-115">Después de la autenticación, el servicio web crea un vale de autenticación (conocido como una "cookie"), administra el vale y comprueba el rol del usuario para la página Inicio de Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="a5dba-115">After authentication, the Web service creates an authentication ticket (known as a "cookie"), manages the ticket, and verifies the user's role for the Home page of Report Manager.</span></span>

6.  <span data-ttu-id="a5dba-116">El servicio web devuelve la cookie al explorador y muestra la interfaz de usuario adecuada en Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="a5dba-116">The Web service returns the cookie to the browser and displays the appropriate user interface in Report Manager.</span></span>

7.  <span data-ttu-id="a5dba-117">Una vez autenticado el usuario, el explorador realiza las solicitudes a Administrador de informes a la vez que transmite la cookie en el encabezado HTTP.</span><span class="sxs-lookup"><span data-stu-id="a5dba-117">After the user is authenticated, the browser makes requests to Report Manager while transmitting the cookie in the HTTP header.</span></span> <span data-ttu-id="a5dba-118">Estas solicitudes son una respuesta a las acciones del usuario dentro de la aplicación Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="a5dba-118">These requests are in response to user actions within the Report Manager application.</span></span>

8.  <span data-ttu-id="a5dba-119">La cookie se transmite en el encabezado HTTP al servicio web junto con la operación del usuario solicitada.</span><span class="sxs-lookup"><span data-stu-id="a5dba-119">The cookie is transmitted in the HTTP header to the Web service along with the requested user operation.</span></span>

9. <span data-ttu-id="a5dba-120">La cookie se valida y si es válida, el servidor de informes devuelve el descriptor de seguridad y otra información relativa a la operación solicitada desde la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a5dba-120">The cookie is validated, and if it is valid, the report server returns the security descriptor and other information relating to the requested operation from the report server database.</span></span>

10. <span data-ttu-id="a5dba-121">Si la cookie es válida, el servidor de informes realiza una llamada a la extensión de seguridad para comprobar si el usuario está autorizado para realizar la operación concreta.</span><span class="sxs-lookup"><span data-stu-id="a5dba-121">If the cookie is valid, the report server makes a call to the security extension to check if the user is authorized to perform the specific operation.</span></span>

11. <span data-ttu-id="a5dba-122">Si el usuario está autorizado, el servidor de informes realiza la operación solicitada y devuelve el control al autor de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="a5dba-122">If the user is authorized, the report server performs the requested operation and returns control to the caller.</span></span>

12. <span data-ttu-id="a5dba-123">Una vez autenticado el usuario, el acceso URL al servidor de informes utiliza la misma cookie.</span><span class="sxs-lookup"><span data-stu-id="a5dba-123">After the user is authenticated, URL access to the report server uses the same cookie.</span></span> <span data-ttu-id="a5dba-124">La cookie se transmite en el encabezado HTTP.</span><span class="sxs-lookup"><span data-stu-id="a5dba-124">The cookie is transmitted in the HTTP header.</span></span>

13. <span data-ttu-id="a5dba-125">El usuario continúa solicitando las operaciones en el servidor de informes hasta que la sesión haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="a5dba-125">The user continues to request operations on the report server until the session has ended.</span></span>

## <a name="when-to-implement-a-security-extension"></a><span data-ttu-id="a5dba-126">Cuándo implementar una extensión de seguridad</span><span class="sxs-lookup"><span data-stu-id="a5dba-126">When to Implement a Security Extension</span></span>
 <span data-ttu-id="a5dba-127">Se recomienda que, siempre que sea posible, se use la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="a5dba-127">We recommend that you use Windows Authentication if at all possible.</span></span> <span data-ttu-id="a5dba-128">Sin embargo, la autenticación personalizada y autorización para [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] pueden ser adecuadas en los dos casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a5dba-128">However, custom authentication and authorization for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] may be appropriate in the following two cases:</span></span>

-   <span data-ttu-id="a5dba-129">Tiene una aplicación de Internet o de extranet que no puede utilizar las cuentas de Windows.</span><span class="sxs-lookup"><span data-stu-id="a5dba-129">You have an Internet or extranet application that cannot use Windows accounts.</span></span>

-   <span data-ttu-id="a5dba-130">Tiene usuarios y roles personalizados y necesita proporcionar un esquema de autorización correspondiente en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5dba-130">You have custom-defined users and roles and need to provide a matching authorization scheme in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="a5dba-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5dba-131">See Also</span></span>
 <span data-ttu-id="a5dba-132">[Implementar una extensión de seguridad](../security-extension/implementing-a-security-extension.md) [configurar administrador de informes para pasar cookies de autenticación personalizadas](../../security/configure-the-web-portal-to-pass-custom-authentication-cookies.md)</span><span class="sxs-lookup"><span data-stu-id="a5dba-132">[Implementing a Security Extension](../security-extension/implementing-a-security-extension.md) [Configure Report Manager to Pass Custom Authentication Cookies](../../security/configure-the-web-portal-to-pass-custom-authentication-cookies.md)</span></span>


