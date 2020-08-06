---
title: Relleno de una tabla jerárquica usando métodos jerárquicos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- HierarchyID
helpviewer_keywords:
- HierarchyID
ms.assetid: 2c95fa60-5b8e-4a05-ac09-cffe2b05900a
author: stevestein
ms.author: sstein
ms.openlocfilehash: ef99d711a772a075f568a83f5d56fcecaaa598f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674693"
---
# <a name="populating-a-hierarchical-table-using-hierarchical-methods"></a><span data-ttu-id="d86ae-102">Rellenar una tabla jerárquica usando métodos jerárquicos</span><span class="sxs-lookup"><span data-stu-id="d86ae-102">Populating a Hierarchical Table Using Hierarchical Methods</span></span>
  [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="d86ae-103">tiene 8 empleados que trabajan en el departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="d86ae-103">has 8 employees working in the Marketing department.</span></span> <span data-ttu-id="d86ae-104">La jerarquía de empleados ofrece el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="d86ae-104">The employee hierarchy looks like this:</span></span>  
  
 <span data-ttu-id="d86ae-105">**David**, **EmployeeID** 6, es el jefe de marketing.</span><span class="sxs-lookup"><span data-stu-id="d86ae-105">**David**, **EmployeeID** 6, is the Marketing Manager.</span></span> <span data-ttu-id="d86ae-106">Tres especialistas en marketing notifican a **David**:</span><span class="sxs-lookup"><span data-stu-id="d86ae-106">Three Marketing Specialists report to **David**:</span></span>  
  
-   <span data-ttu-id="d86ae-107">**Sariya**, **EmployeeID** 46</span><span class="sxs-lookup"><span data-stu-id="d86ae-107">**Sariya**, **EmployeeID** 46</span></span>  
  
-   <span data-ttu-id="d86ae-108">**John**, **EmployeeID** 271</span><span class="sxs-lookup"><span data-stu-id="d86ae-108">**John**, **EmployeeID** 271</span></span>  
  
-   <span data-ttu-id="d86ae-109">**Jill**, **EmployeeID** 119</span><span class="sxs-lookup"><span data-stu-id="d86ae-109">**Jill**, **EmployeeID** 119</span></span>  
  
 <span data-ttu-id="d86ae-110">La asistente de marketing **Wanida** (**id. de empleado** 269) notifica a **Sariya**, mientras que la asistente de marketing **Mary** (**id. de empleado** 272) notifica a **John**.</span><span class="sxs-lookup"><span data-stu-id="d86ae-110">Marketing Assistant **Wanida** (**EmployeeID** 269), reports to **Sariya**, and Marketing Assistant **Mary** (**EmployeeID** 272), reports to **John**.</span></span>  
  
### <a name="to-insert-the-root-of-the-hierarchy-tree"></a><span data-ttu-id="d86ae-111">Para insertar la raíz del árbol de jerarquía</span><span class="sxs-lookup"><span data-stu-id="d86ae-111">To insert the root of the hierarchy tree</span></span>  
  
1.  <span data-ttu-id="d86ae-112">El ejemplo siguiente inserta a **David** , jefe de marketing, en la raíz de la jerarquía dentro de la tabla.</span><span class="sxs-lookup"><span data-stu-id="d86ae-112">The following example inserts **David** the Marketing Manager into the table at the root of the hierarchy.</span></span> <span data-ttu-id="d86ae-113">La columna **OrdLevel** es una columna calculada.</span><span class="sxs-lookup"><span data-stu-id="d86ae-113">The **OrdLevel** column is a computed column.</span></span> <span data-ttu-id="d86ae-114">Por lo tanto, no forma parte de la instrucción INSERT.</span><span class="sxs-lookup"><span data-stu-id="d86ae-114">Therefore, it is not part of the INSERT statement.</span></span> <span data-ttu-id="d86ae-115">Este primer registro usa el método [GetRoot()](/sql/t-sql/data-types/getroot-database-engine) para que se rellene este primer registro como la raíz de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="d86ae-115">This first record uses the [GetRoot()](/sql/t-sql/data-types/getroot-database-engine) method to populate this first record as the root of the hierarchy.</span></span>  
  
    ```  
    INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
    VALUES (hierarchyid::GetRoot(), 6, 'David', 'Marketing Manager') ;  
    GO  
    ```  
  
2.  <span data-ttu-id="d86ae-116">Ejecute el código siguiente para examinar la fila inicial de la tabla:</span><span class="sxs-lookup"><span data-stu-id="d86ae-116">Execute the following code to examine initial row in the table:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    ```  
  
 <span data-ttu-id="d86ae-117">Al igual que en la lección anterior, se usa el método `ToString()` para convertir el tipo de datos de `hierarchyid` en un formato más comprensible.</span><span class="sxs-lookup"><span data-stu-id="d86ae-117">As in the previous lesson, we use the `ToString()` method to convert the `hierarchyid` data type to a format that is more easily understood.</span></span>  
  
### <a name="to-insert-a-subordinate-employee"></a><span data-ttu-id="d86ae-118">Para insertar a un empleado subordinado</span><span class="sxs-lookup"><span data-stu-id="d86ae-118">To insert a subordinate employee</span></span>  
  
1.  <span data-ttu-id="d86ae-119">**Sariya** notifica a **David**.</span><span class="sxs-lookup"><span data-stu-id="d86ae-119">**Sariya** reports to **David**.</span></span> <span data-ttu-id="d86ae-120">Para insertar el nodo **de Sariya** , debe crear un valor **OrgNode** adecuado del tipo de datos `hierarchyid` .</span><span class="sxs-lookup"><span data-stu-id="d86ae-120">To insert **Sariya's** node, you must create an appropriate **OrgNode** value of data type `hierarchyid`.</span></span> <span data-ttu-id="d86ae-121">El código siguiente crea una variable de tipo de datos de `hierarchyid` y lo rellena con el valor raíz OrgNode de la tabla.</span><span class="sxs-lookup"><span data-stu-id="d86ae-121">The following code creates a variable of data type `hierarchyid` and populates it with the root OrgNode value of the table.</span></span> <span data-ttu-id="d86ae-122">Después, usa esa variable con el método [GetDescendant()](/sql/t-sql/data-types/getdescendant-database-engine) para insertar una fila que es un nodo subordinado.</span><span class="sxs-lookup"><span data-stu-id="d86ae-122">Then uses that variable with the [GetDescendant()](/sql/t-sql/data-types/getdescendant-database-engine) method to insert row that is a subordinate node.</span></span> <span data-ttu-id="d86ae-123">`GetDescendant` toma dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="d86ae-123">`GetDescendant` takes two arguments.</span></span> <span data-ttu-id="d86ae-124">Revise las opciones siguientes de los valores de argumento:</span><span class="sxs-lookup"><span data-stu-id="d86ae-124">Review the following options for the argument values:</span></span>  
  
    -   <span data-ttu-id="d86ae-125">Si el elemento primario es NULL, `GetDescendant` devolverá NULL.</span><span class="sxs-lookup"><span data-stu-id="d86ae-125">If parent is NULL, `GetDescendant` returns NULL.</span></span>  
  
    -   <span data-ttu-id="d86ae-126">Si el elemento primario no es NULL y child1 y child2 son NULL, `GetDescendant` devuelve un elemento secundario del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="d86ae-126">If parent is not NULL, and both child1 and child2 are NULL, `GetDescendant` returns a child of parent.</span></span>  
  
    -   <span data-ttu-id="d86ae-127">Si el elemento primario y child1 no son NULL y, a su vez, child2 es NULL, `GetDescendant` devuelve un elemento secundario del elemento primario mayor que child1.</span><span class="sxs-lookup"><span data-stu-id="d86ae-127">If parent and child1 are not NULL, and child2 is NULL, `GetDescendant` returns a child of parent greater than child1.</span></span>  
  
    -   <span data-ttu-id="d86ae-128">Si el elemento primario y child2 no son NULL y, a su vez, child1 es NULL, `GetDescendant` devuelve un elemento secundario del elemento primario menor que child2.</span><span class="sxs-lookup"><span data-stu-id="d86ae-128">If parent and child2 are not NULL and child1 is NULL, `GetDescendant` returns a child of parent less than child2.</span></span>  
  
    -   <span data-ttu-id="d86ae-129">Si el elemento primario, child1 y child2 no son NULL, `GetDescendant` devuelve un elemento secundario del elemento primario mayor que child1 y menor que child2.</span><span class="sxs-lookup"><span data-stu-id="d86ae-129">If parent, child1, and child2 are all not NULL, `GetDescendant` returns a child of parent greater than child1 and less than child2.</span></span>  
  
     <span data-ttu-id="d86ae-130">El código siguiente utiliza los argumentos `(NULL, NULL)` de la raíz primaria porque todavía no hay filas en la tabla (excepto la raíz).</span><span class="sxs-lookup"><span data-stu-id="d86ae-130">The following code uses the `(NULL, NULL)` arguments of the root parent because there are not yet any rows in the table except the root.</span></span> <span data-ttu-id="d86ae-131">Ejecute el código siguiente para insertar a **Sariya**:</span><span class="sxs-lookup"><span data-stu-id="d86ae-131">Execute the following code to insert **Sariya**:</span></span>  
  
    ```  
    DECLARE @Manager hierarchyid   
    SELECT @Manager = hierarchyid::GetRoot()  
    FROM HumanResources.EmployeeOrg ;  
  
    INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
    VALUES  
    (@Manager.GetDescendant(NULL, NULL), 46, 'Sariya', 'Marketing Specialist') ;  
  
    ```  
  
2.  <span data-ttu-id="d86ae-132">Repita la consulta realizada con el primer procedimiento para consultar la tabla y ver cómo aparecen las entradas:</span><span class="sxs-lookup"><span data-stu-id="d86ae-132">Repeat the query from the first procedure to query the table and see how the entries appear:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    /1/          0x58    1        46         Sariya  Marketing Specialist  
    ```  
  
### <a name="to-create-a-procedure-for-entering-new-nodes"></a><span data-ttu-id="d86ae-133">Para crear un procedimiento que sirva para escribir nuevos nodos</span><span class="sxs-lookup"><span data-stu-id="d86ae-133">To create a procedure for entering new nodes</span></span>  
  
1.  <span data-ttu-id="d86ae-134">Para simplificar la entrada de datos, cree el siguiente procedimiento almacenado a fin de agregar empleados a la tabla **EmployeeOrg** .</span><span class="sxs-lookup"><span data-stu-id="d86ae-134">To simplify entering data, create the following stored procedure to add employees to the **EmployeeOrg** table.</span></span> <span data-ttu-id="d86ae-135">El procedimiento acepta valores de entrada sobre el empleado que se está agregando.</span><span class="sxs-lookup"><span data-stu-id="d86ae-135">The procedure accepts input values about the employee being added.</span></span> <span data-ttu-id="d86ae-136">Este proceso contiene el **EmployeeID** del jefe del nuevo empleado, el número de **EmployeeID** del nuevo empleado, así como su nombre y puesto.</span><span class="sxs-lookup"><span data-stu-id="d86ae-136">This includes the **EmployeeID** of the new employee's manager, the new employee's **EmployeeID** number, and their first name and title.</span></span> <span data-ttu-id="d86ae-137">El procedimiento usa `GetDescendant()` y también el método [GetAncestor()](/sql/t-sql/data-types/getancestor-database-engine) .</span><span class="sxs-lookup"><span data-stu-id="d86ae-137">The procedure uses `GetDescendant()` and also the [GetAncestor()](/sql/t-sql/data-types/getancestor-database-engine) method.</span></span> <span data-ttu-id="d86ae-138">Ejecute el código siguiente para crear el procedimiento:</span><span class="sxs-lookup"><span data-stu-id="d86ae-138">Execute the following code to create the procedure:</span></span>  
  
    ```  
    CREATE PROC AddEmp(@mgrid int, @empid int, @e_name varchar(20), @title varchar(20))   
    AS   
    BEGIN  
       DECLARE @mOrgNode hierarchyid, @lc hierarchyid  
       SELECT @mOrgNode = OrgNode   
       FROM HumanResources.EmployeeOrg   
       WHERE EmployeeID = @mgrid  
       SET TRANSACTION ISOLATION LEVEL SERIALIZABLE  
       BEGIN TRANSACTION  
          SELECT @lc = max(OrgNode)   
          FROM HumanResources.EmployeeOrg   
          WHERE OrgNode.GetAncestor(1) =@mOrgNode ;  
  
          INSERT HumanResources.EmployeeOrg (OrgNode, EmployeeID, EmpName, Title)  
          VALUES(@mOrgNode.GetDescendant(@lc, NULL), @empid, @e_name, @title)  
       COMMIT  
    END ;  
    GO  
    ```  
  
2.  <span data-ttu-id="d86ae-139">El ejemplo siguiente agrega los 4 empleados restantes que notifican directa o indirectamente a **David**.</span><span class="sxs-lookup"><span data-stu-id="d86ae-139">The following example adds the remaining 4 employees that report directly or indirectly to **David**.</span></span>  
  
    ```  
    EXEC AddEmp 6, 271, 'John', 'Marketing Specialist' ;  
    EXEC AddEmp 6, 119, 'Jill', 'Marketing Specialist' ;  
    EXEC AddEmp 46, 269, 'Wanida', 'Marketing Assistant' ;  
    EXEC AddEmp 271, 272, 'Mary', 'Marketing Assistant' ;  
    ```  
  
3.  <span data-ttu-id="d86ae-140">Vuelva a ejecutar la consulta siguiente y examine las filas de la tabla **EmployeeOrg** :</span><span class="sxs-lookup"><span data-stu-id="d86ae-140">Again, execute the following query examine the rows in the **EmployeeOrg** table:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    GO  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    Text_OrgNode OrgNode OrgLevel EmployeeID EmpName Title  
    ------------ ------- -------- ---------- ------- -----------------  
    /            Ox      0        6          David   Marketing Manager  
    /1/          0x58    1        46         Sariya  Marketing Specialist  
    /1/1/        0x5AC0  2        269        Wanida  Marketing Assistant  
    /2/          0x68    1        271        John    Marketing Specialist  
    /2/1/        0x6AC0  2        272        Mary    Marketing Assistant  
    /3/          0x78    1        119        Jill    Marketing Specialist  
    ```  
  
 <span data-ttu-id="d86ae-141">La tabla estará totalmente rellena con la organización del departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="d86ae-141">The table is now fully populated with the Marketing organization.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="d86ae-142">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="d86ae-142">Next Task in Lesson</span></span>  
 [<span data-ttu-id="d86ae-143">Realizar una consulta a una tabla jerárquica mediante métodos de jerarquía</span><span class="sxs-lookup"><span data-stu-id="d86ae-143">Querying a Hierarchical Table Using Hierarchy Methods</span></span>](lesson-2-3-querying-a-hierarchical-table-using-hierarchy-methods.md)  
  
  
