---
title: Modificación de restricciones CHECK | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, modifying
- modifying constraints
- constraints [SQL Server], check
- constraints [SQL Server], modifying
ms.assetid: f22daef8-e350-40ef-8ff0-b5f87d1d9e56
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8377c80590612c8b68c315f7c37823eb8f5c5093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674026"
---
# <a name="modify-check-constraints"></a><span data-ttu-id="46f76-102">Modificar restricciones CHECK</span><span class="sxs-lookup"><span data-stu-id="46f76-102">Modify Check Constraints</span></span>
  <span data-ttu-id="46f76-103">Puede modificar una restricción CHECK en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] si desea cambiar la expresión de la restricción o las opciones que habilitan o deshabilitan la restricción para condiciones específicas.</span><span class="sxs-lookup"><span data-stu-id="46f76-103">You can modify a check constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] when you want to change the constraint expression or the options that enable or disable the constraint for specific conditions.</span></span>  
  
 <span data-ttu-id="46f76-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="46f76-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="46f76-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="46f76-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="46f76-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="46f76-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="46f76-107">**Para modificar una restricción CHECK con:**</span><span class="sxs-lookup"><span data-stu-id="46f76-107">**To modify a check constraint using:**</span></span>  
  
     [<span data-ttu-id="46f76-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="46f76-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="46f76-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="46f76-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="46f76-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="46f76-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="46f76-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="46f76-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="46f76-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="46f76-112">Permissions</span></span>  
 <span data-ttu-id="46f76-113">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="46f76-113">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="46f76-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="46f76-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-check-constraint"></a><span data-ttu-id="46f76-115">Para modificar una restricción CHECK</span><span class="sxs-lookup"><span data-stu-id="46f76-115">To modify a check constraint</span></span>  
  
1.  <span data-ttu-id="46f76-116">En el **Explorador de objetos**, haga clic con el botón derecho en la tabla que contiene la restricción CHECK y seleccione **Diseñar**.</span><span class="sxs-lookup"><span data-stu-id="46f76-116">In the **Object Explorer**, right-click the table containing the check constraint and select **Design**.</span></span>  
  
2.  <span data-ttu-id="46f76-117">En el menú **Diseñador de tablas**, haga clic en **Restricciones CHECK...** .</span><span class="sxs-lookup"><span data-stu-id="46f76-117">On the **Table Designer** menu, click **Check Constraints...**.</span></span>  
  
3.  <span data-ttu-id="46f76-118">En el cuadro de diálogo **Restricciones CHECK** , en **Restricción CHECK seleccionada**, seleccione la restricción que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="46f76-118">In the **Check Constraints** dialog box, under **Selected Check Constraint**, select the constraint you wish to edit.</span></span>  
  
4.  <span data-ttu-id="46f76-119">Complete una de las acciones descritas en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="46f76-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="46f76-120">A</span><span class="sxs-lookup"><span data-stu-id="46f76-120">To</span></span>|<span data-ttu-id="46f76-121">Siga estos pasos</span><span class="sxs-lookup"><span data-stu-id="46f76-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="46f76-122">Modificar la expresión de restricción</span><span class="sxs-lookup"><span data-stu-id="46f76-122">Edit the constraint expression</span></span>|<span data-ttu-id="46f76-123">Escriba la nueva expresión en el campo **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="46f76-123">Type the new expression in the **Expression** field.</span></span>|  
    |<span data-ttu-id="46f76-124">Cambiar el nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="46f76-124">Rename the constraint</span></span>|<span data-ttu-id="46f76-125">Escriba un nuevo nombre en el campo **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="46f76-125">Type a new name in the **Name** field.</span></span>|  
    |<span data-ttu-id="46f76-126">Aplicar la restricción a datos existentes</span><span class="sxs-lookup"><span data-stu-id="46f76-126">Apply the constraint to existing data</span></span>|<span data-ttu-id="46f76-127">Active la opción **Comprobar datos existentes al crear o habilitar** .</span><span class="sxs-lookup"><span data-stu-id="46f76-127">Select the **Check Existing Data on Creation or Enabling** option.</span></span>|  
    |<span data-ttu-id="46f76-128">Deshabilitar la restricción cuando se agregan nuevos datos a la tabla o cuando se actualizan datos existentes en la tabla.</span><span class="sxs-lookup"><span data-stu-id="46f76-128">Disable the constraint when new data is added to the table or when existing data is updated in the table.</span></span>|<span data-ttu-id="46f76-129">Desactive la opción **Exigir restricción para INSERT y UPDATE** .</span><span class="sxs-lookup"><span data-stu-id="46f76-129">Clear the **Enforce Constraint for INSERTs and UPDATEs** option.</span></span>|  
    |<span data-ttu-id="46f76-130">Deshabilitar la restricción cuando un agente de replicación inserta o actualiza datos en una tabla.</span><span class="sxs-lookup"><span data-stu-id="46f76-130">Disable the constraint when a replication agent inserts or updates data in your table.</span></span>|<span data-ttu-id="46f76-131">Desactive la opción **Exigir para replicación** .</span><span class="sxs-lookup"><span data-stu-id="46f76-131">Clear the **Enforce For Replication** option.</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="46f76-132">Algunas bases de datos tienen diferente funcionalidad para las restricciones CHECK.</span><span class="sxs-lookup"><span data-stu-id="46f76-132">Some databases have different functionality for check constraints.</span></span>  
  
5.  <span data-ttu-id="46f76-133">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="46f76-133">Click **Close**.</span></span>  
  
6.  <span data-ttu-id="46f76-134">En el menú **Archivo** , haga clic en **Guardar**_table name_.</span><span class="sxs-lookup"><span data-stu-id="46f76-134">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="46f76-135">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="46f76-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="46f76-136">**Para modificar una restricción CHECK**</span><span class="sxs-lookup"><span data-stu-id="46f76-136">**To modify a check constraint**</span></span>  
  
 <span data-ttu-id="46f76-137">Para modificar una restricción `CHECK` mediante [!INCLUDE[tsql](../../includes/tsql-md.md)], primero deberá eliminar la restricción `CHECK` existente y, a continuación, volver a crearla con la nueva definición.</span><span class="sxs-lookup"><span data-stu-id="46f76-137">To modify a `CHECK` constraint using [!INCLUDE[tsql](../../includes/tsql-md.md)], you must first delete the existing `CHECK` constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="46f76-138">Para obtener más información, vea [Eliminar restricciones CHECK](delete-check-constraints.md) y [Crear restricciones CHECK](create-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="46f76-138">For more information, see [Delete Check Constraints](delete-check-constraints.md) and [Create Check Constraints](create-check-constraints.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
