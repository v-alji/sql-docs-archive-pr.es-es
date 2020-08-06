---
title: Uso de la interfaz IDeliveryReportServerInformation para una extensión de entrega | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- IDeliveryReportServerInformation interface
- delivery extensions [Reporting Services], retrieving report server information
ms.assetid: adbce647-18f3-470c-8114-42f8bcc95dc2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 52e137d1a866305ec6435a4940fe98448bce5778
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678070"
---
# <a name="using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension"></a><span data-ttu-id="c4105-102">Utilizar la interfaz IDeliveryReportServerInformation para una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="c4105-102">Using the IDeliveryReportServerInformation Interface for a Delivery Extension</span></span>
  <span data-ttu-id="c4105-103">La interfaz <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> expone varias propiedades que se pueden utilizar para recuperar información sobre un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c4105-103">The <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> interface exposes several properties that you can use to retrieve information about a report server.</span></span> <span data-ttu-id="c4105-104">Puede usar esta información para entregar notificaciones e informes.</span><span class="sxs-lookup"><span data-stu-id="c4105-104">You can use this information to deliver notifications and reports.</span></span> <span data-ttu-id="c4105-105">Al implementar la clase de extensión de entrega, implementa la propiedad <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> cuando lo requiere la interfaz <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>.</span><span class="sxs-lookup"><span data-stu-id="c4105-105">When implementing your delivery extension class, you implement the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> property as required by the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface.</span></span> <span data-ttu-id="c4105-106">La propiedad <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> devuelve un objeto que implementa la interfaz <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation>.</span><span class="sxs-lookup"><span data-stu-id="c4105-106">The <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ReportServerInformation%2A> property returns an object that implements the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> interface.</span></span> <span data-ttu-id="c4105-107">En este objeto puede obtener una lista de las extensiones de representación que admite actualmente el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c4105-107">From this object you can get a list of rendering extensions currently supported by the report server.</span></span>  
  
 <span data-ttu-id="c4105-108">El `for` bucle siguiente podría usarse para almacenar una lista de extensiones de representación disponibles actualmente en el servidor de informes en un objeto **ArrayList** .</span><span class="sxs-lookup"><span data-stu-id="c4105-108">The following `for` loop could be used to store a list of rendering extensions currently available on the report server in an **ArrayList** object.</span></span>  
  
```vb  
Dim renderFormats As New ArrayList()  
Dim e As Microsoft.ReportingServices.Interfaces.Extension  
For Each e In  ReportServerInformation.RenderingExtension  
   If e.Visible Then  
      renderFormats.Add(e.Name)  
   End If  
Next e  
```  
  
```csharp  
ArrayList renderFormats = new ArrayList();  
foreach (Microsoft.ReportingServices.Interfaces.Extension e in ReportServerInformation.RenderingExtension)  
{   
   if (e.Visible)  
   {  
      renderFormats.Add(e.Name);  
   }  
}  
```  
  
 <span data-ttu-id="c4105-109">Para más información sobre la interfaz <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation>, vea [Uso de la interfaz IDeliveryReportServerInformation para una extensión de entrega](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md).</span><span class="sxs-lookup"><span data-stu-id="c4105-109">For more information about the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> interface, see [Using the IDeliveryReportServerInformation Interface for a Delivery Extension](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4105-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4105-110">See Also</span></span>  
 <xref:Microsoft.ReportingServices.Interfaces>   
 <span data-ttu-id="c4105-111">[Implementar una extensión de entrega](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="c4105-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="c4105-112">Biblioteca de extensiones de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c4105-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
