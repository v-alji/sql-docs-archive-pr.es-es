---
title: Usar datos XML en las aplicaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- parameters [XML in SQL Server]
- XML [SQL Server], ADO
- columns [XML in SQL Server], ADO.NET
- ADO [XML in SQL Server]
- columns [XML in SQL Server], SQL Server Native Client
- xml data type [SQL Server], ADO
- SQLNCLI, XML
- xml data type [SQL Server], SQL Server Native Client
- SQL Server Native Client, XML
- ADO.NET [XML in SQL Server]
- XML [SQL Server], ADO.NET
- columns [XML in SQL Server], ADO
- xml data type [SQL Server], ADO.NET
- XML [SQL Server], SQL Server Native Client
ms.assetid: 5dabf7e0-c6df-451d-a070-4661f84607fd
author: rothja
ms.author: jroth
ms.openlocfilehash: 79dd4f4d2ff3cd61bc33c632f499bfb8e8817f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744002"
---
# <a name="use-xml-data-in-applications"></a><span data-ttu-id="08914-102">Usar datos XML en las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="08914-102">Use XML Data in Applications</span></span>
  <span data-ttu-id="08914-103">En este tema se describen las opciones que están disponibles para trabajar con tipos de datos `xml` en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="08914-103">This topic describes the options that are available to you for working with the `xml` data type in your application.</span></span> <span data-ttu-id="08914-104">El tema incluye información acerca de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08914-104">The topic includes information about the following:</span></span>  
  
-   <span data-ttu-id="08914-105">Controlar XML desde una columna de tipo `xml` usando ADO y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="08914-105">Handling XML from an `xml` type column by using ADO and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span></span>  
  
-   <span data-ttu-id="08914-106">Controlar XML desde una columna de tipo `xml` utilizando ADO.NET</span><span class="sxs-lookup"><span data-stu-id="08914-106">Handling XML from an `xml` type column by using ADO.NET</span></span>  
  
-   <span data-ttu-id="08914-107">Controlar el tipo `xml` en parámetros utilizando ADO.NET</span><span class="sxs-lookup"><span data-stu-id="08914-107">Handling `xml` type in parameters by using ADO.NET</span></span>  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-ado-and-sql-server-native-client"></a><span data-ttu-id="08914-108">Controlar XML desde una columna de tipo XML usando ADO y SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="08914-108">Handling XML from an xml Type Column by Using ADO and SQL Server Native Client</span></span>  
 <span data-ttu-id="08914-109">Para usar componentes MDAC con el fin de obtener acceso a los tipos y características introducidos en [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], debe establecer la propiedad de inicialización DataTypeCompatibility en la cadena de conexión de ADO.</span><span class="sxs-lookup"><span data-stu-id="08914-109">To use MDAC components to access the types and features that were introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you must set the DataTypeCompatibility initialization property in the ADO connection string.</span></span>  
  
 <span data-ttu-id="08914-110">Por ejemplo, en el siguiente ejemplo de Visual Basic Scripting Edition (VBScript) se muestra el resultado de la realización de una consulta a una columna de tipo de datos `xml`, `Demographics`, de la tabla `Sales.Store` de la base de datos de ejemplo `AdventureWorks2012`.</span><span class="sxs-lookup"><span data-stu-id="08914-110">For example, the following Visual Basic Scripting Edition (VBScript) sample shows the results of querying an `xml` data type column, `Demographics`, in the `Sales.Store` table of the `AdventureWorks2012` sample database.</span></span> <span data-ttu-id="08914-111">Específicamente, la consulta busca el valor de la instancia de esta columna para la fila en la que `CustomerID` es igual a `3`.</span><span class="sxs-lookup"><span data-stu-id="08914-111">Specifically, the query looks for the instance value of this column for the row where the `CustomerID` is equal to `3`.</span></span>  
  
```  
Const DS = "MyServer"  
Const DB = "AdventureWorks2012"  
  
Set objConn = CreateObject("ADODB.Connection")  
Set objRs = CreateObject("ADODB.Recordset")  
  
CommandText = "SELECT Demographics" & _  
              " FROM Sales.Store" & _  
              " INNER JOIN Sales.Customer" & _  
              " ON Sales.Store.BusinessEntityID = sales.customer.StoreID" & _  
              " WHERE Sales.Customer.CustomerID = 3" & _  
              " OR Sales.Customer.CustomerID = 4"  
  
ConnectionString = "Provider=SQLNCLI11" & _  
                   ";Data Source=" & DS & _  
                   ";Initial Catalog=" & DB & _  
                   ";Integrated Security=SSPI;" & _  
                   "DataTypeCompatibility=80"  
  
'Connect to the data source.  
objConn.Open ConnectionString  
  
'Execute command through the connection and display  
Set objRs = objConn.Execute(CommandText)  
  
Dim rowcount  
rowcount = 0  
Do While Not objRs.EOF  
   rowcount = rowcount + 1  
   MsgBox "Row " & rowcount & _  
           vbCrLf & vbCrLf & objRs(0)  
   objRs.MoveNext  
Loop  
  
'Clean up.  
objRs.Close  
objConn.Close  
Set objRs = Nothing  
Set objConn = Nothing  
```  
  
 <span data-ttu-id="08914-112">Este ejemplo muestra cómo establecer la propiedad de compatibilidad de tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="08914-112">This example shows how to set the data type compatibility property.</span></span> <span data-ttu-id="08914-113">De manera predeterminada, se establece en 0 cuando se usa [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="08914-113">By default, this is set to 0 when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="08914-114">Si establece el valor en 80, el proveedor de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client hará que las columnas de tipo `xml` y las definidas por el usuario aparezcan como tipos de datos de [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08914-114">If you set the value to 80, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client provider will make `xml` and user-defined type columns appear as [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] data types.</span></span> <span data-ttu-id="08914-115">Serán DBTYPE_WSTR y DBTYPE_BYTES, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="08914-115">This would be DBTYPE_WSTR and DBTYPE_BYTES, respectively.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="08914-116">Native Client también debe estar instalado en el equipo cliente y la cadena de conexión debe especificar que se use como proveedor de datos con "`Provider=SQLNCLI11;...`".</span><span class="sxs-lookup"><span data-stu-id="08914-116">Native Client must also be installed on the client computer and the connection string must specify it for use as the data provider with "`Provider=SQLNCLI11;...`".</span></span>  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="08914-117">Para probar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="08914-117">To test this example</span></span>  
  
1.  <span data-ttu-id="08914-118">Compruebe que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client está instalado y que en el equipo cliente está disponible MDAC 2.6 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="08914-118">Verify that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is installed and that MDAC 2.6.0or later is available on the client computer.</span></span>  
  
     <span data-ttu-id="08914-119">Para obtener más información, consulte [Programación de SQL Server Native Client](../native-client/sql-server-native-client-programming.md).</span><span class="sxs-lookup"><span data-stu-id="08914-119">For more information, see [SQL Server Native Client Programming](../native-client/sql-server-native-client-programming.md).</span></span>  
  
2.  <span data-ttu-id="08914-120">Compruebe que la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está instalada.</span><span class="sxs-lookup"><span data-stu-id="08914-120">Verify that the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
     <span data-ttu-id="08914-121">Este ejemplo requiere la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08914-121">This example requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
3.  <span data-ttu-id="08914-122">Copie el código que se mostró anteriormente en este tema y péguelo en su editor de texto o de código.</span><span class="sxs-lookup"><span data-stu-id="08914-122">Copy the code shown previously in this topic and paste the code into your text or code editor.</span></span> <span data-ttu-id="08914-123">Guarde el archivo como HandlingXmlDataType.vbs.</span><span class="sxs-lookup"><span data-stu-id="08914-123">Save the file as HandlingXmlDataType.vbs.</span></span>  
  
4.  <span data-ttu-id="08914-124">Modifique el script según sea necesario por la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="08914-124">Modify the script as required for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation and save your changes.</span></span>  
  
     <span data-ttu-id="08914-125">Por ejemplo, donde se especifique `MyServer` , debe sustituirlo por `(local)` o por el nombre real del servidor en el que está instalado [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="08914-125">For example, where `MyServer` is specified, you should replace it with either `(local)` or the actual name of the server on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
5.  <span data-ttu-id="08914-126">Ejecute HandlingXmlDataType.vbs y ejecute el script.</span><span class="sxs-lookup"><span data-stu-id="08914-126">Run HandlingXmlDataType.vbs and execute the script.</span></span>  
  
 <span data-ttu-id="08914-127">Los resultados serán similares a los de la siguiente salida de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="08914-127">The results should be similar to the following sample output:</span></span>  
  
```  
Row 1  
  
<StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>1500000</AnnualSales>  
  <AnnualRevenue>150000</AnnualRevenue>  
  <BankName>Primary International</BankName>  
  <BusinessType>OS</BusinessType>  
  <YearOpened>1974</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>38000</SquareFeet>  
  <Brands>3</Brands>  
  <Internet>DSL</Internet>  
  <NumberEmployees>40</NumberEmployees>  
</StoreSurvey>  
  
Row 2  
  
<StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>300000</AnnualSales>  
  <AnnualRevenue>30000</AnnualRevenue>  
  <BankName>United Security</BankName>  
  <BusinessType>BM</BusinessType>  
  <YearOpened>1976</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>6000</SquareFeet>  
  <Brands>2</Brands>  
  <Internet>DSL</Internet>  
  <NumberEmployees>5</NumberEmployees>  
</StoreSurvey>  
```  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-adonet"></a><span data-ttu-id="08914-128">Controlar XML desde una columna de tipo xml utilizando ADO.NET</span><span class="sxs-lookup"><span data-stu-id="08914-128">Handling XML from an xml Type Column by Using ADO.NET</span></span>  
 <span data-ttu-id="08914-129">Para controlar XML desde una `xml` columna de tipo de datos mediante ADO.net y puede [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] usar el comportamiento estándar de la `SqlCommand` clase.</span><span class="sxs-lookup"><span data-stu-id="08914-129">To handle XML from an `xml` data type column by using ADO.NET and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] you can use the standard behavior of the `SqlCommand` class.</span></span> <span data-ttu-id="08914-130">Por ejemplo, una columna de tipo de datos `xml` y sus valores se pueden recuperar de la misma manera que se recupera cualquier columna SQL utilizando una clase `SqlDataReader`. Sin embargo, si desea trabajar con el contenido de una columna de tipo de datos `xml` como XML, primero tendrá que asignar el contenido a un tipo `XmlReader`.</span><span class="sxs-lookup"><span data-stu-id="08914-130">For example, an `xml` data type column and its values can be retrieved in the same way any SQL column is retrieved by using a `SqlDataReader`.However, if you want to work with the contents of an `xml` data type column as XML, you will first have to assign the contents to an `XmlReader` type.</span></span>  
  
 <span data-ttu-id="08914-131">Para obtener más información y código de ejemplo, vea el artículo sobre valores de columnas XML en un lector de datos de la documentación del SDK de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08914-131">For more information and example code, see "XML Column Values in a Data Reader" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK documentation.</span></span>  
  
## <a name="handling-an-xml-type-column-in-parameters-by-using-adonet"></a><span data-ttu-id="08914-132">Controlar una columna de tipo XML como parámetros mediante ADO.NET</span><span class="sxs-lookup"><span data-stu-id="08914-132">Handling an xml Type Column in Parameters by Using ADO.NET</span></span>  
 <span data-ttu-id="08914-133">Para controlar un tipo de datos XML pasado como un parámetro en ADO.NET y [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], puede proporcionar el valor como una instancia del tipo de datos `SqlXml`.</span><span class="sxs-lookup"><span data-stu-id="08914-133">To handle an xml data type passed as a parameter in ADO.NET and the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can supply the value as an instance of the `SqlXml` data type.</span></span> <span data-ttu-id="08914-134">No es necesario realizar ningún control especial, porque las columnas de tipo de datos `xml` de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pueden aceptar valores de parámetros del mismo modo que otros tipos de columnas y de datos, por ejemplo, `string` o `integer`.</span><span class="sxs-lookup"><span data-stu-id="08914-134">No special handling is involved, because `xml` data type columns in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can accept parameter values in the same way as other columns and data types, such as `string` or `integer`.</span></span>  
  
 <span data-ttu-id="08914-135">Para obtener más información y código de ejemplo, vea el artículo sobre valores XML como parámetros de comando de la documentación del SDK de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08914-135">For more information and example code, see "XML Values as Command Parameters" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08914-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08914-136">See Also</span></span>  
 [<span data-ttu-id="08914-137">Datos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="08914-137">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
