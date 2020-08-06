---
title: Usar ADO con SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client, ADO
- data access [SQL Server Native Client], ADO
- ADO [SQL Server Native Client]
- SQLNCLI, ADO
ms.assetid: 118a7cac-4c0d-44fd-b63e-3d542932d239
author: rothja
ms.author: jroth
ms.openlocfilehash: ccd14432aa3541572467a4c651c1f48b1ac957f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748734"
---
# <a name="using-ado-with-sql-server-native-client"></a><span data-ttu-id="fd367-102">Usar ADO con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="fd367-102">Using ADO with SQL Server Native Client</span></span>
  <span data-ttu-id="fd367-103">Con el fin de aprovechar las nuevas características introducidas en, como [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] los conjuntos de resultados activos múltiples (Mars), las notificaciones de consulta, los tipos definidos por el usuario (UDT) o el nuevo tipo de datos **XML** , las aplicaciones existentes que utilizan objetos de datos ActiveX (ADO) deben usar el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client como proveedor de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="fd367-103">In order to take advantage of new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] such as multiple active result sets (MARS), query notifications, user-defined types (UDTs), or the new **xml** data type, existing applications that use ActiveX Data Objects (ADO) should use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider as their data access provider.</span></span>  
  
 <span data-ttu-id="fd367-104">Si no necesita usar ninguna de las características nuevas introducidas en [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], no tiene necesidad de usar el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client; puede seguir usando su proveedor de acceso a datos actual, que suele ser SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="fd367-104">If you do not need to use any of the new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], there is no need to use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider; you can continue using your current data access provider, which is typically SQLOLEDB.</span></span> <span data-ttu-id="fd367-105">Si está mejorando una aplicación existente y necesita usar las características nuevas introducidas en [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], debería utilizar el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="fd367-105">If you are enhancing an existing application and you need to use the new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], you should use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd367-106">Si está desarrollando una nueva aplicación, es recomendable que considere la posibilidad de usar ADO.NET y el proveedor de datos de .NET Framework para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en lugar de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client a fin de obtener acceso a todas las características nuevas de las versiones más recientes de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd367-106">If you are developing a new application, it is recommended that you consider using ADO.NET and the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instead of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to access all the new features of recent versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fd367-107">Para obtener más información acerca del proveedor de datos de .NET Framework para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], vea la documentación de .NET Framework SDK para ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="fd367-107">For more information about the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see the .NET Framework SDK documentation for ADO.NET.</span></span>  
  
 <span data-ttu-id="fd367-108">Para permitir que ADO utilice las características nuevas de las versiones más recientes de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], se han realizado algunas mejoras en el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client que extiende las características principales de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="fd367-108">To enable ADO to use new features of recent versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], some enhancements have been made to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider which extends the core features of OLE DB.</span></span> <span data-ttu-id="fd367-109">Estas mejoras permiten a las aplicaciones ADO usar las características más recientes de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y usar dos tipos de datos introducidos en [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]: **xml** y **udt**.</span><span class="sxs-lookup"><span data-stu-id="fd367-109">These enhancements allow ADO applications to use newer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features and to consume two data types introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]: **xml** and **udt**.</span></span> <span data-ttu-id="fd367-110">Estas mejoras también aprovechan las mejoras realizadas en los tipos de datos **varchar**, **nvarchar** y **varbinary**.</span><span class="sxs-lookup"><span data-stu-id="fd367-110">These enhancements also exploit enhancements to the **varchar**, **nvarchar**, and **varbinary** data types.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="fd367-111">Native Client agrega la propiedad de inicialización SSPROP_INIT_DATATYPECOMPATIBILITY al conjunto de propiedades DBPROPSET_SQLSERVERDBINIT para su uso por parte de las aplicaciones ADO, de modo que los nuevos tipos de datos se expongan de una manera compatible con ADO.</span><span class="sxs-lookup"><span data-stu-id="fd367-111">Native Client adds the SSPROP_INIT_DATATYPECOMPATIBILITY initialization property to the DBPROPSET_SQLSERVERDBINIT property set for use by ADO applications so that the new data types are exposed in a way compatible with ADO.</span></span> <span data-ttu-id="fd367-112">Además, el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client también define una nueva palabra clave de cadena de conexión denominada `DataTypeCompatibility` que se establece en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="fd367-112">In addition, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider also defines a new connection string keyword named `DataTypeCompatibility` that is set in the connection string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd367-113">Las aplicaciones ADO existentes pueden obtener acceso y actualizar XML, UDT, texto de valores grandes y valores de campo binarios mediante el proveedor SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="fd367-113">Existing ADO applications can access and update XML, UDT, and large value text and binary field values using the SQLOLEDB provider.</span></span> <span data-ttu-id="fd367-114">Los nuevos tipos de datos de mayor tamaño **varchar(max)** , **nvarchar(max)** y **varbinary(max)** se devuelven como los tipos ADO **adLongVarChar**, **adLongVarWChar** y **adLongVarBinary** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="fd367-114">The new larger **varchar(max)**, **nvarchar(max)**, and **varbinary(max)** data types are returned as the ADO types **adLongVarChar**, **adLongVarWChar** and **adLongVarBinary** respectively.</span></span> <span data-ttu-id="fd367-115">Las columnas XML se devuelven como **adLongVarChar** y las columnas UDT se devuelven como **adVarBinary**.</span><span class="sxs-lookup"><span data-stu-id="fd367-115">XML columns are returned as **adLongVarChar**, and UDT columns are returned as **adVarBinary**.</span></span> <span data-ttu-id="fd367-116">Sin embargo, si utiliza el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) en lugar de SQLOLEDB, debe asegurarse de establecer la palabra clave `DataTypeCompatibility` en "80" para que los nuevos tipos de datos se asignen correctamente a los tipos de datos de ADO.</span><span class="sxs-lookup"><span data-stu-id="fd367-116">However, if you use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider (SQLNCLI11) instead of SQLOLEDB, you need to make sure to set the `DataTypeCompatibility` keyword to "80" so that the new data types will map correctly to the ADO data types.</span></span>  
  
## <a name="enabling-sql-server-native-client-from-ado"></a><span data-ttu-id="fd367-117">Habilitar SQL Server Native Client desde ADO</span><span class="sxs-lookup"><span data-stu-id="fd367-117">Enabling SQL Server Native Client from ADO</span></span>  
 <span data-ttu-id="fd367-118">Para habilitar el uso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, las aplicaciones ADO deberán implementar las siguientes palabras clave en sus cadenas de conexión:</span><span class="sxs-lookup"><span data-stu-id="fd367-118">To enable the usage of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, ADO applications will need to implement the following keywords in their connection strings:</span></span>  
  
-   `Provider=SQLNCLI11`  
  
-   `DataTypeCompatibility=80`  
  
 <span data-ttu-id="fd367-119">Para obtener más información sobre las palabras clave de cadena de conexiones ADO admitidas en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, vea [usar palabras clave de cadena de conexión con SQL Server Native Client](using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="fd367-119">For more information about the ADO connections string keywords supported in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, see [Using Connection String Keywords with SQL Server Native Client](using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="fd367-120">A continuación se ofrece un ejemplo de cómo establecer una cadena de conexión ADO totalmente habilitada para trabajar con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, incluida la habilitación de la característica Mars:</span><span class="sxs-lookup"><span data-stu-id="fd367-120">The following is an example of establishing an ADO connection string that is fully enabled to work with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, including the enabling of the MARS feature:</span></span>  
  
```  
Dim con As New ADODB.Connection  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;" _  
         & "MARS Connection=True;"  
con.Open  
```  
  
## <a name="examples"></a><span data-ttu-id="fd367-121">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fd367-121">Examples</span></span>  
 <span data-ttu-id="fd367-122">En las secciones siguientes se proporcionan ejemplos de cómo se puede usar ADO con el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client.</span><span class="sxs-lookup"><span data-stu-id="fd367-122">The following sections provide examples of how you can use ADO with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
### <a name="retrieving-xml-column-data"></a><span data-ttu-id="fd367-123">Recuperar datos de columna XML</span><span class="sxs-lookup"><span data-stu-id="fd367-123">Retrieving XML Column Data</span></span>  
 <span data-ttu-id="fd367-124">En este ejemplo, se usa un conjunto de registros para recuperar y mostrar los datos de una columna XML en la base de datos de ejemplo **AdventureWorks** de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fd367-124">In this example, a recordset is used to retrieve and display the data from an XML column in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] **AdventureWorks** sample database.</span></span>  
  
```  
Dim con As New ADODB.Connection  
Dim rst As New ADODB.Recordset  
Dim sXMLResult As String  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _   
         & "DataTypeCompatibility=80;"  
  
con.Open  
  
' Get the xml data as a recordset.  
Set rst.ActiveConnection = con  
rst.Source = "SELECT AdditionalContactInfo FROM Person.Contact " _  
   & "WHERE AdditionalContactInfo IS NOT NULL"  
rst.Open  
  
' Display the data in the recordset.  
While (Not rst.EOF)  
   sXMLResult = rst.Fields("AdditionalContactInfo").Value  
   Debug.Print (sXMLResult)  
   rst.MoveNext  
End While  
  
con.Close  
Set con = Nothing  
```  
  
> [!NOTE]  
>  <span data-ttu-id="fd367-125">No se admite el filtrado de conjuntos de registros con columnas XML.</span><span class="sxs-lookup"><span data-stu-id="fd367-125">Recordset filtering is not supported with XML columns.</span></span> <span data-ttu-id="fd367-126">Si se utiliza, se devolverá un error.</span><span class="sxs-lookup"><span data-stu-id="fd367-126">If used, an error will be returned.</span></span>  
  
### <a name="retrieving-udt-column-data"></a><span data-ttu-id="fd367-127">Recuperar datos de columna UDT</span><span class="sxs-lookup"><span data-stu-id="fd367-127">Retrieving UDT Column Data</span></span>  
 <span data-ttu-id="fd367-128">En este ejemplo, se usa un objeto **Command** para ejecutar una consulta SQL que devuelve un UDT, los datos del UDT se actualizan y, después, los nuevos datos vuelven a insertarse en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fd367-128">In this example, a **Command** object is used to execute a SQL query that returns a UDT, the UDT data is updated, and then the new data is inserted back into the database.</span></span> <span data-ttu-id="fd367-129">En este ejemplo, se asume que el UDT **Point** ya se ha registrado en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fd367-129">This example assumes that the **Point** UDT has already been registered in the database.</span></span>  
  
```  
Dim con As New ADODB.Connection  
Dim cmd As New ADODB.Command  
Dim rst As New ADODB.Recordset  
Dim strOldUDT As String  
Dim strNewUDT As String  
Dim aryTempUDT() As String  
Dim strTempID As String  
Dim i As Integer  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;"  
  
con.Open  
  
' Get the UDT value.  
Set cmd.ActiveConnection = con  
cmd.CommandText = "SELECT ID, Pnt FROM dbo.Points.ToString()"  
Set rst = cmd.Execute  
strTempID = rst.Fields(0).Value  
strOldUDT = rst.Fields(1).Value  
  
' Do something with the UDT by adding i to each point.  
arytempUDT = Split(strOldUDT, ",")  
i = 3  
strNewUDT = LTrim(Str(Int(aryTempUDT(0)) + i)) + "," + _  
   LTrim(Str(Int(aryTempUDT(1)) + i))  
  
' Insert the new value back into the database.  
cmd.CommandText = "UPDATE dbo.Points SET Pnt = '" + strNewUDT + _  
   "' WHERE ID = '" + strTempID + "'"  
cmd.Execute  
  
con.Close  
Set con = Nothing  
```  
  
### <a name="enabling-and-using-mars"></a><span data-ttu-id="fd367-130">Habilitar y utilizar MARS</span><span class="sxs-lookup"><span data-stu-id="fd367-130">Enabling and Using MARS</span></span>  
 <span data-ttu-id="fd367-131">En este ejemplo, la cadena de conexión se construye para habilitar MARS a través del [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client y, a continuación, se crean dos objetos de conjunto de registros para ejecutarse con la misma conexión.</span><span class="sxs-lookup"><span data-stu-id="fd367-131">In this example, the connection string is constructed to enable MARS through the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, and then two recordset objects are created to execute using the same connection.</span></span>  
  
```  
Dim con As New ADODB.Connection  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;" _  
         & "MARS Connection=True;"  
con.Open  
  
Dim recordset1 As New ADODB.Recordset  
Dim recordset2 As New ADODB.Recordset  
  
Dim recordsaffected As Integer  
Set recordset1 =  con.Execute("SELECT * FROM Table1", recordsaffected, adCmdText)  
Set recordset2 =  con.Execute("SELECT * FROM Table2", recordsaffected, adCmdText)  
  
con.Close  
Set con = Nothing  
```  
  
 <span data-ttu-id="fd367-132">En versiones anteriores del proveedor OLE DB, este código hacía que se crease una conexión implícita en la segunda ejecución porque solo podía abrirse un conjunto de resultados activo por cada conexión única.</span><span class="sxs-lookup"><span data-stu-id="fd367-132">In prior versions of the OLE DB provider, this code would cause an implicit connection to be created on the second execution because only one active set of results could be opened per a single connection.</span></span> <span data-ttu-id="fd367-133">Dado que la conexión implícita no estaba agrupada en el grupo de conexiones OLE DB, esto produciría una sobrecarga adicional.</span><span class="sxs-lookup"><span data-stu-id="fd367-133">Because the implicit connection was not pooled in the OLE DB connection pool this would cause additional overhead.</span></span> <span data-ttu-id="fd367-134">Con la característica MARS expuesta por el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client, se obtienen varios resultados activos en la conexión.</span><span class="sxs-lookup"><span data-stu-id="fd367-134">With the MARS feature exposed by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, you get multiple active results on the one connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd367-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd367-135">See Also</span></span>  
 [<span data-ttu-id="fd367-136">Generar aplicaciones con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="fd367-136">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
