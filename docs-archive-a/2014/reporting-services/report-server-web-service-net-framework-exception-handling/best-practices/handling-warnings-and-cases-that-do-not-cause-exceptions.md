---
title: Administrar las advertencias y casos que no producen excepciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], warnings that don't cause
- warnings [Reporting Services]
ms.assetid: 475c0713-6265-44e7-9ebc-ebdd1b89e0af
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 88d3daf63cf5f04975a2941d0634f357ce81456c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746739"
---
# <a name="handling-warnings-and-cases-that-do-not-cause-exceptions"></a><span data-ttu-id="7b870-102">Administrar las advertencias y casos que no producen excepciones</span><span class="sxs-lookup"><span data-stu-id="7b870-102">Handling Warnings and Cases That Do Not Cause Exceptions</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="7b870-103">no genera excepciones para las advertencias y ciertos errores.</span><span class="sxs-lookup"><span data-stu-id="7b870-103">does not throw exceptions for warnings and certain errors.</span></span> <span data-ttu-id="7b870-104">Por ejemplo, al utilizar el método <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> para publicar un nuevo informe en un servidor de informes, cualquier advertencia que se produzca se devuelve como una matriz de objetos <xref:ReportService2010.Warning>.</span><span class="sxs-lookup"><span data-stu-id="7b870-104">For example, when you use the <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> method to publish a new report to a report server, any warnings that occur are returned as an array of <xref:ReportService2010.Warning> objects.</span></span> <span data-ttu-id="7b870-105">Estas advertencias se deberían administrar y mostrar para que se puedan tomar las medidas adecuadas.</span><span class="sxs-lookup"><span data-stu-id="7b870-105">These warnings should be handled and displayed so that appropriate action can be taken.</span></span>  
  
```vb  
Try  
   rs.CreateCatalogItem(name, parentFolder, False, definition, Nothing, warnings)  
  
   If Not (warnings.Length = 0) Then  
      Dim warning As Warning  
      For Each warning In warnings  
         Console.WriteLine(warning.Message)  
      Next warning  
   Else  
      Console.WriteLine("Report {0} created successfully with no warnings", name)  
   End If  
  
Catch ex As SoapException  
   Console.WriteLine(ex.Detail("Message").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   rs.CreateCatalogItem("Report", name, parentFolder, false, definition, null, out warnings);  
  
   if (warnings.Length != 0)  
   {  
      foreach (Warning warning in warnings)  
      {  
         Console.WriteLine(warning.Message);  
      }  
   }  
   else  
      Console.WriteLine("Report {0} created successfully with no warnings", name);  
}  
  
catch (SoapException ex)  
{  
   Console.WriteLine(ex.Detail["Message"].InnerXml);  
}  
```  
  
 <span data-ttu-id="7b870-106">Otra manera de administrar los errores es evaluar los valores que devuelven ciertos métodos.</span><span class="sxs-lookup"><span data-stu-id="7b870-106">Another way to handle errors is to evaluate the return values of certain methods.</span></span> <span data-ttu-id="7b870-107">Por ejemplo, el método <xref:ReportService2010.ReportingService2010.FindItems%2A> se puede utilizar para buscar los elementos específicos en la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7b870-107">For example, the <xref:ReportService2010.ReportingService2010.FindItems%2A> method can be used to search for specific items in the report server database.</span></span> <span data-ttu-id="7b870-108">Si no se encuentra ningún elemento que coincida con el criterio de búsqueda, se devuelve una matriz NULL de los objetos <xref:ReportService2010.CatalogItem>.</span><span class="sxs-lookup"><span data-stu-id="7b870-108">If no items are found that match the search criteria, a null array of <xref:ReportService2010.CatalogItem> objects is returned.</span></span> <span data-ttu-id="7b870-109">Debería evaluar la matriz, comprobar si es `null` y permitir que el usuario sepa si no se encontró ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="7b870-109">You should evaluate the array, check for `null`, and let the user know if no items were found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b870-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b870-110">See Also</span></span>  
 <xref:ReportService2010.CatalogItem>   
 <span data-ttu-id="7b870-111">[Introducción al control de excepciones en Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="7b870-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="7b870-112">Clase SoapException de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7b870-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
