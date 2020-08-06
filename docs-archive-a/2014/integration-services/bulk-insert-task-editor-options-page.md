---
title: Editor de la tarea inserción masiva (página Opciones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.options.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: b3702811-3eb8-4b28-9190-5ae7a1a7bb6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1751d1e0ac01d5459a8c76e6a48626c2ad6deafd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748877"
---
# <a name="bulk-insert-task-editor-options-page"></a><span data-ttu-id="4e7b6-102">Editor de la tarea Inserción masiva (página Opciones)</span><span class="sxs-lookup"><span data-stu-id="4e7b6-102">Bulk Insert Task Editor (Options Page)</span></span>
  <span data-ttu-id="4e7b6-103">Use la página **Opciones** del cuadro de diálogo **Editor de la tarea Inserción masiva** para establecer las propiedades de la operación de inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-103">Use the **Options** page of the **Bulk Insert Task Editor** dialog box to set properties for the bulk insert operation.</span></span> <span data-ttu-id="4e7b6-104">La tarea Inserción masiva copia gran cantidad de datos en una tabla o vista de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e7b6-104">The Bulk Insert task copies large amounts of data into a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table or view.</span></span>  
  
 <span data-ttu-id="4e7b6-105">Para más información sobre las inserciones masivas, vea [Tarea Inserción masiva](control-flow/bulk-insert-task.md) y [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4e7b6-105">To learn about working with bulk inserts, see [Bulk Insert Task](control-flow/bulk-insert-task.md) and [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4e7b6-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="4e7b6-106">Options</span></span>  
 <span data-ttu-id="4e7b6-107">**CodePage**</span><span class="sxs-lookup"><span data-stu-id="4e7b6-107">**CodePage**</span></span>  
 <span data-ttu-id="4e7b6-108">Especifique la página de códigos de los datos incluidos en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-108">Specify the code page of the data in the data file.</span></span>  
  
 <span data-ttu-id="4e7b6-109">**DataFileType**</span><span class="sxs-lookup"><span data-stu-id="4e7b6-109">**DataFileType**</span></span>  
 <span data-ttu-id="4e7b6-110">Especifique el valor del tipo de datos que desea utilizar en la operación de carga.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-110">Specify the data-type value to use in the load operation.</span></span>  
  
 <span data-ttu-id="4e7b6-111">**BatchSize**</span><span class="sxs-lookup"><span data-stu-id="4e7b6-111">**BatchSize**</span></span>  
 <span data-ttu-id="4e7b6-112">Especifique el número de filas de un lote.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-112">Specify the number of rows in a batch.</span></span> <span data-ttu-id="4e7b6-113">El valor predeterminado es todo el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-113">The default is the entire data file.</span></span> <span data-ttu-id="4e7b6-114">Si establece el valor cero en **BatchSize** , se cargarán los datos en un único lote.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-114">If you set **BatchSize** to zero, the data is loaded in a single batch.</span></span>  
  
 <span data-ttu-id="4e7b6-115">**LastRow**</span><span class="sxs-lookup"><span data-stu-id="4e7b6-115">**LastRow**</span></span>  
 <span data-ttu-id="4e7b6-116">Especifique la última fila que desea copiar.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-116">Specify the last row to copy.</span></span>  
  
 <span data-ttu-id="4e7b6-117">**FirstRow**</span><span class="sxs-lookup"><span data-stu-id="4e7b6-117">**FirstRow**</span></span>  
 <span data-ttu-id="4e7b6-118">Especifique la primera fila desde la que desea empezar a copiar.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-118">Specify the first row from which to start copying.</span></span>  
  
 <span data-ttu-id="4e7b6-119">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="4e7b6-119">**Options**</span></span>  
 |<span data-ttu-id="4e7b6-120">Término</span><span class="sxs-lookup"><span data-stu-id="4e7b6-120">Term</span></span>|<span data-ttu-id="4e7b6-121">Definición</span><span class="sxs-lookup"><span data-stu-id="4e7b6-121">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="4e7b6-122">**Restricciones CHECK**</span><span class="sxs-lookup"><span data-stu-id="4e7b6-122">**Check constraints**</span></span>|<span data-ttu-id="4e7b6-123">Seleccione esta opción para comprobar las restricciones de la tabla y de la columna.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-123">Select to check the table and column constraints.</span></span>|  
|<span data-ttu-id="4e7b6-124">**Mantener valores NULL**</span><span class="sxs-lookup"><span data-stu-id="4e7b6-124">**Keep nulls**</span></span>|<span data-ttu-id="4e7b6-125">Seleccione esta opción para conservar los valores NULL durante la operación de inserción masiva, en lugar de insertar valores predeterminados en las columnas vacías.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-125">Select to retain null values during the bulk insert operation, instead of inserting any default values for empty columns.</span></span>|  
|<span data-ttu-id="4e7b6-126">**Habilitar la inserción de identidad**</span><span class="sxs-lookup"><span data-stu-id="4e7b6-126">**Enable identity insert**</span></span>|<span data-ttu-id="4e7b6-127">Seleccione esta opción para insertar valores existentes en una columna de identidad.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-127">Select to insert existing values into an identity column.</span></span>|  
|<span data-ttu-id="4e7b6-128">**Bloqueo de tabla**</span><span class="sxs-lookup"><span data-stu-id="4e7b6-128">**Table lock**</span></span>|<span data-ttu-id="4e7b6-129">Seleccione esta opción para bloquear la tabla durante la inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-129">Select to lock the table during the bulk insert.</span></span>|  
|<span data-ttu-id="4e7b6-130">**Activar desencadenadores**</span><span class="sxs-lookup"><span data-stu-id="4e7b6-130">**Fire triggers**</span></span>|<span data-ttu-id="4e7b6-131">Seleccione esta opción para activar desencadenadores de inserción, actualización o eliminación en la tabla.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-131">Select to fire any insert, update, or delete triggers on the table.</span></span>|  
  
 <span data-ttu-id="4e7b6-132">**SortedData**</span><span class="sxs-lookup"><span data-stu-id="4e7b6-132">**SortedData**</span></span>  
 <span data-ttu-id="4e7b6-133">Especifique la cláusula ORDER BY en la instrucción de inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-133">Specify the ORDER BY clause in the bulk insert statement.</span></span> <span data-ttu-id="4e7b6-134">El nombre de columna que proporcione debe ser una columna válida de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-134">The column name that you supply must be a valid column in the destination table.</span></span> <span data-ttu-id="4e7b6-135">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-135">The default is `false`.</span></span> <span data-ttu-id="4e7b6-136">Significa que los datos están ordenados mediante una cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-136">This means that the data is not sorted by an ORDER BY clause.</span></span>  
  
 <span data-ttu-id="4e7b6-137">**MaxErrors**</span><span class="sxs-lookup"><span data-stu-id="4e7b6-137">**MaxErrors**</span></span>  
 <span data-ttu-id="4e7b6-138">Especifique el número máximo de errores que pueden producirse antes de que se cancele la operación de inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-138">Specify the maximum number of errors that can occur before the bulk insert operation is canceled.</span></span> <span data-ttu-id="4e7b6-139">El valor 0 indica que se permite un número infinito de errores.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-139">A value of 0 indicates that an infinite number of errors are allowed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4e7b6-140">Cada fila que no pueda importarse con la operación de carga masiva se contabilizará como un error.</span><span class="sxs-lookup"><span data-stu-id="4e7b6-140">Each row that cannot be imported by the bulk load operation is counted as one error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e7b6-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4e7b6-141">See Also</span></span>  
 <span data-ttu-id="4e7b6-142">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4e7b6-142">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="4e7b6-143">[Editor de la tarea inserción masiva &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="4e7b6-143">[Bulk Insert Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="4e7b6-144">[Editor de la tarea inserción masiva &#40;página de conexión&#41;](../../2014/integration-services/bulk-insert-task-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="4e7b6-144">[Bulk Insert Task Editor &#40;Connection Page&#41;](../../2014/integration-services/bulk-insert-task-editor-connection-page.md) </span></span>  
 <span data-ttu-id="4e7b6-145">[Página Expresiones](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="4e7b6-145">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="4e7b6-146">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="4e7b6-146">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
