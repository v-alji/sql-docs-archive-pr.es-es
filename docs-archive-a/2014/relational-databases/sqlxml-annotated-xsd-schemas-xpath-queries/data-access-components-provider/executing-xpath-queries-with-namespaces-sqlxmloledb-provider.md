---
title: Ejecutar consultas XPath con espacios de nombres (proveedor SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing XPath queries
- namespaces property
- queries [SQLXML], SQLXMLOLEDB Provider
- XPath queries [SQLXML], namespaces
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- namespaces [SQLXML], XPath queries
ms.assetid: 024a4b7d-435d-47ba-9e80-2c2f640108f5
author: rothja
ms.author: jroth
ms.openlocfilehash: ff692b49a4c32c14655af3a9eb07071dc60ba2a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746193"
---
# <a name="executing-xpath-queries-with-namespaces-sqlxmloledb-provider"></a><span data-ttu-id="b6b1d-102">Ejecutar consultas XPath con espacios de nombres (proveedor SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="b6b1d-102">Executing XPath Queries with Namespaces (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="b6b1d-103">Las consultas XPath pueden incluir espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-103">XPath queries can include namespaces.</span></span> <span data-ttu-id="b6b1d-104">Si los elementos de esquema son espacios de nombres calificados (es decir, si incluyen un espacio de nombres de destino), las consultas XPath que se realicen en el esquema deben especificar este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-104">If the schema elements are namespace qualified (that is, if they include a target namespace), XPath queries against the schema must specify this namespace.</span></span>  
  
 <span data-ttu-id="b6b1d-105">Dado que no se admite el uso del carácter comodín (\*) en SQLXML 4.0, la consulta XPath debe especificarse utilizando un prefijo de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-105">Because using the wildcard character (\*) is not supported in SQLXML 4.0, you must specify the XPath query by using a namespace prefix.</span></span> <span data-ttu-id="b6b1d-106">Para resolver este prefijo, use la propiedad namespaces para especificar el enlace del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-106">To resolve this prefix, use the namespaces property to specify the namespace binding.</span></span>  
  
 <span data-ttu-id="b6b1d-107">En el ejemplo siguiente, la consulta XPath especifica espacios de nombres mediante el carácter comodín ( \* ) y las funciones XPath de nombre local () y espacio de nombres-URI ().</span><span class="sxs-lookup"><span data-stu-id="b6b1d-107">In the following example, the XPath query specifies namespaces by using the wildcard character (\*) and the local-name() and namespace-uri() XPath functions.</span></span> <span data-ttu-id="b6b1d-108">Esta consulta XPath devuelve todos los elementos donde el nombre local es `Contact` y el URI del espacio de nombres es `urn:myschema:Contacts`.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-108">This XPath query returns all the elements where the local name is `Contact` and the namespace URI is `urn:myschema:Contacts`.</span></span>  
  
```  
/*[local-name() = 'Contact' and namespace-uri() = 'urn:myschema:Contacts']  
```  
  
 <span data-ttu-id="b6b1d-109">En SQLXML 4.0, esta consulta XPath debe especificarse con un prefijo de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-109">In SQLXML 4.0, this XPath query must be specified with a namespace prefix.</span></span> <span data-ttu-id="b6b1d-110">Un ejemplo sería `x:Contact`, donde `x` es el prefijo del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-110">An example is `x:Contact`, where `x` is the namespace prefix.</span></span> <span data-ttu-id="b6b1d-111">Fíjese en el siguiente esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="b6b1d-111">Consider the following XSD schema:</span></span>  
  
```  
<schema xmlns="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
            xmlns:con="urn:myschema:Contacts"  
            targetNamespace="urn:myschema:Contacts">  
<complexType name="ContactType">  
  <attribute name="CID" sql:field="ContactID" type="ID"/>  
  <attribute name="FName" sql:field="FirstName" type="string"/>  
  <attribute name="LName" sql:field="LastName"/>   
</complexType>  
<element name="Contact" type="con:ContactType" sql:relation="Person.Contact"/>  
</schema>  
```  
  
 <span data-ttu-id="b6b1d-112">Dado que en este esquema se define el espacio de nombres de destino, una consulta XPath (como "Employee") en el esquema debe incluir el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-112">Because this schema defines the target namespace, an XPath query (such as "Employee") against the schema must include the namespace.</span></span>  
  
 <span data-ttu-id="b6b1d-113">Se trata de una aplicación [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic de ejemplo que ejecuta una consulta XPath (x:Employee) en el esquema XSD anterior.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-113">This is a sample [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application that executes an XPath query (x:Employee) against the preceding XSD schema.</span></span> <span data-ttu-id="b6b1d-114">Para resolver el prefijo, el enlace del espacio de nombres se especifica mediante la propiedad namespaces.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-114">To resolve the prefix, the namespace binding is specified by using the namespaces property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6b1d-115">En el código, debe suministrarse el nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-115">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="b6b1d-116">Además, este ejemplo especifica el uso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) para el proveedor de datos, que exige la instalación de software cliente de red adicional.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-116">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider, which requires additional network client software to be installed.</span></span> <span data-ttu-id="b6b1d-117">Para obtener más información, vea [requisitos del sistema para SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="b6b1d-117">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Private Sub Form_Load()  
    Dim con As New ADODB.Connection  
    Dim cmd As New ADODB.Command  
    Dim stm As New ADODB.Stream  
    con.Open "provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Data Source=SqlServerName;Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
    Set cmd.ActiveConnection = con  
    stm.Open  
    cmd.Properties("Output Stream").Value = stm  
    cmd.Properties("Output Encoding") = "utf-8"  
    cmd.Properties("Mapping schema") = "C:\DirectoryPath\con-ex.xml"  
    cmd.Properties("namespaces") = "xmlns:x='urn:myschema:Contacts'"  
    '  Debug.Print "Set Command Dialect to DBGUID_XPATH"  
    cmd.Dialect = "{ec2a4293-e898-11d2-b1b7-00c04f680c56}"  
    cmd.CommandText = "x:Contact"  
    cmd.Execute , , adExecuteStream   
    stm.Position = 0  
    Debug.Print stm.ReadText(adReadAll)  
End Sub  
```  
  
### <a name="to-test-this-application"></a><span data-ttu-id="b6b1d-118">Para probar esta aplicación</span><span class="sxs-lookup"><span data-stu-id="b6b1d-118">To test this application</span></span>  
  
1.  <span data-ttu-id="b6b1d-119">Guarde el esquema XSD de ejemplo en una carpeta.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-119">Save the sample XSD schema in a folder.</span></span>  
  
2.  <span data-ttu-id="b6b1d-120">Cree un proyecto ejecutable Visual Basic y copie el código en él.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-120">Create a Visual Basic executable project, and copy the code into it.</span></span> <span data-ttu-id="b6b1d-121">Modifique la ruta de acceso al directorio especificada según corresponda.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-121">Change the specified directory path as appropriate.</span></span>  
  
3.  <span data-ttu-id="b6b1d-122">Agregue la siguiente referencia al proyecto:</span><span class="sxs-lookup"><span data-stu-id="b6b1d-122">Add the following project reference:</span></span>  
  
    ```  
    "Microsoft ActiveX Data Objects 2.8 Library"  
    ```  
  
4.  <span data-ttu-id="b6b1d-123">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-123">Execute the application.</span></span>  
  
 <span data-ttu-id="b6b1d-124">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="b6b1d-124">This is the partial result:</span></span>  
  
```  
<y0:Employee xmlns:y0="urn:myschema:Contacts"   
             LName="Achong" CID="1" FName="Gustavo"/>  
<y0:Employee xmlns:y0="urn:myschema:Employees"   
             LName="Abel" CID="2" FName="Catherine"/>  
```  
  
 <span data-ttu-id="b6b1d-125">Los prefijos que se generan en el documento XML son arbitrarios, pero se asignan al mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6b1d-125">The prefixes that are generated in the XML document are arbitrary, but they map to the same namespace.</span></span>  
  
  
