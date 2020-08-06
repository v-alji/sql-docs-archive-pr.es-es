---
title: Usar los resultados de FOR XML en el código de aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, application code usage
- XML [SQL Server], FOR XML clause
- ASP.NET [SQL Server]
- .NET Framework [SQL Server], FOR XML data
- ADO [SQL Server]
- XML data islands [SQL Server]
- data islands [SQL Server]
ms.assetid: 41ae67bd-ece9-49ea-8062-c8d658ab4154
author: rothja
ms.author: jroth
ms.openlocfilehash: 3cabe7e65cb53a28a370615ed84e38ba2b8db44c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676380"
---
# <a name="use-for-xml-results-in-application-code"></a><span data-ttu-id="0c3df-102">Usar los resultados de FOR XML en el código de aplicación</span><span class="sxs-lookup"><span data-stu-id="0c3df-102">Use FOR XML Results in Application Code</span></span>
  <span data-ttu-id="0c3df-103">Al utilizar cláusulas FOR XML con consultas SQL, se pueden recuperar e incluso convertir los resultados de la consulta como datos XML.</span><span class="sxs-lookup"><span data-stu-id="0c3df-103">By using FOR XML clauses with SQL queries, you can retrieve and even cast query results as XML data.</span></span> <span data-ttu-id="0c3df-104">Esta funcionalidad permite realizar las siguientes operaciones cuando los resultados de las consultas FOR XML se pueden utilizar en el código de aplicación XML:</span><span class="sxs-lookup"><span data-stu-id="0c3df-104">This functionality allows you to do the following when FOR XML query results can be used in XML application code:</span></span>  
  
-   <span data-ttu-id="0c3df-105">Consultar tablas SQL de instancias de valores de [Datos XML &#40;SQL Server&#41;](xml-data-sql-server.md)</span><span class="sxs-lookup"><span data-stu-id="0c3df-105">Query SQL tables for instances of [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) values</span></span>  
  
-   <span data-ttu-id="0c3df-106">Aplicar la [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md) para devolver como XML el resultado de las consultas que contienen datos con tipo de texto o imagen</span><span class="sxs-lookup"><span data-stu-id="0c3df-106">Apply the [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md) to return the result of queries that contain text or image typed data as XML</span></span>  
  
 <span data-ttu-id="0c3df-107">Este tema proporciona ejemplos que muestran estos planteamientos.</span><span class="sxs-lookup"><span data-stu-id="0c3df-107">This topic provides examples that demonstrate these approaches.</span></span>  
  
## <a name="retrieving-for-xml-data-with-ado-and-xml-data-islands"></a><span data-ttu-id="0c3df-108">Recuperar datos FOR XML con islas de datos ADO y XML</span><span class="sxs-lookup"><span data-stu-id="0c3df-108">Retrieving FOR XML Data with ADO and XML Data Islands</span></span>  
 <span data-ttu-id="0c3df-109">El objeto ADO `Stream` u otros objetos que admiten la interfaz COM `IStream`, como los objetos `Request` y `Response` de las páginas Active Server (ASP), se pueden utilizar para contener los resultados cuando se trabaja con consultas FOR XML.</span><span class="sxs-lookup"><span data-stu-id="0c3df-109">The ADO `Stream` object or other objects that support the COM `IStream` interface, such as the Active Server Pages (ASP) `Request` and `Response` objects, can be used to contain the results when you are working with FOR XML queries.</span></span>  
  
 <span data-ttu-id="0c3df-110">Por ejemplo, el siguiente código ASP muestra los resultados que se obtienen al consultar una columna de tipo de datos `xml`, Demographics, en la tabla Sales.Store de la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0c3df-110">For example, the following ASP code shows the results of querying an `xml` data type column, Demographics, in the Sales.Store table of the AdventureWorks sample database.</span></span> <span data-ttu-id="0c3df-111">Concretamente, la consulta busca el valor de instancia de esta columna para la fila en la que CustomerID es igual a 3.</span><span class="sxs-lookup"><span data-stu-id="0c3df-111">Specifically, the query looks for the instance value of this column for the row where the CustomerID is equal to 3.</span></span>  
  
```  
<!-- BeginRecordAndStreamVBS -->  
<%@ LANGUAGE = VBScript %>  
<!-- %  Option Explicit      % -->  
<!-- 'Request.ServerVariables("SERVER_NAME") & ";" & _ -->  
<HTML>  
<HEAD>  
<META NAME="GENERATOR" Content="Microsoft Developer Studio"/>  
<META HTTP-EQUIV="Content-Type" content="text/html"; charset="iso-8859-1">  
<TITLE>FOR XML Query Example</TITLE>  
<STYLE>  
   BODY  
   {  
      FONT-FAMILY: Tahoma;  
      FONT-SIZE: 8pt;  
      OVERFLOW: auto  
   }  
   H3  
   {  
      FONT-FAMILY: Tahoma;  
      FONT-SIZE: 8pt;  
      OVERFLOW: auto  
   }  
</STYLE>  
  
<!-- #include file="adovbs.inc" -->  
<%  
   Response.Write "<H3>Server-side processing</H3>"  
   Response.Write "Page Generated @ " & Now() & "<BR/>"  
   Dim adoConn  
   Set adoConn = Server.CreateObject("ADODB.Connection")  
   Dim sConn  
   sConn = "Provider=SQLOLEDB;Data Source=(local);" & _  
            "Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
   Response.write "Connect String = " & sConn & "<BR/>"  
   adoConn.ConnectionString = sConn  
   adoConn.CursorLocation = adUseClient  
   adoConn.Open  
   Response.write "ADO Version = " & adoConn.Version & "<BR/>"  
   Response.write "adoConn.State = " & adoConn.State & "<BR/>"  
   Dim adoCmd  
   Set adoCmd = Server.CreateObject("ADODB.Command")  
   Set adoCmd.ActiveConnection = adoConn  
   Dim sQuery  
   sQuery = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'><sql:query>SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</sql:query></ROOT>"  
   Response.write "Query String = " & sQuery & "<BR/>"  
   Dim adoStreamQuery  
   Set adoStreamQuery = Server.CreateObject("ADODB.Stream")  
   adoStreamQuery.Open  
   adoStreamQuery.WriteText sQuery, adWriteChar  
   adoStreamQuery.Position = 0  
   adoCmd.CommandStream = adoStreamQuery  
   adoCmd.Dialect = "{5D531CB2-E6Ed-11D2-B252-00C04F681B71}"  
   Response.write "Pushing XML to client for processing "  & "<BR/>"  
   adoCmd.Properties("Output Stream") = Response  
   Response.write "<XML ID='MyDataIsle'>"  
   adoCmd.Execute , , 1024  
   Response.write "</XML>"  
%>  
<SCRIPT language="VBScript" For="window" Event="onload">  
   Dim xmlDoc  
   Set xmlDoc = MyDataIsle.XMLDocument  
   Dim root  
   Set root = xmlDoc.documentElement.childNodes.Item(0).childNodes.Item(0).childNodes.Item(0)  
   For each child in root.childNodes  
      dim OutputXML  
      OutputXML = document.all("log").innerHTML  
      document.all("log").innerHTML = OutputXML & "<LI><B>" & child.nodeName &  ":</B>  " & child.Text  & "</LI>"  
   Next  
   MsgBox xmlDoc.xml  
</SCRIPT>  
</HEAD>  
<BODY>  
   <H3>Client-side processing of XML Document MyDataIsle</H3>  
   <UL id=log>  
   </UL>  
</BODY>  
</HTML>  
<!-- EndRecordAndStreamVBS -->  
```  
  
 <span data-ttu-id="0c3df-112">Esta página ASP de ejemplo contiene código VBScript de servidor que utiliza ADO para ejecutar la consulta FOR XML y devolver los resultados XML en una isla de datos XML, MyDataIsle.</span><span class="sxs-lookup"><span data-stu-id="0c3df-112">This example ASP page contains server-side VBScript that uses ADO to execute the FOR XML query and return the XML results in an XML data island, MyDataIsle.</span></span> <span data-ttu-id="0c3df-113">Después, la isla de datos XML se devuelve en el explorador para su posterior procesamiento del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="0c3df-113">This XML data island is then returned in the browser for additional client-side processing.</span></span> <span data-ttu-id="0c3df-114">Después, para procesar el contenido de la isla de datos XML se utiliza código VBScript del lado cliente adicional.</span><span class="sxs-lookup"><span data-stu-id="0c3df-114">Additional client-side VBScript code is then used to process the contents of the XML data island.</span></span> <span data-ttu-id="0c3df-115">Este proceso se lleva a cabo antes de mostrar el contenido como parte del DHTML resultante y abrir un cuadro de mensaje con el contenido de la isla de datos XML previamente procesado.</span><span class="sxs-lookup"><span data-stu-id="0c3df-115">This process is performed before displaying the contents as part of the resultant DHTML and opening a message box to show the preprocessed contents of the XML data island.</span></span>  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="0c3df-116">Para probar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c3df-116">To test this example</span></span>  
  
1.  <span data-ttu-id="0c3df-117">Compruebe que se ha instalado IIS y la base de datos de ejemplo AdventureWorks de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c3df-117">Verify that IIS is installed and that the AdventureWorks sample database for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been installed.</span></span>  
  
     <span data-ttu-id="0c3df-118">Este ejemplo requiere la instalación de Internet Information Services (IIS) 5.0 ó una versión posterior, con la compatibilidad con ASP habilitada.</span><span class="sxs-lookup"><span data-stu-id="0c3df-118">This example requires that Internet Information Services (IIS) version 5.0, or later versions, are installed with ASP support enabled.</span></span> <span data-ttu-id="0c3df-119">Asimismo, debe instalarse la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0c3df-119">Also, the AdventureWorks sample database has to be installed.</span></span>  
  
2.  <span data-ttu-id="0c3df-120">Copie el ejemplo de código previamente proporcionado y péguelo en su editor XML o editor de texto habitual.</span><span class="sxs-lookup"><span data-stu-id="0c3df-120">Copy the code example that was previously provided and paste it into the XML or text editor that you use.</span></span> <span data-ttu-id="0c3df-121">Guarde el archivo como RetrieveResults.asp en el directorio raíz que se utiliza para IIS.</span><span class="sxs-lookup"><span data-stu-id="0c3df-121">Save the file as RetrieveResults.asp in the root directory that is used for IIS.</span></span> <span data-ttu-id="0c3df-122">Normalmente es C:Inetpub\wwwroot.</span><span class="sxs-lookup"><span data-stu-id="0c3df-122">Typically, this is C:Inetpub\wwwroot.</span></span>  
  
3.  <span data-ttu-id="0c3df-123">Abra la página ASP en una ventana del explorador utilizando la dirección URL siguiente.</span><span class="sxs-lookup"><span data-stu-id="0c3df-123">Open the ASP page in a browser window by using the following URL.</span></span> <span data-ttu-id="0c3df-124">Primero, sustituya "MyServer" por "localhost" o el verdadero nombre del servidor donde se han instalado [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e IIS.</span><span class="sxs-lookup"><span data-stu-id="0c3df-124">First, replace 'MyServer' with either "localhost" or the actual name of the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and IIS are installed.</span></span>  
  
    ```  
    http://MyServer/RetrieveResults.asp  
    ```  
  
 <span data-ttu-id="0c3df-125">Los resultados de la página HTML generada que aparecen serán similares a la siguiente salida de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0c3df-125">The generated HTML page results that appear will be similar to the following sample output:</span></span>  
  
##### <a name="server-side-processing"></a><span data-ttu-id="0c3df-126">Procesamiento en el servidor</span><span class="sxs-lookup"><span data-stu-id="0c3df-126">Server-side processing</span></span>  
 <span data-ttu-id="0c3df-127">Page Generated \@ 3/11/2006 3:36:02 PM</span><span class="sxs-lookup"><span data-stu-id="0c3df-127">Page Generated \@ 3/11/2006 3:36:02 PM</span></span>  
  
 <span data-ttu-id="0c3df-128">Connect String = Provider=SQLOLEDB;Data Source=MyServer;Initial Catalog=AdventureWorks;Integrated Security=SSPI;</span><span class="sxs-lookup"><span data-stu-id="0c3df-128">Connect String = Provider=SQLOLEDB;Data Source=MyServer;Initial Catalog=AdventureWorks;Integrated Security=SSPI;</span></span>  
  
 <span data-ttu-id="0c3df-129">ADO Version = 2.8</span><span class="sxs-lookup"><span data-stu-id="0c3df-129">ADO Version = 2.8</span></span>  
  
 <span data-ttu-id="0c3df-130">adoConn.State = 1</span><span class="sxs-lookup"><span data-stu-id="0c3df-130">adoConn.State = 1</span></span>  
  
 <span data-ttu-id="0c3df-131">Query String = SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</span><span class="sxs-lookup"><span data-stu-id="0c3df-131">Query String = SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO</span></span>  
  
 <span data-ttu-id="0c3df-132">Pushing XML to client for processing</span><span class="sxs-lookup"><span data-stu-id="0c3df-132">Pushing XML to client for processing</span></span>  
  
##### <a name="client-side-processing-of-xml-document-mydataisle"></a><span data-ttu-id="0c3df-133">Procesamiento del documento XML MyDataIsle en el cliente</span><span class="sxs-lookup"><span data-stu-id="0c3df-133">Client-side processing of XML Document MyDataIsle</span></span>  
  
-   <span data-ttu-id="0c3df-134">**AnnualSales:** 1 500 000</span><span class="sxs-lookup"><span data-stu-id="0c3df-134">**AnnualSales:** 1500000</span></span>  
  
-   <span data-ttu-id="0c3df-135">**AnnualRevenue:** 150 000</span><span class="sxs-lookup"><span data-stu-id="0c3df-135">**AnnualRevenue:** 150000</span></span>  
  
-   <span data-ttu-id="0c3df-136">**BankName:** Primary International</span><span class="sxs-lookup"><span data-stu-id="0c3df-136">**BankName:** Primary International</span></span>  
  
-   <span data-ttu-id="0c3df-137">**BusinessType:** SO</span><span class="sxs-lookup"><span data-stu-id="0c3df-137">**BusinessType:** OS</span></span>  
  
-   <span data-ttu-id="0c3df-138">**YearOpened:** 1974</span><span class="sxs-lookup"><span data-stu-id="0c3df-138">**YearOpened:** 1974</span></span>  
  
-   <span data-ttu-id="0c3df-139">**Specialty:** Carreteras</span><span class="sxs-lookup"><span data-stu-id="0c3df-139">**Specialty:** Road</span></span>  
  
-   <span data-ttu-id="0c3df-140">**SquareFeet:** 38 000</span><span class="sxs-lookup"><span data-stu-id="0c3df-140">**SquareFeet:** 38000</span></span>  
  
-   <span data-ttu-id="0c3df-141">**Brands:** 3</span><span class="sxs-lookup"><span data-stu-id="0c3df-141">**Brands:** 3</span></span>  
  
-   <span data-ttu-id="0c3df-142">**Internet:** DSL</span><span class="sxs-lookup"><span data-stu-id="0c3df-142">**Internet:** DSL</span></span>  
  
-   <span data-ttu-id="0c3df-143">**NumberEmployees:** 40</span><span class="sxs-lookup"><span data-stu-id="0c3df-143">**NumberEmployees:** 40</span></span>  
  
 <span data-ttu-id="0c3df-144">A continuación, el cuadro de mensaje VBScript mostrará el siguiente contenido de la isla de datos XML original, sin filtrar, que ha sido devuelto en los resultados de la consulta FOR XML.</span><span class="sxs-lookup"><span data-stu-id="0c3df-144">The VBScript message box will then show the following original, unfiltered XML data island contents that were returned by the FOR XML query results.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Sales.Store>  
    <Demographics>  
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
    </Demographics>  
  </Sales.Store>  
</ROOT>  
```  
  
## <a name="retrieving-for-xml-data-with-aspnet-and-the-net-framework"></a><span data-ttu-id="0c3df-145">Recuperar datos FOR XML con ASP.NET y .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0c3df-145">Retrieving FOR XML Data with ASP.NET and the .NET Framework</span></span>  
 <span data-ttu-id="0c3df-146">Como en el ejemplo anterior, el siguiente código ASP.NET muestra los resultados que se obtienen al consultar una columna de tipo de datos `xml`, Demographics, en la tabla Sales.Store de la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0c3df-146">As in the previous example, the following ASP.NET code shows the results of querying an `xml` data type column, Demographics, in the Sales.Store table of the AdventureWorks sample database.</span></span> <span data-ttu-id="0c3df-147">Como en el ejemplo anterior, la consulta busca el valor de instancia de esta columna para la fila en la que CustomerID es igual a 3.</span><span class="sxs-lookup"><span data-stu-id="0c3df-147">As in the previous example, the query looks for the instance value of this column for the row where the CustomerID is equal to 3.</span></span>  
  
 <span data-ttu-id="0c3df-148">En este ejemplo, se utilizan las siguientes API administradas de Microsoft .NET Framework para devolver y representar los resultados de la consulta FOR XML:</span><span class="sxs-lookup"><span data-stu-id="0c3df-148">In this example, the following Microsoft .NET Framework managed APIs are used to accomplish the return and rendering of the FOR XML query results:</span></span>  
  
1.  <span data-ttu-id="0c3df-149">Se utiliza `SqlConnection` para abrir una conexión con SQL Server basada en el contenido de una variable de cadena de conexión especificada, strConn.</span><span class="sxs-lookup"><span data-stu-id="0c3df-149">`SqlConnection` is used to open a connection to SQL Server, based on the contents of a specified connection string variable, strConn.</span></span>  
  
2.  <span data-ttu-id="0c3df-150">A continuación, se utiliza `SqlDataAdapter` como adaptador de datos y se emplea la conexión SQL y una cadena de consulta SQL especificada para ejecutar la consulta FOR XML.</span><span class="sxs-lookup"><span data-stu-id="0c3df-150">`SqlDataAdapter` is then used as the data adapter and it uses the SQL connection and a specified SQL query string to execute the FOR XML query.</span></span>  
  
3.  <span data-ttu-id="0c3df-151">Después de que se ha ejecutado la consulta, se llama al método `SqlDataAdapter.Fill`, al que se le pasa una instancia de `DataSet,` MyDataSet, para llenar el conjunto de datos con la salida de la consulta FOR XML.</span><span class="sxs-lookup"><span data-stu-id="0c3df-151">After the query has executed, the `SqlDataAdapter.Fill` method is then called and passed an instance of a `DataSet,` MyDataSet, in order to fill the data set with the output of the FOR XML query.</span></span>  
  
4.  <span data-ttu-id="0c3df-152">Después, se llama al método `DataSet.GetXml` para devolver los resultados de la consulta como una cadena que se puede mostrar en la página HTML generada en el servidor.</span><span class="sxs-lookup"><span data-stu-id="0c3df-152">The `DataSet.GetXml` method is then called to return the query results as a string that can be displayed in the server-generated HTML page.</span></span>  
  
    ```  
    <%@ Page Language="VB" %>  
    <HTML>  
    <HEAD>  
    <TITLE>FOR XML Query Example</TITLE>  
    <STYLE>  
       BODY  
       {  
          FONT-FAMILY: Tahoma;  
          FONT-SIZE: 8pt;  
          OVERFLOW: auto  
       }  
       H3  
       {  
          FONT-FAMILY: Tahoma;  
          FONT-SIZE: 8pt;  
          OVERFLOW: auto  
       }  
    </STYLE>  
    </HEAD>  
    <BODY>  
    <%  
    Dim s as String  
    s = "<H3>Server-side processing</H3>" & _  
        "Page Generated @ " & Now() & "<BR/>"  
  
    Dim SQL As String   
    SQL = "SELECT Demographics from Sales.Store WHERE CustomerID = 3 FOR XML AUTO"  
  
    Dim strConn As String   
    strConn = "Server=(local);Database=AdventureWorks;Integrated Security=SSPI;"  
  
    Dim MySqlConn As New System.Data.SqlClient.SqlConnection(strConn)  
    Dim MySqlAdapter As New System.Data.SqlClient.SqlDataAdapter(SQL,MySqlConn)  
    Dim MyDataSet As New System.Data.DataSet  
  
    MySqlConn.Open()  
    s = s & "<P>SqlConnection opened.</P>"   
  
    MySqlAdapter.Fill(MyDataSet)  
    s = s & "<P>" & MyDataSet.GetXml  & "</P>"  
  
    MySqlConn.Close()  
    s = s & "<P>SqlConnection closed.</P>"   
  
    Message.InnerHtml=s  
    %>  
    <SPAN id="Message" runat=server />  
    </BODY>  
    </HTML>  
    ```  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="0c3df-153">Para probar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c3df-153">To test this example</span></span>  
  
1.  <span data-ttu-id="0c3df-154">Compruebe que se ha instalado IIS y la base de datos de ejemplo AdventureWorks de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c3df-154">Verify that IIS is installed and that the AdventureWorks sample database for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been installed.</span></span>  
  
     <span data-ttu-id="0c3df-155">Este ejemplo requiere la instalación de Internet Information Services (IIS) 5.0 ó una versión posterior, con la compatibilidad con ASP.NET habilitada.</span><span class="sxs-lookup"><span data-stu-id="0c3df-155">This example requires that Internet Information Services (IIS) version 5.0, or later versions, are installed with ASP.NET support enabled.</span></span> <span data-ttu-id="0c3df-156">Asimismo, debe instalarse la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0c3df-156">Also, the AdventureWorks sample database has to be installed.</span></span>  
  
2.  <span data-ttu-id="0c3df-157">Copie el código previamente proporcionado y péguelo en su editor XML o editor de texto habitual.</span><span class="sxs-lookup"><span data-stu-id="0c3df-157">Copy the code that was previously provided and paste it into the XML or text editor that you use.</span></span> <span data-ttu-id="0c3df-158">Guarde el archivo como RetrieveResults.aspx en el directorio raíz utilizado para IIS.</span><span class="sxs-lookup"><span data-stu-id="0c3df-158">Save the file as RetrieveResults.aspx in the root directory used for IIS.</span></span> <span data-ttu-id="0c3df-159">Normalmente es C:Inetpub\wwwroot.</span><span class="sxs-lookup"><span data-stu-id="0c3df-159">Typically, this is C:Inetpub\wwwroot.</span></span>  
  
3.  <span data-ttu-id="0c3df-160">Abra la página ASP.NET en una ventana del explorador utilizando la dirección URL siguiente.</span><span class="sxs-lookup"><span data-stu-id="0c3df-160">Open the ASP.NET page in a browser window using the following URL.</span></span> <span data-ttu-id="0c3df-161">Primero, sustituya "MyServer" por "localhost" o el verdadero nombre del servidor donde se han instalado [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e IIS.</span><span class="sxs-lookup"><span data-stu-id="0c3df-161">First, replace 'MyServer' with either "localhost" or the actual name of the server where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and IIS are installed.</span></span>  
  
    ```  
    http://MyServer/RetrieveResults.aspx  
    ```  
  
 <span data-ttu-id="0c3df-162">Los resultados de la página HTML generada que aparecen serán similares a la siguiente salida de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0c3df-162">The generated HTML page results that appear will be similar to the following sample output:</span></span>  
  
##### <a name="server-side-processing"></a><span data-ttu-id="0c3df-163">Procesamiento en el servidor</span><span class="sxs-lookup"><span data-stu-id="0c3df-163">Server-side processing</span></span>  
  
```  
Page Generated @ 3/11/2006 3:36:02 PM  
  
SqlConnection opened.  
  
<Sales.Store><Demographics><StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey"><AnnualSales>1500000</AnnualSales><AnnualRevenue>150000</AnnualRevenue><BankName>Primary International</BankName><BusinessType>OS</BusinessType><YearOpened>1974</YearOpened><Specialty>Road</Specialty><SquareFeet>38000</SquareFeet><Brands>3</Brands><Internet>DSL</Internet><NumberEmployees>40</NumberEmployees></StoreSurvey></Demographics></Sales.Store>  
  
SqlConnection closed.  
```  
  
> [!NOTE]  
>  <span data-ttu-id="0c3df-164">La [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `xml` compatibilidad con tipos de datos permite solicitar que el resultado de una consulta for XML se devuelva como `xml` tipo de datos, en lugar de datos con tipo de cadena o imagen, especificando la [Directiva Type](type-directive-in-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="0c3df-164">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]`xml` data type support lets you request that the result of a FOR XML query be returned as `xml` data type, instead of as string or image typed data, by specifying the [TYPE directive](type-directive-in-for-xml-queries.md).</span></span> <span data-ttu-id="0c3df-165">Cuando se usa la directiva TYPE en las consultas FOR XML, el tipo de acceso que se proporciona mediante programación a los resultados de FOR XML es similar al que se muestra en [Usar datos XML en las aplicaciones](use-xml-data-in-applications.md).</span><span class="sxs-lookup"><span data-stu-id="0c3df-165">When the TYPE directive is used in FOR XML queries, it provides programmatic access to the FOR XML results similar to that shown in [Use XML Data in Applications](use-xml-data-in-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c3df-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c3df-166">See Also</span></span>  
 [<span data-ttu-id="0c3df-167">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0c3df-167">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
