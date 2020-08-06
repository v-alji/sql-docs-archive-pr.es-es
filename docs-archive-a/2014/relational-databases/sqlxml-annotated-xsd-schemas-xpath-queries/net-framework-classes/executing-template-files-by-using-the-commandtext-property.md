---
title: Ejecutar archivos de plantilla mediante la propiedad CommandText | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], executing template files
- SQLXML Managed Classes, executing template files
- templates [SQLXML], SQLXML Managed Classes
- executing template files [SQLXML]
- CommandText property
ms.assetid: f1b1278d-252d-4a06-836e-4ef77f338ef9
author: rothja
ms.author: jroth
ms.openlocfilehash: f5507e84daf57ca4646fae3efe78c6105af35700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661877"
---
# <a name="executing-template-files-by-using-the-commandtext-property"></a><span data-ttu-id="3042b-102">Ejecutar archivos de plantilla utilizando la propiedad CommandText</span><span class="sxs-lookup"><span data-stu-id="3042b-102">Executing Template Files by Using the CommandText Property</span></span>
  <span data-ttu-id="3042b-103">En este ejemplo se muestra cómo se pueden especificar los archivos de plantilla que están compuestos de consultas SQL o XPath mediante el uso de CommandTextproperty.</span><span class="sxs-lookup"><span data-stu-id="3042b-103">This example illustrates how template files that consist of SQL or XPath queries can be specified by using the CommandTextproperty.</span></span> <span data-ttu-id="3042b-104">En lugar de especificar la consulta SQL o XPath como el valor de CommandText, puede especificar un nombre de archivo como valor.</span><span class="sxs-lookup"><span data-stu-id="3042b-104">Instead of specifying the SQL or XPath query as the value of CommandText, you can specify a file name as the value.</span></span> <span data-ttu-id="3042b-105">En el ejemplo siguiente, la propiedad CommandType se especifica como SqlXmlCommandType. TemplateFile.</span><span class="sxs-lookup"><span data-stu-id="3042b-105">In the following example, the CommandType property is specified as SqlXmlCommandType.TemplateFile.</span></span>  
  
 <span data-ttu-id="3042b-106">La aplicación de ejemplo ejecuta esta plantilla:</span><span class="sxs-lookup"><span data-stu-id="3042b-106">The sample application executes this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
    SELECT TOP 2 ContactID, FirstName, LastName   
    FROM   Person.Contact  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="3042b-107">Esta es la aplicación de ejemplo C#.</span><span class="sxs-lookup"><span data-stu-id="3042b-107">This is the C# sample application.</span></span> <span data-ttu-id="3042b-108">Para probar la aplicación, guarde la plantilla (TemplateFile.xml) y, a continuación, ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3042b-108">To test the application, save the template (TemplateFile.xml) and then execute the application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3042b-109">En el código, debe proporcionar el nombre de la instancia de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="3042b-109">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
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
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandType = SqlXmlCommandType.TemplateFile;  
         cmd.CommandText = "TemplateFile.xml";  
         using (Stream strm = cmd.ExecuteStream()){  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="3042b-110">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="3042b-110">To test the application</span></span>  
  
1.  <span data-ttu-id="3042b-111">Asegúrese de que tiene [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3042b-111">Make sure that you have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
2.  <span data-ttu-id="3042b-112">Guarde la plantilla XML (TemplateFile.xml) que se proporciona en este ejemplo en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="3042b-112">Save the XML template (TemplateFile.xml) that is provided in this example in a folder.</span></span>  
  
3.  <span data-ttu-id="3042b-113">Guarde el código C# (DocSample.cs) que se proporciona en este ejemplo en la misma carpeta en la que se almacena el esquema.</span><span class="sxs-lookup"><span data-stu-id="3042b-113">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="3042b-114">(Si almacena los archivos en otra carpeta, tendrá que modificar el código y especificar la ruta de acceso al directorio adecuada para el esquema de asignación).</span><span class="sxs-lookup"><span data-stu-id="3042b-114">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
4.  <span data-ttu-id="3042b-115">Compile el código.</span><span class="sxs-lookup"><span data-stu-id="3042b-115">Compile the code.</span></span> <span data-ttu-id="3042b-116">Para compilar el código en el símbolo del sistema, use:</span><span class="sxs-lookup"><span data-stu-id="3042b-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="3042b-117">Esto crea una aplicación ejecutable (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="3042b-117">This creates an executable (DocSample.exe).</span></span>  
  
5.  <span data-ttu-id="3042b-118">En el símbolo del sistema, ejecute DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="3042b-118">At the command prompt, execute DocSample.exe.</span></span>  
  
 <span data-ttu-id="3042b-119">Si pasa un parámetro a una plantilla, el nombre del parámetro debe comenzar con arroba (@); por ejemplo, p.Name = " @ContactID ", donde p es un objeto SqlXmlParameter.</span><span class="sxs-lookup"><span data-stu-id="3042b-119">If you pass a parameter to a template, the parameter name must begin with at sign (@); for example, p.Name="@ContactID", where p is a SqlXmlParameter object.</span></span>  
  
 <span data-ttu-id="3042b-120">Ésta es la plantilla actualizada que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="3042b-120">This is the updated template which takes one parameter.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:header>  
     <sql:param name='ContactID'>1</sql:param>    
  </sql:header>  
  <sql:query>  
    SELECT ContactID, FirstName, LastName  
    FROM   Person.Contact  
    WHERE  ContactID=@ContactID  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="3042b-121">Éste es el código actualizado en el que se pasa un parámetro para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3042b-121">This is the updated code in which a parameter is passed in to execute the template.</span></span>  
  
```  
public static int testParams()  
{  
  
   Stream strm;  
   SqlXmlParameter p;  
  
   SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
   cmd.CommandType = SqlXmlCommandType.TemplateFile;  
   cmd.CommandText = "TemplateFile.xml";  
   p = cmd.CreateParameter();  
   p.Name="@ContactID";  
   p.Value = "1";  
   strm = cmd.ExecuteStream();  
   StreamReader sw = new StreamReader(strm);  
   Console.WriteLine(sw.ReadToEnd());  
   return 0;        
}  
```  
  
  
