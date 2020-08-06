---
title: Usar WQL y lenguajes de scripting con el proveedor WMI para la administración de configuración | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- queries [WMI]
- scripts [WMI]
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
- WMI Provider for Configuration Management, scripts
ms.assetid: c1e64905-3c2b-4974-88f4-abf17cf7e289
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d8c903cd0e993728865bce3371c349a2d0ba7485
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672835"
---
# <a name="using-wql-and-scripting-languages-with-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="f6893-102">Utilizar WQL y languages de scripting con el proveedor WMI para la administración de configuración</span><span class="sxs-lookup"><span data-stu-id="f6893-102">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>
  <span data-ttu-id="f6893-103">Las aplicaciones de administración obtienen acceso a los servicios y la configuración de red de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante el proveedor de Instrumental de administración de Windows (WMI) para los objetos de administración de configuración de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="f6893-103">Management applications access [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings using the Windows Management Instrumentation (WMI) Provider for Configuration Management objects in two ways:</span></span>  
  
-   <span data-ttu-id="f6893-104">Mediante un editor WQL o herramienta de consulta, como WBEMTest.exe, para consultar el objeto establecido con el lenguaje (WQL) del Instrumental de administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="f6893-104">Using a WQL editor or query tool, such as WBEMTest.exe to query the object set with the Windows Management Instrumentation Language (WQL).</span></span>  
  
-   <span data-ttu-id="f6893-105">Mediante un lenguaje de scripting, como VBScript.</span><span class="sxs-lookup"><span data-stu-id="f6893-105">Using a scripting language, such as VBScript.</span></span>  
  
 <span data-ttu-id="f6893-106">Alternativamente, los servicios y la configuración de red de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se pueden administrar mediante programación usando los objetos administrados WMI en SMO.</span><span class="sxs-lookup"><span data-stu-id="f6893-106">Alternatively, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings can be managed programmatically using the WMI managed objects in SMO.</span></span> <span data-ttu-id="f6893-107">Para obtener más información acerca de la programación de objetos administrados por WMI, vea [administrar servicios y configuración de red mediante el proveedor WMI](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="f6893-107">For more information about programming WMI managed objects, see [Managing Services and Network Settings by Using WMI Provider](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span></span>  
  
 <span data-ttu-id="f6893-108">Se puede tener acceso al proveedor WMI para administración de configuración mediante elAdministrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span><span class="sxs-lookup"><span data-stu-id="f6893-108">The WMI provider for Configuration Management can be accessed by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span></span> <span data-ttu-id="f6893-109">Para obtener más información sobre el acceso al proveedor WMI desde una interfaz de usuario, consulte los [temas de procedimientos de administración de servicios &#40;Administrador de configuración de SQL Server&#41;](../../database-engine/managing-services-how-to-topics-sql-server-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f6893-109">For more information about accessing the WMI provider from a user interface, see [Managing Services How-to Topics &#40;SQL Server Configuration Manager&#41;](../../database-engine/managing-services-how-to-topics-sql-server-configuration-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6893-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f6893-110">See Also</span></span>  
 <span data-ttu-id="f6893-111">[Obtener acceso al proveedor WMI para la administración de configuración mediante WQL](access-wmi-provider-for-configuration-management-using-wql.md) </span><span class="sxs-lookup"><span data-stu-id="f6893-111">[Access WMI Provider for Configuration Management using WQL](access-wmi-provider-for-configuration-management-using-wql.md) </span></span>  
 [<span data-ttu-id="f6893-112">Modificar propiedades avanzadas de servicios SQL Server mediante VBScript</span><span class="sxs-lookup"><span data-stu-id="f6893-112">Modify SQL Server Service Advanced Properties using VBScript</span></span>](access-wmi-provider-for-configuration-management-using-vbscript.md)  
  
  
