---
title: Modificación de restricciones UNIQUE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying constraints
- UNIQUE constraints [SQL Server], modifying
- constraints [SQL Server], modifying
- constraints [SQL Server], unique
ms.assetid: fddbdc9e-958b-4614-8e88-6ca205d64a4e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 74b044202f7e8e9bc762f025833cf2d0ff84c4c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678123"
---
# <a name="modify-unique-constraints"></a><span data-ttu-id="311b9-102">Modificar restricciones UNIQUE</span><span class="sxs-lookup"><span data-stu-id="311b9-102">Modify Unique Constraints</span></span>
  <span data-ttu-id="311b9-103">Puede modificar una restricción UNIQUE en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="311b9-103">You can modify a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="311b9-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="311b9-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="311b9-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="311b9-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="311b9-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="311b9-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="311b9-107">**Para modificar una restricción UNIQUE con:**</span><span class="sxs-lookup"><span data-stu-id="311b9-107">**To modify a unique constraint using:**</span></span>  
  
     [<span data-ttu-id="311b9-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="311b9-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="311b9-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="311b9-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="311b9-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="311b9-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="311b9-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="311b9-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="311b9-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="311b9-112">Permissions</span></span>  
 <span data-ttu-id="311b9-113">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="311b9-113">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="311b9-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="311b9-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-unique-constraint"></a><span data-ttu-id="311b9-115">Para modificar una restricción UNIQUE</span><span class="sxs-lookup"><span data-stu-id="311b9-115">To modify a unique constraint</span></span>  
  
1.  <span data-ttu-id="311b9-116">En el **Explorador de objetos**, haga clic con el botón derecho en la tabla que contiene la restricción UNIQUE y seleccione **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="311b9-116">In the **Object Explorer**, right-click the table containing the unique constraint and select **Design**.</span></span>  
  
2.  <span data-ttu-id="311b9-117">En el menú **Diseñador de tablas**, haga clic en **Índices o claves...** .</span><span class="sxs-lookup"><span data-stu-id="311b9-117">On the **Table Designer** menu, click **Indexes/Keys...**.</span></span>  
  
3.  <span data-ttu-id="311b9-118">En el cuadro de diálogo **Índices o claves** , en **Clave principal o única, o índice seleccionado**, seleccione la restricción que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="311b9-118">In the **Indexes/Keys** dialog box, under **Selected Primary/Unique Key or Index**, select the constraint you wish to edit.</span></span>  
  
4.  <span data-ttu-id="311b9-119">Complete una de las acciones descritas en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="311b9-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="311b9-120">A</span><span class="sxs-lookup"><span data-stu-id="311b9-120">To</span></span>|<span data-ttu-id="311b9-121">Siga estos pasos</span><span class="sxs-lookup"><span data-stu-id="311b9-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="311b9-122">Cambiar las columnas a las que está asociada la restricción</span><span class="sxs-lookup"><span data-stu-id="311b9-122">Change the columns that the constraint is associated with</span></span>|<span data-ttu-id="311b9-123">1) En la cuadrícula situada debajo de **(General)** , haga clic en **Columnas** y después en los puntos suspensivos **(...)** situados a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="311b9-123">1) In the grid under **(General)**, click **Columns** and then click the ellipses **(...)** to the right of the property.</span></span><br /><br /> <span data-ttu-id="311b9-124">2) En el cuadro de diálogo **Columnas de índice** , especifique la nueva columna o criterio de ordenación (o ambos) del índice.</span><span class="sxs-lookup"><span data-stu-id="311b9-124">2) In the **Index Columns** dialog box, specify the new column or sort order or both for the index.</span></span>|  
    |<span data-ttu-id="311b9-125">Cambiar el nombre de la restricción</span><span class="sxs-lookup"><span data-stu-id="311b9-125">Rename the constraint</span></span>|<span data-ttu-id="311b9-126">En la cuadrícula situada debajo de **Identidad**, escriba un nuevo nombre en el cuadro **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="311b9-126">In the grid under **Identity**, type a new name in the **Name** box.</span></span> <span data-ttu-id="311b9-127">Asegúrese de que el nuevo nombre no esté duplicado en la lista **Clave principal o única, o índice seleccionado** .</span><span class="sxs-lookup"><span data-stu-id="311b9-127">Make sure that your new name does not duplicate a name in the **Selected Primary/Unique Key or Index** list.</span></span>|  
    |<span data-ttu-id="311b9-128">Establecer la opción de índice clúster</span><span class="sxs-lookup"><span data-stu-id="311b9-128">Set the clustered option</span></span>|<span data-ttu-id="311b9-129">En la cuadrícula situada debajo de **Diseñador de tablas**, seleccione **Crear como CLUSTERED** y, en el menú desplegable, elija Sí para crear un índice agrupado o No para crear un índice no agrupado.</span><span class="sxs-lookup"><span data-stu-id="311b9-129">In the grid under **Table Designer**, select **Create As Clustered** and from the dropdown choose Yes to create a clustered index and No to create a nonclustered one.</span></span> <span data-ttu-id="311b9-130">Solo puede existir un índice clúster por tabla.</span><span class="sxs-lookup"><span data-stu-id="311b9-130">Only one clustered index can exist per table.</span></span> <span data-ttu-id="311b9-131">Si ya existe un índice clúster en esta tabla, deberá desactivar esta configuración en el índice original.</span><span class="sxs-lookup"><span data-stu-id="311b9-131">If a clustered index already exists in this table, you must clear this setting on the original index.</span></span>|  
    |<span data-ttu-id="311b9-132">Definir un factor de relleno</span><span class="sxs-lookup"><span data-stu-id="311b9-132">Define a fill factor</span></span>|<span data-ttu-id="311b9-133">En la cuadrícula situada debajo de **Diseñador de tablas**, expanda la categoría **Especificación de relleno** y escriba un entero de 0 a 100 en el cuadro **Factor de relleno** .</span><span class="sxs-lookup"><span data-stu-id="311b9-133">In the grid under **Table Designer**, expand the **Fill Specification** category and type an integer from 0 to 100 in the **Fill Factor** box.</span></span>|  
  
5.  <span data-ttu-id="311b9-134">En el menú **Archivo** , haga clic en **Guardar**_table name_.</span><span class="sxs-lookup"><span data-stu-id="311b9-134">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="to-modify-a-unique-constraint"></a><a name="TsqlProcedure"></a> <span data-ttu-id="311b9-135">**Para modificar una restricción UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="311b9-135">**To modify a unique constraint**</span></span>  
  
 <span data-ttu-id="311b9-136">Para modificar una restricción UNIQUE mediante Transact-SQL, deberá eliminar la restricción UNIQUE existente y, a continuación, volver a crearla con la nueva definición.</span><span class="sxs-lookup"><span data-stu-id="311b9-136">To modify a UNIQUE constraint using Transact-SQL, you must first delete the existing UNIQUE constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="311b9-137">Para obtener más información, consulte [Delete Unique Constraints](delete-unique-constraints.md) y [Create Unique Constraints](create-unique-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="311b9-137">For more information, see [Delete Unique Constraints](delete-unique-constraints.md) and [Create Unique Constraints](create-unique-constraints.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
