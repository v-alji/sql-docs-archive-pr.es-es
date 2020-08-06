---
title: Editor del administrador de conexiones de varios archivos planos (página general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multifile.general.f1
helpviewer_keywords:
- Multiple Flat Files Connection Manager Editor
ms.assetid: 00129d43-2772-413b-bdf8-ac5de81cf4a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f30a422794723f216d30e05f0750fb1e974e0920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748172"
---
# <a name="multiple-flat-files-connection-manager-editor-general-page"></a><span data-ttu-id="9c592-102">Editor del administrador de conexiones de varios archivos planos (página General)</span><span class="sxs-lookup"><span data-stu-id="9c592-102">Multiple Flat Files Connection Manager Editor (General Page)</span></span>
  <span data-ttu-id="9c592-103">Utilice la página **General** del cuadro de diálogo **Editor del administrador de conexiones de varios archivos planos** para seleccionar un grupo de archivos que tengan el mismo formato de datos y para especificar su formato de datos.</span><span class="sxs-lookup"><span data-stu-id="9c592-103">Use the **General** page of the **Multiple Flat Files Connection Manager Editor** dialog box to select a group of files that have the same data format, and to specify their data format.</span></span> <span data-ttu-id="9c592-104">Una conexión de varios archivos planos permite que un paquete se conecte a un grupo de archivos de texto que tengan el mismo formato.</span><span class="sxs-lookup"><span data-stu-id="9c592-104">A multiple flat files connection enables a package to connect to a group of text files that have the same format.</span></span>  
  
 <span data-ttu-id="9c592-105">Para obtener más información acerca del administrador de conexiones de varios archivos planos, vea [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9c592-105">To learn more about the Multiple Flat Files connection manager, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9c592-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="9c592-106">Options</span></span>  
 <span data-ttu-id="9c592-107">**Nombre del administrador de conexiones**</span><span class="sxs-lookup"><span data-stu-id="9c592-107">**Connection manager name**</span></span>  
 <span data-ttu-id="9c592-108">Especifique un nombre único para la conexión de varios archivos planos en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9c592-108">Provide a unique name for the Multiple Flat Files connection in the workflow.</span></span> <span data-ttu-id="9c592-109">El nombre que indique se mostrará en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c592-109">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="9c592-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9c592-110">**Description**</span></span>  
 <span data-ttu-id="9c592-111">Describe la conexión.</span><span class="sxs-lookup"><span data-stu-id="9c592-111">Describe the connection.</span></span> <span data-ttu-id="9c592-112">Como método recomendado, describa la conexión desde el punto de vista de su propósito, para que los paquetes estén autodocumentados y sean más fáciles de mantener.</span><span class="sxs-lookup"><span data-stu-id="9c592-112">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="9c592-113">**Nombres de archivos**</span><span class="sxs-lookup"><span data-stu-id="9c592-113">**File names**</span></span>  
 <span data-ttu-id="9c592-114">Escriba la ruta de acceso y los nombres de los archivos que se van a utilizar en la conexión de varios archivos planos.</span><span class="sxs-lookup"><span data-stu-id="9c592-114">Type the path and file names to use in the Multiple Flat Files connection.</span></span> <span data-ttu-id="9c592-115">Puede especificar varios archivos mediante el uso de caracteres comodín, como en el ejemplo "C:\\*.txt", o mediante el uso del carácter de barra vertical (|) para separar varios nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="9c592-115">You can specify multiple files by using wildcard characters, as in the example "C:\\*.txt", or by using the vertical pipe character (|) to separate multiple file names.</span></span> <span data-ttu-id="9c592-116">Todos los archivos deben tener el mismo formato de datos.</span><span class="sxs-lookup"><span data-stu-id="9c592-116">All files must have the same data format.</span></span>  
  
 <span data-ttu-id="9c592-117">**Browse**</span><span class="sxs-lookup"><span data-stu-id="9c592-117">**Browse**</span></span>  
 <span data-ttu-id="9c592-118">Busque los nombres de los archivos que se van a utilizar en la conexión de varios archivos planos.</span><span class="sxs-lookup"><span data-stu-id="9c592-118">Browse the file names to use in the Multiple Flat Files connection.</span></span> <span data-ttu-id="9c592-119">Puede seleccionar varios archivos.</span><span class="sxs-lookup"><span data-stu-id="9c592-119">You can select multiple files.</span></span> <span data-ttu-id="9c592-120">Todos los archivos deben tener el mismo formato de datos.</span><span class="sxs-lookup"><span data-stu-id="9c592-120">All files must have the same data format.</span></span>  
  
 <span data-ttu-id="9c592-121">**Configuración regional**</span><span class="sxs-lookup"><span data-stu-id="9c592-121">**Locale**</span></span>  
 <span data-ttu-id="9c592-122">Especifique la ubicación para proporcionar información de ordenación y de conversión de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="9c592-122">Specify the location to provide information for ordering and for date and time conversion.</span></span>  
  
 <span data-ttu-id="9c592-123">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="9c592-123">**Unicode**</span></span>  
 <span data-ttu-id="9c592-124">Indique si se va a utilizar Unicode.</span><span class="sxs-lookup"><span data-stu-id="9c592-124">Indicate whether to use Unicode.</span></span> <span data-ttu-id="9c592-125">El uso de Unicode impide especificar una página de códigos.</span><span class="sxs-lookup"><span data-stu-id="9c592-125">Using Unicode precludes specifying a code page.</span></span>  
  
 <span data-ttu-id="9c592-126">**Página de códigos**</span><span class="sxs-lookup"><span data-stu-id="9c592-126">**Code page**</span></span>  
 <span data-ttu-id="9c592-127">Especifique la página de códigos para el texto no Unicode.</span><span class="sxs-lookup"><span data-stu-id="9c592-127">Specify the code page for non-Unicode text.</span></span>  
  
 <span data-ttu-id="9c592-128">**Formato**</span><span class="sxs-lookup"><span data-stu-id="9c592-128">**Format**</span></span>  
 <span data-ttu-id="9c592-129">Indique si se utiliza formato delimitado, de ancho fijo o derecho irregular.</span><span class="sxs-lookup"><span data-stu-id="9c592-129">Indicate whether to use delimited, fixed width, or ragged right formatting.</span></span> <span data-ttu-id="9c592-130">Todos los archivos deben tener el mismo formato de datos.</span><span class="sxs-lookup"><span data-stu-id="9c592-130">All files must have the same data format.</span></span>  
  
|<span data-ttu-id="9c592-131">Valor</span><span class="sxs-lookup"><span data-stu-id="9c592-131">Value</span></span>|<span data-ttu-id="9c592-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c592-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9c592-133">Delimitado</span><span class="sxs-lookup"><span data-stu-id="9c592-133">Delimited</span></span>|<span data-ttu-id="9c592-134">Las columnas se separan mediante delimitadores, que se especifican en la página **Columnas** .</span><span class="sxs-lookup"><span data-stu-id="9c592-134">Columns are separated by delimiters, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="9c592-135">Ancho fijo</span><span class="sxs-lookup"><span data-stu-id="9c592-135">Fixed width</span></span>|<span data-ttu-id="9c592-136">Las columnas tienen un ancho fijo, que se especifica arrastrando líneas de marcador en la página **Columnas** .</span><span class="sxs-lookup"><span data-stu-id="9c592-136">Columns have a fixed width, specified by dragging marker lines on the **Columns** page.</span></span>|  
|<span data-ttu-id="9c592-137">Derecho irregular</span><span class="sxs-lookup"><span data-stu-id="9c592-137">Ragged right</span></span>|<span data-ttu-id="9c592-138">Los archivos de derecho irregular son los archivos en los que todas las columnas tienen un ancho fijo, a excepción de la última, que está delimitada por el delimitador de filas, que se especifica en la página **Columnas** .</span><span class="sxs-lookup"><span data-stu-id="9c592-138">Ragged right files are files in which every column has a fixed width, except for the last column, which is delimited by the row delimiter, specified on the **Columns** page.</span></span>|  
  
 <span data-ttu-id="9c592-139">**Calificador de texto**</span><span class="sxs-lookup"><span data-stu-id="9c592-139">**Text qualifier**</span></span>  
 <span data-ttu-id="9c592-140">Especifique el calificador de texto que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="9c592-140">Specify the text qualifier to use.</span></span> <span data-ttu-id="9c592-141">Por ejemplo, puede especificar que el texto se incluya entre comillas.</span><span class="sxs-lookup"><span data-stu-id="9c592-141">For example, you can specify to enclose text with quotation marks.</span></span>  
  
 <span data-ttu-id="9c592-142">**Delimitador de filas de encabezados**</span><span class="sxs-lookup"><span data-stu-id="9c592-142">**Header row delimiter**</span></span>  
 <span data-ttu-id="9c592-143">Seleccione uno de los delimitadores de filas de encabezados de la lista o escriba el texto delimitador.</span><span class="sxs-lookup"><span data-stu-id="9c592-143">Select from the list of delimiters for header rows, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="9c592-144">Valor</span><span class="sxs-lookup"><span data-stu-id="9c592-144">Value</span></span>|<span data-ttu-id="9c592-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c592-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9c592-146">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="9c592-146">**{CR}{LF}**</span></span>|<span data-ttu-id="9c592-147">La fila de encabezado está delimitada por una combinación de retorno de carro y avance de línea.</span><span class="sxs-lookup"><span data-stu-id="9c592-147">The header row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="9c592-148">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="9c592-148">**{CR}**</span></span>|<span data-ttu-id="9c592-149">La fila de encabezado está delimitada por un retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="9c592-149">The header row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="9c592-150">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="9c592-150">**{LF}**</span></span>|<span data-ttu-id="9c592-151">La fila de encabezado está delimitada por un avance de línea.</span><span class="sxs-lookup"><span data-stu-id="9c592-151">The header row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="9c592-152">**Punto y coma {;}**</span><span class="sxs-lookup"><span data-stu-id="9c592-152">**Semicolon {;}**</span></span>|<span data-ttu-id="9c592-153">La fila de encabezado está delimitada por un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="9c592-153">The header row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="9c592-154">**Dos puntos {:}**</span><span class="sxs-lookup"><span data-stu-id="9c592-154">**Colon {:}**</span></span>|<span data-ttu-id="9c592-155">La fila de encabezado está delimitada por dos puntos.</span><span class="sxs-lookup"><span data-stu-id="9c592-155">The header row is delimited by a colon.</span></span>|  
|<span data-ttu-id="9c592-156">**Coma {,}**</span><span class="sxs-lookup"><span data-stu-id="9c592-156">**Comma {,}**</span></span>|<span data-ttu-id="9c592-157">La fila de encabezado está delimitada por una coma.</span><span class="sxs-lookup"><span data-stu-id="9c592-157">The header row is delimited by a comma.</span></span>|  
|<span data-ttu-id="9c592-158">**Tabulación {t}**</span><span class="sxs-lookup"><span data-stu-id="9c592-158">**Tab {t}**</span></span>|<span data-ttu-id="9c592-159">La fila de encabezado está delimitada por una tabulación.</span><span class="sxs-lookup"><span data-stu-id="9c592-159">The header row is delimited by a tab.</span></span>|  
|<span data-ttu-id="9c592-160">**Barra vertical {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="9c592-160">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="9c592-161">La fila de encabezado está delimitada por una barra vertical.</span><span class="sxs-lookup"><span data-stu-id="9c592-161">The header row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="9c592-162">**Filas de encabezados que se omitirán**</span><span class="sxs-lookup"><span data-stu-id="9c592-162">**Header rows to skip**</span></span>  
 <span data-ttu-id="9c592-163">Especifica el número de filas de encabezados que se van a omitir, en caso de que esto ocurra.</span><span class="sxs-lookup"><span data-stu-id="9c592-163">Specify the number of header rows to skip, if any.</span></span>  
  
 <span data-ttu-id="9c592-164">**Nombres de columna de la primera fila de datos**</span><span class="sxs-lookup"><span data-stu-id="9c592-164">**Column names in the first data row**</span></span>  
 <span data-ttu-id="9c592-165">Indica si deben esperarse o deben especificarse nombres de columna en la primera fila de datos.</span><span class="sxs-lookup"><span data-stu-id="9c592-165">Indicate whether to expect or provide column names in the first data row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c592-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c592-166">See Also</span></span>  
 <span data-ttu-id="9c592-167">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9c592-167">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="9c592-168">[&#40;página columnas del editor del administrador de conexiones de varios archivos planos&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="9c592-168">[Multiple Flat Files Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-columns-page.md) </span></span>  
 <span data-ttu-id="9c592-169">[Editor del administrador de conexiones de varios archivos planos &#40;página avanzadas&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="9c592-169">[Multiple Flat Files Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="9c592-170">Editor del administrador de conexiones de varios archivos planos &#40;página Vista previa&#41;</span><span class="sxs-lookup"><span data-stu-id="9c592-170">Multiple Flat Files Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/multiple-flat-files-connection-manager-editor-preview-page.md)  
  
  
