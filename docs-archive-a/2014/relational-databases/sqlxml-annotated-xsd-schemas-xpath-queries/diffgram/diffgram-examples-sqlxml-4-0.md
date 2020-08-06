---
title: Ejemplos de DiffGram (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], examples
- examples [SQLXML], DiffGram
- diffgr:parentID
- parentID annotation
ms.assetid: fc148583-dfd3-4efb-a413-f47b150b0975
author: rothja
ms.author: jroth
ms.openlocfilehash: 04fb355af01f9853149a84af72471375d9135468
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673595"
---
# <a name="diffgram-examples-sqlxml-40"></a><span data-ttu-id="883bf-102">Ejemplos de DiffGram (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="883bf-102">DiffGram Examples (SQLXML 4.0)</span></span>
  <span data-ttu-id="883bf-103">Los ejemplos de este tema incluyen de una serie de DiffGram que realizan operaciones de inserción, actualización y eliminación en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="883bf-103">The examples in this topic consist of DiffGrams that perform insert, update, and delete operations to the database.</span></span> <span data-ttu-id="883bf-104">Antes de usar los ejemplos, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="883bf-104">Before using the examples, note the following:</span></span>  
  
-   <span data-ttu-id="883bf-105">Los ejemplos usan dos tablas (Cust y Ord) que deberá crear si desea probar los ejemplos de DiffGram:</span><span class="sxs-lookup"><span data-stu-id="883bf-105">The examples use two tables (Cust and Ord) that must be created if you want to test the DiffGram examples:</span></span>  
  
    ```  
    Cust(CustomerID, CompanyName, ContactName)  
    Ord(OrderID, CustomerID)  
    ```  
  
-   <span data-ttu-id="883bf-106">La mayoría de los ejemplos de este tema usan el siguiente esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="883bf-106">Most of the examples in this topic use the following XSD Schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
    <xsd:annotation>  
      <xsd:documentation>  
        Diffgram Customers/Orders Schema.  
      </xsd:documentation>  
      <xsd:appinfo>  
           <sql:relationship name="CustomersOrders"   
                      parent="Cust"  
                      parent-key="CustomerID"  
                      child-key="CustomerID"  
                      child="Ord"/>  
      </xsd:appinfo>  
    </xsd:annotation>  
  
    <xsd:element name="Customer" sql:relation="Cust">  
      <xsd:complexType>  
        <xsd:sequence>  
          <xsd:element name="CompanyName"    type="xsd:string"/>  
          <xsd:element name="ContactName"    type="xsd:string"/>  
           <xsd:element name="Order" sql:relation="Ord" sql:relationship="CustomersOrders">  
            <xsd:complexType>  
              <xsd:attribute name="OrderID" type="xsd:int" sql:field="OrderID"/>  
              <xsd:attribute name="CustomerID" type="xsd:string"/>  
            </xsd:complexType>  
          </xsd:element>  
        </xsd:sequence>  
        <xsd:attribute name="CustomerID" type="xsd:string" sql:field="CustomerID"/>  
      </xsd:complexType>  
    </xsd:element>  
  
    </xsd:schema>     
    ```  
  
     <span data-ttu-id="883bf-107">Guarde este esquema como DiffGramSchema.xml en la misma carpeta donde haya guardado los demás archivos que se utilizan en los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="883bf-107">Save this schema as DiffGramSchema.xml in the same folder where you save other files used in the examples.</span></span>  
  
## <a name="a-deleting-a-record-by-using-a-diffgram"></a><span data-ttu-id="883bf-108">A.</span><span class="sxs-lookup"><span data-stu-id="883bf-108">A.</span></span> <span data-ttu-id="883bf-109">Eliminar un registro mediante un DiffGram</span><span class="sxs-lookup"><span data-stu-id="883bf-109">Deleting a record by using a DiffGram</span></span>  
 <span data-ttu-id="883bf-110">El DiffGram de este ejemplo elimina un registro de cliente (cuyo CustomerID es ALFKI) de la tabla Cust y elimina el registro de pedido correspondiente (cuyo OrderID es 1) de la tabla Ord.</span><span class="sxs-lookup"><span data-stu-id="883bf-110">The DiffGram in this example deletes a customer (whose CustomerID is ALFKI) record from the Cust table and deletes the corresponding order record (whose OrderID is 1) from the Ord table.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
           xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
           xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance/>  
  
    <diffgr:before>  
        <Order diffgr:id="Order1"   
               msdata:rowOrder="0"   
               CustomerID="ALFKI"   
               OrderID="1"/>  
        <Customer diffgr:id="Customer1"   
                  msdata:rowOrder="0"   
                  CustomerID="ALFKI">  
           <CompanyName>Alfreds Futterkiste</CompanyName>  
           <ContactName>Maria Anders</ContactName>  
        </Customer>  
    </diffgr:before>  
    <msdata:errors/>  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="883bf-111">En el **\<before>** bloque, hay un **\<Order>** elemento (**diffgr: ID = "Order1"**) y un **\<Customer>** elemento (**diffgr: ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="883bf-111">In the **\<before>** block, there is an **\<Order>** element (**diffgr:id="Order1"**) and a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="883bf-112">Estos elementos representan registros existentes en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="883bf-112">These elements represent existing records in the database.</span></span> <span data-ttu-id="883bf-113">El **\<DataInstance>** elemento no tiene los registros correspondientes (con el mismo **diffgr: ID**).</span><span class="sxs-lookup"><span data-stu-id="883bf-113">The **\<DataInstance>** element does not have the corresponding records (with the same **diffgr:id**).</span></span> <span data-ttu-id="883bf-114">Esto indica una operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="883bf-114">This indicates a delete operation.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="883bf-115">Para probar el DiffGram:</span><span class="sxs-lookup"><span data-stu-id="883bf-115">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="883bf-116">Cree estas tablas en la base de datos **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="883bf-116">Create these tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="883bf-117">Agregue estos datos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="883bf-117">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
3.  <span data-ttu-id="883bf-118">Copie el DiffGram anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="883bf-118">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="883bf-119">Guarde el archivo como MyDiffGram.xml en la misma carpeta utilizada en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="883bf-119">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="883bf-120">Copie el DiffGramSchema proporcionado anteriormente en este tema y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="883bf-120">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="883bf-121">Guarde el archivo como DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="883bf-121">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="883bf-122">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el DiffGram.</span><span class="sxs-lookup"><span data-stu-id="883bf-122">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="883bf-123">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="883bf-123">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="b-inserting-a-record-by-using-a-diffgram"></a><span data-ttu-id="883bf-124">B.</span><span class="sxs-lookup"><span data-stu-id="883bf-124">B.</span></span> <span data-ttu-id="883bf-125">Insertar un registro mediante un DiffGram</span><span class="sxs-lookup"><span data-stu-id="883bf-125">Inserting a record by using a DiffGram</span></span>  
 <span data-ttu-id="883bf-126">En este ejemplo, el DiffGram inserta un registro en la tabla Cust y otro registro en la tabla Ord.</span><span class="sxs-lookup"><span data-stu-id="883bf-126">In this example, the DiffGram inserts a record in the Cust table and a record in the Ord table.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"   
      sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
          xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
          xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
       <Customer diffgr:id="Customer1" msdata:rowOrder="0"    
                 diffgr:hasChanges="inserted" CustomerID="ALFKI">  
        <CompanyName>C3Company</CompanyName>  
        <ContactName>C3Contact</ContactName>  
        <Order diffgr:id="Order1"   
               msdata:rowOrder="0"  
               diffgr:hasChanges="inserted"   
               CustomerID="ALFKI" OrderID="1"/>  
      </Customer>  
    </DataInstance>  
  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="883bf-127">En este DiffGram **\<before>** , no se especifica el bloque (no se identificó ningún registro de base de datos existente).</span><span class="sxs-lookup"><span data-stu-id="883bf-127">In this DiffGram the **\<before>** block is not specified (no existing database records identified).</span></span> <span data-ttu-id="883bf-128">Hay dos instancias de registro (identificadas por **\<Customer>** los **\<Order>** elementos y del **\<DataInstance>** bloque) que se asignan a las tablas CUST y Ord, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="883bf-128">There are two record instances (identified by the **\<Customer>** and **\<Order>** elements in the **\<DataInstance>** block) that map to Cust and Ord tables, respectively.</span></span> <span data-ttu-id="883bf-129">Ambos elementos especifican el atributo **diffgr: hasChanges** (**hasChanges = "Inserted"**).</span><span class="sxs-lookup"><span data-stu-id="883bf-129">Both of these elements specify the **diffgr:hasChanges** attribute (**hasChanges="inserted"**).</span></span> <span data-ttu-id="883bf-130">Esto indica una operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="883bf-130">This indicates an insert operation.</span></span> <span data-ttu-id="883bf-131">En este DiffGram, si se especifica **hasChanges = "Modified"**, se indica que desea modificar un registro que no existe, lo que genera un error.</span><span class="sxs-lookup"><span data-stu-id="883bf-131">In this DiffGram, if you specify **hasChanges="modified"**, you are indicating that you want to modify a record that does not exist, which results in an error.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="883bf-132">Para probar el DiffGram:</span><span class="sxs-lookup"><span data-stu-id="883bf-132">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="883bf-133">Cree estas tablas en la base de datos **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="883bf-133">Create these tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="883bf-134">Agregue estos datos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="883bf-134">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
3.  <span data-ttu-id="883bf-135">Copie el DiffGram anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="883bf-135">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="883bf-136">Guarde el archivo como MyDiffGram.xml en la misma carpeta utilizada en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="883bf-136">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="883bf-137">Copie el DiffGramSchema proporcionado anteriormente en este tema y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="883bf-137">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="883bf-138">Guarde el archivo como DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="883bf-138">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="883bf-139">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el DiffGram.</span><span class="sxs-lookup"><span data-stu-id="883bf-139">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="883bf-140">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="883bf-140">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="c-updating-an-existing-record-by-using-a-diffgram"></a><span data-ttu-id="883bf-141">C.</span><span class="sxs-lookup"><span data-stu-id="883bf-141">C.</span></span> <span data-ttu-id="883bf-142">Actualizar un registro existente mediante un DiffGram</span><span class="sxs-lookup"><span data-stu-id="883bf-142">Updating an existing record by using a DiffGram</span></span>  
 <span data-ttu-id="883bf-143">En este ejemplo, el DiffGram actualiza la información del cliente ALFKI (CompanyName y ContactName).</span><span class="sxs-lookup"><span data-stu-id="883bf-143">In this example, the DiffGram updates customer information (CompanyName and ContactName) for customer ALFKI.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
           xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
           xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
      <Customer diffgr:id="Customer1"   
                msdata:rowOrder="0" diffgr:hasChanges="modified"   
                CustomerID="ALFKI">  
          <CompanyName>Bottom Dollar Markets</CompanyName>  
          <ContactName>Antonio Moreno</ContactName>  
      </Customer>  
    </DataInstance>  
  
    <diffgr:before>  
     <Customer diffgr:id="Customer1"   
               msdata:rowOrder="0"   
               CustomerID="ALFKI">  
        <CompanyName>Alfreds Futterkiste</CompanyName>  
        <ContactName>Maria Anders</ContactName>  
      </Customer>  
    </diffgr:before>  
  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="883bf-144">El **\<before>** bloque incluye un **\<Customer>** elemento (**diffgr: ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="883bf-144">The **\<before>** block includes a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="883bf-145">El **\<DataInstance>** bloque incluye el **\<Customer>** elemento correspondiente con el mismo **identificador**. El **\<customer>** elemento de **\<NewDataSet>** también especifica **diffgr: hasChanges = "Modified"**.</span><span class="sxs-lookup"><span data-stu-id="883bf-145">The **\<DataInstance>** block includes the corresponding **\<Customer>** element with same **id**. The **\<customer>** element in the **\<NewDataSet>** also specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="883bf-146">Esto indica una operación de actualización y el registro del cliente en la tabla **Cust** se actualiza en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="883bf-146">This indicates an update operation, and the customer record in the **Cust** table is updated accordingly.</span></span> <span data-ttu-id="883bf-147">Tenga en cuenta que si no se especifica el atributo **diffgr: hasChanges** , la lógica de procesamiento de DiffGram omite este elemento y no se realiza ninguna actualización.</span><span class="sxs-lookup"><span data-stu-id="883bf-147">Note that if the **diffgr:hasChanges** attribute is not specified, the DiffGram processing logic ignores this element and no updates are performed.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="883bf-148">Para probar el DiffGram:</span><span class="sxs-lookup"><span data-stu-id="883bf-148">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="883bf-149">Cree estas tablas en la base de datos **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="883bf-149">Create these tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="883bf-150">Agregue estos datos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="883bf-150">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
3.  <span data-ttu-id="883bf-151">Copie el DiffGram anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="883bf-151">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="883bf-152">Guarde el archivo como MyDiffGram.xml en la misma carpeta utilizada en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="883bf-152">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="883bf-153">Copie el DiffGramSchema proporcionado anteriormente en este tema y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="883bf-153">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="883bf-154">Guarde el archivo como DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="883bf-154">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="883bf-155">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el DiffGram.</span><span class="sxs-lookup"><span data-stu-id="883bf-155">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="883bf-156">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="883bf-156">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="d-inserting-updating-and-deleting-records-by-using-a-diffgram"></a><span data-ttu-id="883bf-157">D.</span><span class="sxs-lookup"><span data-stu-id="883bf-157">D.</span></span> <span data-ttu-id="883bf-158">Insertar, actualizar y eliminar registros mediante un DiffGram</span><span class="sxs-lookup"><span data-stu-id="883bf-158">Inserting, updating, and deleting records by using a DiffGram</span></span>  
 <span data-ttu-id="883bf-159">En este ejemplo, se usa un DiffGram relativamente complejo para realizar operaciones de inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="883bf-159">In this example, a relatively complex DiffGram is used to perform insert, update, and delete operations.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
      <Customer diffgr:id="Customer2" msdata:rowOrder="1"   
                diffgr:hasChanges="modified"   
                CustomerID="ANATR">  
          <CompanyName>Bottom Dollar Markets</CompanyName>  
          <ContactName>Elizabeth Lincoln</ContactName>  
          <Order diffgr:id="Order2" msdata:rowOrder="1"   
               msdata:hiddenCustomerID="ANATR"   
               CustomerID="ANATR" OrderID="2"/>  
      </Customer>  
  
      <Customer diffgr:id="Customer3" msdata:rowOrder="2"   
                CustomerID="ANTON">  
         <CompanyName>Chop-suey Chinese</CompanyName>  
         <ContactName>Yang Wang</ContactName>  
         <Order diffgr:id="Order3" msdata:rowOrder="2"   
               msdata:hiddenCustomerID="ANTON"   
               CustomerID="ANTON" OrderID="3"/>  
      </Customer>  
      <Customer diffgr:id="Customer4" msdata:rowOrder="3"   
                diffgr:hasChanges="inserted"   
                CustomerID="AROUT">  
         <CompanyName>Around the Horn</CompanyName>  
         <ContactName>Thomas Hardy</ContactName>  
         <Order diffgr:id="Order4" msdata:rowOrder="3"   
                diffgr:hasChanges="inserted"   
                msdata:hiddenCustomerID="AROUT"   
               CustomerID="AROUT" OrderID="4"/>  
      </Customer>  
    </DataInstance>  
    <diffgr:before>  
      <Order diffgr:id="Order1" msdata:rowOrder="0"   
             msdata:hiddenCustomerID="ALFKI"   
             CustomerID="ALFKI" OrderID="1"/>  
      <Customer diffgr:id="Customer1" msdata:rowOrder="0"   
                CustomerID="ALFKI">  
        <CompanyName>Alfreds Futterkiste</CompanyName>  
        <ContactName>Maria Anders</ContactName>  
      </Customer>  
      <Customer diffgr:id="Customer2" msdata:rowOrder="1"   
                CustomerID="ANATR">  
        <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
        <ContactName>Ana Trujillo</ContactName>  
      </Customer>  
    </diffgr:before>  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="883bf-160">La lógica de DiffGram procesa este DiffGram del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="883bf-160">The DiffGram logic processes this DiffGram as follows:</span></span>  
  
-   <span data-ttu-id="883bf-161">De acuerdo con la lógica de procesamiento de DiffGram, todos los elementos de nivel superior del **\<before>** bloque se asignan a las tablas correspondientes, tal y como se describe en el esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="883bf-161">In accordance with DiffGram processing logic, all the top-level elements in the **\<before>** block map to corresponding tables, as described in the mapping schema.</span></span>  
  
-   <span data-ttu-id="883bf-162">El **\<before>** bloque tiene un **\<Order>** elemento (**dffgr: ID = "Order1"**) y un **\<Customer>** elemento (**diffgr: ID = "Customer1"**) para los que no hay ningún elemento correspondiente en el **\<DataInstance>** bloque (con el mismo identificador).</span><span class="sxs-lookup"><span data-stu-id="883bf-162">The **\<before>** block has an **\<Order>** element (**dffgr:id="Order1"**) and a **\<Customer>** element (**diffgr:id="Customer1"**) for which there is no corresponding element in the **\<DataInstance>** block (with the same ID).</span></span> <span data-ttu-id="883bf-163">Esto indica una operación de eliminación y los registros se eliminan de las tablas Cust y Ord.</span><span class="sxs-lookup"><span data-stu-id="883bf-163">This indicates a delete operation, and the records are deleted from the Cust and Ord tables.</span></span>  
  
-   <span data-ttu-id="883bf-164">El **\<before>** bloque tiene un **\<Customer>** elemento (**diffgr: ID = "Customer2"**) para el que hay un **\<Customer>** elemento correspondiente en el **\<DataInstance>** bloque (con el mismo identificador).</span><span class="sxs-lookup"><span data-stu-id="883bf-164">The **\<before>** block has a **\<Customer>** element (**diffgr:id="Customer2"**) for which there is a corresponding **\<Customer>** element in the **\<DataInstance>** block (with the same ID).</span></span> <span data-ttu-id="883bf-165">El elemento del **\<DataInstance>** bloque especifica **diffgr: hasChanges = "Modified"**.</span><span class="sxs-lookup"><span data-stu-id="883bf-165">The element in the **\<DataInstance>** block specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="883bf-166">Se trata de una operación de actualización en la que para Customer ANATR, la información de CompanyName y ContactName se actualiza en la tabla Cust con los valores que se especifican en el **\<DataInstance>** bloque.</span><span class="sxs-lookup"><span data-stu-id="883bf-166">This is an update operation in which for customer ANATR, the CompanyName and ContactName information is updated in the Cust table using values that are specified in the **\<DataInstance>** block.</span></span>  
  
-   <span data-ttu-id="883bf-167">El **\<DataInstance>** bloque tiene un **\<Customer>** elemento (**diffgr: ID = "Customer3"**) y un **\<Order>** elemento (**diffgr: ID = "Order3"**).</span><span class="sxs-lookup"><span data-stu-id="883bf-167">The **\<DataInstance>** block has a **\<Customer>** element (**diffgr:id="Customer3"**) and an **\<Order>** element (**diffgr:id="Order3"**).</span></span> <span data-ttu-id="883bf-168">Ninguno de estos elementos especifica el atributo **diffgr: hasChanges** .</span><span class="sxs-lookup"><span data-stu-id="883bf-168">Neither of these elements specify the **diffgr:hasChanges** attribute.</span></span> <span data-ttu-id="883bf-169">Por lo tanto, la lógica de procesamiento de DiffGram omite estos elementos.</span><span class="sxs-lookup"><span data-stu-id="883bf-169">Therefore, the DiffGram processing logic ignores these elements.</span></span>  
  
-   <span data-ttu-id="883bf-170">El **\<DataInstance>** bloque tiene un **\<Customer>** elemento (**diffgr: ID = "Customer4"**) y un **\<Order>** elemento (**diffgr: ID = "Order4"**) para los que no hay elementos correspondientes en el \<before> bloque.</span><span class="sxs-lookup"><span data-stu-id="883bf-170">The **\<DataInstance>** block has a **\<Customer>** element (**diffgr:id="Customer4"**) and an **\<Order>** element (**diffgr:id="Order4"**) for which there are no corresponding elements in the \<before> block.</span></span> <span data-ttu-id="883bf-171">Estos elementos del **\<DataInstance>** bloque especifican **diffgr: hasChanges = "Inserted"**.</span><span class="sxs-lookup"><span data-stu-id="883bf-171">These elements in the **\<DataInstance>** block specify **diffgr:hasChanges="inserted"**.</span></span> <span data-ttu-id="883bf-172">Por lo tanto, se agrega un nuevo registro a la tabla Cust y a la tabla Ord.</span><span class="sxs-lookup"><span data-stu-id="883bf-172">Therefore, a new record is added in the Cust table and in the Ord table.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="883bf-173">Para probar el DiffGram:</span><span class="sxs-lookup"><span data-stu-id="883bf-173">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="883bf-174">Cree las tablas siguientes en la base de datos **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="883bf-174">Create the following tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="883bf-175">Agregue estos datos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="883bf-175">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
3.  <span data-ttu-id="883bf-176">Copie el DiffGram anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="883bf-176">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="883bf-177">Guarde el archivo como MyDiffGram.xml en la misma carpeta utilizada en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="883bf-177">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="883bf-178">Copie el DiffGramSchema proporcionado anteriormente en este tema y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="883bf-178">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="883bf-179">Guarde el archivo como DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="883bf-179">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="883bf-180">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el DiffGram.</span><span class="sxs-lookup"><span data-stu-id="883bf-180">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="883bf-181">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="883bf-181">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="e-applying-updates-by-using-a-diffgram-with-the-diffgrparentid-annotation"></a><span data-ttu-id="883bf-182">E.</span><span class="sxs-lookup"><span data-stu-id="883bf-182">E.</span></span> <span data-ttu-id="883bf-183">Aplicar actualizaciones mediante un DiffGram con la anotación diffgr:parentID</span><span class="sxs-lookup"><span data-stu-id="883bf-183">Applying updates by using a DiffGram with the diffgr:parentID annotation</span></span>  
 <span data-ttu-id="883bf-184">En este ejemplo se muestra cómo se utiliza la anotación **parentId** que se especifica en el **\<before>** bloque del DiffGram para aplicar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="883bf-184">This example illustrates how the **parentID** annotation that is specified in the **\<before>** block of the DiffGram is used in applying the updates.</span></span>  
  
```  
<NewDataSet />  
<diffgr:before>  
   <Order diffgr:id="Order1" msdata:rowOrder="0" OrderID="2" />  
   <Order diffgr:id="Order3" msdata:rowOrder="2" OrderID="4" />  
  
   <OrderDetail diffgr:id="OrderDetail1"   
                diffgr:parentId="Order1"   
                msdata:rowOrder="0"   
                ProductID="13"   
                OrderID="2" />  
   <OrderDetail diffgr:id="OrderDetail3"   
                diffgr:parentId="Order3"  
                ProductID="77"  
                OrderID="4"/>  
</diffgr:before>  
</diffgr:diffgram>  
```  
  
 <span data-ttu-id="883bf-185">Este DiffGram especifica una operación de eliminación porque solo hay un **\<before>** bloque.</span><span class="sxs-lookup"><span data-stu-id="883bf-185">This DiffGram specifies a delete operation because there is only a **\<before>** block.</span></span> <span data-ttu-id="883bf-186">En el DiffGram, la anotación **parentId** se usa para especificar una relación de elementos primarios y secundarios entre los pedidos y los detalles del pedido.</span><span class="sxs-lookup"><span data-stu-id="883bf-186">In the DiffGram, the **parentID** annotation is used to specify a parent-child relationship between the orders and order details.</span></span> <span data-ttu-id="883bf-187">Cuando SQLXML elimina los registros, elimina los registros de la tabla secundaria que se identifica mediante esta relación y, a continuación, elimina los registros de la tabla primaria correspondiente.</span><span class="sxs-lookup"><span data-stu-id="883bf-187">When SQLXML deletes the records, it deletes records from the child table that is identified by this relationship and then deletes the records from the corresponding parent table.</span></span>  
  
  
