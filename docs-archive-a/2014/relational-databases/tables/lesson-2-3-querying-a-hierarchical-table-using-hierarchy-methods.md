---
title: Realización de una consulta a una tabla jerárquica mediante métodos de jerarquía | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 3b4f7dae-65b5-4d8d-8641-87aba9aa692d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6c86c8e8678fc821dc3796a511349c1c3498bdb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674028"
---
# <a name="querying-a-hierarchical-table-using-hierarchy-methods"></a><span data-ttu-id="60962-102">Realizar una consulta a una tabla jerárquica mediante métodos de jerarquía</span><span class="sxs-lookup"><span data-stu-id="60962-102">Querying a Hierarchical Table Using Hierarchy Methods</span></span>
  <span data-ttu-id="60962-103">Ahora que está totalmente rellena la tabla HumanResources.EmployeeOrg, esta tarea mostrará cómo realizar una consulta en la jerarquía utilizando alguno de los métodos jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="60962-103">Now that the HumanResources.EmployeeOrg table is fully populated, this task will show you how to query the hierarchy using some of the hierarchical methods.</span></span>  
  
### <a name="to-find-subordinate-nodes"></a><span data-ttu-id="60962-104">Para buscar nodos subordinados</span><span class="sxs-lookup"><span data-stu-id="60962-104">To find subordinate nodes</span></span>  
  
1.  <span data-ttu-id="60962-105">Sariya tiene un empleado subordinado.</span><span class="sxs-lookup"><span data-stu-id="60962-105">Sariya has one subordinate employee.</span></span> <span data-ttu-id="60962-106">Para consultar los subordinados de Sariya, ejecute la consulta siguiente que usa el método [IsDescendantOf](/sql/t-sql/data-types/isdescendantof-database-engine) :</span><span class="sxs-lookup"><span data-stu-id="60962-106">To query for Sariya's subordinates, execute the following query that uses the [IsDescendantOf](/sql/t-sql/data-types/isdescendantof-database-engine) method:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.IsDescendantOf(@CurrentEmployee ) = 1 ;  
    ```  
  
     <span data-ttu-id="60962-107">El resultado muestra tanto a Sariya como a Wanida.</span><span class="sxs-lookup"><span data-stu-id="60962-107">The result lists both Sariya and Wanida.</span></span> <span data-ttu-id="60962-108">Sariya aparece porque es el descendiente de nivel 0.</span><span class="sxs-lookup"><span data-stu-id="60962-108">Sariya is listed because she is the descendant at the 0 level.</span></span> <span data-ttu-id="60962-109">Wanida es el descendiente de nivel 1.</span><span class="sxs-lookup"><span data-stu-id="60962-109">Wanida is the descendant at the 1 level.</span></span>  
  
2.  <span data-ttu-id="60962-110">También se puede consultar esta información mediante el método [GetAncestor](/sql/t-sql/data-types/getancestor-database-engine) .</span><span class="sxs-lookup"><span data-stu-id="60962-110">You can also query for this information by using the [GetAncestor](/sql/t-sql/data-types/getancestor-database-engine) method.</span></span> <span data-ttu-id="60962-111">`GetAncestor` toma un argumento para el nivel que está intentando devolver.</span><span class="sxs-lookup"><span data-stu-id="60962-111">`GetAncestor` takes an argument for the level that you are trying to return.</span></span> <span data-ttu-id="60962-112">Puesto que Wanida está un nivel por debajo de Sariya, use `GetAncestor(1)` como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="60962-112">Since Wanida is one level underneath Sariya, use `GetAncestor(1)` as demonstrated in the following code:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 46 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(1) = @CurrentEmployee  
    ```  
  
     <span data-ttu-id="60962-113">Esta vez el resultado solo muestra a Wanida.</span><span class="sxs-lookup"><span data-stu-id="60962-113">This time the result lists only Wanida.</span></span>  
  
3.  <span data-ttu-id="60962-114">Ahora cambie `@CurrentEmployee` a David (EmployeeID 6) y el nivel a 2.</span><span class="sxs-lookup"><span data-stu-id="60962-114">Now change the `@CurrentEmployee` to David (EmployeeID 6) and the level to 2.</span></span> <span data-ttu-id="60962-115">Ejecute lo siguiente para que también devuelva a Wanida:</span><span class="sxs-lookup"><span data-stu-id="60962-115">Execute the following to also return Wanida:</span></span>  
  
    ```  
    DECLARE @CurrentEmployee hierarchyid  
  
    SELECT @CurrentEmployee = OrgNode  
    FROM HumanResources.EmployeeOrg  
    WHERE EmployeeID = 6 ;  
  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode.GetAncestor(2) = @CurrentEmployee  
    ```  
  
     <span data-ttu-id="60962-116">Esta vez, recibe también a Mary que también notifica a David, dos niveles más abajo.</span><span class="sxs-lookup"><span data-stu-id="60962-116">This time, you also receive Mary who also reports to David, two levels down.</span></span>  
  
### <a name="to-use-getroot-and-getlevel"></a><span data-ttu-id="60962-117">Para usar GetRoot y GetLevel</span><span class="sxs-lookup"><span data-stu-id="60962-117">To use GetRoot, and GetLevel</span></span>  
  
1.  <span data-ttu-id="60962-118">A medida que la jerarquía crece, es más difícil determinar el lugar que ocupan los miembros en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="60962-118">As the hierarchy grows larger it is more difficult to determine where the members are in the hierarchy.</span></span> <span data-ttu-id="60962-119">Use el método [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) para buscar cuántos niveles existen bajo cada fila de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="60962-119">Use the [GetLevel](/sql/t-sql/data-types/getlevel-database-engine) method to find how many levels down each row is in the hierarchy.</span></span> <span data-ttu-id="60962-120">Ejecute el código siguiente para ver los niveles de todas las filas:</span><span class="sxs-lookup"><span data-stu-id="60962-120">Execute the following code to view the levels of all the rows:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode,   
    OrgNode.GetLevel() AS EmpLevel, *  
    FROM HumanResources.EmployeeOrg ;  
    GO  
  
    ```  
  
2.  <span data-ttu-id="60962-121">Use el método [GetRoot](/sql/t-sql/data-types/getroot-database-engine) para buscar el nodo raíz en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="60962-121">Use the [GetRoot](/sql/t-sql/data-types/getroot-database-engine) method to find the root node in the hierarchy.</span></span> <span data-ttu-id="60962-122">El código siguiente devuelve la fila única que es la raíz:</span><span class="sxs-lookup"><span data-stu-id="60962-122">The following code returns the single row which is the root:</span></span>  
  
    ```  
    SELECT OrgNode.ToString() AS Text_OrgNode, *  
    FROM HumanResources.EmployeeOrg  
    WHERE OrgNode = hierarchyid::GetRoot() ;  
    GO  
  
    ```  
  
 <span data-ttu-id="60962-123">La tarea siguiente reorganizará la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="60962-123">The next task will reorganize the hierarchy.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="60962-124">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="60962-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="60962-125">Reordenar los datos de una tabla jerárquica mediante métodos jerárquicos</span><span class="sxs-lookup"><span data-stu-id="60962-125">Reordering Data in a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-4-reordering-data-in-a-hierarchical-table-using-hierarchical-methods.md)  
  
  
