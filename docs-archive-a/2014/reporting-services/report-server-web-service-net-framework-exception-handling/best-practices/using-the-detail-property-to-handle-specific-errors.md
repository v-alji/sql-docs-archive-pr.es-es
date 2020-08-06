---
title: Usar la propiedad Detail para administrar errores concretos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], Detail property
- Detail property
- InnerText property
ms.assetid: 4392633d-b46b-41e6-bc12-efb64e166704
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f8ac62dc381d8f665a44fc0897ba1f4215aa8e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747458"
---
# <a name="using-the-detail-property-to-handle-specific-errors"></a><span data-ttu-id="96948-102">Usar la propiedad Detail para administrar errores concretos</span><span class="sxs-lookup"><span data-stu-id="96948-102">Using the Detail Property to Handle Specific Errors</span></span>
  <span data-ttu-id="96948-103">Para clasificar más las excepciones, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] devuelve información de error adicional en la propiedad **InnerText** de los elementos secundarios en la propiedad **Detail** de la excepción SOAP.</span><span class="sxs-lookup"><span data-stu-id="96948-103">To further classify exceptions, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] returns additional error information in the **InnerText** property of the child elements in the SOAP exception's **Detail** property.</span></span> <span data-ttu-id="96948-104">Dado que la propiedad **Detail** es un objeto **XmlNode**, puede tener acceso al texto interno del elemento secundario **Message** utilizando el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="96948-104">Because the **Detail** property is an **XmlNode** object, you can access the inner text of the **Message** child element using the following code.</span></span>  
  
 <span data-ttu-id="96948-105">Para obtener una lista de todos los elementos secundarios disponibles contenidos en la propiedad **Detail**, vea [Propiedad Detail](../soapexception-class/detail-property.md).</span><span class="sxs-lookup"><span data-stu-id="96948-105">For a list of all of the available child elements contained in the **Detail** property, see [Detail Property](../soapexception-class/detail-property.md).</span></span> <span data-ttu-id="96948-106">Para obtener más información, vea "propiedad detail" en la [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] documentación del SDK.</span><span class="sxs-lookup"><span data-stu-id="96948-106">For more information, see "Detail Property" in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
```vb  
Try  
' Code for accessing the report server  
Catch ex As SoapException  
   ' The exception is a SOAP exception, so use  
   ' the Detail property's Message element.  
   Console.WriteLine(ex.Detail("Message").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   // Code for accessing the report server  
}  
catch (SoapException ex)  
{  
   // The exception is a SOAP exception, so use  
   // the Detail property's Message element.  
   Console.WriteLine(ex.Detail["Message"].InnerXml);  
}  
```  
  
```vb  
Try  
' Code for accessing the report server  
Catch ex As SoapException  
   If ex.Detail("ErrorCode").InnerXml = "rsInvalidItemName" Then  
   End If ' Perform an action based on the specific error code  
End Try  
```  
  
```csharp  
try  
{  
   // Code for accessing the report server  
}  
catch (SoapException ex)  
{  
   if (ex.Detail["ErrorCode"].InnerXml == "rsInvalidItemName")  
   {  
      // Perform an action based on the specific error code  
   }  
}  
```  
  
 <span data-ttu-id="96948-107">La línea de código siguiente escribe el código de error concreto que se va a devolver en la excepción SOAP para la consola.</span><span class="sxs-lookup"><span data-stu-id="96948-107">The following line of code writes the specific error code being returned in the SOAP Exception to the console.</span></span> <span data-ttu-id="96948-108">Podría evaluar también el código de error y realizar acciones específicas.</span><span class="sxs-lookup"><span data-stu-id="96948-108">You could also evaluate the error code and perform specific actions.</span></span>  
  
```vb  
Console.WriteLine(ex.Detail("ErrorCode").InnerXml)  
```  
  
```csharp  
Console.WriteLine(ex.Detail["ErrorCode"].InnerXml);  
```  
  
## <a name="see-also"></a><span data-ttu-id="96948-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96948-109">See Also</span></span>  
 <span data-ttu-id="96948-110">[Introducción al control de excepciones en Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="96948-110">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 <span data-ttu-id="96948-111">[Reporting Services (clase SoapException)](../soapexception-class/reporting-services-soapexception-class.md) </span><span class="sxs-lookup"><span data-stu-id="96948-111">[Reporting Services SoapException Class](../soapexception-class/reporting-services-soapexception-class.md) </span></span>  
 [<span data-ttu-id="96948-112">Tabla de errores de SoapException</span><span class="sxs-lookup"><span data-stu-id="96948-112">SoapException Errors Table</span></span>](../soapexception-class/soapexception-errors-table.md)  
  
  
