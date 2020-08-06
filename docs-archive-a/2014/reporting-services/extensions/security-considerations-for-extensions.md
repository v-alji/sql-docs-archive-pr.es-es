---
title: Consideraciones de seguridad para las extensiones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
- extensions [Reporting Services], security
- permissions [Reporting Services], extensions
ms.assetid: 58cbdfeb-1105-4a7d-a3b8-b897ff95f367
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e7819f4d6de2003c9982d33ab00cfa0d4030aa36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677430"
---
# <a name="security-considerations-for-extensions"></a><span data-ttu-id="a618f-102">Consideraciones de seguridad para las extensiones</span><span class="sxs-lookup"><span data-stu-id="a618f-102">Security Considerations for Extensions</span></span>
  <span data-ttu-id="a618f-103">Cada aplicación que tenga como destino Common Language Runtime (CLR) debe interactuar con el sistema de seguridad de CLR.</span><span class="sxs-lookup"><span data-stu-id="a618f-103">Every application that targets the common language runtime (CLR) must interact with the CLR security system.</span></span> <span data-ttu-id="a618f-104">Cuando se ejecuta dicha aplicación, el CLR la evalúa automáticamente y le concede un conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="a618f-104">When such an application runs, it is automatically evaluated and given a set of permissions by the CLR.</span></span> <span data-ttu-id="a618f-105">Según los permisos que reciba la aplicación, continúa ejecutándose o genera una excepción de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a618f-105">Depending on the permissions that the application receives, it either continues running or generates a security exception.</span></span> <span data-ttu-id="a618f-106">La configuración de seguridad local y las directivas de los archivos de configuración de la directiva de seguridad para un servidor de informes determinado definen los permisos de código que un ensamblado recibe.</span><span class="sxs-lookup"><span data-stu-id="a618f-106">The local security settings and policies in the security policy configuration files for a particular report server define the code permissions that an assembly receives.</span></span>  
  
 <span data-ttu-id="a618f-107">Antes de solicitar los permisos, es necesario tener en cuenta los recursos y operaciones protegidas que se piensa usar en el código de la extensión y también saber qué permisos protegen esos recursos y operaciones.</span><span class="sxs-lookup"><span data-stu-id="a618f-107">Before requesting permissions, you need to be aware of the resources and protected operations your extension code is planning to use, and you also need to know which permissions protect those resources and operations.</span></span> <span data-ttu-id="a618f-108">Además, se ha de realizar un seguimiento de los recursos a los que tienen acceso los métodos de bibliotecas de clases a los que llaman los componentes de la extensión.</span><span class="sxs-lookup"><span data-stu-id="a618f-108">In addition, you need to keep track of any resources accessed by any class library methods that are called by the extension components.</span></span> <span data-ttu-id="a618f-109">Para obtener más información, vea "Solicitar permisos" en la Guía del programador de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a618f-109">For more information, see "Requesting Permissions" in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Developer's Guide.</span></span>  
  
 <span data-ttu-id="a618f-110">Las extensiones implementadas en un servidor de informes se deben ejecutar como de plena confianza, lo que significa que la extensión tiene que formar parte de un grupo de código al que se haya concedido el conjunto de permisos **FullTrust**.</span><span class="sxs-lookup"><span data-stu-id="a618f-110">Extensions deployed to a report server must run as fully trusted, meaning that your extension needs to be part of a code group that is granted the **FullTrust** permission set.</span></span> <span data-ttu-id="a618f-111">Esto también significa que la extensión puede tener acceso a ciertos recursos del servidor y operaciones disponibles a través del CLR, en función del usuario que se esté autenticando para un informe determinado.</span><span class="sxs-lookup"><span data-stu-id="a618f-111">This also means that your extension may have access to certain server resources and operations available through the CLR depending on the user that is being authenticated for a particular report.</span></span> <span data-ttu-id="a618f-112">Para más información sobre grupos de código y extensiones, vea [Seguridad de acceso del código en Reporting Services](secure-development/code-access-security-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="a618f-112">For more information about code groups and extensions, see [Code Access Security in Reporting Services](secure-development/code-access-security-in-reporting-services.md).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="a618f-113">aplica la seguridad de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] para todas sus extensiones.</span><span class="sxs-lookup"><span data-stu-id="a618f-113">enforces [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] security for all of its extensions.</span></span>  
  
 <span data-ttu-id="a618f-114">Las condiciones siguientes se aplican a la implementación de las extensiones de seguridad, procesamiento de datos, entrega y representación en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a618f-114">The following conditions apply to the deployment of data processing, delivery, rendering, and security extensions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="a618f-115">Solo el administrador local tiene permiso para implementar una extensión.</span><span class="sxs-lookup"><span data-stu-id="a618f-115">Only the local administrator has permission to deploy an extension.</span></span>  
  
-   <span data-ttu-id="a618f-116">Solo los usuarios con los permisos de lectura/escritura adecuados pueden cambiar los archivos de configuración para el componente de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que se extiende.</span><span class="sxs-lookup"><span data-stu-id="a618f-116">Only users with the appropriate read/write permissions can change the configuration files for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] component that is being extended.</span></span>  
  
-   <span data-ttu-id="a618f-117">Solo los usuarios con privilegios tienen el permiso para modificar los archivos de directiva de seguridad y habilitar la seguridad de acceso del código para una extensión.</span><span class="sxs-lookup"><span data-stu-id="a618f-117">Only privileged users have permission to edit the security policy files and enable code access security for an extension.</span></span>  
  
 <span data-ttu-id="a618f-118">Para más información sobre la seguridad de acceso del código en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], vea [Desarrollo seguro &#40;Reporting Services&#41;](secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="a618f-118">For more information about code access security in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], see [Secure Development &#40;Reporting Services&#41;](secure-development/secure-development-reporting-services.md).</span></span>  
  
 <span data-ttu-id="a618f-119">Para obtener más información sobre la seguridad de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], vea "Seguridad de .NET Framework" en la Guía del programador de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a618f-119">For more information about [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] security, see ".NET Framework Security" in your [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Developer's Guide.</span></span>  
  
## <a name="initialization-of-extension-assemblies"></a><span data-ttu-id="a618f-120">Inicialización de los ensamblados de extensión</span><span class="sxs-lookup"><span data-stu-id="a618f-120">Initialization of Extension Assemblies</span></span>  
 <span data-ttu-id="a618f-121">Cuando el servidor de informes carga por primera vez las extensiones en la memoria, utilizan las credenciales de cuenta de servicio, porque algunos ensamblados de extensión requieren permisos concretos para tener acceso a los recursos del sistema, leer los archivos de configuración y cargar otros ensamblados dependientes.</span><span class="sxs-lookup"><span data-stu-id="a618f-121">When extensions are first loaded into memory by the report server, they use the service account credentials, because some extension assemblies require specific permissions to access system resources, to read configuration files, and to load other, dependent assemblies.</span></span> <span data-ttu-id="a618f-122">Sin embargo, una vez cargado e inicializado un ensamblado, todas las llamadas subsiguientes a los ensamblados de extensión utilizan las credenciales de la cuenta de usuario en la que se ha iniciado sesión actualmente.</span><span class="sxs-lookup"><span data-stu-id="a618f-122">After an assembly has been loaded and initialized, however, all subsequent calls to extension assemblies use the credentials of the user account that is currently logged on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a618f-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a618f-123">See Also</span></span>  
 <span data-ttu-id="a618f-124">[Extensiones de Reporting Services](reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="a618f-124">[Reporting Services Extensions](reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="a618f-125">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a618f-125">Reporting Services Extension Library</span></span>](reporting-services-extension-library.md)  
  
  
