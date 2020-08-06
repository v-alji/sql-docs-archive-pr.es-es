---
title: Usar la clase Report para una extensión de entrega | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], report information
- Report class
ms.assetid: 1145ac63-eafd-452a-82af-16f85b1676dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a3f750c2383253636db255cbe9f1ce0ee676a9d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678066"
---
# <a name="using-the-report-class-for-a-delivery-extension"></a><span data-ttu-id="2343c-102">Usar la clase Report para una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="2343c-102">Using the Report Class for a Delivery Extension</span></span>
  <span data-ttu-id="2343c-103">La clase <xref:Microsoft.ReportingServices.Interfaces.Report> representa un informe en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="2343c-103">The <xref:Microsoft.ReportingServices.Interfaces.Report> class represents a report in the report server database.</span></span> <span data-ttu-id="2343c-104">Cada suscripción está asociada a un informe concreto.</span><span class="sxs-lookup"><span data-stu-id="2343c-104">Any subscription is associated with a specific report.</span></span> <span data-ttu-id="2343c-105">El informe está contenido en la notificación.</span><span class="sxs-lookup"><span data-stu-id="2343c-105">The report is contained in the notification.</span></span> <span data-ttu-id="2343c-106">La extensión de entrega puede utilizar el objeto <xref:Microsoft.ReportingServices.Interfaces.Report> que forma parte de la notificación para representar el informe.</span><span class="sxs-lookup"><span data-stu-id="2343c-106">Your delivery extension can use the <xref:Microsoft.ReportingServices.Interfaces.Report> object that is part of the notification to render the report.</span></span> <span data-ttu-id="2343c-107">El objeto <xref:Microsoft.ReportingServices.Interfaces.Report> también contiene las propiedades específicas del informe, como la dirección URL para el informe en el servidor de informes y el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="2343c-107">The <xref:Microsoft.ReportingServices.Interfaces.Report> object also contains report-specific properties, such as the URL to the report on the report server and the name of the report.</span></span> <span data-ttu-id="2343c-108">Todas estas propiedades se pueden utilizar como parte del proveedor de entrega.</span><span class="sxs-lookup"><span data-stu-id="2343c-108">These properties can all be used as part of your delivery provider.</span></span>  
  
 <span data-ttu-id="2343c-109">El método <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> de la clase <xref:Microsoft.ReportingServices.Interfaces.Report> se puede utilizar para representar un informe.</span><span class="sxs-lookup"><span data-stu-id="2343c-109">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method of the <xref:Microsoft.ReportingServices.Interfaces.Report> class can be used to render a report.</span></span> <span data-ttu-id="2343c-110">El método <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> devuelve una matriz de uno o más objetos <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> que comprenden un único informe representado.</span><span class="sxs-lookup"><span data-stu-id="2343c-110">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method returns an array of one or more <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects that together comprise a single rendered report.</span></span> <span data-ttu-id="2343c-111">El primer objeto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> es el informe representado.</span><span class="sxs-lookup"><span data-stu-id="2343c-111">The first <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object is the rendered report.</span></span> <span data-ttu-id="2343c-112">Cualquier otro objeto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> son los recursos que se deben entregar junto con los datos del informe (por ejemplo, un archivo HTML e imágenes asociadas).</span><span class="sxs-lookup"><span data-stu-id="2343c-112">Any other <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects are resources that must be delivered along with the report data (for example, an HTML file and associated images).</span></span> <span data-ttu-id="2343c-113">Las extensiones de representación que son extensiones de un único flujo (IMAGE, PDF, MHTML y Excel) devuelven solo un objeto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> en la matriz.</span><span class="sxs-lookup"><span data-stu-id="2343c-113">Rendering extensions that are single-stream rendering extensions (IMAGE, PDF, MHTML, and Excel) return only one <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object in the array.</span></span>  
  
 <span data-ttu-id="2343c-114">El objeto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>, que contiene el flujo del informe, puede estar incluido como parte de una entrega.</span><span class="sxs-lookup"><span data-stu-id="2343c-114">The <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object, which contains the report stream, can be included as part of a delivery.</span></span>  
  
 <span data-ttu-id="2343c-115">Para ver un ejemplo de cómo utilizar la clase <xref:Microsoft.ReportingServices.Interfaces.Report>, vea [Muestras de productos de SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="2343c-115">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.Report> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2343c-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2343c-116">See Also</span></span>  
 <span data-ttu-id="2343c-117">[Implementar una extensión de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="2343c-117">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 <span data-ttu-id="2343c-118">[Biblioteca de extensiones de Reporting Services](../reporting-services-extension-library.md) </span><span class="sxs-lookup"><span data-stu-id="2343c-118">[Reporting Services Extension Library](../reporting-services-extension-library.md) </span></span>  
 [<span data-ttu-id="2343c-119">Uso de la clase RenderedOutputFile para una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="2343c-119">Using the RenderedOutputFile Class for a Delivery Extension</span></span>](using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
  
  
