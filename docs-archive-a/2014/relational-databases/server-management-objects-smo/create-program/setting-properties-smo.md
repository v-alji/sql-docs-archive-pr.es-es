---
title: Establecer propiedades | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SMO [SQL Server], properties
- SQL Server Management Objects, properties
- properties [SMO]
ms.assetid: 342569ba-d2f7-44d2-8f3f-ae9c701c7f0f
author: stevestein
ms.author: sstein
ms.openlocfilehash: de381f8e4e9dfe9f6590638742e988f866ccabdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747546"
---
# <a name="setting-properties"></a><span data-ttu-id="9ffd2-102">Establecer propiedades</span><span class="sxs-lookup"><span data-stu-id="9ffd2-102">Setting Properties</span></span>
  <span data-ttu-id="9ffd2-103">Las propiedades son valores que almacenan información descriptiva sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-103">Properties are values that store descriptive information about the object.</span></span> <span data-ttu-id="9ffd2-104">Por ejemplo, las [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Opciones de configuración se representan mediante las <xref:Microsoft.SqlServer.Management.Smo.Server.Configuration%2A> propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-104">For example, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] configuration options are represented by the <xref:Microsoft.SqlServer.Management.Smo.Server.Configuration%2A> object's properties.</span></span> <span data-ttu-id="9ffd2-105">Se puede tener acceso a las propiedades de forma directa o indirecta mediante la colección de propiedades.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-105">Properties can be accessed either directly or indirectly by using the property collection.</span></span> <span data-ttu-id="9ffd2-106">Para tener acceso directamente a las propiedades, se utiliza la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ffd2-106">Accessing properties directly uses the following syntax:</span></span>  
  
 `objInstance.PropertyName`  
  
 <span data-ttu-id="9ffd2-107">Un valor de propiedad se puede modificar o recuperar dependiendo de si la propiedad tiene acceso de lectura/escritura o acceso de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-107">A property value can be modified or retrieved depending on whether the property has read/write access or read-only access.</span></span> <span data-ttu-id="9ffd2-108">También es necesario establecer ciertas propiedades antes de que se pueda crear un objeto.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-108">It is also necessary to set certain properties before an object can be created.</span></span> <span data-ttu-id="9ffd2-109">Para obtener más información, vea la referencia de SMO del objeto concreto.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-109">For more information, see the SMO reference for the particular object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ffd2-110">Las colecciones de objetos secundarios aparecen como la propiedad de un objeto.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-110">Collections of child objects appear as the property of an object.</span></span> <span data-ttu-id="9ffd2-111">Por ejemplo, la colección `Tables` es una propiedad de un objeto `Server`.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-111">For example, the `Tables` collection is a property of a `Server` object.</span></span> <span data-ttu-id="9ffd2-112">Para más información, consulte [Using Collections](using-collections.md).</span><span class="sxs-lookup"><span data-stu-id="9ffd2-112">For more information, see [Using Collections](using-collections.md).</span></span>  
  
 <span data-ttu-id="9ffd2-113">Las propiedades de un objeto son miembros de la colección Properties.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-113">The properties of an object are members of the Properties collection.</span></span> <span data-ttu-id="9ffd2-114">La colección Properties se puede utilizar para recorrer en iteración cada propiedad de un objeto.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-114">The Properties collection can be used to iterate through every property of an object.</span></span>  
  
 <span data-ttu-id="9ffd2-115">A veces una propiedad no está disponible por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9ffd2-115">Sometimes a property is not available for the following reasons:</span></span>  
  
-   <span data-ttu-id="9ffd2-116">La versión de servidor no admite la propiedad, como en el caso de que intente obtener acceso a una propiedad que representa una nueva característica de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en una versión anterior de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ffd2-116">The server version does not support the property, such as if you try to access a property that represents a new [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] feature on an older version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="9ffd2-117">El servidor no proporciona datos para la propiedad, como en el caso de que intente obtener acceso a una propiedad que representa un componente de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que no está instalado.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-117">The server does not provide data for the property, such as if you try to access a property that represents a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] component that is not installed.</span></span>  
  
 <span data-ttu-id="9ffd2-118">Puede controlar estas circunstancias si detecta las excepciones SMO <xref:Microsoft.SqlServer.Management.Smo.UnknownPropertyException> y <xref:Microsoft.SqlServer.Management.Smo.PropertyCannotBeRetrievedException>.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-118">You can handle these circumstances by catching the <xref:Microsoft.SqlServer.Management.Smo.UnknownPropertyException> and the <xref:Microsoft.SqlServer.Management.Smo.PropertyCannotBeRetrievedException> SMO exceptions.</span></span>  
  
## <a name="setting-default-initialization-fields"></a><span data-ttu-id="9ffd2-119">Establecer campos de inicialización predeterminados</span><span class="sxs-lookup"><span data-stu-id="9ffd2-119">Setting Default Initialization Fields</span></span>  
 <span data-ttu-id="9ffd2-120">SMO realiza una optimización al recuperar objetos.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-120">SMO performs an optimization when retrieving objects.</span></span> <span data-ttu-id="9ffd2-121">La optimización reduce el número de propiedades cargadas mediante la aplicación de una escala automática entre los estados siguientes:</span><span class="sxs-lookup"><span data-stu-id="9ffd2-121">The optimization minimizes the number of properties loaded by automatically scaling between the following states:</span></span>  
  
1.  <span data-ttu-id="9ffd2-122">Parcialmente cargado.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-122">Partially loaded.</span></span> <span data-ttu-id="9ffd2-123">Cuando se hace referencia por primera vez a un objeto, tiene un mínimo de propiedades disponibles (como Nombre y Esquema).</span><span class="sxs-lookup"><span data-stu-id="9ffd2-123">When an object is first referenced it has a minimum of properties available (such as Name and Schema).</span></span>  
  
2.  <span data-ttu-id="9ffd2-124">Totalmente cargado.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-124">Fully loaded.</span></span> <span data-ttu-id="9ffd2-125">Cuando se hace referencia a una propiedad, las propiedades restantes que se cargan rápidamente se inicializan y pasan a estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-125">When any property is referenced, the remaining properties that are quick to load, are initialized and are made available.</span></span>  
  
3.  <span data-ttu-id="9ffd2-126">Propiedades que utilizan mucha memoria.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-126">Properties that use lots of memory.</span></span> <span data-ttu-id="9ffd2-127">Las propiedades no disponibles restantes utilizan mucha memoria y tienen un valor de propiedad <xref:Microsoft.SqlServer.Management.Smo.Property.Expensive%2A> de True (como <xref:Microsoft.SqlServer.Management.Smo.Database.DataSpaceUsage%2A>).</span><span class="sxs-lookup"><span data-stu-id="9ffd2-127">The remaining unavailable properties use lots of memory and have an <xref:Microsoft.SqlServer.Management.Smo.Property.Expensive%2A> property value of true (such as <xref:Microsoft.SqlServer.Management.Smo.Database.DataSpaceUsage%2A>).</span></span> <span data-ttu-id="9ffd2-128">Estas propiedades solo se cargan cuando se hace referencia a ellas de forma específica.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-128">These properties are loaded only when specifically referenced.</span></span>  
  
 <span data-ttu-id="9ffd2-129">Si la aplicación captura propiedades adicionales, además de las que se proporcionan en el estado parcialmente cargado, envía una consulta para recuperar estas propiedades adicionales y pasa al estado totalmente cargado.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-129">If your application does fetch extra properties, besides the ones provided in the partially loaded state, it submits a query to retrieve these extra properties and scales up to the fully loaded state.</span></span> <span data-ttu-id="9ffd2-130">Esto puede producir un tráfico innecesario entre cliente y servidor.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-130">This can cause unnecessary traffic between the client and server.</span></span> <span data-ttu-id="9ffd2-131">Si se llama al método <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> se puede conseguir una mayor optimización.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-131">More optimization can be achieved by calling the <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method.</span></span> <span data-ttu-id="9ffd2-132">El método <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> permite la especificación de las propiedades que se cargan al inicializar el objeto.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-132">The <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method allows specification of the properties that are loaded when the object is initialized.</span></span>  
  
 <span data-ttu-id="9ffd2-133">El método <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> establece el comportamiento de carga de propiedades para el resto de aplicación o hasta que se restablece.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-133">The <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method sets the property loading behavior for the rest of application or until it is reset.</span></span> <span data-ttu-id="9ffd2-134">Puede guardar el comportamiento original mediante el método <xref:Microsoft.SqlServer.Management.Smo.Server.GetDefaultInitFields%2A> y restaurarlo cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-134">You can save the original behavior by using the <xref:Microsoft.SqlServer.Management.Smo.Server.GetDefaultInitFields%2A> method and restore it as required.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9ffd2-135">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9ffd2-135">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="getting-and-setting-a-property-in-visual-basic"></a><span data-ttu-id="9ffd2-136">Obtener y establecer una propiedad en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ffd2-136">Getting and Setting a Property in Visual Basic</span></span>  
 <span data-ttu-id="9ffd2-137">En este ejemplo de código se muestra cómo obtener la propiedad <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Information> y cómo establecer la propiedad <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> de la propiedad <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> en el miembro `ExecuteSql` del tipo enumerado <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes>.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-137">This code example shows how to get the <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Information> object and how to set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property to the `ExecuteSql` member of the <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> enumerated type.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties1](SMO How to#SMO_VBProperties1)]  -->  
  
## <a name="getting-and-setting-a-property-in-visual-c"></a><span data-ttu-id="9ffd2-138">Obtener y establecer una propiedad en Visual C#</span><span class="sxs-lookup"><span data-stu-id="9ffd2-138">Getting and Setting a Property in Visual C#</span></span>  
 <span data-ttu-id="9ffd2-139">En este ejemplo de código se muestra cómo obtener la propiedad <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Information> y cómo establecer la propiedad <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> de la propiedad <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> en el miembro `ExecuteSql` del tipo enumerado <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes>.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-139">This code example shows how to get the <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Information> object and how to set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property to the `ExecuteSql` member of the <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> enumerated type.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Get a property.   
Console.WriteLine(srv.Information.Version);   
//Set a property.   
srv.ConnectionContext.SqlExecutionModes = SqlExecutionModes.ExecuteSql;   
}  
```  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-basic"></a><span data-ttu-id="9ffd2-140">Establecer diversas propiedades antes de crear un objeto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ffd2-140">Setting Various Properties Before an Object is Created in Visual Basic</span></span>  
 <span data-ttu-id="9ffd2-141">En este ejemplo de código se muestra cómo establecer directamente la propiedad <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Table> y cómo crear y agregar columnas antes de crear el objeto <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-141">This code example shows how to directly set the <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Table> object, and how to create and add columns before you create the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties2](SMO How to#SMO_VBProperties2)]  -->  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-c"></a><span data-ttu-id="9ffd2-142">Establecer diversas propiedades antes de crear un objeto en Visual C#</span><span class="sxs-lookup"><span data-stu-id="9ffd2-142">Setting Various Properties Before an Object is Created in Visual C#</span></span>  
 <span data-ttu-id="9ffd2-143">En este ejemplo de código se muestra cómo establecer directamente la propiedad <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Table> y cómo crear y agregar columnas antes de crear el objeto <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-143">This code example shows how to directly set the <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Table> object, and how to create and add columns before you create the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Create a new table in the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
Table tb;   
//Specify the parent database, table schema, and the table name in the constructor.   
tb = new Table(db, "Test_Table", "HumanResources");   
//Add columns because the table requires columns before it can be created.   
Column c1;   
//Specify the parent table, the column name, and data type in the constructor.   
c1 = new Column(tb, "ID", DataType.Int);   
tb.Columns.Add(c1);   
c1.Nullable = false;   
c1.Identity = true;   
c1.IdentityIncrement = 1;   
c1.IdentitySeed = 0;   
Column c2;   
c2 = new Column(tb, "Name", DataType.NVarChar(100));   
c2.Nullable = false;   
tb.Columns.Add(c2);   
tb.AnsiNullsStatus = true;   
//Create the table on the instance of SQL Server.   
tb.Create();   
}  
```  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-basic"></a><span data-ttu-id="9ffd2-144">Recorrer en iteración todas las propiedades de un objeto en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ffd2-144">Iterating Through All Properties of an Object in Visual Basic</span></span>  
 <span data-ttu-id="9ffd2-145">En este ejemplo de código se recorre en iteración la colección `Properties` del objeto <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> y las propiedades de esta colección se muestran en la pantalla Salida de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ffd2-145">This code example iterates through the `Properties` collection of the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object and displays them on the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Output screen.</span></span>  
  
 <span data-ttu-id="9ffd2-146">En el ejemplo, el objeto <xref:Microsoft.SqlServer.Management.Smo.Property> se ha incluido entre corchetes porque también es una palabra clave de [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ffd2-146">In the example, the <xref:Microsoft.SqlServer.Management.Smo.Property> object has been put in square parentheses because it is also a [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] keyword.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties3](SMO How to#SMO_VBProperties3)]  -->  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-c"></a><span data-ttu-id="9ffd2-147">Recorrer en iteración todas las propiedades de un objeto en Visual C#</span><span class="sxs-lookup"><span data-stu-id="9ffd2-147">Iterating Through All Properties of an Object in Visual C#</span></span>  
 <span data-ttu-id="9ffd2-148">En este ejemplo de código se recorre en iteración la colección `Properties` del objeto <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> y las propiedades de esta colección se muestran en la pantalla Salida de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ffd2-148">This code example iterates through the `Properties` collection of the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object and displays them on the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Output screen.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Set properties on the uspGetEmployeedManagers stored procedure on the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
StoredProcedure sp;   
sp = db.StoredProcedures("uspGetEmployeeManagers");   
sp.AnsiNullsStatus = false;   
sp.QuotedIdentifierStatus = false;   
//Iterate through the properties of the stored procedure and display.   
  Property p;   
  foreach ( p in sp.Properties) {   
    Console.WriteLine(p.Name + p.Value);   
  }   
}  
```  
  
## <a name="setting-default-initialization-fields-in-visual-basic"></a><span data-ttu-id="9ffd2-149">Establecer campos de inicialización predeterminados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ffd2-149">Setting Default Initialization Fields in Visual Basic</span></span>  
 <span data-ttu-id="9ffd2-150">En este ejemplo de código se muestra cómo minimizar el número de propiedades de objeto inicializadas en un programa SMO.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-150">This code example shows how to minimize the number of object properties initialized in an SMO program.</span></span> <span data-ttu-id="9ffd2-151">Debe incluir la instrucción `using System.Collections.Specialized` para utilizar el objeto <xref:System.Collections.Specialized.StringCollection>.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-151">You have to include the `using System.Collections.Specialized`; statement to use the <xref:System.Collections.Specialized.StringCollection> object.</span></span>  
  
 <span data-ttu-id="9ffd2-152">Puede utilizarse [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] para comparar el número de instrucciones enviadas a la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con esta optimización.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-152">[!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] can be used to compare the number statements sent to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with this optimization.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDefaultInitFields1](SMO How to#SMO_VBDefaultInitFields1)]  -->  
  
## <a name="setting-default-initialization-fields-in-visual-c"></a><span data-ttu-id="9ffd2-153">Establecer campos de inicialización predeterminados en Visual C#</span><span class="sxs-lookup"><span data-stu-id="9ffd2-153">Setting Default Initialization Fields in Visual C#</span></span>  
 <span data-ttu-id="9ffd2-154">En este ejemplo de código se muestra cómo minimizar el número de propiedades de objeto inicializadas en un programa SMO.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-154">This code example shows how to minimize the number of object properties initialized in an SMO program.</span></span> <span data-ttu-id="9ffd2-155">Debe incluir la instrucción `using System.Collections.Specialized` para utilizar el objeto <xref:System.Collections.Specialized.StringCollection>.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-155">You have to include the `using System.Collections.Specialized`; statement to use the <xref:System.Collections.Specialized.StringCollection> object.</span></span>  
  
 <span data-ttu-id="9ffd2-156">Puede utilizarse [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] para comparar el número de instrucciones enviadas a la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con esta optimización.</span><span class="sxs-lookup"><span data-stu-id="9ffd2-156">[!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] can be used to compare the number statements sent to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with this optimization.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Assign the Table object type to a System.Type object variable.   
Table tb;   
Type typ;   
tb = new Table();   
typ = tb.GetType;   
//Assign the current default initialization fields for the Table object type to a   
//StringCollection object variable.   
StringCollection sc;   
sc = srv.GetDefaultInitFields(typ);   
//Set the default initialization fields for the Table object type to the CreateDate property.   
srv.SetDefaultInitFields(typ, "CreateDate");   
//Retrieve the Schema, Name, and CreateDate properties for every table in AdventureWorks2012.   
   //Note that the improvement in performance can be viewed in SQL Server Profiler.   
foreach ( tb in db.Tables) {   
   Console.WriteLine(tb.Schema + "." + tb.Name + " " + tb.CreateDate);   
}   
//Set the default initialization fields for the Table object type back to the original settings.   
srv.SetDefaultInitFields(typ, sc);   
}  
```  
  
  
