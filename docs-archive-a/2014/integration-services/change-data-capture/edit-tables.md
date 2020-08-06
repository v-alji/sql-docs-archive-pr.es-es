---
title: Editar tablas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- tabProps
ms.assetid: fed8fada-2abc-45e2-8228-0656f9c599cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8e8058a0c3e8b81814283f055e4c4ac2b08dd2fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663053"
---
# <a name="edit-tables"></a><span data-ttu-id="fc895-102">Editar tablas</span><span class="sxs-lookup"><span data-stu-id="fc895-102">Edit Tables</span></span>
  <span data-ttu-id="fc895-103">Use la pestaña **Tablas** para realizar cambios en las tablas y columnas que seleccionó en la base de datos de origen de Oracle.</span><span class="sxs-lookup"><span data-stu-id="fc895-103">Use the **Tables** tab to make changes to the tables and columns that you selected from the Oracle source database.</span></span> <span data-ttu-id="fc895-104">Esta pestaña contiene los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fc895-104">This tab has the following elements:</span></span>  
  
 <span data-ttu-id="fc895-105">**Lista de la tabla**</span><span class="sxs-lookup"><span data-stu-id="fc895-105">**Table list**</span></span>  
 <span data-ttu-id="fc895-106">La lista de tablas tiene tres columnas:</span><span class="sxs-lookup"><span data-stu-id="fc895-106">The table list has three columns:</span></span>  
  
-   <span data-ttu-id="fc895-107">**Nombre de tabla de Oracle**: nombre de la tabla, incluido el esquema de tabla.</span><span class="sxs-lookup"><span data-stu-id="fc895-107">**Oracle Table Name**: The name of the table, including the table schema.</span></span>  
  
-   <span data-ttu-id="fc895-108">**Instancia de captura**: nombre de la instancia de captura que se usa para denominar los objetos de captura de datos modificados específicos de una instancia.</span><span class="sxs-lookup"><span data-stu-id="fc895-108">**Capture Instance**: The name of the capture instance used to name instance-specific change data capture objects.</span></span> <span data-ttu-id="fc895-109">La instancia de captura no puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="fc895-109">The capture instance cannot be NULL.</span></span> <span data-ttu-id="fc895-110">Si no se especifica, el nombre deriva del nombre del esquema de origen más el nombre de la tabla de origen, con el formato `<schema-name>_<table-name>.` . El nombre de la instancia de captura no puede tener más de 100 caracteres y debe ser único dentro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fc895-110">If not specified, the name is derived from the source schema name plus the source table name in the format `<schema-name>_<table-name>.` The capture instance name cannot exceed 100 characters and must be unique within the database.</span></span> <span data-ttu-id="fc895-111">Puede hacer clic en cualquier celda de esta columna para editar manualmente **capture_instance**.</span><span class="sxs-lookup"><span data-stu-id="fc895-111">You can click in any cell in this column to manually edit the **capture_instance**.</span></span>  
  
-   <span data-ttu-id="fc895-112">**Rol de seguridad**: nombre del rol de base de datos usado para obtener acceso a los datos de cambios.</span><span class="sxs-lookup"><span data-stu-id="fc895-112">**Security Role**: The name of the database role used to gain access to change data.</span></span> <span data-ttu-id="fc895-113">Puede hacer clic en cualquier celda de esta columna para editar manualmente **security_role**.</span><span class="sxs-lookup"><span data-stu-id="fc895-113">You can click in any cell in this column to manually edit the **security_role**.</span></span>  
  
 <span data-ttu-id="fc895-114">**Agregar tablas**</span><span class="sxs-lookup"><span data-stu-id="fc895-114">**Add Tables**</span></span>  
 <span data-ttu-id="fc895-115">Haga clic en **Agregar tablas** para abrir el cuadro de diálogo Selección de tabla, donde puede [Agregar tablas a una instancia CDC](add-tables-to-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="fc895-115">Click **Add Tables** to open the Table Selection dialog box where you can [Add Tables to a CDC Instance](add-tables-to-a-cdc-instance.md).</span></span> <span data-ttu-id="fc895-116">La primera vez que tenga acceso a la base de datos de Oracle en esta sesión, debe [Connect to Oracle](connect-to-oracle.md).</span><span class="sxs-lookup"><span data-stu-id="fc895-116">The first time this session that you access the Oracle database, you must [Connect to Oracle](connect-to-oracle.md).</span></span>  
  
 <span data-ttu-id="fc895-117">**Edición**</span><span class="sxs-lookup"><span data-stu-id="fc895-117">**Edit**</span></span>  
 <span data-ttu-id="fc895-118">Seleccione una tabla de la lista y haga clic en **Editar** para abrir el cuadro de diálogo **Propiedades** de la tabla, donde puede [Editar las propiedades de tabla](edit-the-table-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fc895-118">Select a table from the list and select **Edit** to open the **Properties** dialog box for that table where you can [Edit the Table Properties](edit-the-table-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc895-119">No puede editar la asignación de tipos para las tablas que ya tienen tablas reflejadas.</span><span class="sxs-lookup"><span data-stu-id="fc895-119">You cannot edit type mapping for tables that already have mirror tables.</span></span> <span data-ttu-id="fc895-120">Solo puede hacerlo para las tablas nuevas.</span><span class="sxs-lookup"><span data-stu-id="fc895-120">You can do this for new tables only.</span></span>  
  
 <span data-ttu-id="fc895-121">**Remove**</span><span class="sxs-lookup"><span data-stu-id="fc895-121">**Remove**</span></span>  
 <span data-ttu-id="fc895-122">Seleccione una tabla de la lista y haga clic en **Quitar** para quitar la tabla de la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="fc895-122">Select a table from the list and click **Remove** to remove the table from the CDC instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc895-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc895-123">See Also</span></span>  
 <span data-ttu-id="fc895-124">[Cómo editar las propiedades de la instancia CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="fc895-124">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="fc895-125">Seleccione las columnas y tablas de Oracle </span><span class="sxs-lookup"><span data-stu-id="fc895-125">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
