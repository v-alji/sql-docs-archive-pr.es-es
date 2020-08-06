---
title: Modificación de claves principales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying primary keys
- primary keys [SQL Server], modifying
ms.assetid: 8e2a15ba-1cd1-4408-b860-16c3ee37d635
author: stevestein
ms.author: sstein
ms.openlocfilehash: f24deeac45491f9097d90ee0407464f928a0713b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661859"
---
# <a name="modify-primary-keys"></a><span data-ttu-id="b5459-102">Modificar claves principales</span><span class="sxs-lookup"><span data-stu-id="b5459-102">Modify Primary Keys</span></span>
  <span data-ttu-id="b5459-103">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , una clave principal puede modificarse mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5459-103">You can modify a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b5459-104">Puede modificar la clave principal de una tabla si cambia el orden de las columnas, el nombre del índice, la opción agrupada o el factor de relleno.</span><span class="sxs-lookup"><span data-stu-id="b5459-104">You can modify the primary key of a table by changing the column order, index name, clustered option, or fill factor.</span></span>  
  
 <span data-ttu-id="b5459-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="b5459-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b5459-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="b5459-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b5459-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b5459-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b5459-108">**Para modificar una clave principal con:**</span><span class="sxs-lookup"><span data-stu-id="b5459-108">**To modify a primary key, using:**</span></span>  
  
     [<span data-ttu-id="b5459-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b5459-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b5459-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5459-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b5459-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="b5459-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b5459-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b5459-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b5459-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="b5459-113">Permissions</span></span>  
 <span data-ttu-id="b5459-114">Requiere el permiso ALTER en la tabla.</span><span class="sxs-lookup"><span data-stu-id="b5459-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b5459-115">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b5459-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-primary-key"></a><span data-ttu-id="b5459-116">Para modificar una clave principal</span><span class="sxs-lookup"><span data-stu-id="b5459-116">To modify a primary key</span></span>  
  
1.  <span data-ttu-id="b5459-117">Abra el Diseñador de tablas de la tabla cuya clave principal quiere modificar; después, haga clic con el botón derecho en el Diseñador de tablas y elija **Índices o claves** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b5459-117">Open the Table Designer for the table whose primary key you want to modify, right-click in the Table Designer, and choose **Indexes/Keys** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="b5459-118">En el cuadro de diálogo **Índices o claves** , seleccione el índice de clave principal en la lista **Índice o clave Primary/Unique seleccionados** .</span><span class="sxs-lookup"><span data-stu-id="b5459-118">In the **Indexes/Keys** dialog box, select the primary key index from the **Selected Primary/Unique Key or Index** list.</span></span>  
  
3.  <span data-ttu-id="b5459-119">Complete una de las acciones descritas en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5459-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="b5459-120">A</span><span class="sxs-lookup"><span data-stu-id="b5459-120">To</span></span>|<span data-ttu-id="b5459-121">Siga estos pasos</span><span class="sxs-lookup"><span data-stu-id="b5459-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="b5459-122">Cambiar el nombre de la clave principal</span><span class="sxs-lookup"><span data-stu-id="b5459-122">Rename the primary key</span></span>|<span data-ttu-id="b5459-123">Escriba un nuevo nombre en el cuadro **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="b5459-123">Type a new name in the **Name** box.</span></span> <span data-ttu-id="b5459-124">Asegúrese de que el nuevo nombre no esté duplicado en la lista **Clave principal o única, o índice seleccionado** .</span><span class="sxs-lookup"><span data-stu-id="b5459-124">Make sure that your new name does not duplicate a name in the **Selected Primary/Unique Key or Index** list.</span></span>|  
    |<span data-ttu-id="b5459-125">Establecer la opción de índice clúster</span><span class="sxs-lookup"><span data-stu-id="b5459-125">Set the clustered option</span></span>|<span data-ttu-id="b5459-126">Para crear un índice agrupado para la clave principal, seleccione **Crear como CLUSTERED**y seleccione la opción en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b5459-126">To create a clustered index for the primary key, select **Create as CLUSTERED**, and select the option from the drop-down list box.</span></span> <span data-ttu-id="b5459-127">Solo puede existir un índice clúster por tabla.</span><span class="sxs-lookup"><span data-stu-id="b5459-127">Only one clustered index can exist per table.</span></span> <span data-ttu-id="b5459-128">Si esta opción no está disponible para el índice, antes de nada debe desactivar esta configuración en el índice clúster existente.</span><span class="sxs-lookup"><span data-stu-id="b5459-128">If this option is not available for your index, you must first clear this setting on the existing clustered index.</span></span><br /><br /> <span data-ttu-id="b5459-129">Si no está seleccionada esta opción, se crea un índice no agrupado único.</span><span class="sxs-lookup"><span data-stu-id="b5459-129">If this option is not selected, a unique nonclustered index is created.</span></span>|  
    |<span data-ttu-id="b5459-130">Definir un factor de relleno</span><span class="sxs-lookup"><span data-stu-id="b5459-130">Define a fill factor</span></span>|<span data-ttu-id="b5459-131">Expanda la categoría **Especificación de relleno** y escriba un número entero de 0 a 100 en el cuadro **Factor de relleno** .</span><span class="sxs-lookup"><span data-stu-id="b5459-131">Expand the **Fill Specification** category and type an integer from 0 to 100 in the **Fill factor** box.</span></span> <span data-ttu-id="b5459-132">Para obtener más información sobre los factores de relleno y sus usos, vea [Especificar el factor de relleno para un índice](../indexes/specify-fill-factor-for-an-index.md).</span><span class="sxs-lookup"><span data-stu-id="b5459-132">For more information about fill factors and their uses, see [Specify Fill Factor for an Index](../indexes/specify-fill-factor-for-an-index.md).</span></span>|  
    |<span data-ttu-id="b5459-133">Cambiar el orden de las columnas</span><span class="sxs-lookup"><span data-stu-id="b5459-133">Change the column order</span></span>|<span data-ttu-id="b5459-134">Haga clic en **Columnas** y, después, haga clic en los puntos suspensivos **(...)** situados a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b5459-134">Select **Columns**, and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="b5459-135">En el cuadro de diálogo  **Columnas de índice** , quite las columnas de la clave principal.</span><span class="sxs-lookup"><span data-stu-id="b5459-135">In the  **Index Columns** dialog box, remove the columns from the primary key.</span></span> <span data-ttu-id="b5459-136">A continuación, vuelva a agregar las columnas en el orden que desee.</span><span class="sxs-lookup"><span data-stu-id="b5459-136">Then add the columns back in the order you want.</span></span> <span data-ttu-id="b5459-137">Para quitar una columna de la clave, solo tiene que quitar el nombre de la columna de la lista **Nombre de columna** .</span><span class="sxs-lookup"><span data-stu-id="b5459-137">To remove a column from the key, simply remove the column name from the **Column** name list.</span></span>|  
  
4.  <span data-ttu-id="b5459-138">En el menú **Archivo** , haga clic en **Guardar**_table name_.</span><span class="sxs-lookup"><span data-stu-id="b5459-138">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b5459-139">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b5459-139">Using Transact-SQL</span></span>  
 <span data-ttu-id="b5459-140">**Para modificar una clave principal**</span><span class="sxs-lookup"><span data-stu-id="b5459-140">**To modify a primary key**</span></span>  
  
 <span data-ttu-id="b5459-141">Para modificar una restricción PRIMARY KEY mediante Transact-SQL, primero debe eliminar la restricción PRIMARY KEY existente y, a continuación, vuelva a crearla con la nueva definición.</span><span class="sxs-lookup"><span data-stu-id="b5459-141">To modify a PRIMARY KEY constraint using Transact-SQL, you must first delete the existing PRIMARY KEY constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="b5459-142">Para obtener más información, consulte [Delete Primary Keys](delete-primary-keys.md) y [Create Primary Keys](create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="b5459-142">For more information, see [Delete Primary Keys](delete-primary-keys.md) and [Create Primary Keys](create-primary-keys.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
