---
title: Modelo de objetos SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- object models [SMO]
- SMO [SQL Server], object model
- SQL Server Management Objects, object model
ms.assetid: bd6e59b6-ca46-42c0-adb2-c9d64cf6e00b
author: stevestein
ms.author: sstein
ms.openlocfilehash: c973e381a6cc7de44a0072d012147271eaa609ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744048"
---
# <a name="smo-object-model"></a><span data-ttu-id="bea1c-102">Modelo de objetos SMO</span><span class="sxs-lookup"><span data-stu-id="bea1c-102">SMO Object Model</span></span>
  <span data-ttu-id="bea1c-103">El modelo de objetos SMO se compone de una jerarquía de objetos.</span><span class="sxs-lookup"><span data-stu-id="bea1c-103">The SMO object model is made up of a hierarchy of objects.</span></span> <span data-ttu-id="bea1c-104">El objeto <xref:Microsoft.SqlServer.Management.Smo.Server> es el objeto de nivel superior y todos los objetos de clase de instancia se encuentran debajo del objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="bea1c-104">The <xref:Microsoft.SqlServer.Management.Smo.Server> object is the top level object and all instance class objects reside under the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span>  
  
 <span data-ttu-id="bea1c-105">La clase <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> es una clase de nivel superior con una jerarquía de objeto independiente.</span><span class="sxs-lookup"><span data-stu-id="bea1c-105">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> class is a top level class with a separate object hierarchy.</span></span> <span data-ttu-id="bea1c-106">El <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> objeto representa los [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servicios y la configuración de red disponibles a través del proveedor WMI.</span><span class="sxs-lookup"><span data-stu-id="bea1c-106">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object represents [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings available through the WMI Provider.</span></span>  
  
 <span data-ttu-id="bea1c-107">Además de los objetos <xref:Microsoft.SqlServer.Management.Smo.Server> y <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>, hay varias clases de utilidad que representan tareas u operaciones, como <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup> o <xref:Microsoft.SqlServer.Management.Smo.Restore></span><span class="sxs-lookup"><span data-stu-id="bea1c-107">Besides the <xref:Microsoft.SqlServer.Management.Smo.Server> and <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> objects, there are several utility classes that represent tasks or operations, such as <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup>, or <xref:Microsoft.SqlServer.Management.Smo.Restore></span></span>  
  
 <span data-ttu-id="bea1c-108">El modelo de objetos SMO se compone de varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="bea1c-108">The SMO object model is made up of several namespaces.</span></span> <span data-ttu-id="bea1c-109">Para más información, vea [Espacios de nombres SMO](smo-object-model-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="bea1c-109">For more information, see [SMO Namespaces](smo-object-model-namespaces.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea1c-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bea1c-110">See Also</span></span>  
 <span data-ttu-id="bea1c-111">[Diagrama del modelo de objetos SMO](smo-object-model-diagram.md) </span><span class="sxs-lookup"><span data-stu-id="bea1c-111">[SMO Object Model Diagram](smo-object-model-diagram.md) </span></span>  
 <span data-ttu-id="bea1c-112">[Espacios de nombres SMO](smo-object-model-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="bea1c-112">[SMO Namespaces](smo-object-model-namespaces.md) </span></span>  
 [<span data-ttu-id="bea1c-113">Conceptos del proveedor WMI de administración de configuración</span><span class="sxs-lookup"><span data-stu-id="bea1c-113">WMI Provider for Configuration Management Concepts</span></span>](../wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
