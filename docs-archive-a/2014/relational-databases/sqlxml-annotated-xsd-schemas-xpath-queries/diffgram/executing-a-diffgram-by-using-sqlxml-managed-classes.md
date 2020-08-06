---
title: Ejecutar un DiffGram mediante clases administradas de SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], Managed Classes
- SQLXML Managed Classes, DiffGrams
- Managed Classes [SQLXML], DiffGrams
- SQLXML, Managed Classes
ms.assetid: 81c687ca-8c9f-4f58-801f-8dabcc508a06
author: rothja
ms.author: jroth
ms.openlocfilehash: f36127c37eea73a2872d4bf0aef7172a88e430a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673587"
---
# <a name="executing-a-diffgram-by-using-sqlxml-managed-classes"></a><span data-ttu-id="7fd74-102">Ejecutar un DiffGram utilizando clases administradas de SQLXML</span><span class="sxs-lookup"><span data-stu-id="7fd74-102">Executing a DiffGram by Using SQLXML Managed Classes</span></span>
  <span data-ttu-id="7fd74-103">En este ejemplo se muestra cómo ejecutar un archivo DiffGram en el [!INCLUDE[msCoName](../../../includes/msconame-md.md)] entorno de .NET Framework para aplicar actualizaciones de datos a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tablas mediante las clases administradas de SQLXML (Microsoft. Data. SqlXml).</span><span class="sxs-lookup"><span data-stu-id="7fd74-103">This example shows how to execute a DiffGram file in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework environment to apply data updates to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables using SQLXML Managed Classes (Microsoft.Data.SqlXml).</span></span>  
  
 <span data-ttu-id="7fd74-104">En este ejemplo, el DiffGram actualiza la información del cliente ALFKI (CompanyName y ContactName).</span><span class="sxs-lookup"><span data-stu-id="7fd74-104">In this example, the DiffGram updates customer information (CompanyName and ContactName) for customer ALFKI.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
           xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
           xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
      <Customer diffgr:id="Customer1"   
                msdata:rowOrder="0" diffgr:hasChanges="modified"   
                CustomerID="ALFKI">  
          <CompanyName>Bottom Dollar Markets</CompanyName>  
          <ContactName>Antonio Moreno</ContactName>  
      </Customer>  
    </DataInstance>  
    <diffgr:before>  
     <Customer diffgr:id="Customer1"   
               msdata:rowOrder="0"   
               CustomerID="ALFKI">  
        <CompanyName>Alfreds Futterkiste</CompanyName>  
        <ContactName>Maria Anders</ContactName>  
      </Customer>  
    </diffgr:before>  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="7fd74-105">El **\<before>** bloque incluye un **\<Customer>** elemento (**diffgr: ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="7fd74-105">The **\<before>** block includes a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="7fd74-106">El **\<DataInstance>** bloque incluye el **\<Customer>** elemento correspondiente con el mismo **identificador**. El **\<customer>** elemento de **\<NewDataSet>** también especifica **diffgr: hasChanges = "Modified"**.</span><span class="sxs-lookup"><span data-stu-id="7fd74-106">The **\<DataInstance>** block includes the corresponding **\<Customer>** element with same **id**. The **\<customer>** element in the **\<NewDataSet>** also specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="7fd74-107">Esto indica una operación de actualización y por lo tanto, el registro de cliente de la tabla Cust se actualiza en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="7fd74-107">This indicates an update operation, and the customer record in the Cust table is updated accordingly.</span></span> <span data-ttu-id="7fd74-108">Tenga en cuenta que si no se especifica el atributo **diffgr: hasChanges** , la lógica de procesamiento de DiffGram omite este elemento y no se realiza ninguna actualización.</span><span class="sxs-lookup"><span data-stu-id="7fd74-108">Note that if the **diffgr:hasChanges** attribute is not specified, the DiffGram processing logic ignores this element and no updates are performed.</span></span>  
  
 <span data-ttu-id="7fd74-109">El siguiente es código para una aplicación de tutorial de C# que muestra cómo utilizar las clases administradas de SQLXML para ejecutar el DiffGram anterior y actualizar dos tablas (Cust, Ord) que también creará en la base de datos **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="7fd74-109">The following is code for a C# tutorial application that shows how to use the SQLXML Managed Classes to execute the above DiffGram and update two tables (Cust, Ord) you will also create in the **tempdb** database.</span></span>  
  
```  
using System;  
using System.Data;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=MyServer;database=tempdb;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      SqlXmlAdapter ad;  
      // Need a memory stream to hold diff gram temporarily  
      MemoryStream ms = new MemoryStream();  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.RootTag = "ROOT";  
      cmd.CommandStream = new FileStream("MyDiffgram.xml", FileMode.Open, FileAccess.Read);  
      cmd.CommandType = SqlXmlCommandType.DiffGram;  
      cmd.SchemaPath = "DiffGramSchema.xml";  
      // Load data set  
      DataSet ds = new DataSet();  
      ad = new SqlXmlAdapter(cmd);  
      ad.Fill(ds);  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="7fd74-110">Para probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="7fd74-110">To test the application</span></span>  
  
1.  <span data-ttu-id="7fd74-111">Asegúrese de que .NET Framework está instalado en su equipo.</span><span class="sxs-lookup"><span data-stu-id="7fd74-111">Ensure that the .NET Framework is installed on your computer.</span></span>  
  
2.  <span data-ttu-id="7fd74-112">Guarde el siguiente esquema XSD (DiffGramSchema.xml) en una carpeta:</span><span class="sxs-lookup"><span data-stu-id="7fd74-112">Save the following XSD schema (DiffGramSchema.xml) in a folder:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
     <xsd:annotation>  
      <xsd:documentation>  
        Diffgram Customers/Orders Schema.  
      </xsd:documentation>  
      <xsd:appinfo>  
           <sql:relationship name="CustomersOrders"   
                      parent="Cust"  
                      parent-key="CustomerID"  
                      child-key="CustomerID"  
                      child="Ord"/>  
      </xsd:appinfo>  
     </xsd:annotation>  
     <xsd:element name="Customer" sql:relation="Cust">  
      <xsd:complexType>  
        <xsd:sequence>  
          <xsd:element name="CompanyName"    type="xsd:string"/>  
          <xsd:element name="ContactName"    type="xsd:string"/>  
           <xsd:element name="Order" sql:relation="Ord" sql:relationship="CustomersOrders">  
            <xsd:complexType>  
              <xsd:attribute name="OrderID" type="xsd:int" sql:field="OrderID"/>  
              <xsd:attribute name="CustomerID" type="xsd:string"/>  
            </xsd:complexType>  
          </xsd:element>  
        </xsd:sequence>  
        <xsd:attribute name="CustomerID" type="xsd:string" sql:field="CustomerID"/>  
      </xsd:complexType>  
     </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="7fd74-113">Cree estas tablas en la base de datos **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="7fd74-113">Create these tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
4.  <span data-ttu-id="7fd74-114">Agregue estos datos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7fd74-114">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
5.  <span data-ttu-id="7fd74-115">Copie el DiffGram anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7fd74-115">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="7fd74-116">Guarde el archivo como MyDiffGram.xml en la misma carpeta utilizada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="7fd74-116">Save the file as MyDiffGram.xml in the same folder used in step 1.</span></span>  
  
6.  <span data-ttu-id="7fd74-117">Guarde el código C# (DiffgramSample.cs) que se proporciona arriba en la misma carpeta en la que almacenó DiffGramSchema.xml y MyDiffGram.xml en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="7fd74-117">Save the C# code (DiffgramSample.cs) that is provided above in the same folder in which the DiffGramSchema.xml and MyDiffGram.xml were stored in previous steps.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7fd74-118">Necesitará actualizar el nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la cadena de conexión de '`MyServer`' al nombre real de su instancia instalada de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fd74-118">You will need to update the name of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the connection string from '`MyServer`' to the actual name of your installed instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="7fd74-119">Si almacena los archivos en otra carpeta, tendrá que modificar el código y especificar la ruta de acceso al directorio adecuada para el esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="7fd74-119">If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.</span></span>  
  
7.  <span data-ttu-id="7fd74-120">Compile el código.</span><span class="sxs-lookup"><span data-stu-id="7fd74-120">Compile the code.</span></span> <span data-ttu-id="7fd74-121">Para compilar el código en el símbolo del sistema, use:</span><span class="sxs-lookup"><span data-stu-id="7fd74-121">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DiffgramSample.cs  
    ```  
  
     <span data-ttu-id="7fd74-122">Esto crea una aplicación ejecutable (DiffgramSample.exe).</span><span class="sxs-lookup"><span data-stu-id="7fd74-122">This creates an executable (DiffgramSample.exe).</span></span>  
  
8.  <span data-ttu-id="7fd74-123">En el símbolo del sistema, ejecute DiffgramSample.exe.</span><span class="sxs-lookup"><span data-stu-id="7fd74-123">At the command prompt, execute DiffgramSample.exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd74-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7fd74-124">See Also</span></span>  
 [<span data-ttu-id="7fd74-125">Ejemplos de DiffGram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="7fd74-125">DiffGram Examples &#40;SQLXML 4.0&#41;</span></span>](diffgram-examples-sqlxml-4-0.md)  
  
  
