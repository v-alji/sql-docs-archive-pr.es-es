---
title: Autorización en Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- authorization [Reporting Services]
ms.assetid: 15fc1c7b-560c-4737-b126-e0d428a1b530
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7420b45175ca0b0a5fc66da4a7939b07b79c75b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673511"
---
# <a name="authorization-in-reporting-services"></a><span data-ttu-id="38612-102">La autorización en Reporting Services</span><span class="sxs-lookup"><span data-stu-id="38612-102">Authorization in Reporting Services</span></span>
  <span data-ttu-id="38612-103">La autorización es el proceso de determinar si se debería conceder a una identidad el tipo solicitado de acceso a un recurso determinado en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="38612-103">Authorization is the process of determining whether an identity should be granted the requested type of access to a given resource in the report server database.</span></span> [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="38612-104">utiliza una arquitectura de autorización basada en roles que concede a los usuarios acceso a un recurso determinado según la asignación de roles del usuario para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="38612-104">uses a role-based authorization architecture that grants a user access to a given resource based on the user's role assignment for the application.</span></span> <span data-ttu-id="38612-105">Las extensiones de seguridad para [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] contienen una implementación de un componente de autorización que se utiliza para conceder acceso a los usuarios una vez autenticados en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="38612-105">Security extensions for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] contain an implementation of an authorization component that is used to grant access to users once they are authenticated on the report server.</span></span> <span data-ttu-id="38612-106">La autorización se invoca cuando un usuario intenta realizar una operación en el sistema o en un elemento del servidor de informes a través del acceso de dirección URL y la API SOAP.</span><span class="sxs-lookup"><span data-stu-id="38612-106">Authorization is invoked when a user attempts to perform an operation on the system or a report server item through the SOAP API and via URL access.</span></span> <span data-ttu-id="38612-107">Esto se posibilita a través de la interfaz de extensión de la seguridad **IAuthorizationExtension**.</span><span class="sxs-lookup"><span data-stu-id="38612-107">This is made possible through the security extension interface **IAuthorizationExtension**.</span></span> <span data-ttu-id="38612-108">Según se ha indicado previamente, todas las extensiones heredan de **IExtension** la interfaz básica de cualquier extensión que implemente.</span><span class="sxs-lookup"><span data-stu-id="38612-108">As stated previously, all extensions inherit from **IExtension** the base interface for any extension that you deploy.</span></span> <span data-ttu-id="38612-109">**IExtension** e **IAuthorizationExtension** son miembros del espacio de nombres **Microsoft.ReportingServices.Interfaces** .</span><span class="sxs-lookup"><span data-stu-id="38612-109">**IExtension** and **IAuthorizationExtension** are members of the **Microsoft.ReportingServices.Interfaces** namespace.</span></span>

## <a name="checking-access"></a><span data-ttu-id="38612-110">Comprobar el acceso</span><span class="sxs-lookup"><span data-stu-id="38612-110">Checking Access</span></span>
 <span data-ttu-id="38612-111">En la autorización, la clave de cualquier implementación de seguridad personalizada es la comprobación del acceso, que se implementa en el método <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="38612-111">In authorization, the key to any custom security implementation is the access check, which is implemented in the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method.</span></span> <span data-ttu-id="38612-112">Cada vez que un usuario intenta una operación en el servidor de informes, se llama a <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="38612-112"><xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> is called each time a user attempts an operation on the report server.</span></span> <span data-ttu-id="38612-113">El método <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> se sobrecarga para cada tipo de operación.</span><span class="sxs-lookup"><span data-stu-id="38612-113">The <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method is overloaded for each operation type.</span></span> <span data-ttu-id="38612-114">En las operaciones de carpeta, un ejemplo de comprobación de acceso podría ser similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="38612-114">For folder operations, an example of an access check might look like the following:</span></span>

```
// Overload for Folder operations
public bool CheckAccess(
   string userName, 
   IntPtr userToken, 
   byte[] secDesc, 
   FolderOperation requiredOperation)
{
   // If the user is the administrator, allow unrestricted access.
   if (userName == m_adminUserName) 
      return true;

   AceCollection acl = DeserializeAcl(secDesc);
   foreach(AceStruct ace in acl)
   {
         if (userName == ace.PrincipalName)
         {
            foreach(FolderOperation aclOperation in 
               ace.FolderOperations)
            {
               if (aclOperation == requiredOperation)
                     return true;
            }
         }
   }
   return false;
}
```

 <span data-ttu-id="38612-115">El servidor de informes llama al método <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> pasando el nombre del usuario que ha iniciado sesión, un token de usuario, el descriptor de seguridad para el elemento y la operación solicitada.</span><span class="sxs-lookup"><span data-stu-id="38612-115">The report server calls the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method by passing in the name of the logged-on user, a user token, the security descriptor for the item, and the requested operation.</span></span> <span data-ttu-id="38612-116">Ahora se comprobaría si el descriptor de seguridad tiene el nombre de usuario y el permiso adecuados para completar la solicitud y, a continuación, se devolvería `true` para indicar que se concede el acceso o `false` para indicar que se deniega.</span><span class="sxs-lookup"><span data-stu-id="38612-116">Here you would check the security descriptor for the user name and the appropriate permission to complete the request, then return `true` to signify that access is granted or `false` to signify access is denied.</span></span>

## <a name="security-descriptors"></a><span data-ttu-id="38612-117">Descriptor de seguridad</span><span class="sxs-lookup"><span data-stu-id="38612-117">Security Descriptors</span></span>
 <span data-ttu-id="38612-118">Al establecer directivas de autorización en los elementos de la base de datos del servidor de informes, una aplicación cliente (como el Administrador de informes) envía información del usuario a la extensión de seguridad junto con una directiva de seguridad para el elemento.</span><span class="sxs-lookup"><span data-stu-id="38612-118">When setting authorization policies on items in the report server database, a client application (such as Report Manager) submits the user information to the security extension along with a security policy for the item.</span></span> <span data-ttu-id="38612-119">Esta directiva de seguridad e información de usuario se conocen en conjunto como un descriptor de seguridad.</span><span class="sxs-lookup"><span data-stu-id="38612-119">This security policy and user information are known collectively as a security descriptor.</span></span> <span data-ttu-id="38612-120">Un descriptor de seguridad contiene la información siguiente para un elemento de la base de datos del servidor de informes:</span><span class="sxs-lookup"><span data-stu-id="38612-120">A security descriptor contains the following information for an item in the report server database:</span></span>

-   <span data-ttu-id="38612-121">El grupo o usuario que tiene algún tipo de permiso para realizar las operaciones en el elemento.</span><span class="sxs-lookup"><span data-stu-id="38612-121">The group or user that has some type of permission to perform operations on the item.</span></span>

-   <span data-ttu-id="38612-122">El tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="38612-122">The item's type.</span></span>

-   <span data-ttu-id="38612-123">Una lista de control de acceso discrecional (DACL) que controla el acceso al elemento.</span><span class="sxs-lookup"><span data-stu-id="38612-123">A discretionary access control list controlling access to the item.</span></span>

 <span data-ttu-id="38612-124">Los descriptores de seguridad se crean utilizando los métodos <xref:ReportService2010.ReportingService2010.SetPolicies%2A> y <xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A> del servicio web.</span><span class="sxs-lookup"><span data-stu-id="38612-124">Security descriptors are created using the Web service <xref:ReportService2010.ReportingService2010.SetPolicies%2A> and <xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A> methods.</span></span>

### <a name="authorization-flow"></a><span data-ttu-id="38612-125">Flujo de la autorización</span><span class="sxs-lookup"><span data-stu-id="38612-125">Authorization Flow</span></span>
 <span data-ttu-id="38612-126">La extensión de seguridad configurada actualmente para ejecutarse en el servidor controla la autorización de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38612-126">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] authorization is controlled by the security extension currently configured to run on the server.</span></span> <span data-ttu-id="38612-127">La autorización se basa en los roles y está limitada a los permisos y operaciones que proporciona la arquitectura de seguridad de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="38612-127">Authorization is role-based and limited to the permissions and operations supplied by the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security architecture.</span></span> <span data-ttu-id="38612-128">El diagrama siguiente describe el proceso para autorizar a los usuarios para operar en los elementos de la base de datos del servidor de informes:</span><span class="sxs-lookup"><span data-stu-id="38612-128">The following diagram depicts the process of authorizing users to operate on items in the report server database:</span></span>

 <span data-ttu-id="38612-129">![Flujo de autorización de seguridad de Reporting Services](../../media/rosettasecurityextensionauthorizationflow.gif "Flujo de autorización de seguridad de Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="38612-129">![Reporting Services security authorization flow](../../media/rosettasecurityextensionauthorizationflow.gif "Reporting Services security authorization flow")</span></span>

 <span data-ttu-id="38612-130">Como se muestra en este diagrama, la autorización sigue esta secuencia:</span><span class="sxs-lookup"><span data-stu-id="38612-130">As shown in this diagram, authorization follows this sequence:</span></span>

1.  <span data-ttu-id="38612-131">Una vez autenticadas, las aplicaciones cliente realizan las solicitudes al servidor de informes a través de los métodos de servicio web de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="38612-131">Once authenticated, client applications make requests to the report server through the Reporting Services Web service methods.</span></span> <span data-ttu-id="38612-132">Un vale de autenticación se pasa al servidor de informes en forma de una cookie en el encabezado HTTP de cada solicitud web.</span><span class="sxs-lookup"><span data-stu-id="38612-132">An authentication ticket is passed to the report server in the form of a cookie in the HTTP header of each Web request.</span></span>

2.  <span data-ttu-id="38612-133">La cookie se valida antes de cualquier comprobación de acceso.</span><span class="sxs-lookup"><span data-stu-id="38612-133">The cookie is validated prior to any access check.</span></span>

3.  <span data-ttu-id="38612-134">Una vez validada la cookie, el servidor de informes llama a <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension.GetUserInfo%2A> y se proporciona una identidad al usuario.</span><span class="sxs-lookup"><span data-stu-id="38612-134">Once the cookie is validated, the report server calls <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension.GetUserInfo%2A> and the user is given an identity.</span></span>

4.  <span data-ttu-id="38612-135">El usuario intenta una operación a través del servicio web de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="38612-135">The user attempts an operation through the Reporting Services Web service.</span></span>

5.  <span data-ttu-id="38612-136">El servidor de informes llama al método <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="38612-136">The report server calls the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method.</span></span>

6.  <span data-ttu-id="38612-137">Se recupera el descriptor de seguridad y se pasa a una implementación de extensión de seguridad personalizada de <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="38612-137">The security descriptor is retrieved and passed to a custom security extension implementation of <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span></span> <span data-ttu-id="38612-138">En este punto, el usuario, grupo o equipo se comparan con el descriptor de seguridad del elemento al que se va a tener acceso y se les autoriza a realizar la operación solicitada.</span><span class="sxs-lookup"><span data-stu-id="38612-138">At this point, the user, group, or computer is compared to the security descriptor of the item being accessed and is authorized to perform the requested operation.</span></span>

7.  <span data-ttu-id="38612-139">Si se autoriza al usuario, el servicio web realiza la operación y devuelve una respuesta a la aplicación que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="38612-139">If the user is authorized, the Web service performs the operation and returns a response to the calling application.</span></span>


