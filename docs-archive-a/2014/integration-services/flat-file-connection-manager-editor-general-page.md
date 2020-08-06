---
title: Editor del administrador de conexiones de archivos planos (página general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ffileconnection.general.f1
helpviewer_keywords:
- Flat File Connection Manager Editor
ms.assetid: 77296024-5c1a-4f6a-9665-0b50d45d744c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 478c7bcf56e300b47af93862bf66409a3c94b5f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663621"
---
# <a name="flat-file-connection-manager-editor-general-page"></a><span data-ttu-id="460ab-102">Editor del administrador de conexiones de archivos planos (página General)</span><span class="sxs-lookup"><span data-stu-id="460ab-102">Flat File Connection Manager Editor (General Page)</span></span>
  <span data-ttu-id="460ab-103">Utilice la página **General** del cuadro de diálogo **Editor del administrador de conexiones de archivos planos** para seleccionar un archivo y un formato de datos.</span><span class="sxs-lookup"><span data-stu-id="460ab-103">Use the **General** page of the **Flat File Connection Manager Editor** dialog box to select a file and data format.</span></span> <span data-ttu-id="460ab-104">Las conexiones de archivos planos permiten que un paquete se conecte con un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="460ab-104">A flat file connection enables a package to connect to a text file.</span></span>  
  
 <span data-ttu-id="460ab-105">Para obtener más información acerca del administrador de conexiones de archivos planos, vea [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="460ab-105">To learn more about the Flat File connection manager, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="460ab-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="460ab-106">Options</span></span>  
 <span data-ttu-id="460ab-107">**Nombre del administrador de conexiones**</span><span class="sxs-lookup"><span data-stu-id="460ab-107">**Connection manager name**</span></span>  
 <span data-ttu-id="460ab-108">Especifique un nombre único para la conexión de archivo plano en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="460ab-108">Provide a unique name for the flat file connection in the workflow.</span></span> <span data-ttu-id="460ab-109">El nombre que indique se mostrará en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="460ab-109">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="460ab-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="460ab-110">**Description**</span></span>  
 <span data-ttu-id="460ab-111">Describe la conexión.</span><span class="sxs-lookup"><span data-stu-id="460ab-111">Describe the connection.</span></span> <span data-ttu-id="460ab-112">Como método recomendado, describa la conexión desde el punto de vista de su propósito, para que los paquetes estén autodocumentados y sean más fáciles de mantener.</span><span class="sxs-lookup"><span data-stu-id="460ab-112">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="460ab-113">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="460ab-113">**File name**</span></span>  
 <span data-ttu-id="460ab-114">Escriba la ruta de acceso y el nombre de archivo que utilizará en la conexión de archivos planos.</span><span class="sxs-lookup"><span data-stu-id="460ab-114">Type the path and file name to use in the flat file connection.</span></span>  
  
 <span data-ttu-id="460ab-115">**Browse**</span><span class="sxs-lookup"><span data-stu-id="460ab-115">**Browse**</span></span>  
 <span data-ttu-id="460ab-116">Busque el nombre de archivo que utilizará en la conexión de archivos planos.</span><span class="sxs-lookup"><span data-stu-id="460ab-116">Locate the file name to use in the flat file connection.</span></span>  
  
 <span data-ttu-id="460ab-117">**Configuración regional**</span><span class="sxs-lookup"><span data-stu-id="460ab-117">**Locale**</span></span>  
 <span data-ttu-id="460ab-118">Especifique la configuración regional, que proporciona información específica del idioma para la ordenación y los formatos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="460ab-118">Specify the locale to provide language-specific information for ordering and for date and time formats.</span></span>  
  
 <span data-ttu-id="460ab-119">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="460ab-119">**Unicode**</span></span>  
 <span data-ttu-id="460ab-120">Indique si se va a utilizar Unicode.</span><span class="sxs-lookup"><span data-stu-id="460ab-120">Indicate whether to use Unicode.</span></span> <span data-ttu-id="460ab-121">Si utiliza Unicode, no puede especificar una página de códigos.</span><span class="sxs-lookup"><span data-stu-id="460ab-121">If you use Unicode, you cannot specify a code page.</span></span>  
  
 <span data-ttu-id="460ab-122">**Página de códigos**</span><span class="sxs-lookup"><span data-stu-id="460ab-122">**Code page**</span></span>  
 <span data-ttu-id="460ab-123">Especifique la página de códigos para el texto no Unicode.</span><span class="sxs-lookup"><span data-stu-id="460ab-123">Specify the code page for non-Unicode text.</span></span>  
  
 <span data-ttu-id="460ab-124">**Formato**</span><span class="sxs-lookup"><span data-stu-id="460ab-124">**Format**</span></span>  
 <span data-ttu-id="460ab-125">Indique si el archivo utiliza formato delimitado, de ancho fijo o derecho irregular.</span><span class="sxs-lookup"><span data-stu-id="460ab-125">Indicate whether the file uses delimited, fixed width, or ragged right formatting.</span></span>  
  
|<span data-ttu-id="460ab-126">Value</span><span class="sxs-lookup"><span data-stu-id="460ab-126">Value</span></span>|<span data-ttu-id="460ab-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="460ab-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="460ab-128">Delimitado</span><span class="sxs-lookup"><span data-stu-id="460ab-128">Delimited</span></span>|<span data-ttu-id="460ab-129">Las columnas se separan mediante delimitadores, que se especifican en la página **Columnas** .</span><span class="sxs-lookup"><span data-stu-id="460ab-129">Columns are separated by delimiters, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="460ab-130">Ancho fijo</span><span class="sxs-lookup"><span data-stu-id="460ab-130">Fixed width</span></span>|<span data-ttu-id="460ab-131">Las columnas tienen un ancho fijo.</span><span class="sxs-lookup"><span data-stu-id="460ab-131">Columns have a fixed width.</span></span>|  
|<span data-ttu-id="460ab-132">Derecho irregular</span><span class="sxs-lookup"><span data-stu-id="460ab-132">Ragged right</span></span>|<span data-ttu-id="460ab-133">Los archivos de derecho irregular son archivos en los que todas las columnas tienen un ancho fijo, a excepción de la última.</span><span class="sxs-lookup"><span data-stu-id="460ab-133">Ragged right files are files in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="460ab-134">Se delimita mediante el delimitador de fila.</span><span class="sxs-lookup"><span data-stu-id="460ab-134">It is delimited by the row delimiter.</span></span>|  
  
 <span data-ttu-id="460ab-135">**Calificador de texto**</span><span class="sxs-lookup"><span data-stu-id="460ab-135">**Text qualifier**</span></span>  
 <span data-ttu-id="460ab-136">Especifique el calificador de texto que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="460ab-136">Specify the text qualifier to use.</span></span> <span data-ttu-id="460ab-137">Por ejemplo, puede indicar que los archivos de texto se delimitan con comillas.</span><span class="sxs-lookup"><span data-stu-id="460ab-137">For example, you can specify that text fields are enclosed in quotation marks.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="460ab-138">Tras seleccionar un calificador de texto, no puede volver a elegir la opción **Ninguno** .</span><span class="sxs-lookup"><span data-stu-id="460ab-138">After you select a text qualifier, you cannot re-select the **None** option.</span></span> <span data-ttu-id="460ab-139">Escriba **Ninguno** para anular la selección del calificador de texto.</span><span class="sxs-lookup"><span data-stu-id="460ab-139">Type **None** to de-select the text qualifier.</span></span>  
  
 <span data-ttu-id="460ab-140">**Delimitador de filas de encabezados**</span><span class="sxs-lookup"><span data-stu-id="460ab-140">**Header row delimiter**</span></span>  
 <span data-ttu-id="460ab-141">Seleccione uno de los delimitadores de filas de encabezados de la lista o escriba el texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="460ab-141">Select from the list of delimiters for header rows, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="460ab-142">Valor</span><span class="sxs-lookup"><span data-stu-id="460ab-142">Value</span></span>|<span data-ttu-id="460ab-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="460ab-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="460ab-144">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="460ab-144">**{CR}{LF}**</span></span>|<span data-ttu-id="460ab-145">La fila de encabezado está delimitada por una combinación de retorno de carro y avance de línea.</span><span class="sxs-lookup"><span data-stu-id="460ab-145">The header row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="460ab-146">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="460ab-146">**{CR}**</span></span>|<span data-ttu-id="460ab-147">La fila de encabezado está delimitada por un retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="460ab-147">The header row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="460ab-148">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="460ab-148">**{LF}**</span></span>|<span data-ttu-id="460ab-149">La fila de encabezado está delimitada por un avance de línea.</span><span class="sxs-lookup"><span data-stu-id="460ab-149">The header row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="460ab-150">**Punto y coma {;}**</span><span class="sxs-lookup"><span data-stu-id="460ab-150">**Semicolon {;}**</span></span>|<span data-ttu-id="460ab-151">La fila de encabezado está delimitada por un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="460ab-151">The header row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="460ab-152">**Dos puntos {:}**</span><span class="sxs-lookup"><span data-stu-id="460ab-152">**Colon {:}**</span></span>|<span data-ttu-id="460ab-153">La fila de encabezado está delimitada por dos puntos.</span><span class="sxs-lookup"><span data-stu-id="460ab-153">The header row is delimited by a colon.</span></span>|  
|<span data-ttu-id="460ab-154">**Coma {,}**</span><span class="sxs-lookup"><span data-stu-id="460ab-154">**Comma {,}**</span></span>|<span data-ttu-id="460ab-155">La fila de encabezado está delimitada por una coma.</span><span class="sxs-lookup"><span data-stu-id="460ab-155">The header row is delimited by a comma.</span></span>|  
|<span data-ttu-id="460ab-156">**Tabulación {t}**</span><span class="sxs-lookup"><span data-stu-id="460ab-156">**Tab {t}**</span></span>|<span data-ttu-id="460ab-157">La fila de encabezado está delimitada por una tabulación.</span><span class="sxs-lookup"><span data-stu-id="460ab-157">The header row is delimited by a tab.</span></span>|  
|<span data-ttu-id="460ab-158">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="460ab-158">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="460ab-159">La fila de encabezado está delimitada por una barra vertical.</span><span class="sxs-lookup"><span data-stu-id="460ab-159">The header row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="460ab-160">**Filas de encabezados que se omitirán**</span><span class="sxs-lookup"><span data-stu-id="460ab-160">**Header rows to skip**</span></span>  
 <span data-ttu-id="460ab-161">Especifique el número de filas de encabezado o filas de datos iniciales que se deben omitir, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="460ab-161">Specify the number of header rows or initial data rows to skip, if any.</span></span>  
  
 <span data-ttu-id="460ab-162">**Nombres de columna de la primera fila de datos**</span><span class="sxs-lookup"><span data-stu-id="460ab-162">**Column names in the first data row**</span></span>  
 <span data-ttu-id="460ab-163">Indica si deben esperarse o deben especificarse nombres de columna en la primera fila de datos.</span><span class="sxs-lookup"><span data-stu-id="460ab-163">Indicate whether to expect or provide column names in the first data row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="460ab-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="460ab-164">See Also</span></span>  
 <span data-ttu-id="460ab-165">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="460ab-165">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="460ab-166">[Página &#40;columnas del editor del administrador de conexiones de archivos planos&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="460ab-166">[Flat File Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span></span>  
 <span data-ttu-id="460ab-167">[Página opciones avanzadas del editor del administrador de conexiones de archivos planos &#40;&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="460ab-167">[Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="460ab-168">Editor del administrador de conexiones de archivos planos &#40;página Vista previa&#41;</span><span class="sxs-lookup"><span data-stu-id="460ab-168">Flat File Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/flat-file-connection-manager-editor-preview-page.md)  
  
  
