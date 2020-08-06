---
title: Tabla de ejemplo HumanResources.myTeam (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- myTeam sample table [SQL Server]
- bulk importing [SQL Server], examples
- bulk exporting [SQL Server], examples
ms.assetid: 27da45a0-c1f4-4bf4-ab24-6196e80d3834
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7d4e0cbbf42c2bdd25e3dd7c9577e4d0ec44549a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675377"
---
# <a name="humanresourcesmyteam-sample-table-sql-server"></a><span data-ttu-id="1be61-102">Tabla de ejemplo HumanResources.myTeam (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1be61-102">HumanResources.myTeam Sample Table (SQL Server)</span></span>
  <span data-ttu-id="1be61-103">Muchos de los ejemplos de código de [Importar y exportar datos masivos](bulk-import-and-export-of-data-sql-server.md) requieren una tabla de prueba especial llamada **myTeam**.</span><span class="sxs-lookup"><span data-stu-id="1be61-103">Many of the code examples in [Importing and Exporting Bulk Data](bulk-import-and-export-of-data-sql-server.md) require a special-purpose test table named **myTeam**.</span></span> <span data-ttu-id="1be61-104">Antes de poder ejecutar los ejemplos, debe crear la tabla **myTeam** en el esquema **HumanResources** de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1be61-104">Before you can run the examples, you must create the **myTeam** table in the **HumanResources** schema of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="1be61-105">es una de las bases de datos de ejemplo de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1be61-105">is one of the sample databases in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="1be61-106">La tabla **myTeam** contiene las columnas siguientes.</span><span class="sxs-lookup"><span data-stu-id="1be61-106">The **myTeam** table is contains the following columns.</span></span>  
  
|<span data-ttu-id="1be61-107">Columna</span><span class="sxs-lookup"><span data-stu-id="1be61-107">Column</span></span>|<span data-ttu-id="1be61-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1be61-108">Data type</span></span>|<span data-ttu-id="1be61-109">Nulabilidad</span><span class="sxs-lookup"><span data-stu-id="1be61-109">Nullability</span></span>|<span data-ttu-id="1be61-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1be61-110">Description</span></span>|  
|------------|---------------|-----------------|-----------------|  
|<span data-ttu-id="1be61-111">**EmployeeID**</span><span class="sxs-lookup"><span data-stu-id="1be61-111">**EmployeeID**</span></span>|`smallint`|<span data-ttu-id="1be61-112">No NULL</span><span class="sxs-lookup"><span data-stu-id="1be61-112">Not null</span></span>|<span data-ttu-id="1be61-113">Clave principal para las filas.</span><span class="sxs-lookup"><span data-stu-id="1be61-113">Primary key for the rows.</span></span> <span data-ttu-id="1be61-114">Identificador de empleado de un miembro de mi equipo.</span><span class="sxs-lookup"><span data-stu-id="1be61-114">Employee ID of a member of my team.</span></span>|  
|<span data-ttu-id="1be61-115">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1be61-115">**Name**</span></span>|`nvarchar(50)`|<span data-ttu-id="1be61-116">No NULL</span><span class="sxs-lookup"><span data-stu-id="1be61-116">Not null</span></span>|<span data-ttu-id="1be61-117">Nombre de un miembro de mi equipo.</span><span class="sxs-lookup"><span data-stu-id="1be61-117">Name of a member of my team.</span></span>|  
|<span data-ttu-id="1be61-118">**Título**</span><span class="sxs-lookup"><span data-stu-id="1be61-118">**Title**</span></span>|`nvarchar(50)`|<span data-ttu-id="1be61-119">Nullable</span><span class="sxs-lookup"><span data-stu-id="1be61-119">Nullable</span></span>|<span data-ttu-id="1be61-120">Cargo que tiene el empleado en mi equipo.</span><span class="sxs-lookup"><span data-stu-id="1be61-120">Title the employee performs on my team.</span></span>|  
|<span data-ttu-id="1be61-121">**Información preliminar**</span><span class="sxs-lookup"><span data-stu-id="1be61-121">**Background**</span></span>|`nvarchar(50)`|<span data-ttu-id="1be61-122">No NULL</span><span class="sxs-lookup"><span data-stu-id="1be61-122">Not null</span></span>|<span data-ttu-id="1be61-123">Fecha y hora de la última actualización de la fila.</span><span class="sxs-lookup"><span data-stu-id="1be61-123">Date and time the row was last updated.</span></span> <span data-ttu-id="1be61-124">(Es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="1be61-124">(Default)</span></span>|  
  
 <span data-ttu-id="1be61-125">**Para crear HumanResources.myTeam**</span><span class="sxs-lookup"><span data-stu-id="1be61-125">**To create HumanResources.myTeam**</span></span>  
  
-   <span data-ttu-id="1be61-126">Utilice las siguientes instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="1be61-126">Use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    --Create HumanResources.MyTeam:   
    USE AdventureWorks;  
    GO  
    CREATE TABLE HumanResources.myTeam   
    (EmployeeID smallint NOT NULL,  
    Name nvarchar(50) NOT NULL,  
    Title nvarchar(50) NULL,  
    Background nvarchar(50) NOT NULL DEFAULT ''  
    );  
    GO  
    ```  
  
 <span data-ttu-id="1be61-127">**Para rellenar HumanResources.myTeam**</span><span class="sxs-lookup"><span data-stu-id="1be61-127">**To populate HumanResources.myTeam**</span></span>  
  
-   <span data-ttu-id="1be61-128">Ejecute las siguientes instrucciones `INSERT` para rellenar la tabla con dos filas:</span><span class="sxs-lookup"><span data-stu-id="1be61-128">Execute following `INSERT` statements to populate the table with two rows:</span></span>  
  
    ```  
    USE AdventureWorks;  
    GO  
    INSERT INTO HumanResources.myTeam(EmployeeID,Name,Title,Background)  
       VALUES(77,'Mia Doppleganger','Administrative Assistant','Microsoft Office');  
    GO  
    INSERT INTO HumanResources.myTeam(EmployeeID,Name,Title,Background)  
       VALUES(49,'Hirum Mollicat','I.T. Specialist','Report Writing and Data Mining');  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="1be61-129">Estas instrucciones omiten la cuarta columna, `Background`.</span><span class="sxs-lookup"><span data-stu-id="1be61-129">These statements skip the fourth column, `Background`.</span></span> <span data-ttu-id="1be61-130">Tiene un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1be61-130">This has a default value.</span></span> <span data-ttu-id="1be61-131">Omitir esta columna hace que esta instrucción `INSERT` deje la columna en blanco.</span><span class="sxs-lookup"><span data-stu-id="1be61-131">Skipping this column causes this `INSERT` statement to leave this column blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be61-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1be61-132">See Also</span></span>  
 [<span data-ttu-id="1be61-133">Importar y exportar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1be61-133">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](bulk-import-and-export-of-data-sql-server.md)  
  
  
