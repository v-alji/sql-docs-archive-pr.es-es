---
title: Impedir las solicitudes no válidas | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- invalid requests [Reporting Services]
- exceptions [Reporting Services], invalid requests
- valid requests [Reporting Services]
ms.assetid: 4a4a2d97-4c10-43a9-8298-ef5a820ea549
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 12343955c46fb98fea75048a38749b1db993fa11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676337"
---
# <a name="preventing-invalid-requests"></a><span data-ttu-id="23eb9-102">Impedir las solicitudes no válidas</span><span class="sxs-lookup"><span data-stu-id="23eb9-102">Preventing Invalid Requests</span></span>
  <span data-ttu-id="23eb9-103">Puede impedir que se inicien algunos tipos de excepciones analizando el flujo de la aplicación y asegurándose de que las solicitudes que se van a enviar al servidor de informes son válidas.</span><span class="sxs-lookup"><span data-stu-id="23eb9-103">You can prevent some types of exceptions from being thrown by analyzing your application flow and ensuring that the requests being sent to the report server are valid.</span></span> <span data-ttu-id="23eb9-104">Por ejemplo, en las aplicaciones que permiten a los usuarios agregar o actualizar el nombre de un informe, origen de datos u otro elemento de servidor de informes, debería validar el texto que un usuario podría escribir.</span><span class="sxs-lookup"><span data-stu-id="23eb9-104">For example, in applications that enable users to add or update the name of a report, data source, or other report server item, you should validate the text that a user might enter.</span></span> <span data-ttu-id="23eb9-105">Siempre debería comprobar los caracteres reservados antes de enviar la solicitud a un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="23eb9-105">You should always check for reserved characters before sending the request to a report server.</span></span> <span data-ttu-id="23eb9-106">Use instrucciones **if** condicionales u otras construcciones lógicas en el código para avisar al usuario de que no se han cumplido las condiciones necesarias para enviar solicitudes al servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="23eb9-106">Use conditional **if** statements or other logical constructs in your code to alert the user that they have not met the conditions necessary to send requests to the report server.</span></span>  
  
 <span data-ttu-id="23eb9-107">En el ejemplo de C# simplificado siguiente, se presenta a los usuarios un mensaje de error descriptivo cuando intentan crear un informe con un nombre que contiene un carácter de barra diagonal (/).</span><span class="sxs-lookup"><span data-stu-id="23eb9-107">In the following, simplified C# example, users are presented with a friendly error message when they attempt to create a report with a name that contains a forward slash (/) character.</span></span>  
  
```  
// C#  
private void PublishReport()  
{  
   int index;  
   string reservedChar;  
   string message;  
  
   // Check the text value of the name text box for "/",  
   // a reserved character  
   index = nameTextBox.Text.IndexOf(@"/");  
  
   if ( index != -1) // The text contains the character  
   {  
      reservedChar = nameTextBox.Text.Substring(index, 1);  
      // Build a user-friendly error message  
      message = "The name of the report cannot contain the reserved character " +  
         "\"" + reservedChar + "\". " +  
         "Please enter a valid name for the report. " +  
         "For more information about reserved characters, " +  
         "see the help documentation";  
  
      MessageBox.Show(message, "Invalid Input Error");  
   }  
   else // Publish the report  
   {  
      Byte[] definition = null;  
      Warning[] warnings = {};  
      string name = nameTextBox.Text;  
  
      FileStream stream = File.OpenRead("MyReport.rdl");  
      definition = new Byte[stream.Length];  
      stream.Read(definition, 0, (int) stream.Length);  
      stream.Close();  
      // Create report with user-defined name  
      rs.CreateCatalogItem("Report", name, "/Samples", false, definition, null, out warnings);  
      MessageBox.Show("Report: {0} created successfully", name);  
   }  
}  
```  
  
 <span data-ttu-id="23eb9-108">Para más información sobre los tipos de errores que se pueden evitar antes de que las solicitudes se envíen al servidor de informes, vea [Tabla de errores de SoapException](../soapexception-class/soapexception-errors-table.md).</span><span class="sxs-lookup"><span data-stu-id="23eb9-108">For more information about the types of errors that can be prevented before requests are sent to the report server, see [SoapException Errors Table](../soapexception-class/soapexception-errors-table.md).</span></span> <span data-ttu-id="23eb9-109">Para más información sobre cómo mejorar más el ejemplo anterior mediante bloques try/catch, vea [Using Try and Catch Blocks (Uso de bloques Try y Catch)](using-try-and-catch-blocks.md).</span><span class="sxs-lookup"><span data-stu-id="23eb9-109">For more information about further enhancing the previous example using try/catch blocks, see [Using Try and Catch Blocks](using-try-and-catch-blocks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23eb9-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23eb9-110">See Also</span></span>  
 <span data-ttu-id="23eb9-111">[Introducción al control de excepciones en Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="23eb9-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="23eb9-112">Clase SoapException de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="23eb9-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
