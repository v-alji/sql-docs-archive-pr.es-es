---
title: Expresiones de consulta y nombres de recursos uniformes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
helpviewer_keywords:
- query expressions
- unique resource names
- URN
ms.assetid: e0d30dbe-7daf-47eb-8412-1b96792b6fb9
author: stevestein
ms.author: sstein
ms.openlocfilehash: db6e311dd7d8a824b0e2f22e538e15eefa9fd9ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672150"
---
# <a name="query-expressions-and-uniform-resource-names"></a><span data-ttu-id="d77ba-102">Expresiones de consulta y nombres de recursos uniformes</span><span class="sxs-lookup"><span data-stu-id="d77ba-102">Query Expressions and Uniform Resource Names</span></span>
  <span data-ttu-id="d77ba-103">Los modelos de objetos de administración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (SMO) y los complementos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell usan dos tipos de cadenas de expresiones que se parecen a las expresiones XPath.</span><span class="sxs-lookup"><span data-stu-id="d77ba-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object (SMO) models and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins use two types of expression strings that are similar to XPath expressions.</span></span> <span data-ttu-id="d77ba-104">Las expresiones de consulta son cadenas que especifican un conjunto de criterios usados para enumerar uno o más objetos de una jerarquía del modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="d77ba-104">Query expressions are strings that specify a set of criteria used to enumerate one or more objects in an object model hierarchy.</span></span> <span data-ttu-id="d77ba-105">Un nombre de recurso uniforme (URN) es un tipo específico de cadena de expresión de consulta que identifica exclusivamente un objeto único.</span><span class="sxs-lookup"><span data-stu-id="d77ba-105">A Uniform Resource Name (URN) is a specific type of query expression string that uniquely identifies a single object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d77ba-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d77ba-106">Syntax</span></span>  
  
```
      Object1  
      [<FilterExpression1>]/ ... /ObjectN[<FilterExpressionN>]<FilterExpression>::=  
<PropertyExpression> [and <PropertyExpression>][...n]  
  
<PropertyExpression>::=@BooleanPropertyName=true()  
 | @BooleanPropertyName=false()  
 | contains(@StringPropertyName, 'PatternString')  
  | @StringPropertyName='String'  
 | @DatePropertyName=datetime('DateString')  
 | is_null(@PropertyName)  
 | not(<PropertyExpression>)  
```  
  
## <a name="arguments"></a><span data-ttu-id="d77ba-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d77ba-107">Arguments</span></span>  
 <span data-ttu-id="d77ba-108">*Object*</span><span class="sxs-lookup"><span data-stu-id="d77ba-108">*Object*</span></span>  
 <span data-ttu-id="d77ba-109">Especifica el tipo de objeto que se representa en ese nodo de la cadena de expresión.</span><span class="sxs-lookup"><span data-stu-id="d77ba-109">Specifies the type of object that is represented at that node of the expression string.</span></span> <span data-ttu-id="d77ba-110">Cada objeto representa una clase de colección de estos espacios de nombres del modelo de objetos SMO:</span><span class="sxs-lookup"><span data-stu-id="d77ba-110">Each object represents a collection class from these SMO object model namespaces:</span></span>  
  
 <xref:Microsoft.SqlServer.Management.Smo>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Agent>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Broker>  
  
 <xref:Microsoft.SqlServer.Management.Smo.Mail>  
  
 <xref:Microsoft.SqlServer.Management.Dmf>  
  
 <xref:Microsoft.SqlServer.Management.Facets>  
  
 <xref:Microsoft.SqlServer.Management.RegisteredServers>  
  
 <xref:Microsoft.SqlServer.Management.Smo.RegSvrEnum>  
  
 <span data-ttu-id="d77ba-111">Por ejemplo, especifique el valor Server para la clase **ServerCollection** y el valor Database para la clase **DatabaseCollection** .</span><span class="sxs-lookup"><span data-stu-id="d77ba-111">For example, specify Server for the **ServerCollection** class, Database for the **DatabaseCollection** class.</span></span>  
  
 <span data-ttu-id="d77ba-112">\@*PropertyName*</span><span class="sxs-lookup"><span data-stu-id="d77ba-112">\@*PropertyName*</span></span>  
 <span data-ttu-id="d77ba-113">Especifica el nombre de una de las propiedades de la clase que está asociada con el objeto especificado en *Object*.</span><span class="sxs-lookup"><span data-stu-id="d77ba-113">Specifies the name of one of the properties of the class that is associated with the object specified in *Object*.</span></span> <span data-ttu-id="d77ba-114">El nombre de la propiedad debe llevar un prefijo con el carácter \@.</span><span class="sxs-lookup"><span data-stu-id="d77ba-114">The name of the property must be prefixed with the \@ character.</span></span> <span data-ttu-id="d77ba-115">Por ejemplo, especifique \@ IsAnsiNull para la propiedad de clase de **base de datos** **IsAnsiNull**.</span><span class="sxs-lookup"><span data-stu-id="d77ba-115">For example, specify \@IsAnsiNull for the **Database** class property **IsAnsiNull**.</span></span>  
  
 <span data-ttu-id="d77ba-116">\@*BooleanPropertyName*= true ()</span><span class="sxs-lookup"><span data-stu-id="d77ba-116">\@*BooleanPropertyName*=true()</span></span>  
 <span data-ttu-id="d77ba-117">Enumera todos los objetos en los que el valor de la propiedad booleana especificada se establece en TRUE.</span><span class="sxs-lookup"><span data-stu-id="d77ba-117">Enumerates all objects where the specified Boolean property is set to TRUE.</span></span>  
  
 <span data-ttu-id="d77ba-118">\@*BooleanPropertyName*= false ()</span><span class="sxs-lookup"><span data-stu-id="d77ba-118">\@*BooleanPropertyName*=false()</span></span>  
 <span data-ttu-id="d77ba-119">Enumera todos los objetos en los que el valor de la propiedad booleana especificada se establece en FALSE.</span><span class="sxs-lookup"><span data-stu-id="d77ba-119">Enumerates all objects where the specified Boolean property is set to FALSE.</span></span>  
  
 <span data-ttu-id="d77ba-120">Contains ( \@ *StringPropertyName*, '*PatternString*')</span><span class="sxs-lookup"><span data-stu-id="d77ba-120">contains(\@*StringPropertyName*, '*PatternString*')</span></span>  
 <span data-ttu-id="d77ba-121">Enumera todos los objetos en los que la propiedad de cadena especificada contiene, al menos, una aparición del juego de caracteres especificado en “*PatternString*”.</span><span class="sxs-lookup"><span data-stu-id="d77ba-121">Enumerates all objects where the specified string property contains at least one occurrence of the set of characters that is specified in '*PatternString*'.</span></span>  
  
 <span data-ttu-id="d77ba-122">\@*StringPropertyName*='*PatternString*'</span><span class="sxs-lookup"><span data-stu-id="d77ba-122">\@*StringPropertyName*='*PatternString*'</span></span>  
 <span data-ttu-id="d77ba-123">Enumera todos los objetos en los que el valor de la propiedad de cadena especificada es exactamente igual que el patrón de caracteres especificado en “*PatternString*”.</span><span class="sxs-lookup"><span data-stu-id="d77ba-123">Enumerates all objects where the value of the specified string property is exactly the same as the character pattern that is specified in '*PatternString*'.</span></span>  
  
 <span data-ttu-id="d77ba-124">\@*DatePropertyName*= datetime('*DateString*')</span><span class="sxs-lookup"><span data-stu-id="d77ba-124">\@*DatePropertyName*= datetime('*DateString*')</span></span>  
 <span data-ttu-id="d77ba-125">Enumera todos los objetos en los que el valor de la propiedad de fecha especificada coincide con la fecha especificada en “*DateString*”.</span><span class="sxs-lookup"><span data-stu-id="d77ba-125">Enumerates all objects where the value of the specified date property matches the date that is specified in '*DateString*'.</span></span> <span data-ttu-id="d77ba-126">*DateString* debe seguir el formato aaaa-mm-dd hh:mi:ss.mmm.</span><span class="sxs-lookup"><span data-stu-id="d77ba-126">*DateString* must follow the format yyyy-mm-dd hh:mi:ss.mmm</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d77ba-127">aaaa</span><span class="sxs-lookup"><span data-stu-id="d77ba-127">yyyy</span></span>|<span data-ttu-id="d77ba-128">Año de cuatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="d77ba-128">Four digit year.</span></span>|  
|<span data-ttu-id="d77ba-129">MM</span><span class="sxs-lookup"><span data-stu-id="d77ba-129">mm</span></span>|<span data-ttu-id="d77ba-130">Mes de dos dígitos (del 01 al 12).</span><span class="sxs-lookup"><span data-stu-id="d77ba-130">Two digit month (01 through 12).</span></span>|  
|<span data-ttu-id="d77ba-131">dd</span><span class="sxs-lookup"><span data-stu-id="d77ba-131">dd</span></span>|<span data-ttu-id="d77ba-132">Fecha de dos dígitos (del 01 al 31).</span><span class="sxs-lookup"><span data-stu-id="d77ba-132">Two digit date (01 through 31).</span></span>|  
|<span data-ttu-id="d77ba-133">hh</span><span class="sxs-lookup"><span data-stu-id="d77ba-133">hh</span></span>|<span data-ttu-id="d77ba-134">Hora de dos dígitos en un reloj de 24 horas (del 01 al 23).</span><span class="sxs-lookup"><span data-stu-id="d77ba-134">Two digit hour using a 24 hour clock (01 through 23).</span></span>|  
|<span data-ttu-id="d77ba-135">mi</span><span class="sxs-lookup"><span data-stu-id="d77ba-135">mi</span></span>|<span data-ttu-id="d77ba-136">Minutos de dos dígitos (del 01 al 59).</span><span class="sxs-lookup"><span data-stu-id="d77ba-136">Two digit minutes (01 through 59).</span></span>|  
|<span data-ttu-id="d77ba-137">ss</span><span class="sxs-lookup"><span data-stu-id="d77ba-137">ss</span></span>|<span data-ttu-id="d77ba-138">Segundos de dos dígitos (del 01 al 59).</span><span class="sxs-lookup"><span data-stu-id="d77ba-138">Two digit seconds (01 through 59).</span></span>|  
|<span data-ttu-id="d77ba-139">mmm</span><span class="sxs-lookup"><span data-stu-id="d77ba-139">mmm</span></span>|<span data-ttu-id="d77ba-140">Número de milisegundos (del 001 al 999).</span><span class="sxs-lookup"><span data-stu-id="d77ba-140">Number of milliseconds (001 through 999).</span></span>|  
  
 <span data-ttu-id="d77ba-141">Las fechas que se especifican en este formato se pueden evaluar en cualquier formato de fecha que se almacene en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d77ba-141">The dates that are specified in this format can be evaluated against any date format that is stored in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d77ba-142">is_null ( \@ *PropertyName*)</span><span class="sxs-lookup"><span data-stu-id="d77ba-142">is_null(\@*PropertyName*)</span></span>  
 <span data-ttu-id="d77ba-143">Enumera todos los objetos en los que la propiedad especificada tiene un valor de NULL.</span><span class="sxs-lookup"><span data-stu-id="d77ba-143">Enumerates all objects where the specified property has a value of NULL.</span></span>  
  
 <span data-ttu-id="d77ba-144">no ( \<*PropertyExpression*> )</span><span class="sxs-lookup"><span data-stu-id="d77ba-144">not(\<*PropertyExpression*>)</span></span>  
 <span data-ttu-id="d77ba-145">Niega el valor de evaluación de *PropertyExpression*, enumerando todos los objetos que no coinciden con la condición especificada en *PropertyExpression*.</span><span class="sxs-lookup"><span data-stu-id="d77ba-145">Negates the evaluation value of the *PropertyExpression*, enumerating all objects that do not match the condition specified in *PropertyExpression*.</span></span> <span data-ttu-id="d77ba-146">Por ejemplo, distinto de (contains(\@Name, 'xyz')) enumera todos los objetos que no tienen la cadena xyz en su nombre.</span><span class="sxs-lookup"><span data-stu-id="d77ba-146">For example, not(contains(\@Name, 'xyz')) enumerates all objects that do not have the string xyz in their names.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d77ba-147">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d77ba-147">Remarks</span></span>  
 <span data-ttu-id="d77ba-148">Las expresiones de consulta son cadenas que enumeran los nodos de una jerarquía de modelo SMO.</span><span class="sxs-lookup"><span data-stu-id="d77ba-148">Query expressions are strings that enumerate the nodes in an SMO model hierarchy.</span></span> <span data-ttu-id="d77ba-149">Cada nodo tiene una expresión de filtro que especifica los criterios para determinar los objetos que se enumeran en ese nodo.</span><span class="sxs-lookup"><span data-stu-id="d77ba-149">Each node has a filter expression that specifies the criteria for determining which objects at that node are enumerated.</span></span> <span data-ttu-id="d77ba-150">Las expresiones de consulta se modelan en el lenguaje de expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="d77ba-150">Query expressions are modeled on the XPath expression language.</span></span> <span data-ttu-id="d77ba-151">Las expresiones de consulta implementan un pequeño subconjunto admitido por XPath y, además, tienen algunas extensiones que no se encuentran en XPath.</span><span class="sxs-lookup"><span data-stu-id="d77ba-151">Query expressions implement a small subset of the expressions that are supported by XPath, and also have some extensions that are not found in XPath.</span></span> <span data-ttu-id="d77ba-152">Las expresiones XPath son cadenas que especifican un conjunto de criterios usados para enumerar una o mas de las etiquetas de un documento XML.</span><span class="sxs-lookup"><span data-stu-id="d77ba-152">XPath expressions are strings that specify a set of criteria that are used to enumerate one or more of the tags in an XML document.</span></span> <span data-ttu-id="d77ba-153">Para obtener más información acerca de XPath, vea [W3C XPath Language](http://www.w3.org/TR/xpath20/).</span><span class="sxs-lookup"><span data-stu-id="d77ba-153">For more information about XPath, see [W3C XPath Language](http://www.w3.org/TR/xpath20/).</span></span>  
  
 <span data-ttu-id="d77ba-154">Las expresiones de consulta deben empezar por una referencia absoluta al objeto Server.</span><span class="sxs-lookup"><span data-stu-id="d77ba-154">Query expressions must start with an absolute reference to the Server object.</span></span> <span data-ttu-id="d77ba-155">No se admiten expresiones relativas con una / inicial.</span><span class="sxs-lookup"><span data-stu-id="d77ba-155">Relative expressions with a leading / are not allowed.</span></span> <span data-ttu-id="d77ba-156">La secuencia de objetos que se especifica en una expresión de consulta debe seguir la jerarquía de los objetos de la colección del modelo de objetos asociado.</span><span class="sxs-lookup"><span data-stu-id="d77ba-156">The sequence of objects that are specified in a query expression must follow the hierarchy of collection objects in the associated object model.</span></span> <span data-ttu-id="d77ba-157">Por ejemplo, una expresión de consulta que hace referencia a objetos del espacio de nombres Microsoft.SqlServer.Management.Smo debe empezar por un nodo Server seguido de un nodo Database, etc.</span><span class="sxs-lookup"><span data-stu-id="d77ba-157">For example, a query expression that references objects in the Microsoft.SqlServer.Management.Smo namespace must start with a Server node followed by a Database node, and so on.</span></span>  
  
 <span data-ttu-id="d77ba-158">Si *\<FilterExpression>* no se especifica un para un objeto, se enumeran todos los objetos de ese nodo.</span><span class="sxs-lookup"><span data-stu-id="d77ba-158">If a *\<FilterExpression>* is not specified for an object, all the objects at that node are enumerated.</span></span>  
  
## <a name="uniform-resource-names-urn"></a><span data-ttu-id="d77ba-159">Nombres de recursos uniformes (URN)</span><span class="sxs-lookup"><span data-stu-id="d77ba-159">Uniform Resource Names (URN)</span></span>  
 <span data-ttu-id="d77ba-160">Los URN son un subconjunto de expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="d77ba-160">URNs are a subset of query expressions.</span></span> <span data-ttu-id="d77ba-161">Cada URN forma una referencia completa a un solo objeto.</span><span class="sxs-lookup"><span data-stu-id="d77ba-161">Each URN forms a fully-qualified reference to a single object.</span></span> <span data-ttu-id="d77ba-162">Un URN típico utiliza la propiedad Name para identificar un objeto único de cada nodo.</span><span class="sxs-lookup"><span data-stu-id="d77ba-162">A typical URN uses the Name property to identify a single object at each node.</span></span> <span data-ttu-id="d77ba-163">Por ejemplo, este URN hace referencia a una columna concreta:</span><span class="sxs-lookup"><span data-stu-id="d77ba-163">For example, this URN refers to a specific column:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']/Table[@Name='SalesPerson' and @Schema='Sales']/Column[@Name='SalesPersonID']  
```  
  
## <a name="examples"></a><span data-ttu-id="d77ba-164">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d77ba-164">Examples</span></span>  
  
### <a name="a-enumerating-objects-using-false"></a><span data-ttu-id="d77ba-165">A.</span><span class="sxs-lookup"><span data-stu-id="d77ba-165">A.</span></span> <span data-ttu-id="d77ba-166">Enumerar objetos mediante false()</span><span class="sxs-lookup"><span data-stu-id="d77ba-166">Enumerating objects using false()</span></span>  
 <span data-ttu-id="d77ba-167">Esta expresión de consulta enumera todas las bases de datos que tienen el atributo **AutoClose** definido en false en la instancia predeterminada de **MyComputer**.</span><span class="sxs-lookup"><span data-stu-id="d77ba-167">This query expression enumerates all the databases that have the **AutoClose** attribute set to false in the default instance on **MyComputer**.</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@AutoClose=false()]  
```  
  
### <a name="b-enumerating-objects-using-contains"></a><span data-ttu-id="d77ba-168">B.</span><span class="sxs-lookup"><span data-stu-id="d77ba-168">B.</span></span> <span data-ttu-id="d77ba-169">Enumerar objetos mediante contains</span><span class="sxs-lookup"><span data-stu-id="d77ba-169">Enumerating objects using contains</span></span>  
 <span data-ttu-id="d77ba-170">Esta expresión de consulta enumera todas las bases de datos con distinción entre mayúsculas y minúsculas, y cuyo nombre contiene el carácter 'm'.</span><span class="sxs-lookup"><span data-stu-id="d77ba-170">This query expression enumerates all the databases that are case-insensitive and have the character 'm' in their name.</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@CaseSensitive=false() and contains(@Name, 'm')]   
```  
  
### <a name="c-enumerating-objects-using-not"></a><span data-ttu-id="d77ba-171">C.</span><span class="sxs-lookup"><span data-stu-id="d77ba-171">C.</span></span> <span data-ttu-id="d77ba-172">Enumerar objetos mediante not</span><span class="sxs-lookup"><span data-stu-id="d77ba-172">Enumerating objects using not</span></span>  
 <span data-ttu-id="d77ba-173">Esta expresión de consulta enumera todas las tablas de [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] que no están en el esquema **Production** y contienen la palabra History en el nombre de tabla:</span><span class="sxs-lookup"><span data-stu-id="d77ba-173">This query expression enumerates all of [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] tables that are not in the **Production** schema and contain the word History in the table name:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012']/Table[not(@Schema='Production') and contains(@Name, 'History')]  
```  
  
### <a name="d-not-supplying-a-filter-expression-for-the-final-node"></a><span data-ttu-id="d77ba-174">D.</span><span class="sxs-lookup"><span data-stu-id="d77ba-174">D.</span></span> <span data-ttu-id="d77ba-175">Sin proporcionar ninguna expresión de filtro para el nodo final</span><span class="sxs-lookup"><span data-stu-id="d77ba-175">Not supplying a filter expression for the final node</span></span>  
 <span data-ttu-id="d77ba-176">Esta expresión de consulta enumera todas las columnas de la tabla **AdventureWorks2012.Sales.SalesPerson** :</span><span class="sxs-lookup"><span data-stu-id="d77ba-176">This query expression enumerates all the columns in the **AdventureWorks2012.Sales.SalesPerson** table:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[@Schema='Sales' and @Name='SalesPerson']/Columns  
```  
  
### <a name="e-enumerating-objects-using-datetime"></a><span data-ttu-id="d77ba-177">E.</span><span class="sxs-lookup"><span data-stu-id="d77ba-177">E.</span></span> <span data-ttu-id="d77ba-178">Enumerar objetos mediante datetime</span><span class="sxs-lookup"><span data-stu-id="d77ba-178">Enumerating objects using datetime</span></span>  
 <span data-ttu-id="d77ba-179">Esta expresión de consulta enumera todas las tablas creadas en la base de datos de [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] en un momento concreto:</span><span class="sxs-lookup"><span data-stu-id="d77ba-179">This query expression enumerates all the tables that are created in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database at a specific time:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[@CreateDate=datetime('2008-03-21 19:49:32.647')]  
```  
  
### <a name="f-enumerating-objects-using-is_null"></a><span data-ttu-id="d77ba-180">F.</span><span class="sxs-lookup"><span data-stu-id="d77ba-180">F.</span></span> <span data-ttu-id="d77ba-181">Enumerar objetos mediante is_null</span><span class="sxs-lookup"><span data-stu-id="d77ba-181">Enumerating objects using is_null</span></span>  
 <span data-ttu-id="d77ba-182">Esta expresión de consulta enumera todas las tablas de la base de datos de [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] que no tienen el valor NULL para su propiedad de fecha de última modificación:</span><span class="sxs-lookup"><span data-stu-id="d77ba-182">This query expression enumerates all the tables in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database that do not have NULL for their date last modified property:</span></span>  
  
```  
Server[@Name='MYCOMPUTER']/Database[@Name='AdventureWorks2012"]/Table[Not(is_null(@DateLastModified))]  
```  
  
## <a name="see-also"></a><span data-ttu-id="d77ba-183">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d77ba-183">See Also</span></span>  
 <span data-ttu-id="d77ba-184">[Cmdlet Invoke-PolicyEvaluation](../database-engine/invoke-policyevaluation-cmdlet.md) </span><span class="sxs-lookup"><span data-stu-id="d77ba-184">[Invoke-PolicyEvaluation cmdlet](../database-engine/invoke-policyevaluation-cmdlet.md) </span></span>  
 [<span data-ttu-id="d77ba-185">SQL Server Audit &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="d77ba-185">SQL Server Audit &#40;Database Engine&#41;</span></span>](../relational-databases/security/auditing/sql-server-audit-database-engine.md)  
