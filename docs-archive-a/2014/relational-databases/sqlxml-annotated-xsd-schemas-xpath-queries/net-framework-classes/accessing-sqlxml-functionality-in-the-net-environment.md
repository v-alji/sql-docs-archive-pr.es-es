---
title: Obtener acceso a la funcionalidad SQLXML en el entorno de .NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], accessing SQLXML functionality
- SQLXML Managed Classes, accessing SQLXML functionality
- DiffGrams [SQLXML], accessing SQLXML functionality
- .NET Framework [SQLXML], accessing SQLXML functionality
ms.assetid: 74744535-2945-414d-9a5b-7e8cc363953a
author: rothja
ms.author: jroth
ms.openlocfilehash: a2ba0a54310833c0a1a1315aa94d78fe5650d480
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673584"
---
# <a name="accessing-sqlxml-functionality-in-the-net-environment"></a><span data-ttu-id="dac35-102">Acceso a la funcionalidad de SQLXML en el entorno .NET</span><span class="sxs-lookup"><span data-stu-id="dac35-102">Accessing SQLXML Functionality in the .NET Environment</span></span>
  <span data-ttu-id="dac35-103">En este ejemplo se muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dac35-103">This example shows:</span></span>  
  
-   <span data-ttu-id="dac35-104">Cómo usar [!INCLUDE[msCoName](../../../includes/msconame-md.md)] las clases administradas de SQLXML (Microsoft. Data. SqlXml) para tener acceso a Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en el [!INCLUDE[msCoName](../../../includes/msconame-md.md)] entorno de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dac35-104">How to use [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML Managed Classes (Microsoft.Data.SqlXml) to access Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework environment.</span></span>  
  
-   <span data-ttu-id="dac35-105">Cómo pueden aplicar actualizaciones de datos a tablas los DiffGrams que se generan en el entorno de .NET Framework [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dac35-105">How DiffGrams that are generated in the .NET Framework environment can apply data updates to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables.</span></span>  
  
 <span data-ttu-id="dac35-106">En esta aplicación se ejecuta una consulta XPath para un esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="dac35-106">In this application, an XPath query is executed against an XSD schema.</span></span> <span data-ttu-id="dac35-107">La ejecución de la consulta XPath devuelve un documento XML que consta de datos de contacto (**FirstName**, **LastName**).</span><span class="sxs-lookup"><span data-stu-id="dac35-107">The execution of the XPath query returns an XML document that consists of contact data (**FirstName**, **LastName**).</span></span> <span data-ttu-id="dac35-108">La aplicación carga el documento XML en el conjunto de datos en el entorno de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dac35-108">The application loads the XML document in the dataset in the .NET Framework environment.</span></span> <span data-ttu-id="dac35-109">Se modifican los datos del conjunto de datos: el nombre del primer contacto del conjunto de datos cambia a "Susan".</span><span class="sxs-lookup"><span data-stu-id="dac35-109">The data in the dataset is modified: the contact's first name is changed to "Susan" for the first contact in the dataset.</span></span> <span data-ttu-id="dac35-110">El DiffGram se genera a partir del conjunto de datos y después se aplica la actualización especificada en el DiffGram (el cambio en el nombre del empleado) a la tabla Person.Contact. </span><span class="sxs-lookup"><span data-stu-id="dac35-110">The DiffGram is generated from the dataset, and the update that is specified in the DiffGram (the change in the employee's first name) is then applied to the Person.Contact table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dac35-111">En el código, debe suministrarse el nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="dac35-111">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using System.Data;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      DataRow row;  
      SqlXmlAdapter ad;  
      //need a memory stream to hold diff gram temporarily  
      MemoryStream ms = new MemoryStream();  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.RootTag = "ROOT";  
      cmd.CommandText = "Con";  
      cmd.CommandType = SqlXmlCommandType.XPath;  
      cmd.SchemaPath = "MySchema.xml";  
      //load data set  
      DataSet ds = new DataSet();  
      ad = new SqlXmlAdapter(cmd);  
      ad.Fill(ds);  
      row = ds.Tables["Con"].Rows[0];  
      row["FName"] = "Susan";  
      ad.Update(ds);  
      return 0;  
   }  
   public static int Main(String[] args)  
   {  
      testParams();  
      return 0;  
   }  
}  
```  
  
 <span data-ttu-id="dac35-112">**Para probar el ejemplo:**</span><span class="sxs-lookup"><span data-stu-id="dac35-112">**To test the example:**</span></span>  
  
 <span data-ttu-id="dac35-113">Para probar este ejemplo, debe tener instalado [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework en el equipo.</span><span class="sxs-lookup"><span data-stu-id="dac35-113">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
1.  <span data-ttu-id="dac35-114">Guarde este esquema XSD (MySchema.xml) en una carpeta:</span><span class="sxs-lookup"><span data-stu-id="dac35-114">Save this XSD schema (MySchema.xml) in a folder:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="Con" sql:relation="Person.Contact" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="FName"    
                         sql:field="FirstName"   
                         type="xsd:string" />   
            <xsd:element name="LName"    
                         sql:field="LastName"    
                         type="xsd:string" />  
         </xsd:sequence>  
         <xsd:attribute name="ContactID" type="xsd:integer" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
2.  <span data-ttu-id="dac35-115">Guarde el código C# (DocSample.cs) que se proporciona en este ejemplo en la misma carpeta en la que está almacenado el esquema.</span><span class="sxs-lookup"><span data-stu-id="dac35-115">Save the C# code (DocSample.cs) provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="dac35-116">(Si almacena los archivos en otra carpeta, tendrá que modificar el código y especificar la ruta de acceso al directorio adecuada para el esquema de asignación).</span><span class="sxs-lookup"><span data-stu-id="dac35-116">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="dac35-117">Compile el código.</span><span class="sxs-lookup"><span data-stu-id="dac35-117">Compile the code.</span></span> <span data-ttu-id="dac35-118">Para compilar el código en el símbolo del sistema, use:</span><span class="sxs-lookup"><span data-stu-id="dac35-118">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="dac35-119">Esto crea una aplicación ejecutable (DocSample.exe).</span><span class="sxs-lookup"><span data-stu-id="dac35-119">This creates an executable (DocSample.exe).</span></span>  
  
 <span data-ttu-id="dac35-120">En el símbolo del sistema, ejecute DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="dac35-120">At the command prompt, execute DocSample.exe.</span></span>  
  
  
