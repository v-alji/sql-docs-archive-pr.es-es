---
title: Trabajar con el proveedor WMI para la administración de configuración | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- permissions [WMI]
- connection strings [WMI]
- security [WMI]
- WMI Provider for Configuration Management, connection strings
- WMI Provider for Configuration Management, security
- late binding [WMI]
- WMI Provider for Configuration Management, late binding
- binding [WMI]
ms.assetid: 34daa922-7074-41d0-9077-042bb18c222a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 80f311fb0abae2337f6ea4a5d5d85aaa0d320b94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672834"
---
# <a name="working-with-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="fb9e7-102">Trabajar con el proveedor WMI para la administración de configuración</span><span class="sxs-lookup"><span data-stu-id="fb9e7-102">Working with the WMI Provider for Configuration Management</span></span>
  <span data-ttu-id="fb9e7-103">Tenga en cuenta la siguiente información antes de programar con el proveedor WMI para la Administración de equipos:</span><span class="sxs-lookup"><span data-stu-id="fb9e7-103">Consider the following before programming with the WMI Provider for Computer Management:</span></span>  
  
## <a name="binding"></a><span data-ttu-id="fb9e7-104">Enlace</span><span class="sxs-lookup"><span data-stu-id="fb9e7-104">Binding</span></span>  
 <span data-ttu-id="fb9e7-105">El proveedor WMI para la administración de configuración es un modelo de objetos COM y admite el enlace en tiempo de diseño y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fb9e7-105">The WMI Provider for Configuration Management is a COM object model and it supports early and late binding.</span></span> <span data-ttu-id="fb9e7-106">Con el enlace en tiempo de ejecución puede utilizar lenguajes de script, como VBScript, para manipular mediante programación los servicios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la configuración de red y los alias.</span><span class="sxs-lookup"><span data-stu-id="fb9e7-106">With late binding you can use script languages, such as VBScript, to manipulate the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network settings, and aliases programmatically.</span></span>  
  
 <span data-ttu-id="fb9e7-107">Para obtener más información acerca de la programación de implementaciones del proveedor WMI mediante lenguajes de scripting, vea el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [sitio web](https://go.microsoft.com/fwlink/?linkid=15426)de MSDN.</span><span class="sxs-lookup"><span data-stu-id="fb9e7-107">For further information about programming WMI Provider implementations using scripting languages, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN [Web site](https://go.microsoft.com/fwlink/?linkid=15426).</span></span>  
  
## <a name="specifying-a-connection-string"></a><span data-ttu-id="fb9e7-108">Especificar una cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="fb9e7-108">Specifying a Connection String</span></span>  
 <span data-ttu-id="fb9e7-109">Las aplicaciones dirigen el proveedor WMI para la administración de configuración a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante la conexión a un espacio de nombres WMI definido por el proveedor.</span><span class="sxs-lookup"><span data-stu-id="fb9e7-109">Applications direct the WMI Provider for Configuration Management to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by connecting to a WMI namespace defined by the provider.</span></span> <span data-ttu-id="fb9e7-110">El servicio WMI de Windows asigna este espacio de nombres a la DLL del proveedor DLL y lo carga en memoria.</span><span class="sxs-lookup"><span data-stu-id="fb9e7-110">The Windows WMI service maps this namespace to the provider DLL and loads it into memory.</span></span> <span data-ttu-id="fb9e7-111">Todas las instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se representan con un único espacio de nombres WMI.</span><span class="sxs-lookup"><span data-stu-id="fb9e7-111">All instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are represented with a single WMI namespace.</span></span> <span data-ttu-id="fb9e7-112">El valor predeterminado del espacio de nombres es</span><span class="sxs-lookup"><span data-stu-id="fb9e7-112">The namespace defaults to</span></span>  
  
```  
\\.\root\Microsoft\SqlServer\ComputerManagement12\instance_name  
```  
  
 <span data-ttu-id="fb9e7-113">donde `instance_name` tiene como valor predeterminado `MSSQLSERVER` en una instalación predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb9e7-113">where `instance_name` defaults to `MSSQLSERVER` in a default installation of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fb9e7-114">**Nota:** Si se va a conectar a través de Firewall de Windows, deberá asegurarse de que los equipos estén configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="fb9e7-114">**Note:** If you are connecting through Windows Firewall you will need to make sure your computers are configured appropriately.</span></span> <span data-ttu-id="fb9e7-115">Vea el artículo sobre la conexión a través de Firewall de Windows en la documentación de Instrumental de administración de Windows en el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [sitio web](https://go.microsoft.com/fwlink/?linkid=15426)de MSDN.</span><span class="sxs-lookup"><span data-stu-id="fb9e7-115">See the "Connecting Through Windows Firewall" article in the Windows Management Instrumentation documentation on [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN [Web site](https://go.microsoft.com/fwlink/?linkid=15426).</span></span>  
  
## <a name="permissions-and-server-authentication"></a><span data-ttu-id="fb9e7-116">Permisos y autenticación del servidor</span><span class="sxs-lookup"><span data-stu-id="fb9e7-116">Permissions and Server Authentication</span></span>  
 <span data-ttu-id="fb9e7-117">Para tener acceso al proveedor WMI para la administración de configuración, el script de administración de WMI de cliente se debe ejecutar en el contexto de un administrador en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="fb9e7-117">To access the WMI Provider for Configuration Management, the client WMI management script must be running in the context of an administrator on the target computer.</span></span> <span data-ttu-id="fb9e7-118">Necesita ser miembro del grupo administradores de Windows local en el equipo que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="fb9e7-118">You need to be a member of the local Windows administrators group on the computer you want to manage.</span></span>  
  
 <span data-ttu-id="fb9e7-119">El administrador puede establecer directivas de grupo para controlar el acceso de usuario a los proveedores WMI.</span><span class="sxs-lookup"><span data-stu-id="fb9e7-119">The administrator can set group policies to control user access to WMI providers.</span></span> <span data-ttu-id="fb9e7-120">Para obtener más información sobre cómo establecer directivas de grupo, vea el tema sobre directiva de grupo y MMC en la Ayuda del Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb9e7-120">For more information about setting group policies see "Group Policy and MMC" in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager Help.</span></span>  
  
 <span data-ttu-id="fb9e7-121">El script de administración de WMI se puede utilizar para actualizar la cuenta con la que se ejecutan los servicios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb9e7-121">The WMI management script can be used to update the account under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services run.</span></span>  
  
 <span data-ttu-id="fb9e7-122">El proveedor WMI para la administración de configuración admite los certificados de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fb9e7-122">Security certificates are supported by the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="fb9e7-123">Para obtener más información acerca de los certificados, consulte [jerarquía de cifrado](../security/encryption/encryption-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="fb9e7-123">For more information about certificates, see [Encryption Hierarchy](../security/encryption/encryption-hierarchy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb9e7-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb9e7-124">See Also</span></span>  
 [<span data-ttu-id="fb9e7-125">Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb9e7-125">SQL Server Configuration Manager</span></span>](../sql-server-configuration-manager.md)  
  
  