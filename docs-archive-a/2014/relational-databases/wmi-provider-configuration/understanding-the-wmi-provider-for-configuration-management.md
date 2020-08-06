---
title: Descripción del proveedor WMI para la administración de configuración | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- WMI Provider for Configuration Management, operations supported
ms.assetid: 92323972-7943-4208-bbf4-050774fb6027
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0f4f38265093fdb0c27d6bd49ff64ba4b572111e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661826"
---
# <a name="understanding-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="cf07b-102">Descripción del proveedor WMI para la administración de configuración</span><span class="sxs-lookup"><span data-stu-id="cf07b-102">Understanding the WMI Provider for Configuration Management</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="cf07b-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]proporciona el proveedor WMI para la administración de la configuración.</span><span class="sxs-lookup"><span data-stu-id="cf07b-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="cf07b-104">Esto permite usar Instrumental de administración de Windows (WMI) para administrar servicios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], configuración de red de cliente y servidor de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], y alias de servidor.</span><span class="sxs-lookup"><span data-stu-id="cf07b-104">This lets you use Windows Management Instrumentation (WMI) to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client and server network settings, and server aliases.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="cf07b-105">los objetos WMI representan los servicios, la configuración de red y los alias en el espacio de nombres root\Microsoft\SqlServer\ComputerManagement*nn* del equipo.</span><span class="sxs-lookup"><span data-stu-id="cf07b-105">services, network settings, and aliases are represented by WMI objects in the root\Microsoft\SqlServer\ComputerManagement*nn* namespace of the computer.</span></span> <span data-ttu-id="cf07b-106">Una vez establecida una conexión con el proveedor WMI en el equipo especificado, se pueden consultar los servicios, la configuración de red y el alias mediante WQL o un lenguaje de scripting.</span><span class="sxs-lookup"><span data-stu-id="cf07b-106">After a connection is established with the WMI provider on the specified computer, the services, network settings, and aliases can be queried using WQL or a scripting language.</span></span>  
  
 <span data-ttu-id="cf07b-107">El Proveedor WMI es un proveedor de instancias.</span><span class="sxs-lookup"><span data-stu-id="cf07b-107">The WMI Provider is an instance provider.</span></span> <span data-ttu-id="cf07b-108">Proporciona instancias de las [clases de WMI](../wmi-provider-configuration-classes/wmi-provider-for-configuration-management-classes.md) y admite las siguientes operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="cf07b-108">It supplies instances of the [WMI Classes](../wmi-provider-configuration-classes/wmi-provider-for-configuration-management-classes.md) and supports the following asynchronous operations.</span></span>  
  
 <span data-ttu-id="cf07b-109">Recuperación de instancias</span><span class="sxs-lookup"><span data-stu-id="cf07b-109">Instance retrieval</span></span>  
 <span data-ttu-id="cf07b-110">Recuperación de una instancia de tipo de clase determinada.</span><span class="sxs-lookup"><span data-stu-id="cf07b-110">Retrieval of a particular class type instance.</span></span>  
  
 <span data-ttu-id="cf07b-111">Enumeración</span><span class="sxs-lookup"><span data-stu-id="cf07b-111">Enumeration</span></span>  
 <span data-ttu-id="cf07b-112">Enumeración de todas las instancias de un tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="cf07b-112">Enumeration of all instances of a class type.</span></span>  
  
 <span data-ttu-id="cf07b-113">Modificación</span><span class="sxs-lookup"><span data-stu-id="cf07b-113">Modification</span></span>  
 <span data-ttu-id="cf07b-114">Modificación de una instancia de tipo de clase determinada.</span><span class="sxs-lookup"><span data-stu-id="cf07b-114">Modification of a particular instance of a class type.</span></span>  
  
 <span data-ttu-id="cf07b-115">Las clases tienen métodos que permiten modificar sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="cf07b-115">Classes have methods that allow the modification of their properties.</span></span>  
  
 <span data-ttu-id="cf07b-116">Eliminación</span><span class="sxs-lookup"><span data-stu-id="cf07b-116">Deletion</span></span>  
 <span data-ttu-id="cf07b-117">Quita una instancia de tipo de clase determinada.</span><span class="sxs-lookup"><span data-stu-id="cf07b-117">Removing a particular instance of a class type.</span></span>  
  
 <span data-ttu-id="cf07b-118">Procesamiento de consultas</span><span class="sxs-lookup"><span data-stu-id="cf07b-118">Query processing</span></span>  
 <span data-ttu-id="cf07b-119">La enumeración de instancias de un tipo de clase basada en un filtro.</span><span class="sxs-lookup"><span data-stu-id="cf07b-119">Enumeration of instances of a class type based on a filter.</span></span>  
  
 <span data-ttu-id="cf07b-120">Para ver ejemplos de aplicaciones de administración que usan el proveedor WMI para la administración de configuración, consulte [uso de WQL y lenguajes de scripting con el proveedor WMI para la administración de la configuración](using-wql-and-scripting-languages-with-the-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="cf07b-120">For examples of management application using the WMI Provider for Configuration Management, see [Using WQL and Scripting Languages with the WMI Provider for Configuration Management](using-wql-and-scripting-languages-with-the-wmi-provider.md).</span></span>  
  
 <span data-ttu-id="cf07b-121">Para obtener más información acerca de la programación de aplicaciones de administración mediante el proveedor WMI, vea la documentación de WMI en el [!INCLUDE[msCoName](../../includes/msconame-md.md)] SDK de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf07b-121">For more information about programming management applications using the WMI Provider, see the WMI documentation in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework SDK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf07b-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf07b-122">See Also</span></span>  
 <span data-ttu-id="cf07b-123">[Trabajar con el proveedor WMI para la administración de configuración](working-with-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="cf07b-123">[Working with the WMI Provider for Configuration Management](working-with-the-wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="cf07b-124">Utilizar WQL y languages de scripting con el proveedor WMI para la administración de configuración</span><span class="sxs-lookup"><span data-stu-id="cf07b-124">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>](using-wql-and-scripting-languages-with-the-wmi-provider.md)  
  
  
