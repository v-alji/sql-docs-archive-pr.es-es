---
title: Optimización de la tabla NewOrg | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- optimizing tables
ms.assetid: 89ff6d37-94c0-4773-8be9-dde943fff023
author: stevestein
ms.author: sstein
ms.openlocfilehash: 39c09a3a73051e7a61f3a62a125232d83d1570c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661861"
---
# <a name="optimizing-the-neworg-table"></a><span data-ttu-id="7bc2b-102">Optimizar la tabla NewOrg</span><span class="sxs-lookup"><span data-stu-id="7bc2b-102">Optimizing the NewOrg Table</span></span>
  <span data-ttu-id="7bc2b-103">La tabla **NewOrd** que ha creado en la tarea [rellenar una tabla con datos jerárquicos existentes](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md) contiene toda la información del empleado y representa la estructura jerárquica mediante un `hierarchyid` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-103">The **NewOrd** table that you created in the [Populating a Table with Existing Hierarchical Data](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md) task contains all the employee information, and represents the hierarchical structure by using a `hierarchyid` data type.</span></span> <span data-ttu-id="7bc2b-104">Esta tarea agrega los nuevos índices que admiten las búsquedas en la columna `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-104">This task adds new indexes to support searches on the `hierarchyid` column.</span></span>  
  
## <a name="clustered-index"></a><span data-ttu-id="7bc2b-105">Índice agrupado</span><span class="sxs-lookup"><span data-stu-id="7bc2b-105">Clustered Index</span></span>  
 <span data-ttu-id="7bc2b-106">La `hierarchyid` columna (**OrgNode**) es la clave principal de la tabla **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="7bc2b-106">The `hierarchyid` column (**OrgNode**) is the primary key for the **NewOrg** table.</span></span> <span data-ttu-id="7bc2b-107">Al crear la tabla, contenía un índice agrupado denominado **PK_NewOrg_OrgNode** para exigir la singularidad de la columna **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="7bc2b-107">When the table was created, it contained a clustered index named **PK_NewOrg_OrgNode** to enforce the uniqueness of the **OrgNode** column.</span></span> <span data-ttu-id="7bc2b-108">Este índice clúster también admite una búsqueda con prioridad a la profundidad de la tabla.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-108">This clustered index also supports a depth-first search of the table.</span></span>  
  
## <a name="nonclustered-index"></a><span data-ttu-id="7bc2b-109">Índice no agrupado</span><span class="sxs-lookup"><span data-stu-id="7bc2b-109">Nonclustered Index</span></span>  
 <span data-ttu-id="7bc2b-110">Este paso crea dos índices no clúster que admiten búsquedas típicas.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-110">This step creates two nonclustered indexes to support typical searches.</span></span>  
  
#### <a name="to-index-the-neworg-table-for-efficient-searches"></a><span data-ttu-id="7bc2b-111">Para indizar la tabla NewOrg a fin de realizar búsquedas eficaces</span><span class="sxs-lookup"><span data-stu-id="7bc2b-111">To index the NewOrg table for efficient searches</span></span>  
  
1.  <span data-ttu-id="7bc2b-112">Si quiere ayudar a realizar consultas en el mismo nivel de la jerarquía, use el método [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) para crear una columna calculada que contenga el nivel en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-112">To help queries at the same level in the hierarchy, use the [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) method to create a computed column that contains the level in the hierarchy.</span></span> <span data-ttu-id="7bc2b-113">A continuación, cree un índice compuesto en el nivel y `Hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-113">Then, create a composite index on the level and the `Hierarchyid`.</span></span> <span data-ttu-id="7bc2b-114">Ejecute el código siguiente para crear la columna calculada y el índice con prioridad a la amplitud:</span><span class="sxs-lookup"><span data-stu-id="7bc2b-114">Run the following code to create the computed column and the breadth-first index:</span></span>  
  
    ```  
    ALTER TABLE NewOrg   
       ADD H_Level AS OrgNode.GetLevel() ;  
    CREATE UNIQUE INDEX EmpBFInd   
       ON NewOrg(H_Level, OrgNode) ;  
    GO  
    ```  
  
2.  <span data-ttu-id="7bc2b-115">Cree un índice único en la columna **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="7bc2b-115">Create a unique index on the **EmployeeID** column.</span></span> <span data-ttu-id="7bc2b-116">Esta es la búsqueda singleton tradicional de un empleado único por número de **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="7bc2b-116">This is the traditional singleton lookup of a single employee by **EmployeeID** number.</span></span> <span data-ttu-id="7bc2b-117">Ejecute el código siguiente para crear un índice en **EmployeeID**:</span><span class="sxs-lookup"><span data-stu-id="7bc2b-117">Run the following code to create an index on **EmployeeID**:</span></span>  
  
    ```  
    CREATE UNIQUE INDEX EmpIDs_unq ON NewOrg(EmployeeID) ;  
    GO  
    ```  
  
3.  <span data-ttu-id="7bc2b-118">Ejecute el código siguiente para recuperar los datos en la tabla en el orden de cada uno de los tres índices:</span><span class="sxs-lookup"><span data-stu-id="7bc2b-118">Run the following code to retrieve data from the table in the order of each of the three indexes:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID  
    FROM NewOrg   
    ORDER BY OrgNode;  
  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID   
    FROM NewOrg   
    ORDER BY H_Level, OrgNode;  
  
    SELECT OrgNode.ToString() AS LogicalNode,  
    OrgNode, H_Level, EmployeeID, LoginID   
    FROM NewOrg   
    ORDER BY EmployeeID;  
    GO  
    ```  
  
4.  <span data-ttu-id="7bc2b-119">Compare los conjuntos de resultados para ver cómo se almacena el orden en cada tipo de índice.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-119">Compare the result sets to see how the order is stored in each type of index.</span></span> <span data-ttu-id="7bc2b-120">Solo siguen las primeras cuatro filas de cada de salida.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-120">Only the first four rows of each output follow.</span></span>  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
     <span data-ttu-id="7bc2b-121">Índice con prioridad a la profundidad: los registros del empleado se almacenan junto a su administrador.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-121">Depth-first index: Employee records are stored adjacent to their manager.</span></span>  
  
     `LogicalNode OrgNode    H_Level EmployeeID LoginID`  
  
     `/             0x         0         1      zarifin`  
  
     `/1/          0x58        1         2      tplate`  
  
     `/1/1/       0x5AC0       2         4      schai`  
  
     `/1/1/1/     0x5AD6       3         9      jwang`  
  
     `/1/1/2/     0x5ADA       3        10      malexander`  
  
     `/1/2/       0x5B40       2         5      elang`  
  
     `/1/3/       0x5BC0       2         6      gsmits`  
  
     `/2/         0x68         1         3      hjensen`  
  
     `/2/1/       0x6AC0       2         7      sdavis`  
  
     `/2/2/       0x6B40       2         8      norint`  
  
     <span data-ttu-id="7bc2b-122">El índice con prioridad a**EmployeeID**: las filas se almacenan en secuencia de **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="7bc2b-122">**EmployeeID**-first index: Rows are stored in **EmployeeID** sequence.</span></span>  
  
     `LogicalNode OrgNode    H_Level EmployeeID LoginID`  
  
     `/             0x         0         1      zarifin`  
  
     `/1/          0x58        1         2      tplate`  
  
     `/2/         0x68         1         3      hjensen`  
  
     `/1/1/       0x5AC0       2         4      schai`  
  
     `/1/2/       0x5B40       2         5      elang`  
  
     `/1/3/       0x5BC0       2         6      gsmits`  
  
     `/2/1/       0x6AC0       2         7      sdavis`  
  
     `/2/2/       0x6B40       2         8      norint`  
  
     `/1/1/1/     0x5AD6       3         9      jwang`  
  
     `/1/1/2/     0x5ADA       3        10      malexander`  
  
> [!NOTE]  
>  <span data-ttu-id="7bc2b-123">Para diagramas que muestran la diferencia entre un índice con prioridad a la profundidad y uno con prioridad a la amplitud, consulte [Datos jerárquicos &#40;SQL Server&#41;](../hierarchical-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7bc2b-123">For diagrams that show the difference between a depth-first index and a breadth-first index, see [Hierarchical Data &#40;SQL Server&#41;](../hierarchical-data-sql-server.md).</span></span>  
  
#### <a name="to-drop-the-unnecessary-columns"></a><span data-ttu-id="7bc2b-124">Para eliminar las columnas innecesarias</span><span class="sxs-lookup"><span data-stu-id="7bc2b-124">To drop the unnecessary columns</span></span>  
  
1.  <span data-ttu-id="7bc2b-125">La columna **ManagerID** representa la relación de empleado/administrador, que representa ahora la columna **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="7bc2b-125">The **ManagerID** column represents the employee/manager relationship, which is now represented by the **OrgNode** column.</span></span> <span data-ttu-id="7bc2b-126">Si el resto de aplicaciones no necesitan la columna **ManagerID** , considere la posibilidad de quitarla mediante la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="7bc2b-126">If other applications do not need the **ManagerID** column, consider dropping it by using the following statement:</span></span>  
  
    ```  
    ALTER TABLE NewOrg DROP COLUMN ManagerID ;  
    GO  
    ```  
  
2.  <span data-ttu-id="7bc2b-127">La columna **EmployeeID** también es redundante.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-127">The **EmployeeID** column is also redundant.</span></span> <span data-ttu-id="7bc2b-128">La columna **OrgNode** identifica singularmente a cada empleado.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-128">The **OrgNode** column uniquely identifies each employee.</span></span> <span data-ttu-id="7bc2b-129">Si otras aplicaciones no necesitan la columna **EmployeeID** , considere la posibilidad de quitar el índice y, después, la columna mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="7bc2b-129">If other applications do not need the **EmployeeID** column, consider dropping the index and then the column by using the following code:</span></span>  
  
    ```  
    DROP INDEX EmpIDs_unq ON NewOrg ;  
    ALTER TABLE NewOrg DROP COLUMN EmployeeID ;  
    GO  
    ```  
  
#### <a name="to-replace-the-original-table-with-the-new-table"></a><span data-ttu-id="7bc2b-130">Para sustituir la tabla original por la nueva tabla</span><span class="sxs-lookup"><span data-stu-id="7bc2b-130">To replace the original table with the new table</span></span>  
  
1.  <span data-ttu-id="7bc2b-131">Si la tabla original contenía algún índice o restricción adicional, agréguelos a la tabla **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="7bc2b-131">If your original table contained any additional indexes or constraints, add them to the **NewOrg** table.</span></span>  
  
2.  <span data-ttu-id="7bc2b-132">Reemplace la antigua tabla **EmployeeDemo** por la nueva.</span><span class="sxs-lookup"><span data-stu-id="7bc2b-132">Replace the old **EmployeeDemo** table with the new table.</span></span> <span data-ttu-id="7bc2b-133">Ejecute el código siguiente para quitar la tabla antigua y, a continuación, cambie el nombre de la nueva tabla con el nombre anterior:</span><span class="sxs-lookup"><span data-stu-id="7bc2b-133">Run the following code to drop the old table, and then rename the new table with the old name:</span></span>  
  
    ```  
    DROP TABLE EmployeeDemo ;  
    GO  
    sp_rename 'NewOrg', EmployeeDemo ;  
    GO  
    ```  
  
3.  <span data-ttu-id="7bc2b-134">Ejecute el código siguiente para examinar la tabla final:</span><span class="sxs-lookup"><span data-stu-id="7bc2b-134">Run the following code to examine the final table:</span></span>  
  
    ```  
    SELECT * FROM EmployeeDemo ;  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7bc2b-135">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="7bc2b-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7bc2b-136">Resumen: Conversión de una tabla en una estructura jerárquica</span><span class="sxs-lookup"><span data-stu-id="7bc2b-136">Summary: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-4-summary-converting-a-table-to-a-hierarchical-structure.md)  
  
  
