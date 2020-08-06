---
title: Creación de una tabla mediante el tipo de datos hierarchyid | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 0d1f361f-336c-4571-99d1-f4813b2d9fc4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2c9b59795949e11cabd21b0be8de844b33d73c37
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749686"
---
# <a name="creating-a-table-using-the-hierarchyid-data-type"></a><span data-ttu-id="509b6-102">Crear una tabla mediante el tipo de datos hierarchyid</span><span class="sxs-lookup"><span data-stu-id="509b6-102">Creating a Table Using the hierarchyid Data Type</span></span>
  <span data-ttu-id="509b6-103">El ejemplo siguiente crea una tabla denominada EmployeeOrg que contiene los datos del empleado y la jerarquía correspondiente.</span><span class="sxs-lookup"><span data-stu-id="509b6-103">The following example creates a table named EmployeeOrg, which includes employee data together with their reporting hierarchy.</span></span> <span data-ttu-id="509b6-104">El ejemplo crea la tabla en la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] , aunque esta ubicación es opcional.</span><span class="sxs-lookup"><span data-stu-id="509b6-104">The example creates the table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database, but that is optional.</span></span> <span data-ttu-id="509b6-105">Para mantener un esquema sencillo del ejemplo, esta tabla solo incluye cinco columnas:</span><span class="sxs-lookup"><span data-stu-id="509b6-105">To keep the example simple, this table includes only five columns:</span></span>  
  
-   <span data-ttu-id="509b6-106">OrgNode es una columna `hierarchyid` que almacena la relación jerárquica.</span><span class="sxs-lookup"><span data-stu-id="509b6-106">OrgNode is a `hierarchyid` column that stores the hierarchical relationship.</span></span>  
  
-   <span data-ttu-id="509b6-107">OrgLevel es una columna calculada que se basa en la columna OrgNode y que almacena todos los niveles de nodos de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="509b6-107">OrgLevel is a computed column, based on the OrgNode column that stores each nodes level in the hierarchy.</span></span> <span data-ttu-id="509b6-108">Se usará para crear un índice con prioridad a la amplitud.</span><span class="sxs-lookup"><span data-stu-id="509b6-108">It will be used for a breadth-first index.</span></span>  
  
-   <span data-ttu-id="509b6-109">EmployeeID contiene el número de identificación típico del empleado que se utiliza para aplicaciones como, por ejemplo, la nómina.</span><span class="sxs-lookup"><span data-stu-id="509b6-109">EmployeeID contains the typical employee identification number that is used for applications such as payroll.</span></span> <span data-ttu-id="509b6-110">En el nuevo desarrollo de aplicaciones, las aplicaciones pueden utilizar la columna OrgNode y la columna EmployeeID independiente no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="509b6-110">In new application development, applications can use the OrgNode column and this separate EmployeeID column is not needed.</span></span>  
  
-   <span data-ttu-id="509b6-111">EmpName contiene el nombre del empleado.</span><span class="sxs-lookup"><span data-stu-id="509b6-111">EmpName contains the name of the employee.</span></span>  
  
-   <span data-ttu-id="509b6-112">Title contiene el puesto del empleado.</span><span class="sxs-lookup"><span data-stu-id="509b6-112">Title contains the title of the employee.</span></span>  
  
### <a name="to-create-the-employeeorg-table"></a><span data-ttu-id="509b6-113">Para crear la tabla EmployeeOrg</span><span class="sxs-lookup"><span data-stu-id="509b6-113">To create the EmployeeOrg table</span></span>  
  
1.  <span data-ttu-id="509b6-114">En una ventana del Editor de consultas, ejecute el código siguiente para crear la tabla `EmployeeOrg` .</span><span class="sxs-lookup"><span data-stu-id="509b6-114">In a Query Editor window, run the following code to create the `EmployeeOrg` table.</span></span> <span data-ttu-id="509b6-115">Al especificar la columna `OrgNode` como la clave principal con un índice clúster, se creará un índice con prioridad a la profundidad:</span><span class="sxs-lookup"><span data-stu-id="509b6-115">Specifying the `OrgNode` column as the primary key with a clustered index will create a depth-first index:</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    CREATE TABLE HumanResources.EmployeeOrg  
    (  
       OrgNode hierarchyid PRIMARY KEY CLUSTERED,  
       OrgLevel AS OrgNode.GetLevel(),  
       EmployeeID int UNIQUE NOT NULL,  
       EmpName varchar(20) NOT NULL,  
       Title varchar(20) NULL  
    ) ;  
    GO  
    ```  
  
2.  <span data-ttu-id="509b6-116">Ejecute el código siguiente para crear un índice compuesto en las columnas `OrgLevel` y `OrgNode` que admita búsquedas eficaces con prioridad a la amplitud:</span><span class="sxs-lookup"><span data-stu-id="509b6-116">Run the following code to create a composite index on the `OrgLevel` and `OrgNode` columns to support efficient breadth-first searches:</span></span>  
  
    ```  
    CREATE UNIQUE INDEX EmployeeOrgNc1   
    ON HumanResources.EmployeeOrg(OrgLevel, OrgNode) ;  
    GO  
    ```  
  
 <span data-ttu-id="509b6-117">Ahora ya puede usar la tabla para trabajar con datos.</span><span class="sxs-lookup"><span data-stu-id="509b6-117">The table is now ready for data.</span></span> <span data-ttu-id="509b6-118">La siguiente tarea rellenará la tabla mediante métodos jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="509b6-118">The next task will populate the table by using hierarchical methods.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="509b6-119">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="509b6-119">Next Task in Lesson</span></span>  
 [<span data-ttu-id="509b6-120">Rellenar una tabla jerárquica usando métodos jerárquicos</span><span class="sxs-lookup"><span data-stu-id="509b6-120">Populating a Hierarchical Table Using Hierarchical Methods</span></span>](lesson-2-2-populating-a-hierarchical-table-using-hierarchical-methods.md)  
  
  
