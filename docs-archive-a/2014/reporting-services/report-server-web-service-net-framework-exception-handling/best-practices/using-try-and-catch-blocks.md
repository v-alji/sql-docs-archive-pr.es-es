---
title: Uso de los bloques Try y Catch | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], try/catch blocks
- try/catch blocks [Reporting Services]
ms.assetid: a7a9ef53-e3b6-4bf7-81f3-d85615954e6f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a6aadb392fa4117484f3373ae232c3ed9c4b1d63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749068"
---
# <a name="using-try-and-catch-blocks"></a><span data-ttu-id="455d5-102">Uso de los bloques Try y Catch</span><span class="sxs-lookup"><span data-stu-id="455d5-102">Using Try and Catch Blocks</span></span>
  <span data-ttu-id="455d5-103">Después de limitar las solicitudes no válidas al servidor de informes agregando instrucciones condicionales al código, debería proporcionar un sistema de administración de excepciones adecuado a través del uso de bloques try/catch.</span><span class="sxs-lookup"><span data-stu-id="455d5-103">After you limit invalid requests to the report server by adding conditional statements to your code, you should supply adequate exception handling through the use of try/catch blocks.</span></span> <span data-ttu-id="455d5-104">Esta técnica proporciona otro nivel de protección con las solicitudes que no son válidas.</span><span class="sxs-lookup"><span data-stu-id="455d5-104">This technique provides another layer of protection against requests that are not valid.</span></span> <span data-ttu-id="455d5-105">Si una solicitud al servidor de informes se incluye en un bloque try y esa solicitud hace que el servidor de informes inicie una excepción, esta se detecta en el bloque catch, evitando así que la aplicación finalice inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="455d5-105">If a request to the report server is encased in a try block and that request causes the report server to throw an exception, the exception is caught in the catch block, thus preventing your application from ending unexpectedly.</span></span> <span data-ttu-id="455d5-106">Una vez detectada la excepción, puede utilizarla para indicar al usuario que haga algo de manera diferente o simplemente le permita saber, de una manera descriptiva, que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="455d5-106">Once the exception is caught, you can use the exception to either instruct the user to do something differently, or just let the user know, in a friendly way, that an error has occurred.</span></span> <span data-ttu-id="455d5-107">A continuación, puede utilizar un bloque finally para limpiar los recursos.</span><span class="sxs-lookup"><span data-stu-id="455d5-107">You can then use a finally block to clean up any resources.</span></span> <span data-ttu-id="455d5-108">Lo mejor sería generar un plan de administración de excepciones general para evitar la duplicación innecesaria de bloques try/catch.</span><span class="sxs-lookup"><span data-stu-id="455d5-108">Ideally, you should generate a general exception-handling plan to avoid unnecessary duplication of try/catch blocks.</span></span>  
  
 <span data-ttu-id="455d5-109">En el ejemplo siguiente se utilizan bloques try/catch para mejorar la confiabilidad del código de administración de excepciones.</span><span class="sxs-lookup"><span data-stu-id="455d5-109">The following example uses try/catch blocks to enhance the reliability of the exception handling code.</span></span>  
  
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
         "consult the online documentation";  
  
      MessageBox.Show(message, "Invalid Input Error");  
   }  
   else // Publish the report  
   {  
      Byte[] definition = null;  
      Warning[] warnings = {};  
      string name = nameTextBox.Text;  
  
      try  
      {  
         FileStream stream = File.OpenRead("MyReport.rdl");  
         definition = new Byte[stream.Length];  
         stream.Read(definition, 0, (int) stream.Length);  
         stream.Close();  
         // Create report with user-defined name  
         rs.CreateCatalogItem("Report", name, "/Samples", false, definition, null, out warnings);  
         MessageBox.Show("Report: {0} created successfully", name);  
      }  
  
      // Catch expected exceptions beginning with the most specific,  
      // moving to the least specific  
      catch(IOException ex)  
      {  
         MessageBox.Show(ex.Message, "File IO Exception");  
      }  
  
      catch (SoapException ex)  
      {  
         // The exception is a SOAP exception, so use  
         // the Detail property's Message element.  
         MessageBox.Show(ex.Detail["Message"].InnerXml, "SOAP Exception");   
      }  
  
      catch (Exception ex)  
      {  
         MessageBox.Show(ex.Message, "General Exception");  
      }  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="455d5-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="455d5-110">See Also</span></span>  
 <span data-ttu-id="455d5-111">[Introducción al control de excepciones en Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="455d5-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="455d5-112">Clase SoapException de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="455d5-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
