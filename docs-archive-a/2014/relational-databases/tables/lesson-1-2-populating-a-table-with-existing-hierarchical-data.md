---
title: Relleno de una tabla con los datos jerárquicos existentes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: fd943d84-dbe6-4a05-912b-c88164998d80
author: stevestein
ms.author: sstein
ms.openlocfilehash: 966548b11ad4697abc06de5c5c239a511f80b7af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744630"
---
# <a name="populating-a-table-with-existing-hierarchical-data"></a><span data-ttu-id="db89d-102">Rellenar una tabla con los datos jerárquicos existentes</span><span class="sxs-lookup"><span data-stu-id="db89d-102">Populating a Table with Existing Hierarchical Data</span></span>
  <span data-ttu-id="db89d-103"> Esta tarea crea una nueva tabla y la rellena con los datos de la tabla **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="db89d-103">This task creates a new table and populates it with the data in the **EmployeeDemo** table.</span></span> <span data-ttu-id="db89d-104">Esta tarea consta de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="db89d-104">This task has the following steps:</span></span>  
  
-   <span data-ttu-id="db89d-105">Cree una nueva tabla que contenga una columna `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="db89d-105">Create a new table that contains a `hierarchyid` column.</span></span> <span data-ttu-id="db89d-106">Esta columna podría reemplazar a las columnas **EmployeeID** y **ManagerID** existentes.</span><span class="sxs-lookup"><span data-stu-id="db89d-106">This column could replace the existing **EmployeeID** and **ManagerID** columns.</span></span> <span data-ttu-id="db89d-107">Sin embargo, usted conservará esas columnas.</span><span class="sxs-lookup"><span data-stu-id="db89d-107">However, you will retain those columns.</span></span> <span data-ttu-id="db89d-108">La razón de ello es porque alguna de las aplicaciones existentes podría hacer referencia a esas columnas, y también para ayudarle a entender los datos una vez realizada la transferencia.</span><span class="sxs-lookup"><span data-stu-id="db89d-108">This is because existing applications might refer to those columns, and also to help you understand the data after the transfer.</span></span> <span data-ttu-id="db89d-109">La definición de tabla especifica que **OrgNode** es la clave principal, que requiere que la columna contenga valores únicos.</span><span class="sxs-lookup"><span data-stu-id="db89d-109">The table definition specifies that **OrgNode** is the primary key, which requires the column to contain unique values.</span></span> <span data-ttu-id="db89d-110">El índice agrupado sobre la columna **OrgNode** almacenará la fecha en secuencia **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="db89d-110">The clustered index on the **OrgNode** column will store the date in **OrgNode** sequence.</span></span>  
  
-   <span data-ttu-id="db89d-111">Cree una tabla temporal que se utilizará para averiguar cuántos empleados notifican directamente a cada gerente.</span><span class="sxs-lookup"><span data-stu-id="db89d-111">Create a temporary table that is used to track how many employees report directly to each manager.</span></span>  
  
-   <span data-ttu-id="db89d-112">Rellene la nueva tabla con los datos de la tabla **EmployeeDemo** .</span><span class="sxs-lookup"><span data-stu-id="db89d-112">Populate the new table by using data from the **EmployeeDemo** table.</span></span>  
  
### <a name="to-create-a-new-table-named-neworg"></a><span data-ttu-id="db89d-113">Para crear una nueva tabla denominada NewOrg</span><span class="sxs-lookup"><span data-stu-id="db89d-113">To create a new table named NewOrg</span></span>  
  
-   <span data-ttu-id="db89d-114">En una ventana del Editor de consultas, ejecute el siguiente código para crear una nueva tabla denominada **HumanResources.NewOrg**:</span><span class="sxs-lookup"><span data-stu-id="db89d-114">In a Query Editor window, run the following code to create a new table named **HumanResources.NewOrg**:</span></span>  
  
    ```  
    CREATE TABLE NewOrg  
    (  
      OrgNode hierarchyid,  
      EmployeeID int,  
      LoginID nvarchar(50),  
      ManagerID int  
    CONSTRAINT PK_NewOrg_OrgNode  
      PRIMARY KEY CLUSTERED (OrgNode)  
    );  
    GO  
    ```  
  
### <a name="to-create-a-temporary-table-named-children"></a><span data-ttu-id="db89d-115">Para crear una tabla temporal denominada #Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="db89d-115">To create a temporary table named #Children</span></span>  
  
1.  <span data-ttu-id="db89d-116">Cree una tabla temporal denominada **#Elementos secundarios** con una columna denominada **Num** que contendrá el número de elementos secundarios de cada nodo:</span><span class="sxs-lookup"><span data-stu-id="db89d-116">Create a temporary table named **#Children** with a column named **Num** that will contain the number of children for each node:</span></span>  
  
    ```  
    CREATE TABLE #Children   
       (  
        EmployeeID int,  
        ManagerID int,  
        Num int  
    );  
    GO  
    ```  
  
2.  <span data-ttu-id="db89d-117">Agregue un índice que acelerará significativamente la consulta que rellena la tabla **NewOrg** :</span><span class="sxs-lookup"><span data-stu-id="db89d-117">Add an index that will significantly speed up the query that populates the **NewOrg** table:</span></span>  
  
    ```  
    CREATE CLUSTERED INDEX tmpind ON #Children(ManagerID, EmployeeID);  
    GO  
    ```  
  
### <a name="to-populate-the-neworg-table"></a><span data-ttu-id="db89d-118">Para rellenar la tabla NewOrg</span><span class="sxs-lookup"><span data-stu-id="db89d-118">To populate the NewOrg table</span></span>  
  
1.  <span data-ttu-id="db89d-119">Las consultas recursivas prohíben las subconsultas con agregados.</span><span class="sxs-lookup"><span data-stu-id="db89d-119">Recursive queries forbid subqueries with aggregates.</span></span> <span data-ttu-id="db89d-120">En su lugar, rellene la tabla **#Elementos secundarios** con el código siguiente, que usa el método [ROW_NUMBER ()](/sql/t-sql/functions/row-number-transact-sql) para rellenar la columna **Num** :</span><span class="sxs-lookup"><span data-stu-id="db89d-120">Instead, populate the **#Children** table with the following code, which uses the [ROW_NUMBER()](/sql/t-sql/functions/row-number-transact-sql) method to populate the **Num** column:</span></span>  
  
    ```  
    INSERT #Children (EmployeeID, ManagerID, Num)  
    SELECT EmployeeID, ManagerID,  
      ROW_NUMBER() OVER (PARTITION BY ManagerID ORDER BY ManagerID)   
    FROM EmployeeDemo  
    GO  
  
    ```  
  
2.  <span data-ttu-id="db89d-121">Revise la tabla **#Elementos secundarios** .</span><span class="sxs-lookup"><span data-stu-id="db89d-121">Review the **#Children** table.</span></span> <span data-ttu-id="db89d-122">Observe cómo la columna **Num** contiene números secuenciales para cada administrador.</span><span class="sxs-lookup"><span data-stu-id="db89d-122">Note how the **Num** column contains sequential numbers for each manager.</span></span>  
  
    ```  
    SELECT * FROM #Children ORDER BY ManagerID, Num  
    GO  
  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
     `EmployeeID ManagerID Num`  
  
     `---------- --------- ---`  
  
     `1        NULL       1`  
  
     `2         1         1`  
  
     `3         1         2`  
  
     `4         2         1`  
  
     `5         2         2`  
  
     `6         2         3`  
  
     `7         3         1`  
  
     `8         3         2`  
  
     `9         4         1`  
  
     `10        4         2`  
  
3.  <span data-ttu-id="db89d-123">Rellene la tabla **NewOrg** .</span><span class="sxs-lookup"><span data-stu-id="db89d-123">Populate the **NewOrg** table.</span></span> <span data-ttu-id="db89d-124">Use los métodos GetRoot y ToString para concatenar los valores **numéricos** en el `hierarchyid` formato y, a continuación, actualice la columna **OrgNode** con los valores jerárquicos resultantes:</span><span class="sxs-lookup"><span data-stu-id="db89d-124">Use the GetRoot and ToString methods to concatenate the **Num** values into the `hierarchyid` format, and then update the **OrgNode** column with the resultant hierarchical values:</span></span>  
  
    ```  
    WITH paths(path, EmployeeID)   
    AS (  
    -- This section provides the value for the root of the hierarchy  
    SELECT hierarchyid::GetRoot() AS OrgNode, EmployeeID   
    FROM #Children AS C   
    WHERE ManagerID IS NULL   
  
    UNION ALL   
    -- This section provides values for all nodes except the root  
    SELECT   
    CAST(p.path.ToString() + CAST(C.Num AS varchar(30)) + '/' AS hierarchyid),   
    C.EmployeeID  
    FROM #Children AS C   
    JOIN paths AS p   
       ON C.ManagerID = P.EmployeeID   
    )  
    INSERT NewOrg (OrgNode, O.EmployeeID, O.LoginID, O.ManagerID)  
    SELECT P.path, O.EmployeeID, O.LoginID, O.ManagerID  
    FROM EmployeeDemo AS O   
    JOIN Paths AS P   
       ON O.EmployeeID = P.EmployeeID  
    GO  
  
    ```  
  
4.  <span data-ttu-id="db89d-125">Una columna `hierarchyid` se entiende mejor al convertirla en una cadena de caracteres.</span><span class="sxs-lookup"><span data-stu-id="db89d-125">A `hierarchyid` column is more understandable when you convert it to character format.</span></span> <span data-ttu-id="db89d-126">Revise los datos de la tabla **NewOrg** ; para ello, ejecute el código siguiente, que contiene dos representaciones de la columna **OrgNode** :</span><span class="sxs-lookup"><span data-stu-id="db89d-126">Review the data in the **NewOrg** table by executing the following code, which contains two representations of the **OrgNode** column:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS LogicalNode, *   
    FROM NewOrg   
    ORDER BY LogicalNode;  
    GO  
  
    ```  
  
     <span data-ttu-id="db89d-127">La columna **LogicalNode** convierte la `hierarchyid` columna en un formato de texto más legible que representa la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="db89d-127">The **LogicalNode** column converts the `hierarchyid` column into a more readable text form that represents the hierarchy.</span></span> <span data-ttu-id="db89d-128">En las tareas restantes, utilizará el método `ToString()` para mostrar el formato lógico de las columnas `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="db89d-128">In the remaining tasks, you will use the `ToString()` method to show the logical format of the `hierarchyid` columns.</span></span>  
  
5.  <span data-ttu-id="db89d-129">Elimine la tabla temporal, que ya no se necesita:</span><span class="sxs-lookup"><span data-stu-id="db89d-129">Drop the temporary table, which is no longer needed:</span></span>  
  
    ```  
    DROP TABLE #Children  
    GO  
    ```  
  
 <span data-ttu-id="db89d-130">La tarea siguiente creará los índices para la estructura jerárquica.</span><span class="sxs-lookup"><span data-stu-id="db89d-130">The next task will create indexes to support the hierarchical structure.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="db89d-131">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="db89d-131">Next Task in Lesson</span></span>  
 [<span data-ttu-id="db89d-132">Optimizar la tabla NewOrg</span><span class="sxs-lookup"><span data-stu-id="db89d-132">Optimizing the NewOrg Table</span></span>](lesson-1-3-optimizing-the-neworg-table.md)  
  
  
