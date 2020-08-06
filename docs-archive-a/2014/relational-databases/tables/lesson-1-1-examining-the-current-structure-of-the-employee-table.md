---
title: Examen de la estructura actual de la tabla Employee | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- examining the current structure of the employee
ms.assetid: d546a820-105a-417d-ac35-44a6d1d70ac6
author: stevestein
ms.author: sstein
ms.openlocfilehash: b7f63773ebc1f28fb24f8f1000c3f87ee4d50544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661864"
---
# <a name="examining-the-current-structure-of-the-employee-table"></a><span data-ttu-id="fda24-102">Examen de la estructura actual de la tabla Empleado</span><span class="sxs-lookup"><span data-stu-id="fda24-102">Examining the Current Structure of the Employee Table</span></span>
  <span data-ttu-id="fda24-103"> La base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] contiene una tabla llamada **Employee** en el esquema **HumanResources**.</span><span class="sxs-lookup"><span data-stu-id="fda24-103">The sample [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database contains an **Employee** table in the **HumanResources** schema.</span></span> <span data-ttu-id="fda24-104">Para evitar cambiar la tabla original, este paso realiza una copia de la tabla **Employee** denominada **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="fda24-104">To avoid changing the original table, this step makes a copy of the **Employee** table named **EmployeeDemo**.</span></span> <span data-ttu-id="fda24-105">Para simplificar el ejemplo, copie solo cinco columnas de la tabla original.</span><span class="sxs-lookup"><span data-stu-id="fda24-105">To simplify the example, you only copy five columns from the original table.</span></span> <span data-ttu-id="fda24-106">A continuación, consulte la tabla **humanresources. EmployeeDemo** para revisar cómo se estructuran los datos en una tabla sin utilizar el `hierarchyid` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="fda24-106">Then, you query the **HumanResources.EmployeeDemo** table to review how the data is structured in a table without using the `hierarchyid` data type.</span></span>  
  
### <a name="to-copy-the-employee-table"></a><span data-ttu-id="fda24-107">Para copiar la tabla Employee</span><span class="sxs-lookup"><span data-stu-id="fda24-107">To copy the Employee table</span></span>  
  
1.  <span data-ttu-id="fda24-108">En una ventana del editor de consultas, ejecute el código siguiente para copiar la estructura y los datos de la tabla **Employee** en una nueva tabla denominada **EmployeeDemo**.</span><span class="sxs-lookup"><span data-stu-id="fda24-108">In a Query Editor window, run the following code to copy the table structure and data from the **Employee** table into a new table named **EmployeeDemo**.</span></span>  
  
    ```  
    USE AdventureWorks ;  
    GO  
  
    SELECT EmployeeID, LoginID, ManagerID, Title, HireDate   
    INTO HumanResources.EmployeeDemo   
    FROM HumanResources.Employee ;  
    GO  
    ```  
  
### <a name="to-examine-the-structure-and-data-of-the-employeedemo-table"></a><span data-ttu-id="fda24-109">Para examinar la estructura y los datos de la tabla EmployeeDemo</span><span class="sxs-lookup"><span data-stu-id="fda24-109">To examine the structure and data of the EmployeeDemo table</span></span>  
  
-   <span data-ttu-id="fda24-110">Esta nueva tabla **EmployeeDemo** representa una tabla típica en una base de datos existente que podría desear migrar a una nueva estructura.</span><span class="sxs-lookup"><span data-stu-id="fda24-110">This new **EmployeeDemo** table represents a typical table in an existing database that you might want to migrate to a new structure.</span></span> <span data-ttu-id="fda24-111">En una ventana del editor de consultas, ejecute el código siguiente para mostrar cómo la tabla utiliza una autocombinación para mostrar las relaciones empleado/administrador:</span><span class="sxs-lookup"><span data-stu-id="fda24-111">In a Query Editor window, run the following code to show how the table uses a self join to display the employee/manager relationships:</span></span>  
  
    ```  
    SELECT   
         Mgr.EmployeeID AS MgrID, Mgr.LoginID AS Manager,   
         Emp.EmployeeID AS E_ID, Emp.LoginID, Emp.Title  
    FROM HumanResources.EmployeeDemo AS Emp  
    LEFT JOIN HumanResources.EmployeeDemo AS Mgr  
    ON Emp.ManagerID = Mgr.EmployeeID  
    ORDER BY MgrID, E_ID  
    ```  
  
     [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
    ```  
    MgrID Manager                 E_ID LoginID                  Title  
    NULL NULL                      109 adventure-works\ken0     Chief Executive Officer  
    3    adventure-works\roberto0  4   adventure-works\rob0     Senior Tool Designer  
    3    adventure-works\roberto0  9   adventure-works\gail0    Design Engineer  
    3    adventure-works\roberto0  11  adventure-works\jossef0  Design Engineer  
    3    adventure-works\roberto0  158 adventure-works\dylan0   Research and Development Manager  
    3    adventure-works\roberto0  263 adventure-works\ovidiu0  Senior Tool Designer  
    3    adventure-works\roberto0  267 adventure-works\michael8 Senior Design Engineer  
    3    adventure-works\roberto0  270 adventure-works\sharon0  Design Engineer  
    6    adventure-works\david0    2   adventure-works\kevin0   Marketing Assistant  
    ...  
    ```  
  
     <span data-ttu-id="fda24-112">Los resultados continúan hasta un total de 290 filas.</span><span class="sxs-lookup"><span data-stu-id="fda24-112">The results continue for a total of 290 rows.</span></span>  
  
 <span data-ttu-id="fda24-113">Observe que la cláusula `ORDER BY` hace que la lista de salida muestre juntos los informes directos de cada nivel de administración.</span><span class="sxs-lookup"><span data-stu-id="fda24-113">Notice that the `ORDER BY` clause caused the output to list the direct reports of each management level together.</span></span> <span data-ttu-id="fda24-114">Por ejemplo, los siete informes directos de **MgrID** 3 (roberto0) aparecen agrupados.</span><span class="sxs-lookup"><span data-stu-id="fda24-114">For instance, all seven of the direct reports of **MgrID** 3 (roberto0) are listed adjacent to each other.</span></span> <span data-ttu-id="fda24-115">Aunque no imposible, es mucho más difícil de agrupar a todos aquellos que crean informes para **MgrID** 3.</span><span class="sxs-lookup"><span data-stu-id="fda24-115">Although not impossible, it is much more difficult to group all those who eventually report to **MgrID** 3.</span></span>  
  
 <span data-ttu-id="fda24-116">En la tarea siguiente, crearemos una nueva tabla con un tipo de datos `hierarchyid` y pasaremos los datos a la nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="fda24-116">In the next task, we will create a new table with a `hierarchyid` data type, and move the data into the new table.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="fda24-117">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="fda24-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="fda24-118">Rellenar una tabla con los datos jerárquicos existentes</span><span class="sxs-lookup"><span data-stu-id="fda24-118">Populating a Table with Existing Hierarchical Data</span></span>](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md)  
  
  
