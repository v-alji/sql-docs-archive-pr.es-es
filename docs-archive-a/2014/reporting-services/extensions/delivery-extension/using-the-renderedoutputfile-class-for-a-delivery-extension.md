---
title: Usar la clase RenderedOutputFile para una extensión de entrega | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- RenderedOutputFile class
- data streams [Reporting Services]
- delivery extensions [Reporting Services], data streams
ms.assetid: 8b591801-42d5-49fa-b710-bf7e6917accf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1dcbf250a367326e5cad528384e533a9ac9d945b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678069"
---
# <a name="using-the-renderedoutputfile-class-for-a-delivery-extension"></a><span data-ttu-id="9eaa2-102">Usar la clase RenderedOutputFile para una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="9eaa2-102">Using the RenderedOutputFile Class for a Delivery Extension</span></span>
  <span data-ttu-id="9eaa2-103">La clase <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> representa un flujo de datos e información sobre las propiedades asociadas del mismo.</span><span class="sxs-lookup"><span data-stu-id="9eaa2-103">The <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class represents a data stream and information about the data stream's associated properties.</span></span> <span data-ttu-id="9eaa2-104">La propiedad **Data** de la clase <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> se usa para representar un informe representado o un recurso de informe como un objeto **Stream**.</span><span class="sxs-lookup"><span data-stu-id="9eaa2-104">The **Data** property of the <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class is used to represent a rendered report or report resource as a **Stream** object.</span></span>  
  
 <span data-ttu-id="9eaa2-105">El método <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> del objeto **Report** devuelve una matriz de uno o varios objetos <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> que constituyen en conjunto un único informe representado.</span><span class="sxs-lookup"><span data-stu-id="9eaa2-105">The <xref:Microsoft.ReportingServices.Interfaces.Report.Render%2A> method of the **Report** object returns an array of one or more <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects that together constitute a single rendered report.</span></span> <span data-ttu-id="9eaa2-106">El primer objeto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> es el informe representado.</span><span class="sxs-lookup"><span data-stu-id="9eaa2-106">The first <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object is the rendered report.</span></span> <span data-ttu-id="9eaa2-107">Cualquier otro objeto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> son los recursos que se deben entregar junto con los datos del informe (por ejemplo, un archivo HTML e imágenes asociadas).</span><span class="sxs-lookup"><span data-stu-id="9eaa2-107">Any other <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> objects are resources that must be delivered along with the report data (for example, an HTML file and associated images).</span></span> <span data-ttu-id="9eaa2-108">Las extensiones de representación que son extensiones de un único flujo (IMAGE, PDF, MHTML y EXCEL) devuelven solo un objeto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> en la matriz.</span><span class="sxs-lookup"><span data-stu-id="9eaa2-108">Rendering extensions that are single-stream rendering extensions (IMAGE, PDF, MHTML, and EXCEL) return only one <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object in the array.</span></span>  
  
 <span data-ttu-id="9eaa2-109">Para obtener un ejemplo de cómo usar la clase <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile>, vea [Ejemplos del producto SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="9eaa2-109">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eaa2-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9eaa2-110">See Also</span></span>  
 <span data-ttu-id="9eaa2-111">[Implementar una extensión de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="9eaa2-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="9eaa2-112">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9eaa2-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
