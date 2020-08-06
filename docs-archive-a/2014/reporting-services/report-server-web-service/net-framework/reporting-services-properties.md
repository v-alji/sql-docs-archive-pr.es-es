---
title: Propiedades de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- report servers [Reporting Services], properties
- properties [Reporting Services], about properties
- reports [Reporting Services], properties
- Report Server Web service, properties
- report properties [Reporting Services]
- XML Web service [Reporting Services], properties
- Web service [Reporting Services], properties
- properties [Reporting Services]
ms.assetid: 8c855194-4c20-4ecc-a328-5137d54b560c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61f1f50ea7a49acc616a36a4eaf1d3d5fcdf269a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745010"
---
# <a name="reporting-services-properties"></a><span data-ttu-id="c5bf9-102">Propiedades de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c5bf9-102">Reporting Services Properties</span></span>
  <span data-ttu-id="c5bf9-103">El servidor de informes define un conjunto de propiedades del sistema que son globales al servidor de informes y un conjunto de propiedades de elementos que están asociadas a un elemento individual almacenado en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c5bf9-103">The report server defines a set of system properties that are global to the report server and a set of item properties that are associated with an individual item stored in the report server database.</span></span> <span data-ttu-id="c5bf9-104">Las propiedades definidas por el servidor de informes no se pueden eliminar y en algunos casos son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="c5bf9-104">Properties defined by the report server cannot be deleted, and in some cases they are read-only.</span></span> <span data-ttu-id="c5bf9-105">Una aplicación puede extender las propiedades del sistema y las propiedades de los elementos agregando propiedades definidas por el usuario adicionales a las propiedades de los elementos y del sistema.</span><span class="sxs-lookup"><span data-stu-id="c5bf9-105">An application can extend system properties and item properties by adding additional user-defined properties to the system and item properties.</span></span>  
  
 <span data-ttu-id="c5bf9-106">Los métodos de servicio web siguientes recuperan y establecen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] las propiedades.</span><span class="sxs-lookup"><span data-stu-id="c5bf9-106">The following Web service methods retrieve and set [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] properties.</span></span>  
  
|<span data-ttu-id="c5bf9-107">Método</span><span class="sxs-lookup"><span data-stu-id="c5bf9-107">Method</span></span>|<span data-ttu-id="c5bf9-108">Acción</span><span class="sxs-lookup"><span data-stu-id="c5bf9-108">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.GetProperties%2A>|<span data-ttu-id="c5bf9-109">Devuelve los valores de una o más propiedades en un elemento de la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c5bf9-109">Returns the values of one or more properties on an item in the report server database.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemProperties%2A>|<span data-ttu-id="c5bf9-110">Devuelve una o más propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="c5bf9-110">Returns one or more system properties.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetProperties%2A>|<span data-ttu-id="c5bf9-111">Establece una o varias propiedades de un elemento en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c5bf9-111">Sets one or more properties of an item in the report server database.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSystemProperties%2A>|<span data-ttu-id="c5bf9-112">Establece una o más propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="c5bf9-112">Sets one or more system properties.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="c5bf9-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c5bf9-113">In This Section</span></span>  
  
|<span data-ttu-id="c5bf9-114">Tema</span><span class="sxs-lookup"><span data-stu-id="c5bf9-114">Topic</span></span>|<span data-ttu-id="c5bf9-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5bf9-115">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c5bf9-116">Propiedades de los elementos del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="c5bf9-116">Report Server Item Properties</span></span>](reporting-services-properties-report-server-item-properties.md)|<span data-ttu-id="c5bf9-117">Describe las propiedades específicas del elemento en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5bf9-117">Describes the item-specific properties in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="c5bf9-118">Propiedades del sistema del servidor de informes</span><span class="sxs-lookup"><span data-stu-id="c5bf9-118">Report Server System Properties</span></span>](reporting-services-properties-report-server-system-properties.md)|<span data-ttu-id="c5bf9-119">Describe las propiedades específicas del sistema en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5bf9-119">Describes the system-specific properties in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5bf9-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5bf9-120">See Also</span></span>  
 <span data-ttu-id="c5bf9-121">[Creación de aplicaciones con el servicio web y .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="c5bf9-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="c5bf9-122">[Servicio web del servidor de informes](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="c5bf9-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="c5bf9-123">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c5bf9-123">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
