---
title: Ejecutar consultas SQL mediante el método ExecuteXMLReader | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML], SQLXML Managed Classes
- SQLXML Managed Classes, executing SQL queries
- Managed Classes [SQLXML], executing SQL queries
- ExecuteXmlReader method
- SQL queries [SQLXML]
ms.assetid: f106a4c5-8d6e-40c0-bf1f-11e121afcb01
author: rothja
ms.author: jroth
ms.openlocfilehash: 1570e877ae84a813e5a053df34c35d5fe840969c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673568"
---
# <a name="executing-sql-queries-by-using-the-executexmlreader-method"></a><span data-ttu-id="675e6-102">Ejecutar consultas SQL mediante el método ExecuteXMLReader</span><span class="sxs-lookup"><span data-stu-id="675e6-102">Executing SQL Queries by Using the ExecuteXMLReader Method</span></span>
  <span data-ttu-id="675e6-103">En lugar de usar el método ExecuteToStream, puede utilizar el método ExecuteXmlReader del objeto SqlXmlCommand para ejecutar comandos.</span><span class="sxs-lookup"><span data-stu-id="675e6-103">Instead of using the ExecuteToStream method, you can use the ExecuteXmlReader method of the SqlXmlCommand object to execute commands.</span></span> <span data-ttu-id="675e6-104">Este método devuelve un objeto XmlReader que se puede usar para el procesamiento posterior del resultado (que en este ejemplo está imprimiendo los nombres de los elementos o atributos y los valores).</span><span class="sxs-lookup"><span data-stu-id="675e6-104">This method returns an XmlReader object that can be used for further processing of the result (which in this example is printing the element or attribute names and the values).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="675e6-105">En el código, debe proporcionar el nombre de la instancia de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="675e6-105">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
using System.Xml;  
   class Test  
   {  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks2012;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         SqlXmlParameter p;  
         XmlReader Reader;  
         XmlTextWriter tw;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "select FirstName, LastName from Person.Person where LastName = ? For XML Auto";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         Reader = cmd.ExecuteXmlReader();  
            tw = new XmlTextWriter(Console.Out);  
         Reader.MoveToContent();  
         tw.WriteNode(Reader, false);  
         tw.Flush();  
         tw.Close();  
         Reader.Close();  
  
         return 0;  
      }  
  
      static int Main(string[] args)  
      {  
         testParams();  
         return 0;  
      }  
   }  
```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="675e6-106">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="675e6-106">To test the application</span></span>  
  
1.  <span data-ttu-id="675e6-107">Asegúrese de que tiene [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="675e6-107">Make sure that you have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
2.  <span data-ttu-id="675e6-108">Guarde el código C# (DocSample.cs) que se proporciona en este tema en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="675e6-108">Save the C# code (DocSample.cs) that is provided in this topic in a folder.</span></span>  
  
3.  <span data-ttu-id="675e6-109">Compile el código.</span><span class="sxs-lookup"><span data-stu-id="675e6-109">Compile the code.</span></span> <span data-ttu-id="675e6-110">Para compilar el código en el símbolo del sistema, use:</span><span class="sxs-lookup"><span data-stu-id="675e6-110">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="675e6-111">Esto crea una aplicación ejecutable (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="675e6-111">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="675e6-112">En el símbolo del sistema, ejecute DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="675e6-112">At the command prompt, execute DocSample.exe.</span></span>  
  
  
