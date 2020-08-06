---
title: Pasar parámetros a diagramas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nullvalue attribute
- passing parameters [SQLXML]
- parameters [SQLXML]
- updategrams [SQLXML], passing parameters
- null values [SQLXML]
ms.assetid: 2354e6e7-1860-471f-8711-4e374c5a4ed2
author: rothja
ms.author: jroth
ms.openlocfilehash: 4bc29de2dab3d0bc3587cb21b7005c0c23dcf7c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674735"
---
# <a name="passing-parameters-to-updategrams-sqlxml-40"></a><span data-ttu-id="5ad92-102">Pasar parámetros a diagramas de actualización (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="5ad92-102">Passing Parameters to Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="5ad92-103">Los diagramas de actualización son plantillas; por consiguiente, se les pueden pasar parámetros.</span><span class="sxs-lookup"><span data-stu-id="5ad92-103">Updategrams are templates; therefore, you can pass them parameters.</span></span> <span data-ttu-id="5ad92-104">Para obtener más información sobre cómo pasar parámetros a plantillas, vea [consideraciones de seguridad de diagrama &#40;SQLXML 4,0&#41;](../security/updategram-security-considerations-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5ad92-104">For more information about passing parameters to templates, see [Updategram Security Considerations &#40;SQLXML 4.0&#41;](../security/updategram-security-considerations-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="5ad92-105">Los diagramas de actualización le permiten pasar NULL como un valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="5ad92-105">Updategrams allow you to pass NULL as a parameter value.</span></span> <span data-ttu-id="5ad92-106">Para pasar el valor del parámetro NULL, especifique el atributo `nullvalue`.</span><span class="sxs-lookup"><span data-stu-id="5ad92-106">To pass the NULL parameter value, you specify the `nullvalue` attribute.</span></span> <span data-ttu-id="5ad92-107">A continuación, el valor que se asigna al atributo `nullvalue` se proporciona como el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="5ad92-107">The value that is assigned to the `nullvalue` attribute is then provided as the parameter value.</span></span> <span data-ttu-id="5ad92-108">Los diagramas de actualización tratan este valor como NULL.</span><span class="sxs-lookup"><span data-stu-id="5ad92-108">Updategrams treat this value as NULL.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ad92-109">En `<sql:header>` y `<updg:header>`, debería especificar `nullvalue` como no calificado; mientras que en `<updg:sync>`, debe especificar `nullvalue` como completo (por ejemplo, `updg:nullvalue`).</span><span class="sxs-lookup"><span data-stu-id="5ad92-109">In `<sql:header>` and `<updg:header>`, you should specify the `nullvalue` as unqualified; whereas, in `<updg:sync>`, you specify the `nullvalue` as qualified (for example, `updg:nullvalue`).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5ad92-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5ad92-110">Examples</span></span>  
 <span data-ttu-id="5ad92-111">Para crear ejemplos funcionales mediante los ejemplos siguientes, debe cumplir los requisitos especificados en [requisitos para ejecutar ejemplos de SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="5ad92-111">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
 <span data-ttu-id="5ad92-112">Antes de usar los ejemplos del diagrama de actualización, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ad92-112">Before using the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="5ad92-113">En los ejemplos se usa una asignación predeterminada (es decir, ningún esquema de asignación se especifica en el diagrama de actualización).</span><span class="sxs-lookup"><span data-stu-id="5ad92-113">The examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="5ad92-114">Para obtener más ejemplos de diagramas que usan esquemas de asignación, vea [especificar un esquema de asignación anotado en un diagrama &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5ad92-114">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
### <a name="a-passing-parameters-to-an-updategram"></a><span data-ttu-id="5ad92-115">A.</span><span class="sxs-lookup"><span data-stu-id="5ad92-115">A.</span></span> <span data-ttu-id="5ad92-116">Pasar parámetros a un diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="5ad92-116">Passing parameters to an updategram</span></span>  
 <span data-ttu-id="5ad92-117">En este ejemplo, el diagrama de actualización cambia el apellido de un empleado en la tabla HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="5ad92-117">In this example, the updategram changes the last name of an employee in the HumanResources.Shift table.</span></span> <span data-ttu-id="5ad92-118">Se pasan dos parámetros al diagrama de actualización: ShiftID, que se usa para identificar de manera única un cambio, y Nombre.</span><span class="sxs-lookup"><span data-stu-id="5ad92-118">The updategram is passed two parameters: ShiftID, which is used to uniquely identify a shift, and Name.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header>  
  <updg:param name="ShiftID"/>  
  <updg:param name="Name" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="$ShiftID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="$Name" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="5ad92-119">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="5ad92-119">To test the updategram</span></span>  
  
1.  <span data-ttu-id="5ad92-120">Copie el diagrama de actualización anterior en el Bloc de notas y guárdelo en un archivo como UpdategramWithParameters.xml.</span><span class="sxs-lookup"><span data-stu-id="5ad92-120">Copy the updategram above into Notepad and save it to file as UpdategramWithParameters.xml.</span></span>  
  
2.  <span data-ttu-id="5ad92-121">Prepare el script SQLXML 4,0 test (Sqlxml4test. vbs) en [usar ado para ejecutar consultas sqlxml 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) para ejecutar el diagrama agregando las siguientes líneas después de `cmd.Properties("Output Stream").Value = outStream` :</span><span class="sxs-lookup"><span data-stu-id="5ad92-121">Prepare the SQLXML 4.0 test script (Sqlxml4test.vbs) in [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) to execute the updategram by adding the following lines after the `cmd.Properties("Output Stream").Value = outStream`:</span></span>  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value  
    cmd.Parameters.Append cmd.CreateParameter("@ShiftID",  2, 1,  0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@Name",   200, 1, 50, "New Name")  
    ```  
  
### <a name="b-passing-null-as-a-parameter-value-to-an-updategram"></a><span data-ttu-id="5ad92-122">B.</span><span class="sxs-lookup"><span data-stu-id="5ad92-122">B.</span></span> <span data-ttu-id="5ad92-123">Pasar NULL como un valor del parámetro a un diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="5ad92-123">Passing NULL as a parameter value to an updategram</span></span>  
 <span data-ttu-id="5ad92-124">Para ejecutar un diagrama de actualización, el valor "isnull" se asigna al parámetro que se desea establecer en NULL.</span><span class="sxs-lookup"><span data-stu-id="5ad92-124">In executing an updategram, the "isnull" value is assigned to the parameter that you want to set to NULL.</span></span> <span data-ttu-id="5ad92-125">El diagrama de actualización convierte el valor del parámetro "isnulll" en NULL y lo procesa de forma apropiada.</span><span class="sxs-lookup"><span data-stu-id="5ad92-125">Updategram converts the "isnulll" parameter value to NULL and processes it accordingly.</span></span>  
  
 <span data-ttu-id="5ad92-126">El diagrama de actualización siguiente establece un puesto de empleado en NULL:</span><span class="sxs-lookup"><span data-stu-id="5ad92-126">The following updategram sets an employee title to NULL:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:header nullvalue="isnull" >  
  <updg:param name="EmployeeID"/>  
  <updg:param name="ManagerID" />  
</updg:header>  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Employee EmployeeID="$EmployeeID" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Employee ManagerID="$ManagerID" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="5ad92-127">Para probar el diagrama de actualización</span><span class="sxs-lookup"><span data-stu-id="5ad92-127">To test the updategram</span></span>  
  
1.  <span data-ttu-id="5ad92-128">Copie el diagrama de actualización anterior en el Bloc de notas y guárdelo en un archivo como UpdategramPassingNullvalues.xml.</span><span class="sxs-lookup"><span data-stu-id="5ad92-128">Copy the updategram above into Notepad and save it to file as UpdategramPassingNullvalues.xml.</span></span>  
  
2.  <span data-ttu-id="5ad92-129">Prepare el script SQLXML 4,0 test (Sqlxml4test. vbs) en [usar ado para ejecutar consultas sqlxml 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) para ejecutar el diagrama agregando las siguientes líneas después de `cmd.Properties("Output Stream").Value = outStream` :</span><span class="sxs-lookup"><span data-stu-id="5ad92-129">Prepare the SQLXML 4.0 test script (Sqlxml4test.vbs) in [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md) to execute the updategram by adding the following lines after the `cmd.Properties("Output Stream").Value = outStream`:</span></span>  
  
    ```  
    cmd.NamedParameters = True  
    ' CreateParameter arguments: Name, Type, Direction, Size, Value   
    cmd.Parameters.Append cmd.CreateParameter("@EmployeeID", 3, 1, 0, 1)  
    cmd.Parameters.Append cmd.CreateParameter("@ManagerID",  3, 1, 0, Null)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5ad92-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5ad92-130">See Also</span></span>  
 [<span data-ttu-id="5ad92-131">Consideraciones de seguridad de diagrama &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="5ad92-131">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
