---
title: Eliminar datos mediante diagramas XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- <after> block
- updategrams [SQLXML], deleting data
- <before> block
- mapping-schema attribute
- record deletions [SQLXML]
ms.assetid: 4fb116d7-7652-474a-a567-cb475a20765c
author: rothja
ms.author: jroth
ms.openlocfilehash: d941005c71dc33dd8c4f5c5cc15f645cd0e68177
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675765"
---
# <a name="deleting-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="aaa9d-102">Eliminar datos con diagramas de actualización XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="aaa9d-102">Deleting Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="aaa9d-103">Un diagrama indica una operación de eliminación cuando una instancia de registro aparece en el **\<before>** bloque sin registros correspondientes en el **\<after>** bloque.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-103">An updategram indicates a delete operation when a record instance appears in the **\<before>** block with no corresponding records in the **\<after>** block.</span></span> <span data-ttu-id="aaa9d-104">En este caso, el diagrama elimina el registro del **\<before>** bloque de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-104">In this case, the updategram deletes the record in the **\<before>** block from the database.</span></span>  
  
 <span data-ttu-id="aaa9d-105">Éste es el formato del diagrama de actualización para una operación de eliminación:</span><span class="sxs-lookup"><span data-stu-id="aaa9d-105">This is the updategram format for a delete operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema="SampleSchema.xml"]  >  
   <updg:before>  
       <ElementName />  
      [<ElementName .../>... ]  
   </updg:before>  
    [<updg:after>  
    </updg:after>]  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="aaa9d-106">Puede omitir la **\<after>** etiqueta si diagrama está realizando solo una operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-106">You can omit the **\<after>** tag if the updategram is performing only a delete operation.</span></span> <span data-ttu-id="aaa9d-107">Si no especifica el `mapping-schema` atributo opcional, el **\<ElementName>** especificado en diagrama se asigna a una tabla de base de datos y los elementos secundarios o atributos se asignan a las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-107">If you do not specify the optional `mapping-schema` attribute, the **\<ElementName>** specified in the updategram maps to a database table and the child elements or attributes map to columns in the table.</span></span>  
  
 <span data-ttu-id="aaa9d-108">Si un elemento especificado en diagrama coincide con más de una fila de la tabla o no coincide con ninguna fila, diagrama devuelve un error y cancela el **\<sync>** bloque completo.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-108">If an element specified in the updategram either matches more than one row in the table or does not match any row, the updategram returns an error and cancels the entire **\<sync>** block.</span></span> <span data-ttu-id="aaa9d-109">Un elemento del diagrama de actualización solamente puede eliminar un registro a la vez.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-109">Only one record at a time can be deleted by an element in the updategram.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="aaa9d-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="aaa9d-110">Examples</span></span>  
 <span data-ttu-id="aaa9d-111">Los ejemplos de esta sección utilizan una asignación predeterminada (es decir, no se especifica ningún esquema de asignación en el diagrama de actualización).</span><span class="sxs-lookup"><span data-stu-id="aaa9d-111">Examples in this section use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="aaa9d-112">Para obtener más ejemplos de diagramas que usan esquemas de asignación, vea [especificar un esquema de asignación anotado en un diagrama &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="aaa9d-112">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="aaa9d-113">Para crear ejemplos funcionales mediante los ejemplos siguientes, debe cumplir los requisitos especificados en [requisitos para ejecutar ejemplos de SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="aaa9d-113">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-deleting-a-record-by-using-an-updategram"></a><span data-ttu-id="aaa9d-114">A.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-114">A.</span></span> <span data-ttu-id="aaa9d-115">Eliminar un registro mediante un diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="aaa9d-115">Deleting a record by using an updategram</span></span>  
 <span data-ttu-id="aaa9d-116">Los siguientes diagramas de actualización eliminan dos registros de la tabla HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-116">The following updategrams deletes two records from the HumanResources.Shift table.</span></span>  
  
 <span data-ttu-id="aaa9d-117">En estos ejemplos, el diagrama de actualización no especifica ningún esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-117">In these examples, the updategram does not specify a mapping schema.</span></span> <span data-ttu-id="aaa9d-118">Por tanto, el diagrama de actualización utiliza la asignación predeterminada, en la que el nombre de elemento se asigna a un nombre de tabla y los atributos o subelementos se asignan a columnas.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-118">Therefore, the updategram uses default mapping, in which the element name maps to table name and the attributes or subelements map to columns.</span></span>  
  
 <span data-ttu-id="aaa9d-119">Esta primera diagrama está centrada en atributos e identifica dos turnos (día y noche) en el **\<before>** bloque.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-119">This first updategram is attribute-centric and identifies two shifts (Day-Evening and Evening-Night) in the **\<before>** block.</span></span> <span data-ttu-id="aaa9d-120">Dado que no hay ningún registro correspondiente en el **\<after>** bloque, se trata de una operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-120">Because there is no corresponding record in the **\<after>** block, this is a delete operation.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
       <HumanResources.Shift ShiftID="4"  
                        Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift ShiftID="5"  
                        Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
  </updg:before>  
  <updg:after>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="aaa9d-121">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="aaa9d-121">To test the updategram</span></span>  
  
1.  <span data-ttu-id="aaa9d-122">Complete el ejemplo B ("insertar varios registros mediante un diagrama") en la [inserción de datos mediante XML diagramas &#40;SQLXML 4,0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="aaa9d-122">Complete example B ("Inserting multiple records by using an updategram") in [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
2.  <span data-ttu-id="aaa9d-123">Copie el diagrama anterior en el Bloc de notas y guárdelo como Updategram-RemoveShifts.xml en la misma carpeta que se usó para completar ("insertar varios registros mediante un diagrama") en la [inserción de datos con XML diagramas &#40;SQLXML 4,0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="aaa9d-123">Copy the updategram above to Notepad and save it as Updategram-RemoveShifts.xml in the same folder as was used to complete ("Inserting multiple records by using an updategram") in [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
3.  <span data-ttu-id="aaa9d-124">Cree y use el script de prueba de SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar el diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="aaa9d-124">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="aaa9d-125">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="aaa9d-125">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa9d-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aaa9d-126">See Also</span></span>  
 [<span data-ttu-id="aaa9d-127">Consideraciones de seguridad de diagrama &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="aaa9d-127">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
