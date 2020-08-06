---
title: Utilizar los encabezados SOAP de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Report Server Web service, SOAP
- SOAP headers [Reporting Services]
- SOAP [Reporting Services], headers
- XML Web service [Reporting Services], SOAP
ms.assetid: 306d2c06-a25a-40f8-8a35-13dd32e8841e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f48be183398d4d441b5781c9f9467178c3011e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746736"
---
# <a name="using-reporting-services-soap-headers"></a><span data-ttu-id="cd356-102">Utilizar los encabezados SOAP de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="cd356-102">Using Reporting Services SOAP Headers</span></span>
  <span data-ttu-id="cd356-103">La comunicación con un método de servicio web utilizando SOAP sigue un formato estándar.</span><span class="sxs-lookup"><span data-stu-id="cd356-103">Communication with a Web service method using SOAP follows a standard format.</span></span> <span data-ttu-id="cd356-104">Parte de este formato son los datos que están codificados en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="cd356-104">Part of this format is the data that is encoded in an XML document.</span></span> <span data-ttu-id="cd356-105">El documento XML está compuesto de un elemento raíz **Envelope**, que a su vez está compuesto de un elemento **Body** necesario y un elemento **Header** opcional.</span><span class="sxs-lookup"><span data-stu-id="cd356-105">The XML document consists of a root **Envelope** element, which in turn consists of a required **Body** element and an optional **Header** element.</span></span> <span data-ttu-id="cd356-106">El elemento **Body** contiene los datos específicos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cd356-106">The **Body** element contains the data specific to the message.</span></span> <span data-ttu-id="cd356-107">El elemento **Header** opcional puede contener información adicional no relacionada directamente con el mensaje determinado.</span><span class="sxs-lookup"><span data-stu-id="cd356-107">The optional **Header** element can contain additional information not directly related to the particular message.</span></span> <span data-ttu-id="cd356-108">Cada elemento secundario del elemento **Header** se denomina un encabezado SOAP.</span><span class="sxs-lookup"><span data-stu-id="cd356-108">Each child element of the **Header** element is called a SOAP header.</span></span>  
  
 <span data-ttu-id="cd356-109">Aunque los encabezados SOAP pueden contener datos relacionados con el mensaje, normalmente contienen información procesada por la infraestructura del servidor web.</span><span class="sxs-lookup"><span data-stu-id="cd356-109">Although the SOAP headers can contain data related to the message, they typically contain information processed by the Web server infrastructure.</span></span>  
  
 <span data-ttu-id="cd356-110">Los servicios web del servidor de informes definen varias clases para usarlas en el encabezado SOAP: <xref:ReportService2005.BatchHeader>, <xref:ReportService2010.ItemNamespaceHeader>, <xref:ReportService2010.ServerInfoHeader>, <xref:ReportService2010.TrustedUserHeader> y <xref:ReportExecution2005.ExecutionHeader>.</span><span class="sxs-lookup"><span data-stu-id="cd356-110">The Report Server Web services define several classes for use in the SOAP header: <xref:ReportService2005.BatchHeader>, <xref:ReportService2010.ItemNamespaceHeader>, <xref:ReportService2010.ServerInfoHeader>, <xref:ReportService2010.TrustedUserHeader>, and <xref:ReportExecution2005.ExecutionHeader>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd356-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cd356-111">In This Section</span></span>  
  
|<span data-ttu-id="cd356-112">Tema</span><span class="sxs-lookup"><span data-stu-id="cd356-112">Topic</span></span>|<span data-ttu-id="cd356-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd356-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="cd356-114">Métodos de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="cd356-114">Batching Methods</span></span>](batching-methods.md)|<span data-ttu-id="cd356-115">Describe cómo crear un lote de varias operaciones en una única transacción utilizando <xref:ReportService2005.BatchHeader>.</span><span class="sxs-lookup"><span data-stu-id="cd356-115">Describes how to batch multiple operations into a single transaction using <xref:ReportService2005.BatchHeader>.</span></span>|  
|[<span data-ttu-id="cd356-116">Identificar el estado de ejecución</span><span class="sxs-lookup"><span data-stu-id="cd356-116">Identifying Execution State</span></span>](identifying-execution-state.md)|<span data-ttu-id="cd356-117">Describe cómo administrar el estado de sesión en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] mediante **SessionHeader**.</span><span class="sxs-lookup"><span data-stu-id="cd356-117">Describes how to manage session state in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] using **SessionHeader**.</span></span>|  
|[<span data-ttu-id="cd356-118">Establecer el espacio de nombres de elemento para el método GetProperties</span><span class="sxs-lookup"><span data-stu-id="cd356-118">Setting the Item Namespace for the GetProperties Method</span></span>](setting-the-item-namespace-for-the-getproperties-method.md)|<span data-ttu-id="cd356-119">Describe cómo recuperar las propiedades basándose en la ruta o el Id. de un elemento utilizando el método <xref:ReportService2010.ReportingService2010.GetProperties%2A> y el encabezado SOAP <xref:ReportService2010.ItemNamespaceHeader>.</span><span class="sxs-lookup"><span data-stu-id="cd356-119">Describes how to retrieve properties based on either the path or the ID of an item by using the <xref:ReportService2010.ReportingService2010.GetProperties%2A> method and the <xref:ReportService2010.ItemNamespaceHeader> SOAP header.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd356-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd356-120">See Also</span></span>  
 <span data-ttu-id="cd356-121">[Creación de aplicaciones con el servicio web y .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="cd356-121">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="cd356-122">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cd356-122">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
