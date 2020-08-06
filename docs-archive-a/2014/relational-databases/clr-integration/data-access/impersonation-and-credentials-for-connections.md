---
title: Suplantación y credenciales para las conexiones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- impersonation [CLR integration]
- security [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- authentication [CLR integration]
- user impersonation [CLR integration]
- credentials [CLR integration]
- database objects [CLR integration], security
ms.assetid: 293dce7d-1db2-4657-992f-8c583d6e9ebb
author: rothja
ms.author: jroth
ms.openlocfilehash: cdbc52e07f4502adda7301ce7f635c050ed9c3c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674157"
---
# <a name="impersonation-and-credentials-for-connections"></a><span data-ttu-id="dd158-102">Suplantación y credenciales para conexiones</span><span class="sxs-lookup"><span data-stu-id="dd158-102">Impersonation and Credentials for Connections</span></span>
  <span data-ttu-id="dd158-103">En la integración con Common Language Runtime (CLR) de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], el uso de la autenticación de Windows es complejo, pero es más seguro que usar la autenticación de SOL Server.</span><span class="sxs-lookup"><span data-stu-id="dd158-103">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] common language runtime (CLR) integration, using Windows Authentication is complex, but is more secure than using SQL Server Authentication.</span></span> <span data-ttu-id="dd158-104">Al usar la autenticación de Windows, tenga presente las consideraciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="dd158-104">When using Windows Authentication, keep in mind the following considerations.</span></span>  
  
 <span data-ttu-id="dd158-105">De forma predeterminada, un proceso de SQL Server que se conecta a Windows adquiere el contexto de seguridad de la cuenta de servicio de Windows para SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dd158-105">By default, a SQL Server process that connects out to Windows acquires the security context of the SQL Server Windows service account.</span></span> <span data-ttu-id="dd158-106">Pero es posible asignar una función CLR a una identidad del proxy, para que sus conexiones salientes tengan un contexto de seguridad diferente que el de la cuenta del servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="dd158-106">But it is possible to map a CLR function to a proxy identity, so that its outbound connections have a different security context than that of the Windows service account.</span></span>  
  
 <span data-ttu-id="dd158-107">En algunos casos, puede que desee suplantar al autor de las llamadas mediante la propiedad `SqlContext.WindowsIdentity` en lugar de ejecutarse como una cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="dd158-107">In some cases, you may want to impersonate the caller by using the `SqlContext.WindowsIdentity` property instead of running as the service account.</span></span> <span data-ttu-id="dd158-108">La instancia de `WindowsIdentity` representa la identidad del cliente que invocó el código de llamada y solo está disponible cuando el cliente usó la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="dd158-108">The `WindowsIdentity` instance represents the identity of the client that invoked the calling code, and is only available when the client used Windows Authentication.</span></span> <span data-ttu-id="dd158-109">Después de haber obtenido la instancia de `WindowsIdentity`, puede llamar a `Impersonate` para cambiar el token de seguridad del subproceso y, a continuación, abrir las conexiones de ADO.NET en nombre del cliente.</span><span class="sxs-lookup"><span data-stu-id="dd158-109">After you have obtained the `WindowsIdentity` instance, you can call `Impersonate` to change the security token of the thread, and then open ADO.NET connections on behalf of the client.</span></span>  
  
 <span data-ttu-id="dd158-110">Después de llamar a SQLContext. WindowsIdentity. Impersonate, no puede tener acceso a los datos locales y no puede tener acceso a los datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="dd158-110">After you call SQLContext.WindowsIdentity.Impersonate, you cannot access local data and you cannot access system data.</span></span> <span data-ttu-id="dd158-111">Para acceder a los datos de nuevo, debe llamar a WindowsImpersonationContext. Undo.</span><span class="sxs-lookup"><span data-stu-id="dd158-111">To access data again, you have to call WindowsImpersonationContext.Undo.</span></span>  
  
 <span data-ttu-id="dd158-112">En el ejemplo siguiente se muestra cómo suplantar al autor de las llamadas mediante la propiedad `SqlContext.WindowsIdentity`.</span><span class="sxs-lookup"><span data-stu-id="dd158-112">The following example shows how to impersonate the caller by using the `SqlContext.WindowsIdentity` property.</span></span>  
  
 <span data-ttu-id="dd158-113">Visual C#</span><span class="sxs-lookup"><span data-stu-id="dd158-113">Visual C#</span></span>  
  
```  
WindowsIdentity clientId = null;  
WindowsImpersonationContext impersonatedUser = null;  
  
clientId = SqlContext.WindowsIdentity;  
  
// This outer try block is used to protect from   
// exception filter attacks which would prevent  
// the inner finally block from executing and   
// resetting the impersonation.  
try  
{  
   try  
   {  
      impersonatedUser = clientId.Impersonate();  
      if (impersonatedUser != null)  
         return GetFileDetails(directoryPath);  
         else return null;  
   }  
   finally  
   {  
      if (impersonatedUser != null)  
         impersonatedUser.Undo();  
   }  
}  
catch  
{  
   throw;  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="dd158-114">Para obtener información sobre los cambios de comportamiento en la suplantación, vea [cambios importantes en las características de motor de base de datos en SQL Server 2014](../../../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="dd158-114">For information about behavior changes in impersonation, see [Breaking Changes to Database Engine Features in SQL Server 2014](../../../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md).</span></span>  
  
 <span data-ttu-id="dd158-115">Además, si obtuvo la instancia de identidad en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows, no puede propagar esa instancia a otro equipo de forma predeterminada; la infraestructura de seguridad de Windows restringe esa acción de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dd158-115">Furthermore, if you obtained the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows identity instance, by default you cannot propagate that instance to another computer; Windows security infrastructure restricts that by default.</span></span> <span data-ttu-id="dd158-116">Sin embargo, hay un mecanismo denominado "delegación" que habilita la propagación de identidades de Windows a través de varios equipos de confianza.</span><span class="sxs-lookup"><span data-stu-id="dd158-116">There is, however, a mechanism called "delegation" that enables propagation of Windows identities across multiple trusted computers.</span></span> <span data-ttu-id="dd158-117">Puede obtener más información sobre la delegación en el artículo de TechNet "[transición del protocolo Kerberos y delegación restringida](https://go.microsoft.com/fwlink/?LinkId=50419)".</span><span class="sxs-lookup"><span data-stu-id="dd158-117">You can learn more about delegation in the TechNet article, "[Kerberos Protocol Transition and Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=50419)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd158-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd158-118">See Also</span></span>  
 [<span data-ttu-id="dd158-119">Objeto SqlContext</span><span class="sxs-lookup"><span data-stu-id="dd158-119">SqlContext Object</span></span>](../../clr-integration-data-access-in-process-ado-net/sqlcontext-object.md)  
  
  
