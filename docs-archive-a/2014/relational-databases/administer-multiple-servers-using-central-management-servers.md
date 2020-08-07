---
title: Administrar varios servidores mediante Servidores de administración central | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- multiserver queries
- central management server
- multiserver administration [SQL Server]
- master servers [SQL Server], central management servers
- target configuration [SQL Server]
- server configuration [SQL Server]
ms.assetid: 427911a7-57d4-4542-8846-47c3267a5d9c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3906165b595f6faa15812f70377a3bc0f550e52e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745841"
---
# <a name="administer-multiple-servers-using-central-management-servers"></a><span data-ttu-id="b279d-102">Administrar varios servidores mediante Servidores de administración central</span><span class="sxs-lookup"><span data-stu-id="b279d-102">Administer Multiple Servers Using Central Management Servers</span></span>
  <span data-ttu-id="b279d-103">Puede administrar varios servidores designando los servidores de administración central y creando grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="b279d-103">You can administer multiple servers by designating Central Management Servers and creating server groups.</span></span>  
  
## <a name="benefits-of-central-management-servers-and-server-groups"></a><span data-ttu-id="b279d-104">Ventajas de los servidores de administración central y grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="b279d-104">Benefits of Central Management Servers and Server Groups</span></span>  
 <span data-ttu-id="b279d-105">Una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] que se designa como servidor de administración central mantiene los grupos de servidores que contienen la información de conexión de una o varias instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b279d-105">An instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that is designated as a Central Management Server maintains server groups that contain the connection information for one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b279d-106">Las instrucciones [!INCLUDE[tsql](../includes/tsql-md.md)] y las directivas de la administración basada en directivas se pueden ejecutar al mismo tiempo con grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="b279d-106">[!INCLUDE[tsql](../includes/tsql-md.md)] statements and Policy-Based Management policies can be executed at the same time against server groups.</span></span> <span data-ttu-id="b279d-107">También puede ver los archivos de registro de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en las instancias que se administran a través de un Servidor de administración central.</span><span class="sxs-lookup"><span data-stu-id="b279d-107">You can also view the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] log files on instances that are managed through a Central Management Server.</span></span> <span data-ttu-id="b279d-108">Las versiones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] no se pueden designar como Servidores de administración central.</span><span class="sxs-lookup"><span data-stu-id="b279d-108">Versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] cannot be designated as a Central Management Server.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="b279d-109">también se pueden ejecutar con los grupos de servidores locales en Servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="b279d-109">statements can also be executed against local server groups in Registered Servers.</span></span>  
  
### <a name="related-tasks"></a><span data-ttu-id="b279d-110">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="b279d-110">Related Tasks</span></span>  
 <span data-ttu-id="b279d-111">Para crear un Servidor de administración central y grupos de servidores, use la ventana **Servidores registrados** en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b279d-111">To create a Central Management Server and server groups, use the **Registered Servers** window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b279d-112">Observe que el servidor de administración central no puede ser miembro de un grupo que mantenga.</span><span class="sxs-lookup"><span data-stu-id="b279d-112">Note that the Central Management Server cannot be a member of a group that it maintains.</span></span> <span data-ttu-id="b279d-113">Para obtener más información sobre cómo crear servidores de administración central y grupos de servidores, vea [Crear un servidor de administración central y un grupo de servidores &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md).</span><span class="sxs-lookup"><span data-stu-id="b279d-113">For more information about how to create Central Management Servers and server groups, see [Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b279d-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b279d-114">See Also</span></span>  
 [<span data-ttu-id="b279d-115">Administrar servidores mediante administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="b279d-115">Administer Servers by Using Policy-Based Management</span></span>](policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  