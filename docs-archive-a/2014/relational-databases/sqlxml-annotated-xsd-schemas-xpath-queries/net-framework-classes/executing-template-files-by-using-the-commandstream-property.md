---
title: Ejecutar archivos de plantilla mediante la propiedad CommandStream | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], executing template files
- SQLXML Managed Classes, executing template files
- templates [SQLXML], SQLXML Managed Classes
- CommandStream property
ms.assetid: 55c564e3-56d1-4d85-bcaa-703e2905dd57
author: rothja
ms.author: jroth
ms.openlocfilehash: c57a2ab2f3780a8bc75b53b0cceeee0799fcfcc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661878"
---
# <a name="executing-template-files-by-using-the-commandstream-property"></a><span data-ttu-id="5468e-102">Ejecutar archivos de plantilla utilizando la propiedad CommandStream</span><span class="sxs-lookup"><span data-stu-id="5468e-102">Executing Template Files by Using the CommandStream Property</span></span>
  <span data-ttu-id="5468e-103">En este ejemplo se muestra cómo se pueden especificar los archivos de plantilla que están compuestos de consultas SQL o XPath mediante la propiedad CommandStream del objeto SqlXmlCommand.</span><span class="sxs-lookup"><span data-stu-id="5468e-103">This example illustrates how template files that consist of SQL or XPath queries can be specified by using the CommandStream property of the SqlXmlCommand object.</span></span> <span data-ttu-id="5468e-104">En esta aplicación, se abre un FileStreamobject para un archivo de comandos y se asigna la secuencia de archivos como CommandStream que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="5468e-104">In this application, a FileStreamobject is opened for a command file, and the file stream is assigned as the CommandStream that is executed.</span></span>  
  
 <span data-ttu-id="5468e-105">En el ejemplo siguiente, la propiedad CommandType se especifica como SqlXmlCommandType. template (no como TemplateFile).</span><span class="sxs-lookup"><span data-stu-id="5468e-105">In the following example, the CommandType property is specified as SqlXmlCommandType.Template (not as TemplateFile).</span></span>  
  
 <span data-ttu-id="5468e-106">Esta es la plantilla XML de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5468e-106">This is the sample XML template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
    SELECT TOP 2 ContactID, FirstName, LastName   
    FROM   Person.Contact  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="5468e-107">Esta es la aplicación C# de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5468e-107">This is the sample C# application.</span></span> <span data-ttu-id="5468e-108">Para probar la aplicación, guarde la plantilla (TemplateFile.xml) y, a continuación, ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5468e-108">To test the application, save the template (TemplateFile.xml) and then execute the application.</span></span> <span data-ttu-id="5468e-109">La aplicación ejecuta la consulta especificada en la plantilla XML y muestra el documento XML generado en pantalla.</span><span class="sxs-lookup"><span data-stu-id="5468e-109">The application executes the query that is specified in the XML template and displays the XML document that is generated on the screen.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5468e-110">En el código, debe proporcionar el nombre de la instancia de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="5468e-110">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         //Stream strm;  
         MemoryStream ms = new MemoryStream();  
         StreamWriter sw = new StreamWriter(ms);  
         ms.Position = 0;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandStream = new FileStream("TemplateFile.xml", FileMode.Open, FileAccess.Read);  
         cmd.CommandType = SqlXmlCommandType.Template;  
         using (Stream strm = cmd.ExecuteStream())  
         {  
            using (StreamReader sr = new StreamReader(strm)){  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         return 0;        
      }  
  
      public static int Main(String[] args)  
      {  
         testParams();     
         return 0;  
      }  
   }  
```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="5468e-111">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="5468e-111">To test the application</span></span>  
  
1.  <span data-ttu-id="5468e-112">Guarde la plantilla XML (TemplateFile.xml) que se proporciona en este ejemplo en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="5468e-112">Save the XML template (TemplateFile.xml) that is provided in this example in a folder.</span></span>  
  
2.  <span data-ttu-id="5468e-113">Guarde el código C# (DocSample.cs) que se proporciona en este ejemplo en la misma carpeta en la que se almacena el esquema.</span><span class="sxs-lookup"><span data-stu-id="5468e-113">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="5468e-114">(Si almacena los archivos en otra carpeta, tendrá que modificar el código y especificar la ruta de acceso al directorio adecuada para el esquema de asignación).</span><span class="sxs-lookup"><span data-stu-id="5468e-114">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="5468e-115">Compile el código.</span><span class="sxs-lookup"><span data-stu-id="5468e-115">Compile the code.</span></span> <span data-ttu-id="5468e-116">Para compilar el código en el símbolo del sistema, use:</span><span class="sxs-lookup"><span data-stu-id="5468e-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="5468e-117">Esto crea una aplicación ejecutable (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="5468e-117">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="5468e-118">En el símbolo del sistema, ejecute DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="5468e-118">At the command prompt, execute DocSample.exe.</span></span>  
  
  
