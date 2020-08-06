---
title: Asignaciones de columnas (Asistente para importación y exportación de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.columnmapandtransform.f1
ms.assetid: eadc54a6-f936-4ffc-91d7-fbfd2bdcab93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7994de1292677421447d441c1ac5aeb2b6fbc618
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674934"
---
# <a name="column-mappings-sql-server-import-and-export-wizard"></a><span data-ttu-id="6abd8-102">Asignaciones de columnas (Asistente para importación y exportación de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6abd8-102">Column Mappings (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="6abd8-103">Utilice el cuadro de diálogo **asignaciones de columnas** para modificar los parámetros de transformación.</span><span class="sxs-lookup"><span data-stu-id="6abd8-103">Use the **Column Mappings** dialog box to edit transformation parameters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6abd8-104">No es necesario copiar todas las columnas en una tabla al seleccionar la opción de copia de tabla.</span><span class="sxs-lookup"><span data-stu-id="6abd8-104">You do not have to copy all the columns in a table when you select the Table Copy option.</span></span> <span data-ttu-id="6abd8-105">Seleccione **\<ignore>** en la columna **destino** de este cuadro de diálogo para las columnas que desea omitir.</span><span class="sxs-lookup"><span data-stu-id="6abd8-105">Select **\<ignore>** in the **Destination** column of this dialog box for columns that you want to skip.</span></span>  
  
 <span data-ttu-id="6abd8-106">Para obtener más información acerca de este asistente, vea [Asistente para importación y exportación de SQL Server](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="6abd8-106">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="6abd8-107">Para obtener información sobre las opciones para iniciar el asistente, así como los permisos necesarios para ejecutar el asistente correctamente, vea [ejecutar el Asistente para importación y exportación de SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="6abd8-107">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="6abd8-108">La finalidad del Asistente para importación y exportación de SQL Server es copiar datos desde un origen a un destino.</span><span class="sxs-lookup"><span data-stu-id="6abd8-108">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="6abd8-109">El asistente también puede crear una base de datos y tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="6abd8-109">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="6abd8-110">Sin embargo, si tiene que copiar diversas bases de datos o tablas, u otros tipos de objetos de bases de datos, debe utilizar el Asistente para copiar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="6abd8-110">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="6abd8-111">Para más información, consulte [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="6abd8-111">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6abd8-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="6abd8-112">Options</span></span>  
 <span data-ttu-id="6abd8-113">**Origen**</span><span class="sxs-lookup"><span data-stu-id="6abd8-113">**Source**</span></span>  
 <span data-ttu-id="6abd8-114">Identifica la tabla, vista o consulta de origen seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6abd8-114">Identifies the selected source table, view, or query.</span></span>  
  
 <span data-ttu-id="6abd8-115">**Destino**</span><span class="sxs-lookup"><span data-stu-id="6abd8-115">**Destination**</span></span>  
 <span data-ttu-id="6abd8-116">Identifica la tabla, vista o consulta de destino seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6abd8-116">Identifies the selected destination table, view, or query.</span></span>  
  
 <span data-ttu-id="6abd8-117">**Crear tabla o archivo de destino**</span><span class="sxs-lookup"><span data-stu-id="6abd8-117">**Create destination table/file**</span></span>  
 <span data-ttu-id="6abd8-118">Especifique si debe crearse una tabla de destino si todavía no existe.</span><span class="sxs-lookup"><span data-stu-id="6abd8-118">Specify whether to create the destination table if it does not already exist.</span></span>  
  
 <span data-ttu-id="6abd8-119">**Eliminar filas en la tabla o archivo de destino**</span><span class="sxs-lookup"><span data-stu-id="6abd8-119">**Delete rows in destination table/file**</span></span>  
 <span data-ttu-id="6abd8-120">Especifique si deben eliminarse datos de una tabla existente antes de cargar datos nuevos.</span><span class="sxs-lookup"><span data-stu-id="6abd8-120">Specify whether to clear the data from an existing table before loading new data.</span></span>  
  
 <span data-ttu-id="6abd8-121">**Anexar filas a la tabla o archivo de destino**</span><span class="sxs-lookup"><span data-stu-id="6abd8-121">**Append rows to destination table/file**</span></span>  
 <span data-ttu-id="6abd8-122">Especifique si deben anexarse datos nuevos a los datos que contiene una tabla existente.</span><span class="sxs-lookup"><span data-stu-id="6abd8-122">Specify whether to append the new data to the data already present in an existing table.</span></span>  
  
 <span data-ttu-id="6abd8-123">**Editar SQL**</span><span class="sxs-lookup"><span data-stu-id="6abd8-123">**Edit SQL**</span></span>  
 <span data-ttu-id="6abd8-124">Use la instrucción predeterminada en el cuadro de diálogo **instrucción CREATE TABLE de SQL** o modifíquela para sus fines.</span><span class="sxs-lookup"><span data-stu-id="6abd8-124">Use the default statement in the **Create Table SQL Statement** dialog box, or modify it for your purposes.</span></span> <span data-ttu-id="6abd8-125">Si modifica la instrucción, también deberá realizar los cambios asociados en la asignación de tablas.</span><span class="sxs-lookup"><span data-stu-id="6abd8-125">If you modify this statement, you must also make associated changes to table mapping.</span></span>  
  
 <span data-ttu-id="6abd8-126">**Quitar y volver a crear la tabla de destino**</span><span class="sxs-lookup"><span data-stu-id="6abd8-126">**Drop and re-create destination table**</span></span>  
 <span data-ttu-id="6abd8-127">Elija esta opción para sobrescribir la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="6abd8-127">Choose this option to overwrite the destination table.</span></span> <span data-ttu-id="6abd8-128">Esta opción solo está disponible si se usa el asistente para crear la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="6abd8-128">This option is only available when you use the wizard to create the destination table.</span></span> <span data-ttu-id="6abd8-129">La tabla de destino se quita y se vuelve a crear solo si guarda el paquete que el asistente crea y, a continuación, ejecuta el paquete de nuevo.</span><span class="sxs-lookup"><span data-stu-id="6abd8-129">The destination table is only dropped and re-created if you save the package that the wizard creates, and then run the package again.</span></span>  
  
 <span data-ttu-id="6abd8-130">**Habilitar la inserción de identidad**</span><span class="sxs-lookup"><span data-stu-id="6abd8-130">**Enable identity insert**</span></span>  
 <span data-ttu-id="6abd8-131">Elija esta opción para poder insertar los valores de identidad existentes del origen de datos en una columna de identidad de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="6abd8-131">Choose this option to allow existing identity values in the source data to be inserted into an identity column in the destination table.</span></span> <span data-ttu-id="6abd8-132">De forma predeterminada, la columna de identidad de destino no lo permite.</span><span class="sxs-lookup"><span data-stu-id="6abd8-132">By default, the destination identity column does not allow this.</span></span>  
  
 <span data-ttu-id="6abd8-133">**Asignaciones**</span><span class="sxs-lookup"><span data-stu-id="6abd8-133">**Mappings**</span></span>  
 <span data-ttu-id="6abd8-134">Muestra el modo en que cada columna del origen de datos se asigna a una columna en el destino.</span><span class="sxs-lookup"><span data-stu-id="6abd8-134">Displays how each column in the data source maps to a column in the destination.</span></span>  
  
 <span data-ttu-id="6abd8-135">Esta lista tiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="6abd8-135">This list has the following columns:</span></span>  
  
 <span data-ttu-id="6abd8-136">**Origen**</span><span class="sxs-lookup"><span data-stu-id="6abd8-136">**Source**</span></span>  
 <span data-ttu-id="6abd8-137">Muestre cada columna de origen para la que pueda definir parámetros de transformación.</span><span class="sxs-lookup"><span data-stu-id="6abd8-137">View each source column for which you can set transformation parameters.</span></span>  
  
 <span data-ttu-id="6abd8-138">**Destino**</span><span class="sxs-lookup"><span data-stu-id="6abd8-138">**Destination**</span></span>  
 <span data-ttu-id="6abd8-139">Especifique si desea omitir una columna durante la operación de copia.</span><span class="sxs-lookup"><span data-stu-id="6abd8-139">Specify whether you want to ignore a column during the copy operation.</span></span> <span data-ttu-id="6abd8-140">Puede copiar solo un subconjunto de columnas si selecciona **\<ignore>** en esta columna para las columnas que desea omitir.</span><span class="sxs-lookup"><span data-stu-id="6abd8-140">You can copy only a subset of columns by selecting **\<ignore>** in this column for columns that you want to skip.</span></span> <span data-ttu-id="6abd8-141">Antes de asignar columnas, debe omitir todas las columnas que no se asignarán.</span><span class="sxs-lookup"><span data-stu-id="6abd8-141">Before you map columns, you must ignore all columns that will not be mapped.</span></span>  
  
 <span data-ttu-id="6abd8-142">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6abd8-142">**Type**</span></span>  
 <span data-ttu-id="6abd8-143">Seleccione un tipo de datos para la columna.</span><span class="sxs-lookup"><span data-stu-id="6abd8-143">Select a data type for the column.</span></span>  
  
 <span data-ttu-id="6abd8-144">**Admisión de valores NULL**</span><span class="sxs-lookup"><span data-stu-id="6abd8-144">**Nullable**</span></span>  
 <span data-ttu-id="6abd8-145">Especifique si una columna aceptará un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="6abd8-145">Specify whether a column will allow a null value.</span></span>  
  
 <span data-ttu-id="6abd8-146">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="6abd8-146">**Size**</span></span>  
 <span data-ttu-id="6abd8-147">Especifique el número de caracteres de la columna.</span><span class="sxs-lookup"><span data-stu-id="6abd8-147">Specify the number of characters in the column.</span></span>  
  
 <span data-ttu-id="6abd8-148">**Precisión**</span><span class="sxs-lookup"><span data-stu-id="6abd8-148">**Precision**</span></span>  
 <span data-ttu-id="6abd8-149">Especifique la precisión de los datos que se muestran, haciendo referencia al número de dígitos.</span><span class="sxs-lookup"><span data-stu-id="6abd8-149">Specify the precision of displayed data, referring to the number of digits.</span></span>  
  
 <span data-ttu-id="6abd8-150">**Escala**</span><span class="sxs-lookup"><span data-stu-id="6abd8-150">**Scale**</span></span>  
 <span data-ttu-id="6abd8-151">Especifique la escala de los datos que se muestran, haciendo referencia al número de posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="6abd8-151">Specify the scale of displayed data, referring to the number of decimal places.</span></span>  
  
  
