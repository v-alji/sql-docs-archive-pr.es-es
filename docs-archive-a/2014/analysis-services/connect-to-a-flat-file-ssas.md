---
title: Conectarse a un archivo plano (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connflatfile.f1
ms.assetid: a365991e-eded-4cd8-89c0-0daf6d658d15
author: minewiskan
ms.author: owend
ms.openlocfilehash: e6bee3c8f7f4b255e6985e8d783365bc8a47599e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670019"
---
# <a name="connect-to-a-flat-file-ssas"></a><span data-ttu-id="d53ac-102">Conectarse a un archivo plano (SSAS)</span><span class="sxs-lookup"><span data-stu-id="d53ac-102">Connect to a Flat File (SSAS)</span></span>
  <span data-ttu-id="d53ac-103">Esta página del **Asistente para la importación de tablas** le permite conectar con un archivo plano (.txt), un archivo separado por caracteres de tabulación (.tab) o un archivo delimitado por comas (.csv).</span><span class="sxs-lookup"><span data-stu-id="d53ac-103">This page of the **Table Import Wizard** enables you to connect to a flat file (.txt), tab-separated file (.tab), or a comma-separated file (.csv).</span></span> <span data-ttu-id="d53ac-104">Para tener acceso al asistente desde [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], en el menú **Modelo** , haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="d53ac-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="d53ac-105">Para conectarse a un archivo plano, debe tener instalado en el equipo el proveedor ACE.</span><span class="sxs-lookup"><span data-stu-id="d53ac-105">To connect to a flat file, you must have the ACE provider installed on your computer.</span></span> <span data-ttu-id="d53ac-106">Para más información, vea [Orígenes de datos compatibles &#40;SSAS tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="d53ac-106">For more information, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d53ac-107">Las credenciales del usuario actual se utilizan al seleccionar un archivo en esta página.</span><span class="sxs-lookup"><span data-stu-id="d53ac-107">The credentials of the current user are used when selecting a file in this page.</span></span> <span data-ttu-id="d53ac-108">Sin embargo, la importación no se realizará correctamente si el usuario especificado en la página Información de suplantación no tiene privilegios suficientes para leer el archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d53ac-108">However, import will not succeed if the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected file.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="d53ac-109">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="d53ac-109">UI element list</span></span>  
 <span data-ttu-id="d53ac-110">**Nombre descriptivo de la conexión**</span><span class="sxs-lookup"><span data-stu-id="d53ac-110">**Friendly connection name**</span></span>  
 <span data-ttu-id="d53ac-111">Escriba un nombre único para esta conexión de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d53ac-111">Type a unique name for this data source connection.</span></span> <span data-ttu-id="d53ac-112">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d53ac-112">This is a required field.</span></span>  
  
 <span data-ttu-id="d53ac-113">**Ruta de acceso del archivo**</span><span class="sxs-lookup"><span data-stu-id="d53ac-113">**File Path**</span></span>  
 <span data-ttu-id="d53ac-114">Especifique la ruta de acceso completa del archivo.</span><span class="sxs-lookup"><span data-stu-id="d53ac-114">Specify a full path for the file.</span></span>  
  
 <span data-ttu-id="d53ac-115">**Browse**</span><span class="sxs-lookup"><span data-stu-id="d53ac-115">**Browse**</span></span>  
 <span data-ttu-id="d53ac-116">Navegue a una ubicación donde haya un archivo.</span><span class="sxs-lookup"><span data-stu-id="d53ac-116">Navigate to a location where a file is available.</span></span>  
  
 <span data-ttu-id="d53ac-117">**Separador de columnas**</span><span class="sxs-lookup"><span data-stu-id="d53ac-117">**Column Separator**</span></span>  
 <span data-ttu-id="d53ac-118">Seleccione los delimitadores de columna disponibles en la lista.</span><span class="sxs-lookup"><span data-stu-id="d53ac-118">Select from a list of available column separators.</span></span> <span data-ttu-id="d53ac-119">Elija un delimitador que no sea probable encontrar en el texto.</span><span class="sxs-lookup"><span data-stu-id="d53ac-119">Choose a separator that is not likely to occur in the text.</span></span>  
  
|<span data-ttu-id="d53ac-120">Value</span><span class="sxs-lookup"><span data-stu-id="d53ac-120">Value</span></span>|<span data-ttu-id="d53ac-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="d53ac-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d53ac-122">Tabulador (t)</span><span class="sxs-lookup"><span data-stu-id="d53ac-122">Tab (t)</span></span>|<span data-ttu-id="d53ac-123">Un tabulador (t) separa las columnas.</span><span class="sxs-lookup"><span data-stu-id="d53ac-123">Columns are separated by a tab (t).</span></span>|  
|<span data-ttu-id="d53ac-124">Coma (,)</span><span class="sxs-lookup"><span data-stu-id="d53ac-124">Comma (,)</span></span>|<span data-ttu-id="d53ac-125">Las columnas se separan mediante una coma (,).</span><span class="sxs-lookup"><span data-stu-id="d53ac-125">Columns are separated by a comma (,).</span></span>|  
|<span data-ttu-id="d53ac-126">Punto y coma (;)</span><span class="sxs-lookup"><span data-stu-id="d53ac-126">Semicolon (;)</span></span>|<span data-ttu-id="d53ac-127">Las columnas se separan mediante un punto y coma (;).</span><span class="sxs-lookup"><span data-stu-id="d53ac-127">Columns are separated by a semicolon (;).</span></span>|  
|<span data-ttu-id="d53ac-128">Space ( )</span><span class="sxs-lookup"><span data-stu-id="d53ac-128">Space ( )</span></span>|<span data-ttu-id="d53ac-129">Las columnas se separan mediante un espacio ( ).</span><span class="sxs-lookup"><span data-stu-id="d53ac-129">Columns are separated by a space ( ).</span></span>|  
|<span data-ttu-id="d53ac-130">Dos puntos (:)</span><span class="sxs-lookup"><span data-stu-id="d53ac-130">Colon (:)</span></span>|<span data-ttu-id="d53ac-131">Las columnas se separan mediante dos puntos (:).</span><span class="sxs-lookup"><span data-stu-id="d53ac-131">Columns are separated by a colon (:).</span></span>|  
|<span data-ttu-id="d53ac-132">Barra vertical (&#124;)</span><span class="sxs-lookup"><span data-stu-id="d53ac-132">Vertical Bar (&#124;)</span></span>|<span data-ttu-id="d53ac-133">Las columnas se separan mediante una barra vertical (&#124;).</span><span class="sxs-lookup"><span data-stu-id="d53ac-133">Columns are separated by a vertical bar (&#124;).</span></span>|  
  
 <span data-ttu-id="d53ac-134">**Avanzadas**</span><span class="sxs-lookup"><span data-stu-id="d53ac-134">**Advanced**</span></span>  
 <span data-ttu-id="d53ac-135">Especifique las opciones de configuración regional y codificación para el archivo plano.</span><span class="sxs-lookup"><span data-stu-id="d53ac-135">Specify the encoding and locale options for the flat file.</span></span>  
  
 <span data-ttu-id="d53ac-136">**Usar primera fila como encabezados de columna**</span><span class="sxs-lookup"><span data-stu-id="d53ac-136">**Use first row as column headers**</span></span>  
 <span data-ttu-id="d53ac-137">Especifique si utilizar la primera fila de datos como encabezados de columna de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="d53ac-137">Specify whether to use the first data row as the column headers of the destination table.</span></span>  
  
 <span data-ttu-id="d53ac-138">**Vista previa de datos**</span><span class="sxs-lookup"><span data-stu-id="d53ac-138">**Data preview**</span></span>  
 <span data-ttu-id="d53ac-139">Obtenga la vista previa de los datos del archivo seleccionado y use las opciones siguientes para modificar la importación de datos.</span><span class="sxs-lookup"><span data-stu-id="d53ac-139">Preview the data in the selected file, and use the following options to modify the data import.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d53ac-140">Solo las primeras 50 filas del archivo se muestran en esta vista previa.</span><span class="sxs-lookup"><span data-stu-id="d53ac-140">Only the first 50 rows in the file are displayed in this preview.</span></span>  
  
|<span data-ttu-id="d53ac-141">Opción</span><span class="sxs-lookup"><span data-stu-id="d53ac-141">Option</span></span>|<span data-ttu-id="d53ac-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="d53ac-142">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d53ac-143">**Casilla en el encabezado de columna**</span><span class="sxs-lookup"><span data-stu-id="d53ac-143">**Checkbox in the column header**</span></span>|<span data-ttu-id="d53ac-144">Active la casilla para incluir la columna en la importación de datos.</span><span class="sxs-lookup"><span data-stu-id="d53ac-144">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="d53ac-145">Desactive la casilla para quitar la columna de la importación de datos.</span><span class="sxs-lookup"><span data-stu-id="d53ac-145">Clear the checkbox to remove the column from the data import.</span></span>|  
|<span data-ttu-id="d53ac-146">**Botón de flecha abajo en el encabezado de columna**</span><span class="sxs-lookup"><span data-stu-id="d53ac-146">**Down-arrow button in the column header**</span></span>|<span data-ttu-id="d53ac-147">Ordene y filtre los datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="d53ac-147">Sort and filter data in the column.</span></span>|  
  
 <span data-ttu-id="d53ac-148">**Borrar filtros de fila**</span><span class="sxs-lookup"><span data-stu-id="d53ac-148">**Clear Row Filters**</span></span>  
 <span data-ttu-id="d53ac-149">Quite todos los filtros que se aplicaron a los datos en las columnas.</span><span class="sxs-lookup"><span data-stu-id="d53ac-149">Remove all filters that were applied to the data in the columns.</span></span>  
  
  
