---
title: Ejecutar consultas SQL (clases administradas de SQLXML) | Microsoft Docs
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
- ExecuteToStream method
- SQL queries [SQLXML]
ms.assetid: a561ae83-a8b6-4b9b-a819-9b86839546b4
author: rothja
ms.author: jroth
ms.openlocfilehash: d869e45de359e602b2451b9f66fa3046f6823c1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673566"
---
# <a name="executing-sql-queries-sqlxml-managed-classes"></a><span data-ttu-id="22871-102">Ejecutar consultas SQL (clases administradas de SQLXML)</span><span class="sxs-lookup"><span data-stu-id="22871-102">Executing SQL Queries (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="22871-103">En este ejemplo se muestra:</span><span class="sxs-lookup"><span data-stu-id="22871-103">This example demonstrates:</span></span>  
  
-   <span data-ttu-id="22871-104">Crear parámetros (objetos SqlXmlParameter).</span><span class="sxs-lookup"><span data-stu-id="22871-104">Creating parameters (SqlXmlParameter objects).</span></span>  
  
-   <span data-ttu-id="22871-105">Asignar valores a las propiedades (nombre y valor) de los objetos SqlXmlParameter.</span><span class="sxs-lookup"><span data-stu-id="22871-105">Assigning values to the properties (Name and Value) of SqlXmlParameter objects.</span></span>  
  
 <span data-ttu-id="22871-106">En este ejemplo se ejecuta una consulta SQL simple para recuperar el nombre, apellido y fecha de nacimiento del empleado cuyo valor de apellido se pasa como parámetro.</span><span class="sxs-lookup"><span data-stu-id="22871-106">In this example, a simple SQL query is executed to retrieve the first name, last name, and birth date of the employee whose last name value is passed as a parameter.</span></span> <span data-ttu-id="22871-107">Al especificar el parámetro (*LastName*), solo se establece la propiedad Value.</span><span class="sxs-lookup"><span data-stu-id="22871-107">In specifying the parameter (*LastName*), only the Value property is set.</span></span> <span data-ttu-id="22871-108">No se ha establecido la propiedad Name porque, en esta consulta, el parámetro es posicional y no se requiere ningún nombre.</span><span class="sxs-lookup"><span data-stu-id="22871-108">The Name property is not set, because in this query the parameter is positional and no name is required.</span></span>  
  
 <span data-ttu-id="22871-109">De forma predeterminada, la propiedad CommandType del objeto SqlXmlCommand es **SQL**.</span><span class="sxs-lookup"><span data-stu-id="22871-109">The CommandType property of the SqlXmlCommand object by default is **Sql**.</span></span> <span data-ttu-id="22871-110">Por tanto, la propiedad no se establece de forma explícita.</span><span class="sxs-lookup"><span data-stu-id="22871-110">Therefore, the property is not explicitly set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="22871-111">En el código, debe proporcionar el nombre de la instancia de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="22871-111">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
 <span data-ttu-id="22871-112">Éste es el código de C#:</span><span class="sxs-lookup"><span data-stu-id="22871-112">This is the C# code:</span></span>  
  
```  
using System;  
  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         Stream strm;  
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);        
         cmd.CommandText = "SELECT FirstName, LastName FROM Person.Contact WHERE LastName=? For XML Auto";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         string strResult;  
         try   
         {  
            strm = cmd.ExecuteStream();  
            strm.Position = 0;  
            using(StreamReader sr = new StreamReader(strm))  
            {  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         catch (SqlXmlException e)  
         {  
            //in case of an error, this prints error returned.  
            e.ErrorStream.Position=0;  
            strResult=new StreamReader(e.ErrorStream).ReadToEnd();  
            System.Console.WriteLine(strResult);  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="22871-113">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="22871-113">To test the application</span></span>  
  
1.  <span data-ttu-id="22871-114">Guarde en una carpeta el código de C# (DocSample.cs) que se proporciona en este tema.</span><span class="sxs-lookup"><span data-stu-id="22871-114">Save the C# code (DocSample.cs) provided in this topic in a folder.</span></span>  
  
2.  <span data-ttu-id="22871-115">Compile el código.</span><span class="sxs-lookup"><span data-stu-id="22871-115">Compile the code.</span></span> <span data-ttu-id="22871-116">Para compilar el código en el símbolo del sistema, use:</span><span class="sxs-lookup"><span data-stu-id="22871-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="22871-117">Esto crea una aplicación ejecutable (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="22871-117">This creates an executable (DocSample.exe).</span></span>  
  
3.  <span data-ttu-id="22871-118">En el símbolo del sistema, ejecute DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="22871-118">At the command prompt, execute DocSample.exe.</span></span>  
  
 <span data-ttu-id="22871-119">Para probar este ejemplo, debe tener instalado [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework en el equipo.</span><span class="sxs-lookup"><span data-stu-id="22871-119">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
 <span data-ttu-id="22871-120">En lugar de especificar consultas SQL como texto de comando, puede especificar una plantilla (como se muestra en el siguiente fragmento de código) que ejecute un diagrama de actualización (que también es una plantilla) para insertar un registro del cliente.</span><span class="sxs-lookup"><span data-stu-id="22871-120">Instead of specifying SQL queries as the command text, you can specify a template (as shown in the following code fragment) that executes an updategram (which is also a template) to insert a customer record.</span></span> <span data-ttu-id="22871-121">Puede especificar plantillas y diagramas de actualización en archivos y ejecutar los archivos.</span><span class="sxs-lookup"><span data-stu-id="22871-121">You can specify templates and updategrams in files and execute files.</span></span> <span data-ttu-id="22871-122">Para obtener más información, vea [ejecutar archivos de plantilla mediante la propiedad CommandText](executing-template-files-by-using-the-commandtext-property.md).</span><span class="sxs-lookup"><span data-stu-id="22871-122">For more information, see [Executing Template Files by Using the CommandText Property](executing-template-files-by-using-the-commandtext-property.md).</span></span>  
  
```  
SqlXmlCommand cmd = new SqlXmlCommand("Provider=SQLOLEDB;Data Source=SqlServerName;Initial Catalog=Database; Integrated Security=SSPI;");  
Stream stm;  
cmd.CommandType = SqlXmlCommandType.UpdateGram;  
cmd.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql' xmlns:updg='urn:schemas-microsoft-com:xml-updategram'>" +  
      "<updg:sync>" +  
       "<updg:before/>" +  
       "<updg:after>" +  
         "<Customer CustomerID='aaaaa' CustomerName='Some Name' CustomerTitle='SomeTitle' />" +  
       "</updg:after>" +  
       "</updg:sync>" +  
       "</ROOT>";  
  
stm = cmd.ExecuteStream();  
stm = null;  
cmd = null;  
```  
  
## <a name="using-executetostream"></a><span data-ttu-id="22871-123">Usar ExecuteToStream</span><span class="sxs-lookup"><span data-stu-id="22871-123">Using ExecuteToStream</span></span>  
 <span data-ttu-id="22871-124">Si tiene una secuencia existente, puede usar el método ExecuteToStream en lugar de crear un objeto de flujo y usar el método Execute.</span><span class="sxs-lookup"><span data-stu-id="22871-124">If you have an existing stream, you can use the ExecuteToStream method instead of creating a Stream object and using the Execute method.</span></span> <span data-ttu-id="22871-125">El código del ejemplo anterior se ha revisado aquí para usar el método ExecuteToStream:</span><span class="sxs-lookup"><span data-stu-id="22871-125">The code from the preceding example is revised here to use the ExecuteToStream method:</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      SqlXmlParameter p;  
      MemoryStream ms = new MemoryStream();  
      StreamReader sr = new StreamReader(ms);  
      ms.Position = 0;  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.CommandText = "select FirstName, LastName from Person.Contact where LastName = ? For XML Auto";  
      p = cmd.CreateParameter();  
      p.Value = "Achong";  
      cmd.ExecuteToStream(ms);  
      ms.Position = 0;  
      Console.WriteLine(sr.ReadToEnd());  
      return 0;        
   }  
   public static int Main(String[] args)  
   {  
      testParams();     
      return 0;  
   }  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="22871-126">También puede utilizar el ExecuteXMLReadermethod que devuelve un objeto XmlReader.</span><span class="sxs-lookup"><span data-stu-id="22871-126">You can also use the ExecuteXMLReadermethod that returns an XmlReader object.</span></span> <span data-ttu-id="22871-127">Para obtener más información, vea [ejecutar consultas SQL mediante el método ExecuteXMLReader](executing-sql-queries-by-using-the-executexmlreader-method.md).</span><span class="sxs-lookup"><span data-stu-id="22871-127">For more information, see [Executing SQL Queries by Using the ExecuteXMLReader Method](executing-sql-queries-by-using-the-executexmlreader-method.md).</span></span>  
  
  
