---
title: Controlar los problemas de simultaneidad de bases de datos en diagramas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- <before> block
- low concurrency protection
- database concurrency [SQLXML]
- timestamp column [SQLXML]
- updategrams [SQLXML], database concurrency
- high concurrency protection [SQLXML]
- optimistic concurrency control
- concurrency [SQLXML]
- intermediate concurrency protection [SQLXML]
ms.assetid: d4b908d1-b25b-4ad9-8478-9cd882e8c44e
author: rothja
ms.author: jroth
ms.openlocfilehash: dd808b2688e8bf05149a5454bee91123878fb2ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674741"
---
# <a name="handling-database-concurrency-issues-in-updategrams-sqlxml-40"></a><span data-ttu-id="249dd-102">Controlar problemas de simultaneidad de base de datos en diagramas de actualización (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="249dd-102">Handling Database Concurrency Issues in Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="249dd-103">Al igual que otros mecanismos de actualización de base de datos, los diagramas de actualización deben lidiar con actualizaciones simultáneas de datos en un entorno multiusuario.</span><span class="sxs-lookup"><span data-stu-id="249dd-103">Like other database update mechanisms, updategrams must deal with concurrent updates to data in a multiuser environment.</span></span> <span data-ttu-id="249dd-104">Los diagramas de actualización usan el control de simultaneidad optimista, que usa la comparación de datos de campos de selección como instantáneas para asegurarse de que otra aplicación de usuario no haya modificado los datos que van a actualizarse desde que se leyeron de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="249dd-104">Updategrams use the Optimistic Concurrency Control, which uses comparison of select field data as snapshots to ensure that the data to be updated has not been altered by another user application since it was read from the database.</span></span> <span data-ttu-id="249dd-105">Diagramas incluye estos valores de instantánea en el **\<before>** bloque de diagramas.</span><span class="sxs-lookup"><span data-stu-id="249dd-105">Updategrams include these snapshot values in the **\<before>** block of the updategrams.</span></span> <span data-ttu-id="249dd-106">Antes de actualizar la base de datos, diagrama comprueba los valores especificados en el **\<before>** bloque con los valores que hay actualmente en la base de datos para asegurarse de que la actualización es válida.</span><span class="sxs-lookup"><span data-stu-id="249dd-106">Before updating the database, the updategram checks the values that are specified in the **\<before>** block against the values currently in the database to ensure that the update is valid.</span></span>  
  
 <span data-ttu-id="249dd-107">El control de simultaneidad optimista ofrece tres niveles de protección en un diagrama de actualización: bajo (ninguno), intermedio y alto.</span><span class="sxs-lookup"><span data-stu-id="249dd-107">The Optimistic Concurrency Control offers three levels of protection in an updategram: low (none), intermediate, and high.</span></span> <span data-ttu-id="249dd-108">Puede decidir qué nivel de protección necesita especificando el diagrama de actualización en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="249dd-108">You can decide what level of protection you need by specifying the updategram accordingly.</span></span>  
  
## <a name="lowest-level-of-protection"></a><span data-ttu-id="249dd-109">Nivel de protección más bajo</span><span class="sxs-lookup"><span data-stu-id="249dd-109">Lowest Level of Protection</span></span>  
 <span data-ttu-id="249dd-110">Este nivel es en realidad una actualización “ciega”, donde la actualización se procesa sin hacer referencia a otras actualizaciones que se hayan realizado desde que la base de datos se leyó por última vez.</span><span class="sxs-lookup"><span data-stu-id="249dd-110">This level is a blind update, in which the update is processed without reference to other updates that have been made since the database was last read.</span></span> <span data-ttu-id="249dd-111">En tal caso, solo se especifican las columnas de clave principal en el **\<before>** bloque para identificar el registro y se especifica la información actualizada en el **\<after>** bloque.</span><span class="sxs-lookup"><span data-stu-id="249dd-111">In such a case, you specify only the primary key column(s) in the **\<before>** block to identify the record, and you specify the updated information in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="249dd-112">Por ejemplo, el nuevo número de teléfono del contacto en el diagrama de actualización siguiente es correcto, independientemente de cuál fuera el número de teléfono anterior.</span><span class="sxs-lookup"><span data-stu-id="249dd-112">For example, the new contact phone number in the following updategram is correct, regardless of what the phone number was previously.</span></span> <span data-ttu-id="249dd-113">Observe cómo el **\<before>** bloque especifica únicamente la columna de clave principal (ContactID).</span><span class="sxs-lookup"><span data-stu-id="249dd-113">Notice how the **\<before>** block specifies only the primary key column (ContactID).</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" />  
</updg:before>  
<updg:after>  
   <Person.Contact ContactID="1" Phone="111-111-1111" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="intermediate-level-of-protection"></a><span data-ttu-id="249dd-114">Nivel de protección intermedio</span><span class="sxs-lookup"><span data-stu-id="249dd-114">Intermediate Level of Protection</span></span>  
 <span data-ttu-id="249dd-115">En este nivel de protección, el diagrama de actualización compara los valores actuales de los datos que se están actualizando con los valores de las columnas de la base de datos para asegurarse de que ninguna otra transacción los haya modificado desde que la transacción del usuario leyó el registro.</span><span class="sxs-lookup"><span data-stu-id="249dd-115">In this level of protection, the updategram compares the current value(s) of the data being updated with the value(s) in the database column(s) to ensure that the values have not been changed by some other transaction since the record was read by your transaction.</span></span>  
  
 <span data-ttu-id="249dd-116">Puede obtener este nivel de protección si especifica las columnas de clave principal y las columnas que se van a actualizar en el **\<before>** bloque.</span><span class="sxs-lookup"><span data-stu-id="249dd-116">You can get this level of protection by specifying the primary key column(s) and the column(s) that you are updating in the **\<before>** block.</span></span>  
  
 <span data-ttu-id="249dd-117">Por ejemplo, este diagrama de actualización cambia el valor de la columna Phone de la tabla Person.Contact para el contacto cuyo ContactID es igual a 1.</span><span class="sxs-lookup"><span data-stu-id="249dd-117">For example, this updategram changes the value in the Phone column of the Person.Contact table for the contact with ContactID of 1.</span></span> <span data-ttu-id="249dd-118">El **\<before>** bloque especifica el atributo **Phone** para asegurarse de que este valor de atributo coincide con el valor de la columna correspondiente en la base de datos antes de aplicar el valor actualizado.</span><span class="sxs-lookup"><span data-stu-id="249dd-118">The **\<before>** block specifies the **Phone** attribute to ensure that this attribute value matches the value in the corresponding column in the database before applying the updated value.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" Phone="398-555-0132" />  
</updg:before>  
<updg:after>  
   <Person.Contact ContactID="1" Phone="111-111-1111" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="high-level-of-protection"></a><span data-ttu-id="249dd-119">Nivel de protección alto</span><span class="sxs-lookup"><span data-stu-id="249dd-119">High Level of Protection</span></span>  
 <span data-ttu-id="249dd-120">Un nivel de protección alto se asegura de que el registro sigue siendo el mismo desde que la aplicación lo leyó por última vez (es decir, desde que la aplicación leyó el registro, ninguna otra transacción lo ha modificado).</span><span class="sxs-lookup"><span data-stu-id="249dd-120">A high level of protection ensures that the record remains the same since your application last read that record (that is, since your application has read the record, it has not been changed by any other transaction).</span></span>  
  
 <span data-ttu-id="249dd-121">Existen dos formas de obtener este nivel de protección alto en las actualizaciones simultáneas:</span><span class="sxs-lookup"><span data-stu-id="249dd-121">There are two ways you can get this high level of protection against concurrent updates:</span></span>  
  
-   <span data-ttu-id="249dd-122">Especifique columnas adicionales en la tabla en el **\<before>** bloque.</span><span class="sxs-lookup"><span data-stu-id="249dd-122">Specify additional columns in the table in the **\<before>** block.</span></span>  
  
     <span data-ttu-id="249dd-123">Si especifica columnas adicionales en el **\<before>** bloque, diagrama compara los valores especificados para estas columnas con los valores que estaban en la base de datos antes de aplicar la actualización.</span><span class="sxs-lookup"><span data-stu-id="249dd-123">If you specify additional columns in the **\<before>** block, the updategram compares the values that are specified for these columns with the values that were in the database before applying the update.</span></span> <span data-ttu-id="249dd-124">Si alguna de las columnas del registro ha cambiado desde que la transacción leyó el registro, el diagrama de actualización no realizará la actualización.</span><span class="sxs-lookup"><span data-stu-id="249dd-124">If any of the record columns has changed since your transaction read the record, the updategram does not perform the update.</span></span>  
  
     <span data-ttu-id="249dd-125">Por ejemplo, el siguiente diagrama actualiza el nombre de desplazamiento, pero especifica columnas adicionales (StartTime, EndTime) en el **\<before>** bloque, lo que solicita un mayor nivel de protección frente a las actualizaciones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="249dd-125">For example, the following updategram updates the shift name, but specifies additional columns (StartTime,EndTime) in the **\<before>** block, thereby requesting a higher level of protection against concurrent updates.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="1"   
                 Name="Day"   
                 StartTime="1900-01-01 07:00:00.000"   
                 EndTime="1900-01-01 15:00:00.000" />  
    </updg:before>  
    <updg:after>  
       <HumanResources.Shift Name="Morning" />  
    </updg:after>  
    </updg:sync>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="249dd-126">Este ejemplo especifica el nivel de protección más alto especificando todos los valores de columna del registro en el **\<before>** bloque.</span><span class="sxs-lookup"><span data-stu-id="249dd-126">This example specifies the highest level of protection by specifying all column values for the record in the **\<before>** block.</span></span>  
  
-   <span data-ttu-id="249dd-127">Especifique la columna de marca de tiempo (si está disponible) en el **\<before>** bloque.</span><span class="sxs-lookup"><span data-stu-id="249dd-127">Specify the timestamp column (if available) in the **\<before>** block.</span></span>  
  
     <span data-ttu-id="249dd-128">En lugar de especificar todas las columnas de registro del `<before` bloque>, puede especificar simplemente la columna de marca de tiempo (si la tabla tiene una) junto con las columnas de clave principal en el **\<before>** bloque.</span><span class="sxs-lookup"><span data-stu-id="249dd-128">Instead of specifying all the record columns in the `<before`> block, you can just specify the timestamp column (if the table has one) along with the primary key column(s) in the **\<before>** block.</span></span> <span data-ttu-id="249dd-129">La base de datos actualizará la columna de marca de tiempo a un valor único tras cada actualización del registro.</span><span class="sxs-lookup"><span data-stu-id="249dd-129">The database updates the timestamp column to a unique value after each update of the record.</span></span> <span data-ttu-id="249dd-130">En este caso, el diagrama de actualización compara el valor de la marca de tiempo con el valor correspondiente de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="249dd-130">In this case, the updategram compares the value of the timestamp with the corresponding value in the database.</span></span> <span data-ttu-id="249dd-131">El valor de marca de tiempo almacenado en la base de datos es un valor binario.</span><span class="sxs-lookup"><span data-stu-id="249dd-131">The timestamp value stored in the database is a binary value.</span></span> <span data-ttu-id="249dd-132">Por lo tanto, la columna de marca de tiempo debe especificarse en el esquema como `dt:type="bin.hex"`, `dt:type="bin.base64"` o `sql:datatype="timestamp"`.</span><span class="sxs-lookup"><span data-stu-id="249dd-132">Therefore, the timestamp column must be specified in the schema as `dt:type="bin.hex"`, `dt:type="bin.base64"`, or `sql:datatype="timestamp"`.</span></span> <span data-ttu-id="249dd-133">(Puede especificar el tipo de `xml` datos o el tipo de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] datos).</span><span class="sxs-lookup"><span data-stu-id="249dd-133">(You can specify either the `xml` data type or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type.)</span></span>  
  
#### <a name="to-test-the-updategram"></a><span data-ttu-id="249dd-134">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="249dd-134">To test the updategram</span></span>  
  
1.  <span data-ttu-id="249dd-135">Cree esta tabla en la base de datos **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="249dd-135">Create this table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Customer (  
                 CustomerID  varchar(5),  
                 ContactName varchar(20),  
                 LastUpdated timestamp)  
    ```  
  
2.  <span data-ttu-id="249dd-136">Agregue este registro de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="249dd-136">Add this sample record:</span></span>  
  
    ```  
    INSERT INTO Customer (CustomerID, ContactName) VALUES   
                         ('C1', 'Andrew Fuller')  
    ```  
  
3.  <span data-ttu-id="249dd-137">Copie el siguiente esquema XSD y péguelo en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="249dd-137">Copy the following XSD schema and paste it into Notepad.</span></span> <span data-ttu-id="249dd-138">Guárdelo como ConcurrencySampleSchema.xml:</span><span class="sxs-lookup"><span data-stu-id="249dd-138">Save it as ConcurrencySampleSchema.xml:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="Customer" sql:relation="Customer" >  
       <xsd:complexType>  
            <xsd:attribute name="CustomerID"    
                           sql:field="CustomerID"   
                           type="xsd:string" />   
  
            <xsd:attribute name="ContactName"    
                           sql:field="ContactName"   
                           type="xsd:string" />  
  
            <xsd:attribute name="LastUpdated"   
                           sql:field="LastUpdated"   
                           type="xsd:hexBinary"   
                 sql:datatype="timestamp" />  
  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
4.  <span data-ttu-id="249dd-139">Copie el código del diagrama de actualización siguiente en Bloc de notas y guárdelo como ConcurrencySampleTemplate.xml en el mismo directorio donde guardó el esquema creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="249dd-139">Copy the following updategram code into Notepad and save it as ConcurrencySampleTemplate.xml in the same directory where you saved the schema created in the previous step.</span></span> <span data-ttu-id="249dd-140">(Tenga en cuenta que el siguiente valor de marca de tiempo de LastUpdated variará con respecto a su tabla Customer de ejemplo, de modo que debe copiar el valor real de LastUpdated de la tabla y pegarlo en el diagrama de actualización.)</span><span class="sxs-lookup"><span data-stu-id="249dd-140">(Note the timestamp value below for LastUpdated will differ in your example Customer table, so copy the actual value for LastUpdated from the table and paste it into the updategram.)</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync mapping-schema="SampleSchema.xml" >  
    <updg:before>  
       <Customer CustomerID="C1"   
                 LastUpdated = "0x00000000000007D1" />  
    </updg:before>  
    <updg:after>  
       <Customer ContactName="Robert King" />  
    </updg:after>  
    </updg:sync>  
    </ROOT>  
    ```  
  
5.  <span data-ttu-id="249dd-141">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="249dd-141">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="249dd-142">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="249dd-142">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="249dd-143">Éste es el esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="249dd-143">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<ElementType name="Customer" sql:relation="Customer" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="ContactName" />  
    <AttributeType name="LastUpdated"  dt:type="bin.hex"   
                                       sql:datatype="timestamp" />  
    <attribute type="CustomerID" />  
    <attribute type="ContactName" />  
    <attribute type="LastUpdated" />  
</ElementType>  
</Schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="249dd-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="249dd-144">See Also</span></span>  
 [<span data-ttu-id="249dd-145">Consideraciones de seguridad de diagrama &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="249dd-145">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
