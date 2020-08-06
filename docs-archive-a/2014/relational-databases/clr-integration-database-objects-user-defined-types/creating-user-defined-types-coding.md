---
title: Codificar tipos definidos por el usuario | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- validation [CLR integration]
- UDTs [CLR integration], coding
- UserDefined serialization format [CLR integration]
- Point UDT
- Parse method
- null values [CLR integration]
- ToString method
- ValidatePoint method
- attributes [CLR integration]
- coding user-defined types [CLR integration]
- Read method
- Write method
- nullability [CLR integration]
- user-defined types [CLR integration], coding
- Currency UDT
- validating UDT values
- exposing UDT properties [CLR integration]
ms.assetid: 1e5b43b3-4971-45ee-a591-3f535e2ac722
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e88c4d8162e5c7c921f5c5062f5b3c23df40a2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669712"
---
# <a name="coding-user-defined-types"></a><span data-ttu-id="aa248-102">Codificar tipos definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="aa248-102">Coding User-Defined Types</span></span>
  <span data-ttu-id="aa248-103">Al codificar la definición de un tipo definido por el usuario (UDT), debe implementar varias características, en función de si implementa el UDT como una clase o como una estructura, así como de las opciones de formato y serialización que haya elegido.</span><span class="sxs-lookup"><span data-stu-id="aa248-103">When coding your user-defined type (UDT) definition, you must implement various features, depending on whether you are implementing the UDT as a class or a structure, as well as on the format and serialization options you have chosen.</span></span>  
  
 <span data-ttu-id="aa248-104">El ejemplo de esta sección muestra cómo implementar un UDT `Point` como `struct` (o `Structure` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="aa248-104">The example in this section illustrates implementing a `Point` UDT as a `struct` (or `Structure` in Visual Basic).</span></span> <span data-ttu-id="aa248-105">El UDT `Point` consta de coordenadas X e Y que se implementan como procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="aa248-105">The `Point` UDT consists of X and Y coordinates implemented as property procedures.</span></span>  
  
 <span data-ttu-id="aa248-106">Para definir un UDT, se requieren los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa248-106">The following namespaces are required when defining a UDT:</span></span>  
  
```vb  
Imports System  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
```  
  
```csharp  
using System;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
```  
  
 <span data-ttu-id="aa248-107">El espacio de nombres `Microsoft.SqlServer.Server` contiene los objetos necesarios para varios atributos del UDT y el espacio de nombres `System.Data.SqlTypes` contiene las clases que representan los tipos de datos nativos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponibles para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aa248-107">The `Microsoft.SqlServer.Server` namespace contains the objects required for various attributes of your UDT, and the `System.Data.SqlTypes` namespace contains the classes that represent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types available to the assembly.</span></span> <span data-ttu-id="aa248-108">Es obvio que puede haber espacios de nombres adicionales que el ensamblado necesite para funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="aa248-108">There may of course be additional namespaces that your assembly requires in order to function correctly.</span></span> <span data-ttu-id="aa248-109">El tipo definido por el usuario `Point` también usa el espacio de nombres `System.Text` para trabajar con cadenas.</span><span class="sxs-lookup"><span data-stu-id="aa248-109">The `Point` UDT also uses the `System.Text` namespace for working with strings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa248-110">Los objetos de base de datos de Visual C++, tales como los tipos definidos por el usuario, compilados con `/clr:pure` no se admiten para la ejecución.</span><span class="sxs-lookup"><span data-stu-id="aa248-110">Visual C++ database objects, such as UDTs, compiled with `/clr:pure` are not supported for execution.</span></span>  
  
## <a name="specifying-attributes"></a><span data-ttu-id="aa248-111">Especificar atributos</span><span class="sxs-lookup"><span data-stu-id="aa248-111">Specifying Attributes</span></span>  
 <span data-ttu-id="aa248-112">Los atributos determinan el modo de usar la serialización para construir la representación de almacenamiento de los UDT y para transmitirlos por valor al cliente.</span><span class="sxs-lookup"><span data-stu-id="aa248-112">Attributes determine how serialization is used to construct the storage representation of UDTs and to transmit UDTs by value to the client.</span></span>  
  
 <span data-ttu-id="aa248-113">Se necesita `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute`.</span><span class="sxs-lookup"><span data-stu-id="aa248-113">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` is required.</span></span> <span data-ttu-id="aa248-114">El atributo `Serializable` es opcional.</span><span class="sxs-lookup"><span data-stu-id="aa248-114">The `Serializable` attribute is optional.</span></span> <span data-ttu-id="aa248-115">También puede especificar `Microsoft.SqlServer.Server.SqlFacetAttribute` para proporcionar información acerca del tipo de valor devuelto de un UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-115">You can also specify the `Microsoft.SqlServer.Server.SqlFacetAttribute` to provide information about the return type of a UDT.</span></span> <span data-ttu-id="aa248-116">Para obtener más información, vea [Atributos personalizados para las rutinas CLR](../clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md).</span><span class="sxs-lookup"><span data-stu-id="aa248-116">For more information, see [Custom Attributes for CLR Routines](../clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md).</span></span>  
  
### <a name="point-udt-attributes"></a><span data-ttu-id="aa248-117">Atributos del UDT Point</span><span class="sxs-lookup"><span data-stu-id="aa248-117">Point UDT Attributes</span></span>  
 <span data-ttu-id="aa248-118">`Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` establece el formato de almacenamiento del UDT `Point` en `Native`.</span><span class="sxs-lookup"><span data-stu-id="aa248-118">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` sets the storage format for the `Point` UDT to `Native`.</span></span> <span data-ttu-id="aa248-119">`IsByteOrdered` se establece en `true`, lo que garantiza que los resultados de las operaciones de comparación en SQL Server sean los mismos que si se hubiesen realizado las mismas operaciones en código administrado.</span><span class="sxs-lookup"><span data-stu-id="aa248-119">`IsByteOrdered` is set to `true`, which guarantees that the results of comparisons are the same in SQL Server as if the same comparison had taken place in managed code.</span></span> <span data-ttu-id="aa248-120">El UDT implementa la interfaz `System.Data.SqlTypes.INullable` para que se tenga en cuenta el valor NULL de los UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-120">The UDT implements the `System.Data.SqlTypes.INullable` interface to make the UDT null aware.</span></span>  
  
 <span data-ttu-id="aa248-121">En el siguiente fragmento de código se muestran los atributos del UDT `Point`.</span><span class="sxs-lookup"><span data-stu-id="aa248-121">The following code fragment shows the attributes for the `Point` UDT.</span></span>  
  
```vb  
<Serializable(), SqlUserDefinedTypeAttribute(Format.Native, _  
  IsByteOrdered:=True)> _  
  Public Structure Point  
    Implements INullable  
```  
  
```csharp  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native,  
  IsByteOrdered=true)]  
public struct Point : INullable  
{  
```  
  
## <a name="implementing-nullability"></a><span data-ttu-id="aa248-122">Implementar la nulabilidad</span><span class="sxs-lookup"><span data-stu-id="aa248-122">Implementing Nullability</span></span>  
 <span data-ttu-id="aa248-123">Además de especificar correctamente los atributos de los ensamblados, el UDT también debe admitir la nulabilidad.</span><span class="sxs-lookup"><span data-stu-id="aa248-123">In addition to specifying the attributes for your assemblies correctly, your UDT must also support nullability.</span></span> <span data-ttu-id="aa248-124">Se tiene en cuenta el valor NULL de los UDT cargados en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], pero para que el UDT reconozca un valor NULL, es necesario que el UDT implemente la interfaz `System.Data.SqlTypes.INullable`.</span><span class="sxs-lookup"><span data-stu-id="aa248-124">UDTs loaded into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are null-aware, but in order for the UDT to recognize a null value, the UDT must implement the `System.Data.SqlTypes.INullable` interface.</span></span>  
  
 <span data-ttu-id="aa248-125">Debe crear una propiedad denominada `IsNull`, necesaria para determinar desde el código CLR si un valor es NULL.</span><span class="sxs-lookup"><span data-stu-id="aa248-125">You must create a property named `IsNull`, which is needed to determine whether a value is null from within CLR code.</span></span> <span data-ttu-id="aa248-126">Cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encuentra una instancia NULL de un UDT, el UDT se conserva mediante los métodos habituales de control de valores NULL.</span><span class="sxs-lookup"><span data-stu-id="aa248-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finds a null instance of a UDT, the UDT is persisted using normal null-handling methods.</span></span> <span data-ttu-id="aa248-127">El servidor no pierde tiempo serializando o deserializando el UDT sin necesidad y no desaprovecha espacio para almacenar un UDT NULL.</span><span class="sxs-lookup"><span data-stu-id="aa248-127">The server does not waste time serializing or deserializing the UDT if it does not have to, and it does not waste space to store a null UDT.</span></span> <span data-ttu-id="aa248-128">Esta comprobación de valores NULL se realiza cada vez que se usa un UDT de CLR, lo que significa que el uso de la construcción IS NULL de [!INCLUDE[tsql](../../includes/tsql-md.md)] para comprobar los UDT que son NULL debería funcionar siempre.</span><span class="sxs-lookup"><span data-stu-id="aa248-128">This check for nulls is performed every time a UDT is brought over from the CLR, which means that using the [!INCLUDE[tsql](../../includes/tsql-md.md)] IS NULL construct to check for null UDTs should always work.</span></span> <span data-ttu-id="aa248-129">El servidor usa también la propiedad `IsNull` para probar si una instancia es NULL.</span><span class="sxs-lookup"><span data-stu-id="aa248-129">The `IsNull` property is also used by the server to test whether an instance is null.</span></span> <span data-ttu-id="aa248-130">Una vez que el servidor determina que el UDT es NULL, puede usar su propio control de valores NULL nativos.</span><span class="sxs-lookup"><span data-stu-id="aa248-130">Once the server determines that the UDT is null, it can use its native null handling.</span></span>  
  
 <span data-ttu-id="aa248-131">El método `get()` de `IsNull` no usa las mayúsculas y minúsculas de un modo especial.</span><span class="sxs-lookup"><span data-stu-id="aa248-131">The `get()` method of `IsNull` is not special-cased in any way.</span></span> <span data-ttu-id="aa248-132">Si una variable `Point``@p` es `Null`, `@p.IsNull` se evalúa de forma predeterminada como "NULL", no como "1".</span><span class="sxs-lookup"><span data-stu-id="aa248-132">If a `Point` variable `@p` is `Null`, then `@p.IsNull` will, by default, evaluate to "NULL", not "1".</span></span> <span data-ttu-id="aa248-133">Esto se debe a que el atributo `SqlMethod(OnNullCall)` del método `IsNull get()` toma como valor predeterminado false.</span><span class="sxs-lookup"><span data-stu-id="aa248-133">This is because the `SqlMethod(OnNullCall)` attribute of the `IsNull get()` method defaults to false.</span></span> <span data-ttu-id="aa248-134">Dado que el objeto es `Null`, cuando se solicita la propiedad no se deserializa el objeto, no se llama al método y se devuelve el valor predeterminado "NULL".</span><span class="sxs-lookup"><span data-stu-id="aa248-134">Because the object is `Null`, when the property is requested the object is not deserialized, the method is not called, and a default value of "NULL" is returned.</span></span>  
  
### <a name="example"></a><span data-ttu-id="aa248-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa248-135">Example</span></span>  
 <span data-ttu-id="aa248-136">En el ejemplo siguiente, la variable `is_Null` es privada y contiene el estado NULL para la instancia del UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-136">In the following example, the `is_Null` variable is private and holds the state of null for the instance of the UDT.</span></span> <span data-ttu-id="aa248-137">El código debe mantener un valor adecuado para `is_Null`.</span><span class="sxs-lookup"><span data-stu-id="aa248-137">Your code must maintain an appropriate value for `is_Null`.</span></span> <span data-ttu-id="aa248-138">El UDT también debe tener una propiedad estática denominada `Null` que devuelve una instancia de valor NULL del UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-138">The UDT must also have a static property named `Null` that returns a null value instance of the UDT.</span></span> <span data-ttu-id="aa248-139">Esto permite al UDT devolver un valor NULL si la instancia también es NULL en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa248-139">This allows the UDT to return a null value if the instance is indeed null in the database.</span></span>  
  
```vb  
Private is_Null As Boolean  
  
Public ReadOnly Property IsNull() As Boolean _  
   Implements INullable.IsNull  
    Get  
        Return (is_Null)  
    End Get  
End Property  
  
Public Shared ReadOnly Property Null() As Point  
    Get  
        Dim pt As New Point  
        pt.is_Null = True  
        Return (pt)  
    End Get  
End Property  
```  
  
```csharp  
private bool is_Null;  
  
public bool IsNull  
{  
    get  
    {  
        return (is_Null);  
    }  
}  
  
public static Point Null  
{  
    get  
    {  
        Point pt = new Point();  
        pt.is_Null = true;  
        return pt;  
    }  
}  
```  
  
### <a name="is-null-vs-isnull"></a><span data-ttu-id="aa248-140">IS NULL frente a IsNull</span><span class="sxs-lookup"><span data-stu-id="aa248-140">IS NULL vs. IsNull</span></span>  
 <span data-ttu-id="aa248-141">Consideremos una tabla que contiene el esquema Points(id int, location Point), donde `Point` es un UDT de CLR, y consideremos las consultas siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa248-141">Consider a table that contains the schema Points(id int, location Point), where `Point` is a CLR UDT, and the following queries:</span></span>  
  
```  
--Query 1  
SELECT ID  
FROM Points  
WHERE NOT (location IS NULL) -- Or, WHERE location IS NOT NULL;  
```  
  
```  
--Query 2:  
SELECT ID  
FROM Points  
WHERE location.IsNull = 0;  
```  
  
 <span data-ttu-id="aa248-142">Ambas consultas devuelven los identificadores de puntos (Points) con ubicaciones (location) que no son `Null`.</span><span class="sxs-lookup"><span data-stu-id="aa248-142">Both queries return the IDs of points with non-`Null` locations.</span></span> <span data-ttu-id="aa248-143">En la consulta 1 (Query 1), se usa el control habitual de valores NULL y no se requiere ninguna deserialización de UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-143">In Query 1, normal null-handling is used, and there no deserialization of UDTs is required.</span></span> <span data-ttu-id="aa248-144">Por otra parte, la consulta 2 (Query 2) tiene que deserializar cada uno de los objetos que no son `Null` y llamar a CLR para obtener el valor de la propiedad `IsNull`.</span><span class="sxs-lookup"><span data-stu-id="aa248-144">Query 2, on the other hand, has to deserialize each non-`Null` object and call into the CLR to obtain the value of the `IsNull` property.</span></span> <span data-ttu-id="aa248-145">Evidentemente, mediante `IS NULL` el rendimiento será mayor y nunca habrá motivos para leer la propiedad `IsNull` de un UDT desde el código [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa248-145">Clearly, using `IS NULL` will exhibit better performance and there should never be a reason to read the `IsNull` property of a UDT from [!INCLUDE[tsql](../../includes/tsql-md.md)] code.</span></span>  
  
 <span data-ttu-id="aa248-146">Entonces, ¿cuál sería el uso de la propiedad `IsNull`?</span><span class="sxs-lookup"><span data-stu-id="aa248-146">So, what is the use of the `IsNull` property?</span></span> <span data-ttu-id="aa248-147">En primer lugar, esta propiedad es necesaria para determinar si un valor es `Null` desde el código CLR.</span><span class="sxs-lookup"><span data-stu-id="aa248-147">First, it is needed to determine whether a value is `Null` from within CLR code.</span></span> <span data-ttu-id="aa248-148">En segundo lugar, el servidor necesita un modo de probar si una instancia es `Null`, por lo que usa esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="aa248-148">Second, the server needs a way to test whether an instance is `Null`, so this property is used by the server.</span></span> <span data-ttu-id="aa248-149">Una vez que determina que es `Null`, puede usar su propio control de valores NULL nativos para administrarla.</span><span class="sxs-lookup"><span data-stu-id="aa248-149">After it determines it is `Null`, then it can use its native null handling to handle it.</span></span>  
  
## <a name="implementing-the-parse-method"></a><span data-ttu-id="aa248-150">Implementar el método Parse</span><span class="sxs-lookup"><span data-stu-id="aa248-150">Implementing the Parse Method</span></span>  
 <span data-ttu-id="aa248-151">Los métodos `Parse` y `ToString` permiten las conversiones a representaciones de cadena o desde representaciones de cadena del UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-151">The `Parse` and `ToString` methods allow for conversions to and from string representations of the UDT.</span></span> <span data-ttu-id="aa248-152">El método `Parse` permite convertir una cadena en un UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-152">The `Parse` method allows a string to be converted into a UDT.</span></span> <span data-ttu-id="aa248-153">Debe declararse como `static` (o `Shared` en Visual Basic) y tomar un parámetro de tipo `System.Data.SqlTypes.SqlString`.</span><span class="sxs-lookup"><span data-stu-id="aa248-153">It must be declared as `static` (or `Shared` in Visual Basic), and take a parameter of type `System.Data.SqlTypes.SqlString`.</span></span>  
  
 <span data-ttu-id="aa248-154">El código siguiente implementa el método `Parse` para el UDT `Point`, que separa las coordenadas X e Y.</span><span class="sxs-lookup"><span data-stu-id="aa248-154">The following code implements the `Parse` method for the `Point` UDT, which separates out the X and Y coordinates.</span></span> <span data-ttu-id="aa248-155">El método `Parse` tiene un único argumento de tipo `System.Data.SqlTypes.SqlString` y asume que los valores X e Y se proporcionan como una cadena delimitada por comas.</span><span class="sxs-lookup"><span data-stu-id="aa248-155">The `Parse` method has a single argument of type `System.Data.SqlTypes.SqlString`, and assumes that X and Y values are supplied as a comma-delimited string.</span></span> <span data-ttu-id="aa248-156">Al establecer el atributo `Microsoft.SqlServer.Server.SqlMethodAttribute.OnNullCall` en `false` se evita llamar al método `Parse` desde una instancia NULL de Point.</span><span class="sxs-lookup"><span data-stu-id="aa248-156">Setting the `Microsoft.SqlServer.Server.SqlMethodAttribute.OnNullCall` attribute to `false` prevents the `Parse` method from being called from a null instance of Point.</span></span>  
  
```vb  
<SqlMethod(OnNullCall:=False)> _  
Public Shared Function Parse(ByVal s As SqlString) As Point  
    If s.IsNull Then  
        Return Null  
    End If  
  
    ' Parse input string here to separate out points.  
    Dim pt As New Point()  
    Dim xy() As String = s.Value.Split(",".ToCharArray())  
    pt.X = Int32.Parse(xy(0))  
    pt.Y = Int32.Parse(xy(1))  
    Return pt  
End Function  
```  
  
```csharp  
[SqlMethod(OnNullCall = false)]  
public static Point Parse(SqlString s)  
{  
    if (s.IsNull)  
        return Null;  
  
    // Parse input string to separate out points.  
    Point pt = new Point();  
    string[] xy = s.Value.Split(",".ToCharArray());  
    pt.X = Int32.Parse(xy[0]);  
    pt.Y = Int32.Parse(xy[1]);  
    return pt;  
}  
```  
  
## <a name="implementing-the-tostring-method"></a><span data-ttu-id="aa248-157">Implementar el método ToString</span><span class="sxs-lookup"><span data-stu-id="aa248-157">Implementing the ToString Method</span></span>  
 <span data-ttu-id="aa248-158">El método `ToString` convierte el UDT `Point` en un valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="aa248-158">The `ToString` method converts the `Point` UDT to a string value.</span></span> <span data-ttu-id="aa248-159">En este caso, se devuelve la cadena "NULL" para una instancia NULL de tipo `Point`.</span><span class="sxs-lookup"><span data-stu-id="aa248-159">In this case, the string "NULL" is returned for a Null instance of the `Point` type.</span></span> <span data-ttu-id="aa248-160">El método `ToString` invierte la acción del método `Parse` mediante el uso de `System.Text.StringBuilder` para devolver una cadena `System.String` delimitada por comas que consta de los valores de las coordenadas X e Y.</span><span class="sxs-lookup"><span data-stu-id="aa248-160">The `ToString` method reverses the `Parse` method by using a `System.Text.StringBuilder` to return a comma-delimited `System.String` consisting of the X and Y coordinate values.</span></span> <span data-ttu-id="aa248-161">Dado que **InvokeIfReceiverIsNull** toma como valor predeterminado False, `Point` no es necesario comprobar si hay una instancia null de.</span><span class="sxs-lookup"><span data-stu-id="aa248-161">Because **InvokeIfReceiverIsNull** defaults to false, the check for a null instance of `Point` is unnecessary.</span></span>  
  
```vb  
Private _x As Int32  
Private _y As Int32  
  
Public Overrides Function ToString() As String  
    If Me.IsNull Then  
        Return "NULL"  
    Else  
        Dim builder As StringBuilder = New StringBuilder  
        builder.Append(_x)  
        builder.Append(",")  
        builder.Append(_y)  
        Return builder.ToString  
    End If  
End Function  
```  
  
```csharp  
private Int32 _x;  
private Int32 _y;  
  
public override string ToString()  
{  
    if (this.IsNull)  
        return "NULL";  
    else  
    {  
        StringBuilder builder = new StringBuilder();  
        builder.Append(_x);  
        builder.Append(",");  
        builder.Append(_y);  
        return builder.ToString();  
    }  
}  
```  
  
## <a name="exposing-udt-properties"></a><span data-ttu-id="aa248-162">Exponer las propiedades del UDT</span><span class="sxs-lookup"><span data-stu-id="aa248-162">Exposing UDT Properties</span></span>  
 <span data-ttu-id="aa248-163">El UDT `Point` expone las coordenadas X e Y que se implementan como propiedades de lectura y escritura públicas de tipo `System.Int32`.</span><span class="sxs-lookup"><span data-stu-id="aa248-163">The `Point` UDT exposes X and Y coordinates that are implemented as public read-write properties of type `System.Int32`.</span></span>  
  
```vb  
Public Property X() As Int32  
    Get  
        Return (Me._x)  
    End Get  
  
    Set(ByVal Value As Int32)  
        _x = Value  
    End Set  
End Property  
  
Public Property Y() As Int32  
    Get  
        Return (Me._y)  
    End Get  
  
    Set(ByVal Value As Int32)  
        _y = Value  
    End Set  
End Property  
```  
  
```csharp  
public Int32 X  
{  
    get  
    {  
        return this._x;  
    }  
    set   
    {  
        _x = value;  
    }  
}  
  
public Int32 Y  
{  
    get  
    {  
        return this._y;  
    }  
    set  
    {  
        _y = value;  
    }  
}  
```  
  
## <a name="validating-udt-values"></a><span data-ttu-id="aa248-164">Validar los valores UDT</span><span class="sxs-lookup"><span data-stu-id="aa248-164">Validating UDT Values</span></span>  
 <span data-ttu-id="aa248-165">Al trabajar con datos UDT, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] convierte automáticamente los valores binarios en valores UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-165">When working with UDT data, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] automatically converts binary values to UDT values.</span></span> <span data-ttu-id="aa248-166">Este proceso de conversión implica la comprobación de que los valores son adecuados para el formato de serialización del tipo, así como asegurarse de que el valor puede deserializarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="aa248-166">This conversion process involves checking that values are appropriate for the serialization format of the type and ensuring that the value can be deserialized correctly.</span></span> <span data-ttu-id="aa248-167">De este modo, se garantiza que el valor puede volver a convertirse a formato binario.</span><span class="sxs-lookup"><span data-stu-id="aa248-167">This ensures that the value can be converted back to binary form.</span></span> <span data-ttu-id="aa248-168">En el caso de los UDT ordenados por bytes, esto también garantiza que el valor binario resultante coincida con el valor binario original.</span><span class="sxs-lookup"><span data-stu-id="aa248-168">In the case of byte-ordered UDTs, this also ensures that the resulting binary value matches the original binary value.</span></span> <span data-ttu-id="aa248-169">De esta forma, se evita que los valores que no son válidos se conserven en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa248-169">This prevents invalid values from being persisted in the database.</span></span> <span data-ttu-id="aa248-170">En algunos casos, este nivel de comprobación puede resultar inadecuado.</span><span class="sxs-lookup"><span data-stu-id="aa248-170">In some cases, this level of checking may be inadequate.</span></span> <span data-ttu-id="aa248-171">Puede ser necesaria una validación adicional cuando se exige que los valores UDT se encuentren en un dominio o intervalo esperado.</span><span class="sxs-lookup"><span data-stu-id="aa248-171">Additional validation may be required when UDT values are required to be in an expected domain or range.</span></span> <span data-ttu-id="aa248-172">Por ejemplo, un UDT que implementa una fecha podría exigir que el valor de día sea un número positivo que pertenezca a un intervalo determinado de valores válidos.</span><span class="sxs-lookup"><span data-stu-id="aa248-172">For example, a UDT that implements a date might require the day value to be a positive number that falls within a certain range of valid values.</span></span>  
  
 <span data-ttu-id="aa248-173">La propiedad `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute.ValidationMethodName` de `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` permite proporcionar el nombre de un método de validación que el servidor ejecuta cuando los datos se asignan a un UDT o se convierten en un UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-173">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute.ValidationMethodName` property of the `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` allows you to supply the name of a validation method that the server runs when data is assigned to a UDT or converted to a UDT.</span></span> <span data-ttu-id="aa248-174">También se llama a `ValidationMethodName` durante la ejecución de la utilidad bcp, BULK INSERT, DBCC CHECKDB, DBCC CHECKFILEGROUP, DBCC CHECKTABLE, consulta distribuida y operaciones de llamada a procedimiento remoto (RPC) de flujo TDS.</span><span class="sxs-lookup"><span data-stu-id="aa248-174">`ValidationMethodName` is also called during the running of the bcp utility, BULK INSERT, DBCC CHECKDB, DBCC CHECKFILEGROUP, DBCC CHECKTABLE, distributed query, and tabular data stream (TDS) remote procedure call (RPC) operations.</span></span> <span data-ttu-id="aa248-175">El valor predeterminado de `ValidationMethodName` es NULL, lo que indica que no hay ningún método de validación.</span><span class="sxs-lookup"><span data-stu-id="aa248-175">The default value for `ValidationMethodName` is null, indicating that there is no validation method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="aa248-176">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa248-176">Example</span></span>  
 <span data-ttu-id="aa248-177">El fragmento de código siguiente muestra la declaración de la clase `Point`, que especifica un `ValidationMethodName` de `ValidatePoint`.</span><span class="sxs-lookup"><span data-stu-id="aa248-177">The following code fragment shows the declaration for the `Point` class, which specifies a `ValidationMethodName` of `ValidatePoint`.</span></span>  
  
```vb  
<Serializable(), SqlUserDefinedTypeAttribute(Format.Native, _  
  IsByteOrdered:=True, _  
  ValidationMethodName:="ValidatePoint")> _  
  Public Structure Point  
```  
  
```csharp  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native,  
  IsByteOrdered=true,   
  ValidationMethodName = "ValidatePoint")]  
public struct Point : INullable  
{  
```  
  
 <span data-ttu-id="aa248-178">Si se especifica un método de validación, debe tener una firma de aspecto similar al fragmento de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="aa248-178">If a validation method is specified, it must have a signature that looks like the following code fragment.</span></span>  
  
```vb  
Private Function ValidationFunction() As Boolean  
    If (validation logic here) Then  
        Return True  
    Else  
        Return False  
    End If  
End Function  
```  
  
```csharp  
private bool ValidationFunction()  
{  
    if (validation logic here)  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
}  
```  
  
 <span data-ttu-id="aa248-179">El método de validación puede tener cualquier ámbito y debe devolver `true` si el valor es válido o, de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="aa248-179">The validation method can have any scope and should return `true` if the value is valid, and `false` otherwise.</span></span> <span data-ttu-id="aa248-180">Si el método devuelve `false` o inicia una excepción, se considera que el valor no es válido y se produce un error.</span><span class="sxs-lookup"><span data-stu-id="aa248-180">If the method returns `false` or throws an exception, the value is treated as not valid and an error is raised.</span></span>  
  
 <span data-ttu-id="aa248-181">En el ejemplo siguiente, el código solamente permite valores iguales a cero o mayores que las coordenadas X e Y.</span><span class="sxs-lookup"><span data-stu-id="aa248-181">In the example below, the code allows only values of zero or greater the X and Y coordinates.</span></span>  
  
```vb  
Private Function ValidatePoint() As Boolean  
    If (_x >= 0) And (_y >= 0) Then  
        Return True  
    Else  
        Return False  
    End If  
End Function  
```  
  
```csharp  
private bool ValidatePoint()  
{  
    if ((_x >= 0) && (_y >= 0))  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
}  
```  
  
### <a name="validation-method-limitations"></a><span data-ttu-id="aa248-182">Limitaciones del método de validación</span><span class="sxs-lookup"><span data-stu-id="aa248-182">Validation Method Limitations</span></span>  
 <span data-ttu-id="aa248-183">El servidor llama al método de validación cuando está realizando conversiones, no cuando los datos se insertan mediante el establecimiento de propiedades individuales ni cuando los datos se insertan mediante una instrucción INSERT de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa248-183">The server calls the validation method when the server is performing conversions, not when data is inserted by setting individual properties or when data is inserted using a [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT statement.</span></span>  
  
 <span data-ttu-id="aa248-184">Debe llamar explícitamente al método de validación desde los establecedores de propiedades y el `Parse` método si desea que el método de validación se ejecute en todas las situaciones.</span><span class="sxs-lookup"><span data-stu-id="aa248-184">You must explicitly call the validation method from property setters and the `Parse` method if you want the validation method to execute in all situations.</span></span> <span data-ttu-id="aa248-185">No se trata de ningún requisito e incluso, en algunos casos, es posible que no se desee.</span><span class="sxs-lookup"><span data-stu-id="aa248-185">This is not a requirement, and in some cases may not even be desirable.</span></span>  
  
### <a name="parse-validation-example"></a><span data-ttu-id="aa248-186">Ejemplo de validación de Parse</span><span class="sxs-lookup"><span data-stu-id="aa248-186">Parse Validation Example</span></span>  
 <span data-ttu-id="aa248-187">Para asegurarse de que el `ValidatePoint` método se invoca en la `Point` clase, debe llamarlo desde el `Parse` método y desde los procedimientos de propiedad que establecen los valores de las coordenadas X e y.</span><span class="sxs-lookup"><span data-stu-id="aa248-187">To ensure that the `ValidatePoint` method is invoked in the `Point` class, you must call it from the `Parse` method and from the property procedures that set the X and Y coordinate values.</span></span> <span data-ttu-id="aa248-188">En el fragmento de código siguiente se muestra cómo llamar al `ValidatePoint` método de validación desde la `Parse` función.</span><span class="sxs-lookup"><span data-stu-id="aa248-188">The following code fragment shows how to call the `ValidatePoint` validation method from the `Parse` function.</span></span>  
  
```vb  
<SqlMethod(OnNullCall:=False)> _  
Public Shared Function Parse(ByVal s As SqlString) As Point  
    If s.IsNull Then  
        Return Null  
    End If  
  
    ' Parse input string here to separate out points.  
    Dim pt As New Point()  
    Dim xy() As String = s.Value.Split(",".ToCharArray())  
    pt.X = Int32.Parse(xy(0))  
    pt.Y = Int32.Parse(xy(1))  
  
    ' Call ValidatePoint to enforce validation  
    ' for string conversions.  
    If Not pt.ValidatePoint() Then  
        Throw New ArgumentException("Invalid XY coordinate values.")  
    End If  
    Return pt  
End Function  
```  
  
```csharp  
[SqlMethod(OnNullCall = false)]  
public static Point Parse(SqlString s)  
{  
    if (s.IsNull)  
        return Null;  
  
    // Parse input string to separate out points.  
    Point pt = new Point();  
    string[] xy = s.Value.Split(",".ToCharArray());  
    pt.X = Int32.Parse(xy[0]);  
    pt.Y = Int32.Parse(xy[1]);  
  
    // Call ValidatePoint to enforce validation  
    // for string conversions.  
    if (!pt.ValidatePoint())   
        throw new ArgumentException("Invalid XY coordinate values.");  
    return pt;  
}  
```  
  
### <a name="property-validation-example"></a><span data-ttu-id="aa248-189">Ejemplo de validación de propiedad</span><span class="sxs-lookup"><span data-stu-id="aa248-189">Property Validation Example</span></span>  
 <span data-ttu-id="aa248-190">En el fragmento de código siguiente se muestra cómo llamar al `ValidatePoint` método de validación desde los procedimientos de propiedad que establecen las coordenadas X e y.</span><span class="sxs-lookup"><span data-stu-id="aa248-190">The following code fragment shows how to call the `ValidatePoint` validation method from the property procedures that set the X and Y coordinates.</span></span>  
  
```vb  
Public Property X() As Int32  
    Get  
        Return (Me._x)  
    End Get  
  
    Set(ByVal Value As Int32)  
        Dim temp As Int32 = _x  
        _x = Value  
        If Not ValidatePoint() Then  
            _x = temp  
            Throw New ArgumentException("Invalid X coordinate value.")  
        End If  
    End Set  
End Property  
  
Public Property Y() As Int32  
    Get  
        Return (Me._y)  
    End Get  
  
    Set(ByVal Value As Int32)  
        Dim temp As Int32 = _y  
        _y = Value  
        If Not ValidatePoint() Then  
            _y = temp  
            Throw New ArgumentException("Invalid Y coordinate value.")  
        End If  
    End Set  
End Property  
```  
  
```csharp  
    public Int32 X  
{  
    get  
    {  
        return this._x;  
    }  
    // Call ValidatePoint to ensure valid range of Point values.  
    set   
    {  
        Int32 temp = _x;  
        _x = value;  
        if (!ValidatePoint())  
        {  
            _x = temp;  
            throw new ArgumentException("Invalid X coordinate value.");  
        }  
    }  
}  
  
public Int32 Y  
{  
    get  
    {  
        return this._y;  
    }  
    set  
    {  
        Int32 temp = _y;  
        _y = value;  
        if (!ValidatePoint())  
        {  
            _y = temp;  
            throw new ArgumentException("Invalid Y coordinate value.");  
        }  
    }  
}  
```  
  
## <a name="coding-udt-methods"></a><span data-ttu-id="aa248-191">Codificar métodos UDT</span><span class="sxs-lookup"><span data-stu-id="aa248-191">Coding UDT Methods</span></span>  
 <span data-ttu-id="aa248-192">Cuando codifique los métodos UDT, tenga en cuenta si el algoritmo usado podría cambiar con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="aa248-192">When coding UDT methods, consider whether the algorithm used could possibly change over time.</span></span> <span data-ttu-id="aa248-193">En ese caso, es posible que desee considerar la posibilidad de crear una clase independiente para los métodos que usa el UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-193">If so, you may want to consider creating a separate class for the methods your UDT uses.</span></span> <span data-ttu-id="aa248-194">Si el algoritmo cambia, puede volver a compilar la clase con el nuevo código, así como cargar el ensamblado en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sin que esto afecte al UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-194">If the algorithm changes, you can recompile the class with the new code and load the assembly into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without affecting the UDT.</span></span> <span data-ttu-id="aa248-195">En muchos casos, los UDT pueden volver a cargarse mediante la instrucción ALTER ASSEMBLY de [!INCLUDE[tsql](../../includes/tsql-md.md)], pero eso podría causar problemas con los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="aa248-195">In many cases UDTs can be reloaded using the [!INCLUDE[tsql](../../includes/tsql-md.md)] ALTER ASSEMBLY statement, but that could potentially cause problems with existing data.</span></span> <span data-ttu-id="aa248-196">Por ejemplo, el `Currency` UDT incluido en la base de datos de ejemplo **AdventureWorks** usa una función **ConvertCurrency** para convertir los valores de moneda, que se implementa en una clase independiente.</span><span class="sxs-lookup"><span data-stu-id="aa248-196">For example, the `Currency` UDT included with the **AdventureWorks** sample database uses a **ConvertCurrency** function to convert currency values, which is implemented in a separate class.</span></span> <span data-ttu-id="aa248-197">Es posible que en un futuro los algoritmos de conversión cambien de modo impredecible o que se necesite nueva funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="aa248-197">It is possible that conversion algorithms may change in unpredictable ways in the future, or that new functionality may be required.</span></span> <span data-ttu-id="aa248-198">La separación de la función **ConvertCurrency** de la `Currency` implementación UDT proporciona mayor flexibilidad a la hora de planear cambios futuros.</span><span class="sxs-lookup"><span data-stu-id="aa248-198">Separating the **ConvertCurrency** function from the `Currency` UDT implementation provides greater flexibility when planning for future changes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="aa248-199">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa248-199">Example</span></span>  
 <span data-ttu-id="aa248-200">La `Point` clase contiene tres métodos sencillos para calcular la distancia: **Distance**, **DistanceFrom** y **DistanceFromXY**.</span><span class="sxs-lookup"><span data-stu-id="aa248-200">The `Point` class contains three simple methods for calculating distance: **Distance**, **DistanceFrom** and **DistanceFromXY**.</span></span> <span data-ttu-id="aa248-201">Cada uno de estos métodos devuelve un valor de tipo `double` y calcula la distancia de `Point` a cero, la distancia de un punto determinado a `Point` y la distancia de las coordenadas X e Y especificadas a `Point`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="aa248-201">Each returns a `double` calculating the distance from `Point` to zero, the distance from a specified point to `Point`, and the distance from specified X and Y coordinates to `Point`.</span></span> <span data-ttu-id="aa248-202">**Distance** y **DistanceFrom** llaman a **DistanceFromXY**y muestran cómo usar argumentos diferentes para cada método.</span><span class="sxs-lookup"><span data-stu-id="aa248-202">**Distance** and **DistanceFrom** each call **DistanceFromXY**, and demonstrate how to use different arguments for each method.</span></span>  
  
```vb  
' Distance from 0 to Point.  
<SqlMethod(OnNullCall:=False)> _  
Public Function Distance() As Double  
    Return DistanceFromXY(0, 0)  
End Function  
  
' Distance from Point to the specified point.  
<SqlMethod(OnNullCall:=False)> _  
Public Function DistanceFrom(ByVal pFrom As Point) As Double  
    Return DistanceFromXY(pFrom.X, pFrom.Y)  
End Function  
  
' Distance from Point to the specified x and y values.  
<SqlMethod(OnNullCall:=False)> _  
Public Function DistanceFromXY(ByVal ix As Int32, ByVal iy As Int32) _  
    As Double  
    Return Math.Sqrt(Math.Pow(ix - _x, 2.0) + Math.Pow(iy - _y, 2.0))  
End Function  
```  
  
```csharp  
// Distance from 0 to Point.  
[SqlMethod(OnNullCall = false)]  
public Double Distance()  
{  
    return DistanceFromXY(0, 0);  
}  
  
// Distance from Point to the specified point.  
[SqlMethod(OnNullCall = false)]  
public Double DistanceFrom(Point pFrom)  
{  
    return DistanceFromXY(pFrom.X, pFrom.Y);  
}  
  
// Distance from Point to the specified x and y values.  
[SqlMethod(OnNullCall = false)]  
public Double DistanceFromXY(Int32 iX, Int32 iY)  
{  
    return Math.Sqrt(Math.Pow(iX - _x, 2.0) + Math.Pow(iY - _y, 2.0));  
}  
```  
  
### <a name="using-sqlmethod-attributes"></a><span data-ttu-id="aa248-203">Usar atributos SqlMethod</span><span class="sxs-lookup"><span data-stu-id="aa248-203">Using SqlMethod Attributes</span></span>  
 <span data-ttu-id="aa248-204">La clase `Microsoft.SqlServer.Server.SqlMethodAttribute` proporciona atributos personalizados que pueden usarse para marcar las definiciones de método a fin de especificar el determinismo en comportamientos de llamada NULL, así como para especificar si un método es un método mutador.</span><span class="sxs-lookup"><span data-stu-id="aa248-204">The `Microsoft.SqlServer.Server.SqlMethodAttribute` class provides custom attributes that can be used to mark method definitions in order to specify determinism, on null call behavior, and to specify whether a method is a mutator.</span></span> <span data-ttu-id="aa248-205">Se asume el uso de valores predeterminados para estas propiedades y solamente se usa el atributo personalizado cuando se necesita un valor no predeterminado.</span><span class="sxs-lookup"><span data-stu-id="aa248-205">Default values for these properties are assumed, and the custom attribute is only used when a non-default value is needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa248-206">La clase `SqlMethodAttribute` se hereda de la clase `SqlFunctionAttribute`; por ello, `SqlMethodAttribute` hereda los campos `FillRowMethodName` y `TableDefinition` de `SqlFunctionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="aa248-206">The `SqlMethodAttribute` class inherits from the `SqlFunctionAttribute` class, so `SqlMethodAttribute` inherits the `FillRowMethodName` and `TableDefinition` fields from `SqlFunctionAttribute`.</span></span> <span data-ttu-id="aa248-207">Esto significa que es posible escribir un método con valores de tabla, que no es el caso.</span><span class="sxs-lookup"><span data-stu-id="aa248-207">This implies that it is possible to write a table-valued method, which is not the case.</span></span> <span data-ttu-id="aa248-208">El método compila y el ensamblado implementa, pero se genera un error sobre el `IEnumerable` tipo de valor devuelto en tiempo de ejecución con el mensaje siguiente: "el método, la propiedad o el campo ' \<name> ' de la clase ' \<class> ' en el ensamblado ' \<assembly> ' tiene un tipo de valor devuelto no válido."</span><span class="sxs-lookup"><span data-stu-id="aa248-208">The method compiles and the assembly deploys, but an error about the `IEnumerable` return type is raised at runtime with the following message: "Method, property, or field '\<name>' in class '\<class>' in assembly '\<assembly>' has invalid return type."</span></span>  
  
 <span data-ttu-id="aa248-209">En la tabla siguiente se describen algunas de las propiedades más relevantes de `Microsoft.SqlServer.Server.SqlMethodAttribute` que pueden usarse en métodos UDT y se indican sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="aa248-209">The following table describes some of the relevant `Microsoft.SqlServer.Server.SqlMethodAttribute` properties that can be used in UDT methods, and lists their default values.</span></span>  
  
 <span data-ttu-id="aa248-210">DataAccess</span><span class="sxs-lookup"><span data-stu-id="aa248-210">DataAccess</span></span>  
 <span data-ttu-id="aa248-211">Indica si la función implica el acceso a los datos de usuario almacenados en la instancia local de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa248-211">Indicates whether the function involves access to user data stored in the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="aa248-212">El valor predeterminado es `DataAccessKind``None`.</span><span class="sxs-lookup"><span data-stu-id="aa248-212">Default is `DataAccessKind`.`None`.</span></span>  
  
 <span data-ttu-id="aa248-213">IsDeterministic</span><span class="sxs-lookup"><span data-stu-id="aa248-213">IsDeterministic</span></span>  
 <span data-ttu-id="aa248-214">Indica si la función genera los mismos valores de salida si se especifican los mismos valores de entrada y el mismo estado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa248-214">Indicates whether the function produces the same output values given the same input values and the same database state.</span></span> <span data-ttu-id="aa248-215">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="aa248-215">Default is `false`.</span></span>  
  
 <span data-ttu-id="aa248-216">IsMutator</span><span class="sxs-lookup"><span data-stu-id="aa248-216">IsMutator</span></span>  
 <span data-ttu-id="aa248-217">Indica si el método produce un cambio de estado en la instancia del UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-217">Indicates whether the method causes a state change in the UDT instance.</span></span> <span data-ttu-id="aa248-218">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="aa248-218">Default is `false`.</span></span>  
  
 <span data-ttu-id="aa248-219">IsPrecise</span><span class="sxs-lookup"><span data-stu-id="aa248-219">IsPrecise</span></span>  
 <span data-ttu-id="aa248-220">Indica si la función implica cálculos imprecisos, como operaciones de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="aa248-220">Indicates whether the function involves imprecise computations, such as floating point operations.</span></span> <span data-ttu-id="aa248-221">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="aa248-221">Default is `false`.</span></span>  
  
 <span data-ttu-id="aa248-222">OnNullCall</span><span class="sxs-lookup"><span data-stu-id="aa248-222">OnNullCall</span></span>  
 <span data-ttu-id="aa248-223">Indica si se llama al método cuando se especifican argumentos de entrada de referencia NULL.</span><span class="sxs-lookup"><span data-stu-id="aa248-223">Indicates whether the method is called when null reference input arguments are specified.</span></span> <span data-ttu-id="aa248-224">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="aa248-224">Default is `true`.</span></span>  
  
### <a name="example"></a><span data-ttu-id="aa248-225">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa248-225">Example</span></span>  
 <span data-ttu-id="aa248-226">La propiedad `Microsoft.SqlServer.Server.SqlMethodAttribute.IsMutator` permite marcar un método que admite un cambio en el estado de una instancia de un UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-226">The `Microsoft.SqlServer.Server.SqlMethodAttribute.IsMutator` property allows you to mark a method that allows a change in the state of an instance of a UDT.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="aa248-227">no permite que el usuario establezca dos propiedades UDT en la cláusula SET de una instrucción UPDATE.</span><span class="sxs-lookup"><span data-stu-id="aa248-227">does not allow you to set two UDT properties in the SET clause of one UPDATE statement.</span></span> <span data-ttu-id="aa248-228">Sin embargo, puede tener un método marcado como mutador que cambie los dos miembros.</span><span class="sxs-lookup"><span data-stu-id="aa248-228">However, you can have a method marked as a mutator that changes the two members.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa248-229">No se permite el uso de métodos mutadores en las consultas.</span><span class="sxs-lookup"><span data-stu-id="aa248-229">Mutator methods are not allowed in queries.</span></span> <span data-ttu-id="aa248-230">Solo puede llamarse a estos métodos en instrucciones de asignación o en instrucciones de modificación de datos.</span><span class="sxs-lookup"><span data-stu-id="aa248-230">They can be called only in assignment statements or data modification statements.</span></span> <span data-ttu-id="aa248-231">Si un método marcado como mutador no devuelve `void` (o no es un `Sub` en Visual Basic), se produce un error en CREATE TYPE.</span><span class="sxs-lookup"><span data-stu-id="aa248-231">If a method marked as mutator does not return `void` (or is not a `Sub` in Visual Basic), CREATE TYPE fails with an error.</span></span>  
  
 <span data-ttu-id="aa248-232">La instrucción siguiente asume la existencia de un UDT `Triangles` que tiene un método `Rotate`.</span><span class="sxs-lookup"><span data-stu-id="aa248-232">The following statement assumes the existence of a `Triangles` UDT that has a `Rotate` method.</span></span> <span data-ttu-id="aa248-233">La siguiente instrucción de actualización de [!INCLUDE[tsql](../../includes/tsql-md.md)] invoca al método `Rotate`:</span><span class="sxs-lookup"><span data-stu-id="aa248-233">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] update statement invokes the `Rotate` method:</span></span>  
  
```  
UPDATE Triangles SET t.RotateY(0.6) WHERE id=5  
```  
  
 <span data-ttu-id="aa248-234">El método `Rotate` se decora con el atributo `SqlMethod` estableciendo `IsMutator` en `true` para que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pueda marcar el método como un método mutador.</span><span class="sxs-lookup"><span data-stu-id="aa248-234">The `Rotate` method is decorated with the `SqlMethod` attribute setting `IsMutator` to `true` so that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can mark the method as a mutator method.</span></span> <span data-ttu-id="aa248-235">El código también establece `OnNullCall` en `false`, lo que indica al servidor que el método devuelve una referencia NULL (`Nothing` en Visual Basic) si alguno de los parámetros de entrada es una referencia NULL.</span><span class="sxs-lookup"><span data-stu-id="aa248-235">The code also sets `OnNullCall` to `false`, which indicates to the server that the method returns a null reference (`Nothing` in Visual Basic) if any of the input parameters are null references.</span></span>  
  
```vb  
<SqlMethod(IsMutator:=True, OnNullCall:=False)> _  
Public Sub Rotate(ByVal anglex as Double, _  
  ByVal angley as Double, ByVal anglez As Double)   
   RotateX(anglex)  
   RotateY(angley)  
   RotateZ(anglez)  
End Sub  
```  
  
```csharp  
[SqlMethod(IsMutator = true, OnNullCall = false)]  
public void Rotate(double anglex, double angley, double anglez)   
{  
   RotateX(anglex);  
   RotateY(angley);  
   RotateZ(anglez);  
}  
```  
  
## <a name="implementing-a-udt-with-a-user-defined-format"></a><span data-ttu-id="aa248-236">Implementar un UDT con un formato definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="aa248-236">Implementing a UDT with a User-Defined Format</span></span>  
 <span data-ttu-id="aa248-237">Al implementar un UDT con un formato definido por el usuario, debe implementar los métodos `Read` y `Write` que implementan la interfaz Microsoft.SqlServer.Server.IBinarySerialize para controlar cómo serializar y deserializar los datos UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-237">When implementing a UDT with a user-defined format, you must implement `Read` and `Write` methods that implement the Microsoft.SqlServer.Server.IBinarySerialize interface to handle serializing and deserializing UDT data.</span></span> <span data-ttu-id="aa248-238">También debe especificar la propiedad `MaxByteSize` de `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute`.</span><span class="sxs-lookup"><span data-stu-id="aa248-238">You must also specify the `MaxByteSize` property of the `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute`.</span></span>  
  
### <a name="the-currency-udt"></a><span data-ttu-id="aa248-239">El UDT Currency</span><span class="sxs-lookup"><span data-stu-id="aa248-239">The Currency UDT</span></span>  
 <span data-ttu-id="aa248-240">A partir de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el UDT `Currency` se incluye con los ejemplos CLR que pueden instalarse con [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa248-240">The `Currency` UDT is included with the CLR samples that can be installed with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="aa248-241">El UDT `Currency` permite administrar cantidades de dinero en el sistema monetario de una referencia cultural determinada.</span><span class="sxs-lookup"><span data-stu-id="aa248-241">The `Currency` UDT supports handling amounts of money in the monetary system of a particular culture.</span></span> <span data-ttu-id="aa248-242">Debe definir dos campos: un campo `string` para `CultureInfo`, que especifica quién emitió la moneda (por ejemplo, es-es) y un campo `decimal` para `CurrencyValue`, la cantidad de dinero.</span><span class="sxs-lookup"><span data-stu-id="aa248-242">You must define two fields: a `string` for `CultureInfo`, which specifies who issued the currency (en-us, for example) and a `decimal` for `CurrencyValue`, the amount of money.</span></span>  
  
 <span data-ttu-id="aa248-243">Aunque el servidor no lo usa para realizar comparaciones, el UDT `Currency` implementa la interfaz `System.IComparable`, que expone un método único, `System.IComparable.CompareTo`.</span><span class="sxs-lookup"><span data-stu-id="aa248-243">Although it is not used by the server for performing comparisons, the `Currency` UDT implements the `System.IComparable` interface, which exposes a single method, `System.IComparable.CompareTo`.</span></span> <span data-ttu-id="aa248-244">Se usa del lado cliente en situaciones en las que se desean realizar comparaciones precisas u ordenar valores de moneda dentro de las referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="aa248-244">This is used on the client side in situations where it is desirable to accurately compare or order currency values within cultures.</span></span>  
  
 <span data-ttu-id="aa248-245">El código que se ejecuta en CLR compara por separado la referencia cultural y el valor de moneda.</span><span class="sxs-lookup"><span data-stu-id="aa248-245">Code running in the CLR compares the culture separately from the currency value.</span></span> <span data-ttu-id="aa248-246">Para el código [!INCLUDE[tsql](../../includes/tsql-md.md)], las acciones siguientes determinan la comparación:</span><span class="sxs-lookup"><span data-stu-id="aa248-246">For [!INCLUDE[tsql](../../includes/tsql-md.md)] code, the following actions determine the comparison:</span></span>  
  
1.  <span data-ttu-id="aa248-247">Establezca el atributo `IsByteOrdered` en true para indicar a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que use la representación binaria que se conserva en el disco para las comparaciones.</span><span class="sxs-lookup"><span data-stu-id="aa248-247">Set the `IsByteOrdered` attribute to true, which tells [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use the persisted binary representation on disk for comparisons.</span></span>  
  
2.  <span data-ttu-id="aa248-248">Use el método `Write` para que el UDT `Currency` determine la forma en que el UDT se conserva en el disco y, por lo tanto, la forma en que los valores UDT se comparan y se ordenan para las operaciones [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa248-248">Use the `Write` method for the `Currency` UDT to determine how the UDT is persisted on disk and therefore how UDT values are compared and ordered for [!INCLUDE[tsql](../../includes/tsql-md.md)] operations.</span></span>  
  
3.  <span data-ttu-id="aa248-249">Guarde el UDT `Currency` con el siguiente formato binario:</span><span class="sxs-lookup"><span data-stu-id="aa248-249">Save the `Currency` UDT using the following binary format:</span></span>  
  
    1.  <span data-ttu-id="aa248-250">Guarde la referencia cultural como una cadena codificada mediante UTF-16, con bytes del 0 al 19, que se rellena a la derecha con caracteres NULL.</span><span class="sxs-lookup"><span data-stu-id="aa248-250">Save the culture as a UTF-16 encoded string for bytes 0-19 with padding to the right with null characters.</span></span>  
  
    2.  <span data-ttu-id="aa248-251">Use el byte 20 y los bytes siguientes para almacenar el valor decimal de la moneda.</span><span class="sxs-lookup"><span data-stu-id="aa248-251">Use bytes 20 and above to contain the decimal value of the currency.</span></span>  
  
 <span data-ttu-id="aa248-252">El propósito del relleno es asegurarse de que la referencia cultural esté completamente separada del valor de moneda, de forma que al comparar un UDT con otro en código [!INCLUDE[tsql](../../includes/tsql-md.md)], los bytes de la referencia cultural se comparen con los bytes de la referencia cultural y los valores de bytes de moneda se comparen con los valores de bytes de moneda.</span><span class="sxs-lookup"><span data-stu-id="aa248-252">The purpose of the padding is to ensure that the culture is completely separated from the currency value, so that when one UDT is compared against another in [!INCLUDE[tsql](../../includes/tsql-md.md)] code, culture bytes are compared against culture bytes, and currency byte values are compared against currency byte values.</span></span>  
  
 <span data-ttu-id="aa248-253">Para obtener la lista de código completa del `Currency` UDT, siga las instrucciones para instalar los ejemplos de CLR en [SQL Server ejemplos de motor de base de datos](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="aa248-253">For the complete code listing for the `Currency` UDT, follow the directions for installing the CLR samples in [SQL Server Database Engine Samples](https://msftengprodsamples.codeplex.com/).</span></span>  
  
### <a name="currency-attributes"></a><span data-ttu-id="aa248-254">Atributos de Currency</span><span class="sxs-lookup"><span data-stu-id="aa248-254">Currency Attributes</span></span>  
 <span data-ttu-id="aa248-255">El UDT `Currency` se define con los atributos siguientes.</span><span class="sxs-lookup"><span data-stu-id="aa248-255">The `Currency` UDT is defined with the following attributes.</span></span>  
  
```vb  
<Serializable(), Microsoft.SqlServer.Server.SqlUserDefinedType( _  
    Microsoft.SqlServer.Server.Format.UserDefined, _  
    IsByteOrdered:=True, MaxByteSize:=32), _  
    CLSCompliant(False)> _  
Public Structure Currency  
Implements INullable, IComparable, _  
Microsoft.SqlServer.Server.IBinarySerialize  
```  
  
```csharp  
[Serializable]  
[SqlUserDefinedType(Format.UserDefined,   
    IsByteOrdered = true, MaxByteSize = 32)]  
    [CLSCompliant(false)]  
    public struct Currency : INullable, IComparable, IBinarySerialize  
    {  
```  
  
## <a name="creating-read-and-write-methods-with-ibinaryserialize"></a><span data-ttu-id="aa248-256">Crear métodos de lectura y escritura con IBinarySerialize</span><span class="sxs-lookup"><span data-stu-id="aa248-256">Creating Read and Write Methods with IBinarySerialize</span></span>  
 <span data-ttu-id="aa248-257">Al elegir el formato de serialización `UserDefined`, también debe implementar la interfaz `IBinarySerialize` y crear sus propios métodos `Read` y `Write`.</span><span class="sxs-lookup"><span data-stu-id="aa248-257">When you choose `UserDefined` serialization format, you also must implement the `IBinarySerialize` interface and create your own `Read` and `Write` methods.</span></span> <span data-ttu-id="aa248-258">Los procedimientos siguientes del UDT `Currency` usan `System.IO.BinaryReader` y `System.IO.BinaryWriter` para leer y escribir en el UDT.</span><span class="sxs-lookup"><span data-stu-id="aa248-258">The following procedures from the `Currency` UDT use the `System.IO.BinaryReader` and `System.IO.BinaryWriter` to read from and write to the UDT.</span></span>  
  
```vb  
' IBinarySerialize methods  
' The binary layout is as follow:  
'    Bytes 0 - 19: Culture name, padded to the right with null  
'    characters, UTF-16 encoded  
'    Bytes 20+: Decimal value of money  
' If the culture name is empty, the currency is null.  
Public Sub Write(ByVal w As System.IO.BinaryWriter) _  
  Implements Microsoft.SqlServer.Server.IBinarySerialize.Write  
    If Me.IsNull Then  
        w.Write(nullMarker)  
        w.Write(System.Convert.ToDecimal(0))  
        Return  
    End If  
  
    If cultureName.Length > cultureNameMaxSize Then  
        Throw New ApplicationException(String.Format(CultureInfo.CurrentUICulture, _  
           "{0} is an invalid culture name for currency as it is too long.", cultureNameMaxSize))  
    End If  
  
    Dim paddedName As String = cultureName.PadRight(cultureNameMaxSize, CChar(vbNullChar))  
  
    For i As Integer = 0 To cultureNameMaxSize - 1  
        w.Write(paddedName(i))  
    Next i  
  
    ' Normalize decimal value to two places  
    currencyVal = Decimal.Floor(currencyVal * 100) / 100  
    w.Write(currencyVal)  
End Sub  
  
Public Sub Read(ByVal r As System.IO.BinaryReader) _  
  Implements Microsoft.SqlServer.Server.IBinarySerialize.Read  
    Dim name As Char() = r.ReadChars(cultureNameMaxSize)  
    Dim stringEnd As Integer = Array.IndexOf(name, CChar(vbNullChar))  
  
    If stringEnd = 0 Then  
        cultureName = Nothing  
        Return  
    End If  
  
    cultureName = New String(name, 0, stringEnd)  
    currencyVal = r.ReadDecimal()  
End Sub  
  
```  
  
```csharp  
// IBinarySerialize methods  
// The binary layout is as follow:  
//    Bytes 0 - 19:Culture name, padded to the right   
//    with null characters, UTF-16 encoded  
//    Bytes 20+:Decimal value of money  
// If the culture name is empty, the currency is null.  
public void Write(System.IO.BinaryWriter w)  
{  
    if (this.IsNull)  
    {  
        w.Write(nullMarker);  
        w.Write((decimal)0);  
        return;  
    }  
  
    if (cultureName.Length > cultureNameMaxSize)  
    {  
        throw new ApplicationException(string.Format(  
            CultureInfo.InvariantCulture,   
            "{0} is an invalid culture name for currency as it is too long.",   
            cultureNameMaxSize));  
    }  
  
    String paddedName = cultureName.PadRight(cultureNameMaxSize, '\0');  
    for (int i = 0; i < cultureNameMaxSize; i++)  
    {  
        w.Write(paddedName[i]);  
    }  
  
    // Normalize decimal value to two places  
    currencyValue = Decimal.Floor(currencyValue * 100) / 100;  
    w.Write(currencyValue);  
}  
public void Read(System.IO.BinaryReader r)  
{  
    char[] name = r.ReadChars(cultureNameMaxSize);  
    int stringEnd = Array.IndexOf(name, '\0');  
  
    if (stringEnd == 0)  
    {  
        cultureName = null;  
        return;  
    }  
  
    cultureName = new String(name, 0, stringEnd);  
    currencyValue = r.ReadDecimal();  
}  
```  
  
 <span data-ttu-id="aa248-259">Para obtener la lista de código completa del `Currency` UDT, vea [SQL Server ejemplos de motor de base de datos](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="aa248-259">For the complete code listing for the `Currency` UDT, see [SQL Server Database Engine Samples](https://msftengprodsamples.codeplex.com/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa248-260">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa248-260">See Also</span></span>  
 [<span data-ttu-id="aa248-261">Crear un tipo definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="aa248-261">Creating a User-Defined Type</span></span>](creating-user-defined-types.md)  
  
