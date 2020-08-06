---
title: Reordenación de los datos de una tabla jerárquica mediante métodos jerárquicos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 7b8064c7-62c6-488d-84d2-57a5828fb907
author: stevestein
ms.author: sstein
ms.openlocfilehash: ac6c93f359a81a80af81182120f213564680de0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662737"
---
# <a name="reordering-data-in-a-hierarchical-table-using-hierarchical-methods"></a><span data-ttu-id="b4e91-102">Reordenar los datos de una tabla jerárquica mediante métodos jerárquicos</span><span class="sxs-lookup"><span data-stu-id="b4e91-102">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>
  <span data-ttu-id="b4e91-103">Reorganizar una jerarquía es una tarea de mantenimiento común.</span><span class="sxs-lookup"><span data-stu-id="b4e91-103">Reorganizing a hierarchy is a common maintenance task.</span></span> <span data-ttu-id="b4e91-104">En esta tarea, usaremos una instrucción UPDATE con el método [GetReparentedValue](/sql/t-sql/data-types/getreparentedvalue-database-engine) para mover primero una única fila a una nueva ubicación en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="b4e91-104">In this task, we will use an UPDATE statement with the [GetReparentedValue](/sql/t-sql/data-types/getreparentedvalue-database-engine) method to first move a single row to a new location in the hierarchy.</span></span> <span data-ttu-id="b4e91-105">A continuación, moveremos un subárbol completo a una nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="b4e91-105">Then we will move an entire sub-tree to a new location.</span></span>  
  
 <span data-ttu-id="b4e91-106">El método `GetReparentedValue` tiene dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="b4e91-106">The `GetReparentedValue` method takes two arguments.</span></span> <span data-ttu-id="b4e91-107">El primer argumento describe la parte de la jerarquía que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="b4e91-107">The first argument describes the part of the hierarchy to be modified.</span></span> <span data-ttu-id="b4e91-108">Por ejemplo, si una jerarquía es **/1/4/2/3/** y quiere cambiar la sección **/1/4/** , la jerarquía se vuelve **/2/1/2/3/**, dejando los dos últimos nodos (**2/3/**) sin modificar. Debe proporcionar los nodos que cambian (**/1/4/**) como el primer argumento.</span><span class="sxs-lookup"><span data-stu-id="b4e91-108">For example, if a hierarchy is **/1/4/2/3/** and you want to change the **/1/4/** section, the hierarchy becomes **/2/1/2/3/**, leaving the last two nodes (**2/3/**) unchanged, you must provide the changing nodes (**/1/4/**) as the first argument.</span></span> <span data-ttu-id="b4e91-109">El segundo argumento proporciona el nuevo nivel de jerarquía; en nuestro ejemplo, **/2/1/**.</span><span class="sxs-lookup"><span data-stu-id="b4e91-109">The second argument provides the new hierarchy level, in our example **/2/1/**.</span></span> <span data-ttu-id="b4e91-110">No es necesario que los dos argumentos tengan el mismo número de niveles.</span><span class="sxs-lookup"><span data-stu-id="b4e91-110">The two arguments do not have to contain the same number of levels.</span></span>  
  
### <a name="to-move-a-single-row-to-a-new-location-in-the-hierarchy"></a><span data-ttu-id="b4e91-111">Para mover una fila única a una nueva ubicación en la jerarquía</span><span class="sxs-lookup"><span data-stu-id="b4e91-111">To move a single row to a new location in the hierarchy</span></span>  
  
1.  <span data-ttu-id="b4e91-112">Actualmente Wanida notifica a Sariya.</span><span class="sxs-lookup"><span data-stu-id="b4e91-112">Currently Wanida reports to Sariya.</span></span> <span data-ttu-id="b4e91-113">En este procedimiento, se mueve a Wanida de su nodo actual **/1/1/,** de modo que notificará a Jill.</span><span class="sxs-lookup"><span data-stu-id="b4e91-113">In this procedure, you move Wanida from her current node **/1/1/,** so that she reports to Jill.</span></span> <span data-ttu-id="b4e91-114">Su nuevo nodo se volverá **/3/1/** , por lo que **/1/** es el primer argumento y **/3/** el segundo.</span><span class="sxs-lookup"><span data-stu-id="b4e91-114">Her new node will become **/3/1/** so **/1/** is the first argument and **/3/** is the second.</span></span> <span data-ttu-id="b4e91-115">Estos se corresponden con los valores **OrgNode** de Sariya y Jill.</span><span class="sxs-lookup"><span data-stu-id="b4e91-115">These correspond to the **OrgNode** values of Sariya and Jill.</span></span> <span data-ttu-id="b4e91-116">Ejecute el código siguiente para mover a Wanida de la organización de Sariya a la de Jill:</span><span class="sxs-lookup"><span data-stu-id="b4e91-116">Execute the following code to move Wanida from Sariya's organization to Jill's:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid , @OldParent hierarchyid, @NewParent hierarchyid  
    SELECT @CurrentEmployee = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 269 ;   
    SELECT @OldParent = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 46 ;   
    SELECT @NewParent = OrgNode FROM HumanResources.EmployeeOrg  
      WHERE EmployeeID = 119 ;   
  
    UPDATE HumanResources.EmployeeOrg  
    SET OrgNode = @CurrentEmployee. GetReparentedValue(@OldParent, @NewParent)   
    WHERE OrgNode = @CurrentEmployee ;  
    GO  
    ```  
  
2.  <span data-ttu-id="b4e91-117">Ejecute el código siguiente para ver el resultado:</span><span class="sxs-lookup"><span data-stu-id="b4e91-117">Execute the following code to see the result:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode, OrgLevel, EmployeeID, EmpName, Title   
    FROM HumanResources.EmployeeOrg ;  
    GO  
    ```  
  
     <span data-ttu-id="b4e91-118">Wanida está ahora en el nodo **/3/1/**.</span><span class="sxs-lookup"><span data-stu-id="b4e91-118">Wanida is now at node **/3/1/**.</span></span>  
  
### <a name="to-reorganize-a-section-of-a-hierarchy"></a><span data-ttu-id="b4e91-119">Para reorganizar una sección de una jerarquía</span><span class="sxs-lookup"><span data-stu-id="b4e91-119">To reorganize a section of a hierarchy</span></span>  
  
1.  <span data-ttu-id="b4e91-120">Para mostrar cómo mover al mismo tiempo un gran número de personas, ejecute primero el código siguiente para agregar un becario a cargo de Wanida:</span><span class="sxs-lookup"><span data-stu-id="b4e91-120">To demonstrate how to move a larger number of people at the same time, first execute the following code to add an intern reporting to Wanida:</span></span>  
  
    ```  
    EXEC AddEmp 269, 291, 'Kevin', 'Marketing Intern'  ;  
    GO  
    ```  
  
2.  <span data-ttu-id="b4e91-121">Ahora Kevin notifica a Wanida, quien notifica a Jill, quien, a su vez, notifica a David.</span><span class="sxs-lookup"><span data-stu-id="b4e91-121">Now Kevin reports to Wanida, who reports to Jill, who reports to David.</span></span> <span data-ttu-id="b4e91-122">Eso quiere decir que Kevin está en el nivel **/3/1/1/**.</span><span class="sxs-lookup"><span data-stu-id="b4e91-122">That means that Kevin is at level **/3/1/1/**.</span></span> <span data-ttu-id="b4e91-123">Para mover todos los subordinados de Jill a un nuevo administrador, vamos a actualizar a un nuevo valor todos los nodos que tienen **/3/** como **OrgNode** .</span><span class="sxs-lookup"><span data-stu-id="b4e91-123">To move all of Jill's subordinates to a new manager, we will update all nodes that have **/3/** as their **OrgNode** to a new value.</span></span> <span data-ttu-id="b4e91-124">Ejecute el código siguiente para actualizar a Wanida de manera que dependa de Sariya, pero dejando que Kevin dependa de Wanida:</span><span class="sxs-lookup"><span data-stu-id="b4e91-124">Execute the following code to update Wanida to report to Sariya, but keep  Kevin reporting to Wanida:</span></span>  
  
    ```  
    DECLARE @OldParent hierarchyid, @NewParent hierarchyid  
    SELECT @OldParent = OrgNode FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 119 ; -- Jill  
    SELECT @NewParent = OrgNode FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ; -- Sariya  
    DECLARE children_cursor CURSOR FOR  
    SELECT OrgNode FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(1) = @OldParent;  
    DECLARE @ChildId hierarchyid;  
    OPEN children_cursor  
    FETCH NEXT FROM children_cursor INTO @ChildId;  
    WHILE @@FETCH_STATUS = 0  
    BEGIN  
    START:  
        DECLARE @NewId hierarchyid;  
        SELECT @NewId = @NewParent.GetDescendant(MAX(OrgNode), NULL)  
        FROM HumanResources.EmployeeOrg WHERE OrgNode.GetAncestor(1) = @NewParent;  
  
        UPDATE HumanResources.EmployeeOrg  
        SET OrgNode = OrgNode.GetReparentedValue(@ChildId, @NewId)  
        WHERE OrgNode.IsDescendantOf(@ChildId) = 1;  
        IF @@error <> 0 GOTO START -- On error, retry  
            FETCH NEXT FROM children_cursor INTO @ChildId;  
    END  
    CLOSE children_cursor;  
    DEALLOCATE children_cursor;  
  
    ```  
  
3.  <span data-ttu-id="b4e91-125">Ejecute el código siguiente para ver el resultado:</span><span class="sxs-lookup"><span data-stu-id="b4e91-125">Execute the following code to see the result:</span></span>  
  
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
/1/1//2      0x5AD0  3        291        Kevin   Marketing Intern  
/2/          0x68    1        271        John    Marketing Specialist  
/2/1/        0x6AC0  2        272        Mary    Marketing Assistant  
/3/          0x78    1        119        Jill    Marketing Specialist  
```  
  
 <span data-ttu-id="b4e91-126">El árbol completo de la organización que había notificado a Jill (tanto Wanida como Kevin) ahora notifica a Sariya.</span><span class="sxs-lookup"><span data-stu-id="b4e91-126">The entire organizational tree that had reported to Jill (both Wanida and Kevin) now reports to Sariya.</span></span>  
  
 <span data-ttu-id="b4e91-127">Para conseguir un procedimiento almacenado que reorganice una sección de una jerarquía, consulte la sección "Mover los subárboles" de [Mover los subárboles](../hierarchical-data-sql-server.md#BKMK_MovingSubtrees).</span><span class="sxs-lookup"><span data-stu-id="b4e91-127">For a stored procedure to reorganize a section of a hierarchy, see the "Moving Subtrees" section of [Moving Subtrees](../hierarchical-data-sql-server.md#BKMK_MovingSubtrees).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b4e91-128">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="b4e91-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b4e91-129">Resumen: Administración de los datos de una tabla jerárquica</span><span class="sxs-lookup"><span data-stu-id="b4e91-129">Summary: Managing Data in a Hierarchical Table</span></span>](lesson-2-5-summary-managing-data-in-a-hierarchical-table.md)  
  
  
