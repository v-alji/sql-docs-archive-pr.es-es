---
title: 'Especificar la profundidad en relaciones recursivas mediante SQL: Max-Depth | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- max-depth annotation
- XPath queries [SQLXML], recursive relationships
- depth in recursive relationships [SQLXML]
- annotated XSD schemas, recursive relationships
- relationships [SQLXML], recursive relationships
- self joins
- recursive relationships [SQLXML]
- recursion [SQLXML]
- sql:max-depth
- recursive joins [SQLXML]
ms.assetid: 0ffdd57d-dc30-44d9-a8a0-f21cadedb327
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e3ccb2de9c7b2ac8f8702b52aa990d755620e46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674039"
---
# <a name="specifying-depth-in-recursive-relationships-by-using-sqlmax-depth"></a><span data-ttu-id="202d3-102">Especificar la profundidad en relaciones recursivas utilizando sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="202d3-102">Specifying Depth in Recursive Relationships by Using sql:max-depth</span></span>
  <span data-ttu-id="202d3-103">En las bases de datos relacionales, cuando una tabla se relaciona consigo misma, este tipo de relación recibe el nombre de relación recursiva.</span><span class="sxs-lookup"><span data-stu-id="202d3-103">In relational databases, when a table is involved in a relationship with itself, it is called a recursive relationship.</span></span> <span data-ttu-id="202d3-104">Por ejemplo, en una relación supervisor-supervisado, una tabla que almacena los registros de empleados se relaciona consigo misma.</span><span class="sxs-lookup"><span data-stu-id="202d3-104">For example, in a supervisor-supervisee relationship, a table storing employee records is involved in a relationship with itself.</span></span> <span data-ttu-id="202d3-105">En este caso, la tabla de empleados desempeña un rol de supervisor en uno de los lados de la relación y un rol de supervisado en el otro lado.</span><span class="sxs-lookup"><span data-stu-id="202d3-105">In this case, the employees table plays a role of supervisor on one side of the relationship, and the same table plays a role of supervisee on the other side.</span></span>  
  
 <span data-ttu-id="202d3-106">Los esquemas de asignación pueden incluir relaciones recursivas donde un elemento y su antecesor son del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="202d3-106">Mapping schemas can include recursive relationships where an element and its ancestor are of the same type.</span></span>  
  
## <a name="example-a"></a><span data-ttu-id="202d3-107">Ejemplo A</span><span class="sxs-lookup"><span data-stu-id="202d3-107">Example A</span></span>  
 <span data-ttu-id="202d3-108">Fíjese en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="202d3-108">Consider the following table:</span></span>  
  
```  
Emp (EmployeeID, FirstName, LastName, ReportsTo)  
```  
  
 <span data-ttu-id="202d3-109">En esta tabla, la columna ReportsTo almacena el identificador de empleado del director.</span><span class="sxs-lookup"><span data-stu-id="202d3-109">In this table, the ReportsTo column stores the employee ID of the manager.</span></span>  
  
 <span data-ttu-id="202d3-110">Supongamos que desea crear una jerarquía XML de empleados en la que el empleado director se sitúa en la parte superior de la jerarquía y los empleados que son subordinados directos de ese director aparecen en la jerarquía correspondiente tal y como se muestra en el siguiente fragmento XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="202d3-110">Assume that you want to generate an XML hierarchy of employees in which the manager employee is at the top of the hierarchy, and in which the employees that report to that manager appear in the corresponding hierarchy as shown in the following sample XML fragment.</span></span> <span data-ttu-id="202d3-111">Lo que muestra este fragmento es el *árbol recursivo* del empleado 1.</span><span class="sxs-lookup"><span data-stu-id="202d3-111">What this fragment shows is the *recursive tree* for employee 1.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
     <Emp FirstName="Andrew" EmployeeID="2" LastName="Fuller" />   
     <Emp FirstName="Janet" EmployeeID="3" LastName="Leverling">  
        <Emp FirstName="Margaret" EmployeeID="4" LastName="Peacock">  
          <Emp FirstName="Steven" EmployeeID="5" LastName="Devolio">  
...  
...  
</root>  
```  
  
 <span data-ttu-id="202d3-112">En este fragmento, el empleado 5 es subordinado directo del empleado 4, el empleado 4 es subordinado directo del empleado 3 y los empleados 3 y 2 son subordinados directos del empleado 1.</span><span class="sxs-lookup"><span data-stu-id="202d3-112">In this fragment, employee 5 reports to employee 4, employee 4 reports to employee 3, and employees 3 and 2 reports to employee 1.</span></span>  
  
 <span data-ttu-id="202d3-113">Para generar este resultado, puede usar el siguiente esquema XSD y especificar una consulta XPath en él.</span><span class="sxs-lookup"><span data-stu-id="202d3-113">To produce this result, you can use the following XSD schema and specify an XPath query against it.</span></span> <span data-ttu-id="202d3-114">El esquema describe un **\<Emp>** elemento de tipo EmployeeType, que consta de un **\<Emp>** elemento secundario del mismo tipo, EmployeeType.</span><span class="sxs-lookup"><span data-stu-id="202d3-114">The schema describes an **\<Emp>** element of type EmployeeType, consisting of an **\<Emp>** child element of the same type, EmployeeType.</span></span> <span data-ttu-id="202d3-115">Se trata de una relación recursiva (el elemento y su antecesor son del mismo tipo).</span><span class="sxs-lookup"><span data-stu-id="202d3-115">This is a recursive relationship (the element and its ancestor are of the same type).</span></span> <span data-ttu-id="202d3-116">Además, el esquema utiliza **\<sql:relationship>** para describir la relación de elementos primarios y secundarios entre el supervisor y el supervisado.</span><span class="sxs-lookup"><span data-stu-id="202d3-116">In addition, the schema uses a **\<sql:relationship>** to describe the parent-child relationship between the supervisor and supervisee.</span></span> <span data-ttu-id="202d3-117">Tenga en cuenta que **\<sql:relationship>** , en este, EMP es la tabla primaria y la secundaria.</span><span class="sxs-lookup"><span data-stu-id="202d3-117">Note that in this **\<sql:relationship>**, Emp is both the parent and the child table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"  
                                  parent="Emp"  
                                  parent-key="EmployeeID"  
                                  child="Emp"  
                                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp" type="EmployeeType"   
                          sql:relation="Emp"   
                          sql:key-fields="EmployeeID"   
                          sql:limit-field="ReportsTo" />  
  <xsd:complexType name="EmployeeType">  
    <xsd:sequence>  
      <xsd:element name="Emp" type="EmployeeType"   
                              sql:relation="Emp"   
                              sql:key-fields="EmployeeID"  
                              sql:relationship="SupervisorSupervisee"  
                              sql:max-depth="6" />  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:ID" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="202d3-118">Dado que la relación es recursiva, necesita algún modo de especificar la profundidad de recursión del esquema.</span><span class="sxs-lookup"><span data-stu-id="202d3-118">Because the relationship is recursive, you need some way to specify the depth of recursion in the schema.</span></span> <span data-ttu-id="202d3-119">De lo contrario, el resultado será una recursión sin fin (empleado subordinado directo de empleado subordinado directo de empleado, etc.).</span><span class="sxs-lookup"><span data-stu-id="202d3-119">Otherwise, the result will be an endless recursion (employee reporting to employee reporting to employee, and so on).</span></span> <span data-ttu-id="202d3-120">La anotación `sql:max-depth` permite especificar la profundidad de la recursión.</span><span class="sxs-lookup"><span data-stu-id="202d3-120">The `sql:max-depth` annotation allows you to specify how deep in the recursion to go.</span></span> <span data-ttu-id="202d3-121">En este ejemplo en concreto, para especificar un valor para `sql:max-depth`, debe conocer la profundidad de la jerarquía de dirección de la compañía.</span><span class="sxs-lookup"><span data-stu-id="202d3-121">In this particular example, to specify a value for `sql:max-depth`, you must know how deep the management hierarchy goes in the company.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="202d3-122">El esquema especifica la anotación `sql:limit-field`, pero no especifica la anotación `sql:limit-value`.</span><span class="sxs-lookup"><span data-stu-id="202d3-122">The schema specifies the `sql:limit-field` annotation, but does not specify the `sql:limit-value` annotation.</span></span> <span data-ttu-id="202d3-123">Esto limita el nodo superior de la jerarquía resultante únicamente a los empleados que no son subordinados directos de nadie.</span><span class="sxs-lookup"><span data-stu-id="202d3-123">This limits the top node in the resulting hierarchy to only those employees who do not report to anyone.</span></span> <span data-ttu-id="202d3-124">(Reportto es NULL). Si `sql:limit-field` se especifica y no se especifica `sql:limit-value` (que tiene como valor predeterminado NULL), la anotación logra esto.</span><span class="sxs-lookup"><span data-stu-id="202d3-124">(ReportsTo is NULL.) Specifying `sql:limit-field` and not specifying `sql:limit-value` (which defaults to NULL) annotation accomplishes this.</span></span> <span data-ttu-id="202d3-125">Si desea que el código XML resultante incluya todos los árboles de informes posibles (el árbol de informes de cada empleado de la tabla), quite la anotación `sql:limit-field` del esquema.</span><span class="sxs-lookup"><span data-stu-id="202d3-125">If you want the resulting XML to include every possible reporting tree (the reporting tree for every employee in the table), remove the `sql:limit-field` annotation from the schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="202d3-126">El siguiente procedimiento usa la base de datos tempdb.</span><span class="sxs-lookup"><span data-stu-id="202d3-126">The following procedure uses the tempdb database.</span></span>  
  
#### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="202d3-127">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="202d3-127">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="202d3-128">Cree una tabla de ejemplo denominada Emp en la base de datos tempdb a la que apunta la raíz virtual.</span><span class="sxs-lookup"><span data-stu-id="202d3-128">Create a sample table called Emp in the tempdb database to which the virtual root points.</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Emp (  
           EmployeeID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    ```  
  
2.  <span data-ttu-id="202d3-129">Agregue estos datos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="202d3-129">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Emp values (1, 'Nancy', 'Devolio',NULL)  
    INSERT INTO Emp values (2, 'Andrew', 'Fuller',1)  
    INSERT INTO Emp values (3, 'Janet', 'Leverling',1)  
    INSERT INTO Emp values (4, 'Margaret', 'Peacock',3)  
    INSERT INTO Emp values (5, 'Steven', 'Devolio',4)  
    INSERT INTO Emp values (6, 'Nancy', 'Buchanan',5)  
    INSERT INTO Emp values (7, 'Michael', 'Suyama',6)  
    ```  
  
3.  <span data-ttu-id="202d3-130">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="202d3-130">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="202d3-131">Guarde el archivo como maxDepth.xml.</span><span class="sxs-lookup"><span data-stu-id="202d3-131">Save the file as maxDepth.xml.</span></span>  
  
4.  <span data-ttu-id="202d3-132">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="202d3-132">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="202d3-133">Guarde el archivo como maxDepthT.xml en el mismo directorio donde guardó maxDepth.xml.</span><span class="sxs-lookup"><span data-stu-id="202d3-133">Save the file as maxDepthT.xml in the same directory where you saved maxDepth.xml.</span></span> <span data-ttu-id="202d3-134">La consulta de la plantilla devuelve todos los empleados de la tabla Emp.</span><span class="sxs-lookup"><span data-stu-id="202d3-134">The query in the template returns all the employees in the Emp table.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="maxDepth.xml">  
        /Emp  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="202d3-135">La ruta de acceso al directorio especificada para el esquema de asignación (maxDepth.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="202d3-135">The directory path specified for the mapping schema (maxDepth.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="202d3-136">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="202d3-136">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\maxDepth.xml"  
    ```  
  
5.  <span data-ttu-id="202d3-137">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="202d3-137">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="202d3-138">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="202d3-138">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="202d3-139">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="202d3-139">This is the result:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
  <Emp FirstName="Andrew" EmployeeID="2" LastName="Fuller" />   
    <Emp FirstName="Janet" EmployeeID="3" LastName="Leverling">  
      <Emp FirstName="Margaret" EmployeeID="4" LastName="Peacock">  
        <Emp FirstName="Steven" EmployeeID="5" LastName="Devolio">  
          <Emp FirstName="Nancy" EmployeeID="6" LastName="Buchanan">  
            <Emp FirstName="Michael" EmployeeID="7" LastName="Suyama" />   
          </Emp>  
        </Emp>  
      </Emp>  
    </Emp>  
  </Emp>  
</root>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="202d3-140">Para crear distintas profundidades de jerarquías en el resultado, cambie el valor de la anotación `sql:max-depth` en el esquema y vuelva a ejecutar la plantilla después de cada cambio.</span><span class="sxs-lookup"><span data-stu-id="202d3-140">To produce different depths of hierarchies in the result, change the value of the `sql:max-depth` annotation in the schema and execute the template again after each change.</span></span>  
  
 <span data-ttu-id="202d3-141">En el esquema anterior, todos los **\<Emp>** elementos tenían exactamente el mismo conjunto de atributos (**EmployeeID**, **FirstName**y **LastName**).</span><span class="sxs-lookup"><span data-stu-id="202d3-141">In the previous schema, all the **\<Emp>** elements had exactly the same set of attributes (**EmployeeID**, **FirstName**, and **LastName**).</span></span> <span data-ttu-id="202d3-142">El esquema siguiente se ha modificado ligeramente para devolver un atributo **Reportto** adicional para todos los **\<Emp>** elementos que informan a un administrador.</span><span class="sxs-lookup"><span data-stu-id="202d3-142">The following schema has been slightly modified to return an additional **ReportsTo** attribute for all the **\<Emp>** elements that report to a manager.</span></span>  
  
 <span data-ttu-id="202d3-143">Por ejemplo, este fragmento XML muestra los subordinados del empleado 1:</span><span class="sxs-lookup"><span data-stu-id="202d3-143">For example, this XML fragment shows the subordinates of employee 1:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
<Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
  <Emp FirstName="Andrew" EmployeeID="2"   
       ReportsTo="1" LastName="Fuller" />   
  <Emp FirstName="Janet" EmployeeID="3"   
       ReportsTo="1" LastName="Leverling">  
...  
...  
```  
  
 <span data-ttu-id="202d3-144">Éste es el esquema revisado:</span><span class="sxs-lookup"><span data-stu-id="202d3-144">This is the revised schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:documentation>  
      Customer-Order-Order Details Schema  
      Copyright 2000 Microsoft. All rights reserved.  
    </xsd:documentation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"   
                  parent="Emp"  
                  parent-key="EmployeeID"  
                  child="Emp"  
                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp"   
                   type="EmpType"   
                   sql:relation="Emp"   
                   sql:key-fields="EmployeeID"   
                   sql:limit-field="ReportsTo" />  
  <xsd:complexType name="EmpType">  
    <xsd:sequence>  
       <xsd:element name="Emp"   
                    type="EmpType"   
                    sql:relation="Emp"   
                    sql:key-fields="EmployeeID"  
                    sql:relationship="SupervisorSupervisee"  
                    sql:max-depth="6"/>  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:int" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
    <xsd:attribute name="ReportsTo" type="xsd:int" />  
  </xsd:complexType>  
</xsd:schema>  
```  
  
## <a name="sqlmax-depth-annotation"></a><span data-ttu-id="202d3-145">Anotación sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="202d3-145">sql:max-depth Annotation</span></span>  
 <span data-ttu-id="202d3-146">En un esquema compuesto de relaciones recursivas, la profundidad de recursión debe especificarse de forma explícita en el esquema.</span><span class="sxs-lookup"><span data-stu-id="202d3-146">In a schema consisting of recursive relationships, the depth of recursion must be explicitly specified in the schema.</span></span> <span data-ttu-id="202d3-147">Esto es necesario para generar correctamente la consulta FOR XML EXPLICIT correspondiente que devuelve los resultados solicitados.</span><span class="sxs-lookup"><span data-stu-id="202d3-147">This is required to successfully produce the corresponding FOR XML EXPLICIT query that returns the requested results.</span></span>  
  
 <span data-ttu-id="202d3-148">Use la anotación `sql:max-depth` en el esquema para especificar la profundidad de recursión de una relación recursiva que se describa en el esquema.</span><span class="sxs-lookup"><span data-stu-id="202d3-148">Use the `sql:max-depth` annotation in the schema to specify the depth of recursion in a recursive relationship that is described in the schema.</span></span> <span data-ttu-id="202d3-149">El valor de la anotación `sql:max-depth` es un número entero positivo (de 1 a 50) que indica el número de recursiones: un valor de 1 detiene la recursión en el elemento para el que se especifica la anotación `sql:max-depth`; un valor de 2 detiene la recursión en el siguiente nivel del elemento en el que se especifica `sql:max-depth`; y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="202d3-149">The value of the `sql:max-depth` annotation is a positive integer (1 to 50) that indicates the number of recursions:  A value of 1 stops the recursion at the element for which the `sql:max-depth` annotation is specified; a value of 2 stops the recursion at the next level from the element at which `sql:max-depth` is specified; and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="202d3-150">En la implementación subyacente, una consulta XPath que se especifica en un esquema de asignación se convierte en una consulta SELECT ... FOR XML EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="202d3-150">In the underlying implementation, an XPath query that is specified against a mapping schema is converted to a SELECT ... FOR XML EXPLICIT query.</span></span> <span data-ttu-id="202d3-151">Esta consulta exige que se especifique una profundidad finita de recursión.</span><span class="sxs-lookup"><span data-stu-id="202d3-151">This query requires you to specify a finite depth of recursion.</span></span> <span data-ttu-id="202d3-152">Cuanto mayor sea el valor que especifique para `sql:max-depth`, mayor será la consulta FOR XML EXPLICIT que se genere.</span><span class="sxs-lookup"><span data-stu-id="202d3-152">The higher the value that you specify for `sql:max-depth`, the larger the FOR XML EXPLICIT query that is generated.</span></span> <span data-ttu-id="202d3-153">Esto puede ralentizar el tiempo de recuperación.</span><span class="sxs-lookup"><span data-stu-id="202d3-153">This might slow the retrieval time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="202d3-154">Los diagramas de actualización y la carga masiva XML omiten la anotación max-depth.</span><span class="sxs-lookup"><span data-stu-id="202d3-154">Updategrams and XML Bulk Load ignore the max-depth annotation.</span></span> <span data-ttu-id="202d3-155">Esto significa que se llevarán a cabo inserciones o actualizaciones recursivas independientemente del valor que se especifique para max-depth.</span><span class="sxs-lookup"><span data-stu-id="202d3-155">This means, recursive updates or insertions will happen regardless of what value you specify for max-depth.</span></span>  
  
## <a name="specifying-sqlmax-depth-on-complex-elements"></a><span data-ttu-id="202d3-156">Especificar sql:max-depth en elementos complejos</span><span class="sxs-lookup"><span data-stu-id="202d3-156">Specifying sql:max-depth on Complex Elements</span></span>  
 <span data-ttu-id="202d3-157">La anotación `sql:max-depth` puede especificarse en cualquier elemento de contenido complejo.</span><span class="sxs-lookup"><span data-stu-id="202d3-157">The `sql:max-depth` annotation can be specified on any complex content element.</span></span>  
  
### <a name="recursive-elements"></a><span data-ttu-id="202d3-158">Elementos recursivos</span><span class="sxs-lookup"><span data-stu-id="202d3-158">Recursive Elements</span></span>  
 <span data-ttu-id="202d3-159">Si se especifica `sql:max-depth` tanto en el elemento primario como en el elemento secundario de una relación recursiva, la anotación `sql:max-depth` especificada en el elemento primario tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="202d3-159">If `sql:max-depth` is specified on both the parent element and the child element in a recursive relationship, the `sql:max-depth` annotation specified on the parent takes precedence.</span></span> <span data-ttu-id="202d3-160">Por ejemplo, en el esquema siguiente, la anotación `sql:max-depth` se especifica tanto en el elemento de empleado primario como en el secundario.</span><span class="sxs-lookup"><span data-stu-id="202d3-160">For example, in the following schema, the `sql:max-depth` annotation is specified on both the parent and the child employee elements.</span></span> <span data-ttu-id="202d3-161">En este caso, `sql:max-depth=4` el parámetro especificado en el **\<Emp>** elemento primario (que desempeña un rol de supervisor) tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="202d3-161">In this case, `sql:max-depth=4`, specified on the **\<Emp>** parent element (playing a role of supervisor), takes precedence.</span></span> <span data-ttu-id="202d3-162">`sql:max-depth`Se omite el especificado en el **\<Emp>** elemento secundario (que desempeña un rol de supervisado).</span><span class="sxs-lookup"><span data-stu-id="202d3-162">The `sql:max-depth` specified on the child **\<Emp>** element (playing a role of supervisee) is ignored.</span></span>  
  
#### <a name="example-b"></a><span data-ttu-id="202d3-163">Ejemplo B</span><span class="sxs-lookup"><span data-stu-id="202d3-163">Example B</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"  
                                  parent="Emp"  
                                  parent-key="EmployeeID"  
                                  child="Emp"  
                                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp" type="EmployeeType"   
                          sql:relation="Emp"   
                          sql:key-fields="EmployeeID"   
                          sql:limit-field="ReportsTo"   
                          sql:max-depth="3" />  
  <xsd:complexType name="EmployeeType">  
    <xsd:sequence>  
      <xsd:element name="Emp" type="EmployeeType"   
                              sql:relation="Emp"   
                              sql:key-fields="EmployeeID"  
                              sql:relationship="SupervisorSupervisee"  
                              sql:max-depth="2" />  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:ID" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="202d3-164">Para probar este esquema, siga los pasos proporcionados para el ejemplo A, anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="202d3-164">To test this schema, follow the steps provided for Sample A, earlier in this topic.</span></span>  
  
### <a name="nonrecursive-elements"></a><span data-ttu-id="202d3-165">Elementos no recursivos</span><span class="sxs-lookup"><span data-stu-id="202d3-165">Nonrecursive Elements</span></span>  
 <span data-ttu-id="202d3-166">Si la anotación `sql:max-depth` se especifica en un elemento del esquema que no presenta ninguna recursión, se omite.</span><span class="sxs-lookup"><span data-stu-id="202d3-166">If the `sql:max-depth` annotation is specified on an element in the schema that does not cause any recursion, it is ignored.</span></span> <span data-ttu-id="202d3-167">En el esquema siguiente, un **\<Emp>** elemento consta de un **\<Constant>** elemento secundario, que, a su vez, tiene un **\<Emp>** elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="202d3-167">In the following schema, an **\<Emp>** element consists of a **\<Constant>** child element, which, in turn, has an **\<Emp>** child element.</span></span>  
  
 <span data-ttu-id="202d3-168">En este esquema, la `sql:max-depth` anotación especificada en el **\<Constant>** elemento se omite porque no hay ninguna recursividad entre el **\<Emp>** elemento primario y el **\<Constant>** elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="202d3-168">In this schema, the `sql:max-depth` annotation specified on the **\<Constant>** element is ignored because there is no recursion between the **\<Emp>** parent and the **\<Constant>** child element.</span></span> <span data-ttu-id="202d3-169">Pero hay recursividad entre el **\<Emp>** antecesor y el **\<Emp>** secundario.</span><span class="sxs-lookup"><span data-stu-id="202d3-169">But there is recursion between the **\<Emp>** ancestor and the **\<Emp>** child.</span></span> <span data-ttu-id="202d3-170">El esquema especifica la anotación `sql:max-depth` en ambos elementos.</span><span class="sxs-lookup"><span data-stu-id="202d3-170">The schema specifies the `sql:max-depth` annotation on both.</span></span> <span data-ttu-id="202d3-171">Por lo tanto, la `sql:max-depth` anotación que se especifica en el antecesor ( **\<Emp>** en el rol supervisor) tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="202d3-171">Therefore, the `sql:max-depth` annotation that is specified on the ancestor (**\<Emp>** in the supervisor role) takes precedence.</span></span>  
  
#### <a name="example-c"></a><span data-ttu-id="202d3-172">Ejemplo C</span><span class="sxs-lookup"><span data-stu-id="202d3-172">Example C</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"   
                  parent="Emp"   
                  child="Emp"   
                  parent-key="EmployeeID"   
                  child-key="ReportsTo"/>  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp"   
               sql:relation="Emp"   
               type="EmpType"  
               sql:limit-field="ReportsTo"  
               sql:max-depth="1" />  
    <xsd:complexType name="EmpType" >  
      <xsd:sequence>  
       <xsd:element name="Constant"   
                    sql:is-constant="1"   
                    sql:max-depth="20" >  
         <xsd:complexType >  
           <xsd:sequence>  
            <xsd:element name="Emp"   
                         sql:relation="Emp" type="EmpType"  
                         sql:relationship="SupervisorSupervisee"   
                         sql:max-depth="3" />  
         </xsd:sequence>  
         </xsd:complexType>  
         </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="EmployeeID" type="xsd:int" />  
    </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="202d3-173">Para probar este esquema, siga los pasos que se proporcionaron para el Ejemplo A anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="202d3-173">To test this schema, follow the steps provided for Example A, earlier in this topic.</span></span>  
  
## <a name="complex-types-derived-by-restriction"></a><span data-ttu-id="202d3-174">Tipos complejos derivados por restricción</span><span class="sxs-lookup"><span data-stu-id="202d3-174">Complex Types Derived by Restriction</span></span>  
 <span data-ttu-id="202d3-175">Si tiene una derivación de tipo complejo por **\<restriction>** , los elementos del tipo complejo base correspondiente no pueden especificar la `sql:max-depth` anotación.</span><span class="sxs-lookup"><span data-stu-id="202d3-175">If you have a complex type derivation by **\<restriction>**, elements of the corresponding base complex type cannot specify the `sql:max-depth` annotation.</span></span> <span data-ttu-id="202d3-176">En estos casos, la anotación `sql:max-depth` puede agregarse al elemento del tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="202d3-176">In these cases, the `sql:max-depth` annotation can be added to the element of the derived type.</span></span>  
  
 <span data-ttu-id="202d3-177">Por otro lado, si tiene una derivación de tipo complejo por **\<extension>** , los elementos del tipo complejo base correspondiente pueden especificar la `sql:max-depth` anotación.</span><span class="sxs-lookup"><span data-stu-id="202d3-177">On the other hand, if you have a complex type derivation by **\<extension>**, the elements of the corresponding base complex type can specify the `sql:max-depth` annotation.</span></span>  
  
 <span data-ttu-id="202d3-178">Por ejemplo, el siguiente esquema XSD genera un error porque la anotación `sql:max-depth` se especifica en el tipo base.</span><span class="sxs-lookup"><span data-stu-id="202d3-178">For example, the following XSD schema generates an error because the `sql:max-depth` annotation is specified on the base type.</span></span> <span data-ttu-id="202d3-179">Esta anotación no se admite en un tipo derivado **\<restriction>** de desde otro tipo.</span><span class="sxs-lookup"><span data-stu-id="202d3-179">This annotation is not supported on a type that is derived by **\<restriction>** from another type.</span></span> <span data-ttu-id="202d3-180">Para corregir este problema, debe cambiar el esquema y especificar la anotación `sql:max-depth` en un elemento del tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="202d3-180">To fix this problem, you must change the schema and specify the `sql:max-depth` annotation on element in the derived type.</span></span>  
  
#### <a name="example-d"></a><span data-ttu-id="202d3-181">Ejemplo D</span><span class="sxs-lookup"><span data-stu-id="202d3-181">Example D</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:complexType name="CustomerBaseType">   
    <xsd:sequence>  
       <xsd:element name="CID" msdata:field="CustomerID" />  
       <xsd:element name="CompanyName"/>  
       <xsd:element name="Customers" msdata:max-depth="3">  
         <xsd:annotation>  
           <xsd:appinfo>  
             <msdata:relationship  
                     parent="Customers"  
                     parent-key="CustomerID"  
                     child-key="CustomerID"  
                     child="Customers" />  
           </xsd:appinfo>  
         </xsd:annotation>  
       </xsd:element>  
    </xsd:sequence>  
  </xsd:complexType>  
  <xsd:element name="Customers" type="CustomerType"/>  
  <xsd:complexType name="CustomerType">  
    <xsd:complexContent>  
       <xsd:restriction base="CustomerBaseType">  
          <xsd:sequence>  
            <xsd:element name="CID"   
                         type="xsd:string"/>  
            <xsd:element name="CompanyName"   
                         type="xsd:string"  
                         msdata:field="CName" />  
            <xsd:element name="Customers"   
                         type="CustomerType" />  
          </xsd:sequence>  
       </xsd:restriction>  
    </xsd:complexContent>  
  </xsd:complexType>  
</xsd:schema>   
```  
  
 <span data-ttu-id="202d3-182">En el esquema, `sql:max-depth` se especifica en un tipo `CustomerBaseType` complejo.</span><span class="sxs-lookup"><span data-stu-id="202d3-182">In the schema, `sql:max-depth` is specified on a `CustomerBaseType` complex type.</span></span> <span data-ttu-id="202d3-183">El esquema también especifica un **\<Customer>** elemento de tipo `CustomerType` , que se deriva de `CustomerBaseType` .</span><span class="sxs-lookup"><span data-stu-id="202d3-183">The schema also specifies a **\<Customer>** element of type `CustomerType`, which is derived from `CustomerBaseType`.</span></span> <span data-ttu-id="202d3-184">Una consulta XPath especificada en un esquema de este tipo generará un error, puesto que `sql:max-depth` no se admite en un elemento que se define en un tipo base de restricción.</span><span class="sxs-lookup"><span data-stu-id="202d3-184">An XPath query specified on such a schema will generate an error, because `sql:max-depth` is not supported on an element that is defined in a restriction base type.</span></span>  
  
## <a name="schemas-with-a-deep-hierarchy"></a><span data-ttu-id="202d3-185">Esquemas con una jerarquía profunda</span><span class="sxs-lookup"><span data-stu-id="202d3-185">Schemas with a Deep Hierarchy</span></span>  
 <span data-ttu-id="202d3-186">Puede tener un esquema que incluya una jerarquía profunda en la que un elemento contiene un elemento secundario, que a su vez contiene otro elemento secundario, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="202d3-186">You might have a schema that includes a deep hierarchy in which an element contains a child element, which in turn contains another child element, and so on.</span></span> <span data-ttu-id="202d3-187">Si la anotación `sql:max-depth` especificada en un esquema de este tipo genera un documento XML que incluye una jerarquía de más de 500 niveles (con el elemento de nivel superior en el nivel 1, su elemento secundario en el nivel 2, etc.), se devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="202d3-187">If the `sql:max-depth` annotation specified in such a schema generates an XML document that includes a hierarchy of more than 500 levels (with top-level element at level 1, its child at level 2, and so on), an error is returned.</span></span>  
  
  
