---
title: Usar esquemas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- XML [SMO]
ms.assetid: 9d04de01-efeb-4b2d-8c28-3234bc7ff2f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: a0e5c58bb05da7025651a4e55e29541d694ba1ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750574"
---
# <a name="using-xml-schemas"></a><span data-ttu-id="bd62e-102">Utilizar esquemas XML</span><span class="sxs-lookup"><span data-stu-id="bd62e-102">Using XML Schemas</span></span>
  <span data-ttu-id="bd62e-103">La programación XML en SMO se limita a proporcionar tipos de datos XML, espacios de nombres XML y la indización simple en columnas de tipo de datos XML.</span><span class="sxs-lookup"><span data-stu-id="bd62e-103">XML programming in SMO is limited to providing XML data types, XML namespaces, and simple indexing on XML data type columns.</span></span>  
  
 [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="bd62e-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]proporciona almacenamiento nativo para las instancias de documentos XML.</span><span class="sxs-lookup"><span data-stu-id="bd62e-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provides native storage for XML document instances.</span></span> <span data-ttu-id="bd62e-105">Los esquemas XML le permiten definir tipos de datos XML complejos, que se pueden utilizar para validar los documentos XML para asegurar la integridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="bd62e-105">XML schemas let you define complex XML data types, which can be used to validate XML documents to ensure data integrity.</span></span> <span data-ttu-id="bd62e-106">El esquema XML se define en el objeto <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="bd62e-106">The XML schema is defined in the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd62e-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd62e-107">Example</span></span>  
 <span data-ttu-id="bd62e-108">Para utilizar cualquier ejemplo de código que se proporcione, deberá elegir el entorno de programación, la plantilla de programación y el lenguaje de programación con los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="bd62e-108">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="bd62e-109">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="bd62e-109">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-an-xml-schema-in-visual-basic"></a><span data-ttu-id="bd62e-110">Crear un esquema XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd62e-110">Creating an XML Schema in Visual Basic</span></span>  
 <span data-ttu-id="bd62e-111">En este ejemplo de código se muestra cómo crear un esquema XML utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="bd62e-111">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="bd62e-112">La propiedad <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>, que define la colección de esquemas XML, contiene varias comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="bd62e-112">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="bd62e-113">Estas comillas se reemplazan por la cadena `chr(34)`.</span><span class="sxs-lookup"><span data-stu-id="bd62e-113">These are replaced by the `chr(34)` string.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBXMLSchema1](SMO How to#SMO_VBXMLSchema1)]  -->  
  
## <a name="creating-an-xml-schema-in-visual-c"></a><span data-ttu-id="bd62e-114">Crear un esquema XML en Visual C#</span><span class="sxs-lookup"><span data-stu-id="bd62e-114">Creating an XML Schema in Visual C#</span></span>  
 <span data-ttu-id="bd62e-115">En este ejemplo de código se muestra cómo crear un esquema XML utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="bd62e-115">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="bd62e-116">La propiedad <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>, que define la colección de esquemas XML, contiene varias comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="bd62e-116">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="bd62e-117">Estas comillas se reemplazan por la cadena `chr(34)`.</span><span class="sxs-lookup"><span data-stu-id="bd62e-117">These are replaced by the `chr(34)` string.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = default(Server);  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Define an XmlSchemaCollection object by supplying the parent  
            // database and name arguments in the constructor.   
            XmlSchemaCollection xsc = default(XmlSchemaCollection);  
            xsc = new XmlSchemaCollection(db, "MySampleCollection");  
            xsc.Text = "<schema xmlns=" + Strings.Chr(34) + "http://www.w3.org/2001/XMLSchema" + Strings.Chr(34) + " xmlns:ns=" + Strings.Chr(34) + "http://ns" + Strings.Chr(34) + "><element name=" + Strings.Chr(34) + "e" + Strings.Chr(34) + " type=" + Strings.Chr(34) + "dateTime" + Strings.Chr(34) + "/></schema>";  
            //Create the XML schema collection on the instance of SQL Server.   
            xsc.Create();  
        }  
```  
  
## <a name="creating-an-xml-schema-in-powershell"></a><span data-ttu-id="bd62e-118">Crear un esquema XML en PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd62e-118">Creating an XML Schema in PowerShell</span></span>  
 <span data-ttu-id="bd62e-119">En este ejemplo de código se muestra cómo crear un esquema XML utilizando el objeto <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection>.</span><span class="sxs-lookup"><span data-stu-id="bd62e-119">This code example shows how to create an XML schema by using the <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection> object.</span></span> <span data-ttu-id="bd62e-120">La propiedad <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A>, que define la colección de esquemas XML, contiene varias comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="bd62e-120">The <xref:Microsoft.SqlServer.Management.Smo.XmlSchemaCollection.Text%2A> property, which defines the XML schema collection, contains several double quotation marks.</span></span> <span data-ttu-id="bd62e-121">Estas comillas se reemplazan por la cadena `chr(34)`.</span><span class="sxs-lookup"><span data-stu-id="bd62e-121">These are replaced by the `chr(34)` string.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance replace LocalMachine with the physical server  
cd \sql\LocalHost  
$srv = Get-Item default  
  
#Reference the AdventureWorks database.  
$db = $srv.Databases["AdventureWorks2012"]  
  
#Create a new schema collection  
$xsc = New-Object -TypeName Microsoft.SqlServer.Management.SMO.XmlSchemaCollection `  
-argumentlist $db,"MySampleCollection"  
  
#Add the xml  
$dq = '"' # the double quote character  
$xsc.Text = "<schema xmlns=" + $dq + "http://www.w3.org/2001/XMLSchema" + $dq + `  
"  xmlns:ns=" + $dq + "http://ns" + $dq + "><element name=" + $dq + "e" + $dq +`  
 " type=" + $dq + "dateTime" + $dq + "/></schema>"  
  
#Create the XML schema collection on the instance of SQL Server.  
$xsc.Create()  
```  
