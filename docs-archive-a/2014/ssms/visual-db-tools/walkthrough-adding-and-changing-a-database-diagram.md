---
title: 'Tutorial: Agregar y modificar un diagrama de base de datos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- database diagrams [SQL Server], about database diagrams
- database diagrams [SQL Server], designing
- database diagrams [SQL Server], creating
ms.assetid: 228caa0d-8f24-46ab-86d1-b6d8631322bc
author: stevestein
ms.author: sstein
ms.openlocfilehash: c35eb3674c817e98a25a74cd0309fc7376fe2f58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663262"
---
# <a name="walkthrough-adding-and-changing-a-database-diagram"></a><span data-ttu-id="d5d4d-102">Tutorial: Incorporación y cambio de un diagrama de base de datos</span><span class="sxs-lookup"><span data-stu-id="d5d4d-102">Walkthrough: Adding and Changing a Database Diagram</span></span>
  <span data-ttu-id="d5d4d-103">En este tutorial se muestra cómo crear y modificar un diagrama de base de datos, así como la forma de realizar cambios en la base de datos mediante el componente Diagramas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-103">This walkthrough illustrates how to create and modify a database diagram and make changes to the database through the database diagrams component.</span></span> <span data-ttu-id="d5d4d-104">También se explica cómo agregar tablas al diagrama, crear relaciones entre las tablas, crear restricciones e índices en las columnas y modificar el nivel de información que puede verse en cada tabla.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-104">You will see how to add tables to diagrams, create relationships between tables, create constraints and indexes on columns, and change the level of information you see for each table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d5d4d-105">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="d5d4d-105">Prerequisites</span></span>  
 <span data-ttu-id="d5d4d-106">Para completar esta visita guiada, necesitará:</span><span class="sxs-lookup"><span data-stu-id="d5d4d-106">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="d5d4d-107">Acceso a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5d4d-107">Access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database</span></span>  
  
-   <span data-ttu-id="d5d4d-108">Una cuenta con privilegios de `dbo` de propietario de la base de datos</span><span class="sxs-lookup"><span data-stu-id="d5d4d-108">An account with database owner `dbo` privileges</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d5d4d-109">Si intenta realizar cambios desde una cuenta sin suficientes privilegios para realizar los cambios en las tablas, aparecerá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-109">If you attempt to make changes when using an account without sufficient privileges to make changes to tables, then an error message appears.</span></span>  
  
## <a name="creating-a-diagram"></a><span data-ttu-id="d5d4d-110">Crear un diagrama</span><span class="sxs-lookup"><span data-stu-id="d5d4d-110">Creating a Diagram</span></span>  
  
#### <a name="to-create-a-new-database-diagram"></a><span data-ttu-id="d5d4d-111">Para crear un nuevo diagrama de base de datos</span><span class="sxs-lookup"><span data-stu-id="d5d4d-111">To create a new database diagram</span></span>  
  
1.  <span data-ttu-id="d5d4d-112">En el menú **Ver** , haga clic en el **Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-112">On the **View** menu, click **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="d5d4d-113">Abra el nodo Bases de datos y, luego, el nodo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5d4d-113">Open the Databases node and then open the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] node.</span></span>  
  
3.  <span data-ttu-id="d5d4d-114">Haga clic con el botón derecho en el nodo Diagramas de base de datos y elija **Nuevo diagrama de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-114">Right-click the Database Diagrams node and choose **New Database Diagram**.</span></span>  
  
     <span data-ttu-id="d5d4d-115">Si la base de datos no tiene los objetos necesarios para crear diagramas, aparece el mensaje siguiente: **Esta base de datos no tiene uno o varios de los objetos de soporte necesarios para usar diagramas de base de datos. ¿Desea crearlos?**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-115">If the database does not have objects necessary to create diagrams, the following message appears: **This database does not have one or more of the support objects required to use database diagramming. Do you wish to create them?**</span></span> <span data-ttu-id="d5d4d-116">Elija **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-116">Choose **Yes**.</span></span>  
  
     <span data-ttu-id="d5d4d-117">Aparecerá el cuadro de diálogo **Agregar tabla** .</span><span class="sxs-lookup"><span data-stu-id="d5d4d-117">The **Add Table** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="d5d4d-118">Seleccione **AddressType (persona)** y **Dirección (persona)** y, luego, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-118">Select **AddressType (Person)** and **Address (Person)** and click **Add**.</span></span>  
  
     <span data-ttu-id="d5d4d-119">Se agregan dos tablas al diagrama.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-119">Two tables are added to the diagram.</span></span>  
  
5.  <span data-ttu-id="d5d4d-120">Cierre el cuadro de diálogo **Agregar tabla** .</span><span class="sxs-lookup"><span data-stu-id="d5d4d-120">Close the **Add Table** dialog box.</span></span>  
  
#### <a name="to-view-different-column-data"></a><span data-ttu-id="d5d4d-121">Para visualizar datos de columna diferentes</span><span class="sxs-lookup"><span data-stu-id="d5d4d-121">To view different column data</span></span>  
  
1.  <span data-ttu-id="d5d4d-122">Haga clic con el botón secundario en la tabla `Address` .</span><span class="sxs-lookup"><span data-stu-id="d5d4d-122">Right-click the `Address` table.</span></span> <span data-ttu-id="d5d4d-123">En el menú contextual, seleccione **Vista de tabla**y, a continuación, haga clic en **Estándar**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-123">On the shortcut menu, point to **Table View**, and then click **Standard**.</span></span>  
  
     <span data-ttu-id="d5d4d-124">La cuadrícula de tabla muestra tres columnas: **Nombre de columna**, **Tipo de datos**, y **Permitir nulos**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-124">The table grid shows three columns: **Column Name**, **Data Type**, and **Allow Nulls**.</span></span>  
  
2.  <span data-ttu-id="d5d4d-125">Haga clic con el botón derecho en la tabla `Address` , haga clic en **Vista de tabla** y seleccione **Claves**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-125">Right-click the `Address` table, click **Table View** and select **Keys**.</span></span>  
  
     <span data-ttu-id="d5d4d-126">En la cuadrícula de la tabla se muestra una columna, con los nombres de tabla y columna.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-126">The table grid shows one column, with the table-column names.</span></span> <span data-ttu-id="d5d4d-127">Solo aparecen las columnas que participan en los índices.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-127">Only those columns participating in indexes appear.</span></span>  
  
## <a name="creating-new-tables"></a><span data-ttu-id="d5d4d-128">Crear nuevas tablas</span><span class="sxs-lookup"><span data-stu-id="d5d4d-128">Creating New Tables</span></span>  
  
#### <a name="to-create-tables-within-diagram-designer"></a><span data-ttu-id="d5d4d-129">Para crear tablas en el Diseñador de diagramas</span><span class="sxs-lookup"><span data-stu-id="d5d4d-129">To create tables within Diagram Designer</span></span>  
  
1.  <span data-ttu-id="d5d4d-130">Haga clic con el botón derecho en una zona del Diseñador de diagramas que no sea una tabla existente y elija **Nueva tabla**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-130">Right-click the Diagram Designer outside the existing tables and choose **New Table**.</span></span>  
  
2.  <span data-ttu-id="d5d4d-131">En el cuadro de diálogo **elegir nombre** , haga clic en **Aceptar** para aceptar el nombre predeterminado `Table1` .</span><span class="sxs-lookup"><span data-stu-id="d5d4d-131">In the **Choose Name** dialog box, click **OK** to accept the default name `Table1`.</span></span>  
  
     <span data-ttu-id="d5d4d-132">Aparecerá una nueva cuadrícula de tabla con tres columnas: **Nombre de columna**, **Tipo de datos**, y **Permitir nulos**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-132">A new table grid appears with three columns: **Column Name**, **Data Type**, and **Allow Nulls**.</span></span>  
  
3.  <span data-ttu-id="d5d4d-133">Agregue la siguiente información a `Table1` :</span><span class="sxs-lookup"><span data-stu-id="d5d4d-133">Add the following information to `Table1`:</span></span>  
  
    |<span data-ttu-id="d5d4d-134">**Nombre de la columna**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-134">**Column Name**</span></span>|<span data-ttu-id="d5d4d-135">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-135">**Data Type**</span></span>|<span data-ttu-id="d5d4d-136">**Permitir valores NULL**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-136">**Allow Nulls**</span></span>|  
    |---------------------|-------------------|---------------------|  
    |`T1col1`|`int`|<span data-ttu-id="d5d4d-137">checked</span><span class="sxs-lookup"><span data-stu-id="d5d4d-137">checked</span></span>|  
    |`T1col2`|`varchar(50)`|<span data-ttu-id="d5d4d-138">checked</span><span class="sxs-lookup"><span data-stu-id="d5d4d-138">checked</span></span>|  
    |`T1col3`|`float`|<span data-ttu-id="d5d4d-139">Activado</span><span class="sxs-lookup"><span data-stu-id="d5d4d-139">checked</span></span>|  
  
4.  <span data-ttu-id="d5d4d-140">Haga clic con el botón derecho en `T1col1` y seleccione **Establecer clave principal**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-140">Right-click `T1col1` and select **Set Primary Key**.</span></span>  
  
     <span data-ttu-id="d5d4d-141">Aparecerá un icono de llave junto al nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-141">A key icon will appear beside the column name.</span></span>  
  
5.  <span data-ttu-id="d5d4d-142">En el menú **Archivo** , haga clic en **Guardar Diagram1**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-142">From the **File** menu, click **Save Diagram1**.</span></span>  
  
6.  <span data-ttu-id="d5d4d-143">En el cuadro de diálogo **elegir nombre** , haga clic en **Aceptar** para aceptar el nombre predeterminado `Diagram1` .</span><span class="sxs-lookup"><span data-stu-id="d5d4d-143">In the **Choose Name** dialog box, click **OK** to accept the default name `Diagram1`.</span></span>  
  
7.  <span data-ttu-id="d5d4d-144">Aparecerá el cuadro de diálogo \*\*Guardar`Table1` con un mensaje que indica que \*\* se guardará en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-144">The **Save** dialog box appears with a message that `Table1` will be saved to the database.</span></span> <span data-ttu-id="d5d4d-145">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-145">Click **Yes**.</span></span>  
  
## <a name="modifying-table-structure"></a><span data-ttu-id="d5d4d-146">Modificar la estructura de la tabla</span><span class="sxs-lookup"><span data-stu-id="d5d4d-146">Modifying Table Structure</span></span>  
 <span data-ttu-id="d5d4d-147">Se pueden agregar restricciones CHECK y crear relaciones entre las tablas en el Diseñador de diagramas.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-147">You can add check constraints and make relationships between tables in Diagram Designer.</span></span>  
  
#### <a name="to-create-check-constraints"></a><span data-ttu-id="d5d4d-148">Para crear restricciones CHECK</span><span class="sxs-lookup"><span data-stu-id="d5d4d-148">To create check constraints</span></span>  
  
1.  <span data-ttu-id="d5d4d-149">En `Table1`, haga clic con el botón derecho en la fila `T1col3` y elija **Comprobar restricciones**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-149">In `Table1`, right-click the `T1col3` row and choose **Check Constraints**.</span></span>  
  
     <span data-ttu-id="d5d4d-150">Aparecerá el cuadro de diálogo **Comprobar restricciones** .</span><span class="sxs-lookup"><span data-stu-id="d5d4d-150">The **Check Constraints** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="d5d4d-151">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-151">Click **Add**.</span></span>  
  
     <span data-ttu-id="d5d4d-152">Aparecerá una nueva restricción en la lista **Restricción de comprobación seleccionada** con el nombre predeterminado `CK_Table1`.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-152">A new constraint appears in the **Selected Check Constraint** list, with the default name `CK_Table1`.</span></span>  
  
3.  <span data-ttu-id="d5d4d-153">Seleccione la fila **Expresión** en la cuadrícula y haga clic en el botón de puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-153">Select the **Expression** row in the grid and click the ellipsis button.</span></span>  
  
     <span data-ttu-id="d5d4d-154">Aparecerá el cuadro de diálogo **Expresión de restricción CHECK**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-154">The **Check Constraint Expression** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="d5d4d-155">Escriba `T1col3 > 5` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-155">Type `T1col3 > 5` and click **OK**.</span></span>  
  
     <span data-ttu-id="d5d4d-156">`Table1` tiene ahora una restricción para que todos los valores escritos en `T1col3` sean mayores de 5.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-156">`Table1` now has a constraint that all values entered into `T1col3` must be greater than 5.</span></span>  
  
5.  <span data-ttu-id="d5d4d-157">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-157">Click **Close**.</span></span>  
  
#### <a name="to-create-relationships-between-tables"></a><span data-ttu-id="d5d4d-158">Para crear relaciones entre tablas</span><span class="sxs-lookup"><span data-stu-id="d5d4d-158">To create relationships between tables</span></span>  
  
1.  <span data-ttu-id="d5d4d-159">Cree una nueva tabla en el Diseñador de diagramas con el nombre `Table2` y con las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="d5d4d-159">Create a new table in Diagram designer named `Table2` with the following columns:</span></span>  
  
    |<span data-ttu-id="d5d4d-160">**Nombre de columna**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-160">**Column Name**</span></span>|<span data-ttu-id="d5d4d-161">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-161">**Data Type**</span></span>|<span data-ttu-id="d5d4d-162">**Permitir valores NULL**</span><span class="sxs-lookup"><span data-stu-id="d5d4d-162">**Allow Nulls**</span></span>|  
    |---------------------|-------------------|---------------------|  
    |`T2col1`|`int`|<span data-ttu-id="d5d4d-163">no seleccionado</span><span class="sxs-lookup"><span data-stu-id="d5d4d-163">not checked</span></span>|  
    |`T2col2`|`varchar(50)`|<span data-ttu-id="d5d4d-164">checked</span><span class="sxs-lookup"><span data-stu-id="d5d4d-164">checked</span></span>|  
    |`T2col3`|`xml`|<span data-ttu-id="d5d4d-165">checked</span><span class="sxs-lookup"><span data-stu-id="d5d4d-165">checked</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="d5d4d-166">Las columnas del lado de la clave principal de una relación de clave externa deben participar en una restricción PRIMARY KEY o UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-166">The columns on the primary key side of a foreign key relationship must participate in either a Primary Key or a Unique Constraint.</span></span>  
  
2.  <span data-ttu-id="d5d4d-167">Arrastre `T2col1` hasta `T1col1`.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-167">Drag `T2col1` to `T1col1`.</span></span>  
  
     <span data-ttu-id="d5d4d-168">Aparecen dos cuadros de diálogo: **Relación de clave externa** en segundo plano y **Tablas y columnas** , en primer plano.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-168">Two dialog boxes appear: **Foreign Key Relationship** in the background and **Tables and Columns** in the foreground.</span></span>  
  
3.  <span data-ttu-id="d5d4d-169">Haga clic en **Aceptar** para guardar la nueva relación.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-169">Click **OK** to save the new relationship.</span></span>  
  
4.  <span data-ttu-id="d5d4d-170">Haga clic en **Aceptar** nuevamente.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-170">Click **OK** again.</span></span>  
  
## <a name="creating-indexes"></a><span data-ttu-id="d5d4d-171">Crear índices</span><span class="sxs-lookup"><span data-stu-id="d5d4d-171">Creating Indexes</span></span>  
 <span data-ttu-id="d5d4d-172">Se pueden crear índices en la mayoría de los tipos de datos, incluso en XML.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-172">You can create indexes on most types of data, including XML.</span></span>  
  
#### <a name="to-create-a-standard-index"></a><span data-ttu-id="d5d4d-173">Para crear un índice estándar</span><span class="sxs-lookup"><span data-stu-id="d5d4d-173">To create a standard index</span></span>  
  
1.  <span data-ttu-id="d5d4d-174">Haga clic con el botón derecho en `Table1` y elija **Índices o claves**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-174">Right-click `Table1` and choose **Indexes/Keys**.</span></span>  
  
     <span data-ttu-id="d5d4d-175">Aparecerá el cuadro de diálogo **Índices o claves** .</span><span class="sxs-lookup"><span data-stu-id="d5d4d-175">The **Indexes/Keys** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="d5d4d-176">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-176">Click **Add**.</span></span>  
  
     <span data-ttu-id="d5d4d-177">Aparecerá un nuevo índice en la lista **Clave principal o única, o índice seleccionado** con un nombre predeterminado similar a `IX_Table1`.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-177">A new index appears in the **Selected Primary/Unique Key or Index** list, with a default name similar to `IX_Table1`.</span></span>  
  
3.  <span data-ttu-id="d5d4d-178">Seleccione la fila **Columnas** y haga clic en el botón de puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-178">Select the **Columns** row and click the ellipsis button.</span></span>  
  
     <span data-ttu-id="d5d4d-179">Aparecerá el cuadro de diálogo **Columnas de índice** .</span><span class="sxs-lookup"><span data-stu-id="d5d4d-179">The **Index Columns** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="d5d4d-180">Haga clic en la flecha de lista desplegable situada bajo **Nombre de columna** y seleccione `T1col2`.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-180">Click the drop-down arrow under **Column Name** and select `T1col2`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d5d4d-181">Puede agregar columnas adicionales a este índice si selecciona la celda situada bajo `T1col2` y elige otro nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-181">You may add additional columns to this index by selecting the cell below `T1col2` and choosing another column name.</span></span>  
  
5.  <span data-ttu-id="d5d4d-182">Haga clic en **Aceptar** para guardar el índice.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-182">Click **OK** to save this index.</span></span>  
  
6.  <span data-ttu-id="d5d4d-183">Haga clic en **Cerrar** en el cuadro de diálogo **Índices o claves** .</span><span class="sxs-lookup"><span data-stu-id="d5d4d-183">Click **Close** in the **Indexes/Keys** dialog box.</span></span>  
  
#### <a name="to-create-an-xml-index"></a><span data-ttu-id="d5d4d-184">Para crear un índice XML</span><span class="sxs-lookup"><span data-stu-id="d5d4d-184">To create an XML index</span></span>  
  
1.  <span data-ttu-id="d5d4d-185">Haga clic con el botón derecho en `T2col1` y elija **Establecer clave principal**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-185">Right-click `T2col1` and choose **Set Primary Key**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d5d4d-186">Para poder agregar un índice XML, se debe establecer otra columna de la tabla como clave principal agrupada.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-186">Adding an XML index requires that another column in the table be set as a clustered primary key.</span></span>  
  
2.  <span data-ttu-id="d5d4d-187">Haga clic con el botón derecho en la fila `T2col3` en `Table2` y seleccione **Índices XML**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-187">Right-click the `T2col3` row in `Table2` and select **XML Indexes**.</span></span>  
  
     <span data-ttu-id="d5d4d-188">Aparecerá el cuadro de diálogo **Índices XML** .</span><span class="sxs-lookup"><span data-stu-id="d5d4d-188">The **XML Indexes** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="d5d4d-189">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-189">Click **Add**.</span></span>  
  
     <span data-ttu-id="d5d4d-190">Se agregará un índice XML con valores predeterminados a la lista **Índice XML seleccionado** .</span><span class="sxs-lookup"><span data-stu-id="d5d4d-190">An XML index with default values will be added to the **Selected XML Index** list.</span></span>  
  
4.  <span data-ttu-id="d5d4d-191">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-191">Click **Close**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d5d4d-192">Los índices XML se crean por cada columna.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-192">XML indexes are created per-column.</span></span> <span data-ttu-id="d5d4d-193">El primer índice XML es el principal y cualquier otro índice es secundario.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-193">The first XML index is primary; any additional indexes are secondary.</span></span>  
  
## <a name="saving-the-diagram"></a><span data-ttu-id="d5d4d-194">Guardar el diagrama</span><span class="sxs-lookup"><span data-stu-id="d5d4d-194">Saving the Diagram</span></span>  
 <span data-ttu-id="d5d4d-195">Todos los cambios realizados en el diagrama no se publican en la base de datos hasta que lo guarde.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-195">All of the changes you make to a diagram are not posted to the database until you save it.</span></span> <span data-ttu-id="d5d4d-196">Si hay problemas o conflictos, aparecerá un cuadro de diálogo con más información.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-196">If there are problems or conflicts, a dialog box appears with more information.</span></span>  
  
#### <a name="to-save-a-database-diagram"></a><span data-ttu-id="d5d4d-197">Para guardar el diagrama de base de datos</span><span class="sxs-lookup"><span data-stu-id="d5d4d-197">To save a database diagram</span></span>  
  
1.  <span data-ttu-id="d5d4d-198">En el menú **Archivo** , seleccione **Guardar Diagram1**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-198">On the **File** menu, select **Save Diagram1**.</span></span>  
  
     <span data-ttu-id="d5d4d-199">Aparecerá el cuadro de diálogo **Guardar** .</span><span class="sxs-lookup"><span data-stu-id="d5d4d-199">The **Save** dialog box appears.</span></span> <span data-ttu-id="d5d4d-200">Si selecciona la opción **Advertir sobre las tablas afectadas** , se proporcionará información acerca de las tablas nuevas o modificadas.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-200">If **Warn about Tables Affected** is selected, information about new or changed tables is listed.</span></span>  
  
2.  <span data-ttu-id="d5d4d-201">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-201">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="d5d4d-202">Si se produce algún error, aparecerá el cuadro de diálogo **Notificaciones después de guardar** con los errores y las causas.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-202">If any errors occurred, the **Post-Save Notifications** dialog box appears with the errors and their causes.</span></span> <span data-ttu-id="d5d4d-203">Solucione los errores y guarde el diagrama de nuevo.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-203">Fix the errors and save the diagram again.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d5d4d-204">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d5d4d-204">Next Steps</span></span>  
 <span data-ttu-id="d5d4d-205">Este diagrama es básico, únicamente con dos tablas existentes y otras dos nuevas, pero muestra el potencial de la creación de diagramas en una base de datos existente o de la creación de un nuevo esquema visual.</span><span class="sxs-lookup"><span data-stu-id="d5d4d-205">This is a basic diagram with just two existing and two new tables, but it illustrates the potential for diagramming an existing database or creating a new schema visually.</span></span> <span data-ttu-id="d5d4d-206">Algunas sugerencias de investigación adicional son:</span><span class="sxs-lookup"><span data-stu-id="d5d4d-206">Suggestions for more exploration include:</span></span>  
  
-   <span data-ttu-id="d5d4d-207">Crear nuevos diagramas que incluyan grupos de tablas relacionadas</span><span class="sxs-lookup"><span data-stu-id="d5d4d-207">Create new diagrams containing groups of related tables</span></span>  
  
-   <span data-ttu-id="d5d4d-208">Personalizar el volumen de información que aparece en cada tabla</span><span class="sxs-lookup"><span data-stu-id="d5d4d-208">Customize the amount of information shown for each table</span></span>  
  
-   <span data-ttu-id="d5d4d-209">Modificar el diseño y agregar anotaciones</span><span class="sxs-lookup"><span data-stu-id="d5d4d-209">Change the layout and add annotations</span></span>  
  
-   <span data-ttu-id="d5d4d-210">Copiar el diagrama en un mapa de bits</span><span class="sxs-lookup"><span data-stu-id="d5d4d-210">Copy the diagram to a bitmap</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d4d-211">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5d4d-211">See Also</span></span>  
 <span data-ttu-id="d5d4d-212">[Personalizar la cantidad de información que se muestra en los diagramas &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d5d4d-212">[Customize the Amount of Information Displayed in Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="d5d4d-213">[Configurar el diseñador de diagramas de base de datos &#40;Visual Database Tools&#41;](set-up-database-diagram-designer-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d5d4d-213">[Set Up Database Diagram Designer &#40;Visual Database Tools&#41;](set-up-database-diagram-designer-visual-database-tools.md) </span></span>  
 <span data-ttu-id="d5d4d-214">[Agregar tablas a diagramas &#40;Visual Database Tools&#41;](add-tables-to-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d5d4d-214">[Add Tables to Diagrams &#40;Visual Database Tools&#41;](add-tables-to-diagrams-visual-database-tools.md) </span></span>  
 <span data-ttu-id="d5d4d-215">[Crear relaciones entre tablas en un diagrama &#40;Visual Database Tools&#41;](create-relationships-between-tables-on-a-diagram-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d5d4d-215">[Create Relationships Between Tables on a Diagram &#40;Visual Database Tools&#41;](create-relationships-between-tables-on-a-diagram-visual-database-tools.md) </span></span>  
 <span data-ttu-id="d5d4d-216">[Crear índices XML](../../relational-databases/xml/create-xml-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="d5d4d-216">[Create XML Indexes](../../relational-databases/xml/create-xml-indexes.md) </span></span>  
 <span data-ttu-id="d5d4d-217">[Copiar una imagen de un diagrama de base de datos en el portapapeles &#40;Visual Database Tools&#41;](copy-an-image-of-a-database-diagram-to-the-clipboard-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d5d4d-217">[Copy an Image of a Database Diagram to the Clipboard &#40;Visual Database Tools&#41;](copy-an-image-of-a-database-diagram-to-the-clipboard-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="d5d4d-218">Trabajar con el diseño de diagramas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="d5d4d-218">Work with Diagram Layout &#40;Visual Database Tools&#41;</span></span>](work-with-diagram-layout-visual-database-tools.md)  
  
  
