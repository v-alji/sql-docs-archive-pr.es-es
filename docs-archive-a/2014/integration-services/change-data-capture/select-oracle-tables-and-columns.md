---
title: Seleccionar tablas y columnas de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- selTabCol
ms.assetid: bf73f80e-a954-4c5f-874e-17fdd4082715
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d51e597f1210643b1543ed981045ade7b2fc2b62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671123"
---
# <a name="select-oracle-tables-and-columns"></a><span data-ttu-id="d821b-102">Seleccionar tablas y columnas de Oracle</span><span class="sxs-lookup"><span data-stu-id="d821b-102">Select Oracle Tables and Columns</span></span>
  <span data-ttu-id="d821b-103">Use la página Seleccionar tablas y columnas de Oracle para seleccionar las tablas de la base de datos de origen de Oracle donde se capturan cambios.</span><span class="sxs-lookup"><span data-stu-id="d821b-103">Use the Select Oracle Tables and Columns page to select the tables from the Oracle source database where changes are captured.</span></span> <span data-ttu-id="d821b-104">Esta página contiene los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d821b-104">This page has the following elements:</span></span>  
  
## <a name="options"></a><span data-ttu-id="d821b-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="d821b-105">Options</span></span>  
 <span data-ttu-id="d821b-106">**Lista de la tabla**</span><span class="sxs-lookup"><span data-stu-id="d821b-106">**Table list**</span></span>  
 <span data-ttu-id="d821b-107">La lista de tablas tiene tres columnas:</span><span class="sxs-lookup"><span data-stu-id="d821b-107">The table list has three columns:</span></span>  
  
-   <span data-ttu-id="d821b-108">**Nombre de tabla de Oracle**: nombre de la tabla, incluido el esquema de tabla.</span><span class="sxs-lookup"><span data-stu-id="d821b-108">**Oracle Table Name**: The name of the table, including the table schema.</span></span>  
  
-   <span data-ttu-id="d821b-109">**Instancia de captura**: nombre de la instancia de captura que se usa para denominar los objetos de captura de datos modificados específicos de una instancia.</span><span class="sxs-lookup"><span data-stu-id="d821b-109">**Capture Instance**: The name of the capture instance used to name instance-specific change data capture objects.</span></span> <span data-ttu-id="d821b-110">La instancia de captura no puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="d821b-110">The capture instance cannot be NULL.</span></span>  
  
     <span data-ttu-id="d821b-111">Si no se especifica, el nombre se obtiene del nombre del esquema de origen al que se agrega el nombre de la tabla de origen en el formato `<schema-name>_<table-name>`.</span><span class="sxs-lookup"><span data-stu-id="d821b-111">If not specified, the name is derived from the source schema name plus the source table name in the format `<schema-name>_<table-name>`.</span></span> <span data-ttu-id="d821b-112">El nombre de la instancia de captura no puede tener más de 100 caracteres y debe ser único dentro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d821b-112">The capture instance name cannot exceed 100 characters and must be unique within the database.</span></span>  
  
     <span data-ttu-id="d821b-113">Puede hacer clic en cualquier celda de esta columna para editar manualmente **capture_instance**.</span><span class="sxs-lookup"><span data-stu-id="d821b-113">You can click in any cell in this column to manually edit the **capture_instance**.</span></span>  
  
-   <span data-ttu-id="d821b-114">**Rol de seguridad**: nombre del rol de acceso de base de datos usado para controlar el acceso a los datos modificados.</span><span class="sxs-lookup"><span data-stu-id="d821b-114">**Security Role**: The name of the database gating role used to control access to change data.</span></span>  
  
     <span data-ttu-id="d821b-115">Puede hacer clic en cualquier celda de esta columna para editar manualmente **security_role**.</span><span class="sxs-lookup"><span data-stu-id="d821b-115">You can click in any cell in this column to manually edit the **security_role**.</span></span>  
  
 <span data-ttu-id="d821b-116">**Agregar tablas**</span><span class="sxs-lookup"><span data-stu-id="d821b-116">**Add Tables**</span></span>  
 <span data-ttu-id="d821b-117">Haga clic en **Agregar tablas** para abrir el cuadro de diálogo Selección de tabla, donde puede [Seleccionar tablas de Oracle para capturar cambios](select-oracle-tables-for-capturing-changes.md).</span><span class="sxs-lookup"><span data-stu-id="d821b-117">Click **Add Tables** to open the Table Selection dialog box where you can [Select Oracle Tables for Capturing Changes](select-oracle-tables-for-capturing-changes.md).</span></span>  
  
 <span data-ttu-id="d821b-118">**Edición**</span><span class="sxs-lookup"><span data-stu-id="d821b-118">**Edit**</span></span>  
 <span data-ttu-id="d821b-119">Seleccione una tabla de la lista y seleccione **Editar** para abrir el cuadro de diálogo **Propiedades** de la tabla, donde puede [Realizar cambios en las tablas seleccionadas para capturar cambios](make-changes-to-the-tables-selected-for-capturing-changes.md).</span><span class="sxs-lookup"><span data-stu-id="d821b-119">Select a table from the list and select **Edit** to open the **Properties** dialog box for that table where you can [Make Changes to the Tables Selected for Capturing Changes](make-changes-to-the-tables-selected-for-capturing-changes.md).</span></span>  
  
 <span data-ttu-id="d821b-120">**Remove**</span><span class="sxs-lookup"><span data-stu-id="d821b-120">**Remove**</span></span>  
 <span data-ttu-id="d821b-121">Seleccione una tabla de la lista y haga clic en **Quitar** para quitar la tabla de la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="d821b-121">Select a table from the list and click **Remove** to remove the table from the CDC instance.</span></span>  
  
 <span data-ttu-id="d821b-122">Después de [Seleccionar tablas de Oracle para capturar cambios](select-oracle-tables-for-capturing-changes.md) o [Realizar cambios en las tablas seleccionadas para capturar cambios](make-changes-to-the-tables-selected-for-capturing-changes.md) con los cuadros de diálogo correspondientes, haga clic en **Siguiente** para [Generar y ejecutar el script de registro complementario](generate-and-run-the-supplemental-logging-script.md).</span><span class="sxs-lookup"><span data-stu-id="d821b-122">After you [Select Oracle Tables for Capturing Changes](select-oracle-tables-for-capturing-changes.md) and/or [Make Changes to the Tables Selected for Capturing Changes](make-changes-to-the-tables-selected-for-capturing-changes.md) using the correct dialog boxes, click **Next** to [Generate and Run the Supplemental Logging Script](generate-and-run-the-supplemental-logging-script.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d821b-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d821b-123">See Also</span></span>  
 <span data-ttu-id="d821b-124">[Cómo crear la instancia de base de datos de cambios de SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="d821b-124">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 <span data-ttu-id="d821b-125">[Editar tablas](edit-tables.md) </span><span class="sxs-lookup"><span data-stu-id="d821b-125">[Edit Tables](edit-tables.md) </span></span>  
 <span data-ttu-id="d821b-126">[Agregar tablas a una instancia CDC](add-tables-to-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="d821b-126">[Add Tables to a CDC Instance](add-tables-to-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="d821b-127">Editar las propiedades de tabla</span><span class="sxs-lookup"><span data-stu-id="d821b-127">Edit the Table Properties</span></span>](edit-the-table-properties.md)  
  
  
