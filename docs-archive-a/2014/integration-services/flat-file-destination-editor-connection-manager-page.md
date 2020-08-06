---
title: Editor de destino de archivos planos (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfiledestadapter.connection.f1
helpviewer_keywords:
- Flat File Destination Editor
ms.assetid: b01571fa-bc19-4742-8eed-ac163172a919
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6997b72851c2b7bfc56445e6ddb01cfe6e9b04cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663616"
---
# <a name="flat-file-destination-editor-connection-manager-page"></a><span data-ttu-id="2346c-102">Editor de destino de archivos planos (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="2346c-102">Flat File Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="2346c-103">Utilice la página **Administrador de conexiones** del cuadro de diálogo **Editor de destino de archivos planos** para seleccionar la conexión de archivos planos del destino y para especificar si se debe sobrescribir o anexar en el archivo de destino existente.</span><span class="sxs-lookup"><span data-stu-id="2346c-103">Use the **Connection Manager** page of the **Flat File Destination Editor** dialog box to select the flat file connection for the destination, and to specify whether to overwrite or append to the existing destination file.</span></span> <span data-ttu-id="2346c-104">El destino de archivo plano escribe datos en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="2346c-104">The flat file destination writes data to a text file.</span></span> <span data-ttu-id="2346c-105">Este archivo de texto puede tener los formatos: delimitado, ancho fijo, ancho fijo con delimitadores de fila o derecho irregular.</span><span class="sxs-lookup"><span data-stu-id="2346c-105">This text file can be in delimited, fixed width, fixed width with row delimiter, or ragged right format.</span></span>  
  
 <span data-ttu-id="2346c-106">Para obtener más información acerca del destino de archivo plano, vea [Flat File Destination](data-flow/flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="2346c-106">To learn more about the Flat File destination, see [Flat File Destination](data-flow/flat-file-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2346c-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="2346c-107">Options</span></span>  
 <span data-ttu-id="2346c-108">**Administrador de conexiones de archivos planos**</span><span class="sxs-lookup"><span data-stu-id="2346c-108">**Flat File connection manager**</span></span>  
 <span data-ttu-id="2346c-109">Seleccione un administrador de conexiones existente en el cuadro de lista o haga clic en **Nueva**para crear una conexión.</span><span class="sxs-lookup"><span data-stu-id="2346c-109">Select an existing connection manager by using the list box, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="2346c-110">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="2346c-110">**New**</span></span>  
 <span data-ttu-id="2346c-111">Cree una conexión con los cuadros de diálogo **Formato del archivo plano** y **Editor del administrador de conexiones de archivos planos** .</span><span class="sxs-lookup"><span data-stu-id="2346c-111">Create a new connection by using the **Flat File Format** and **Flat File Connection Manager Editor** dialog boxes.</span></span>  
  
 <span data-ttu-id="2346c-112">Además de los formatos estándar de archivo plano delimitado, ancho fijo y desigual a la derecha, el cuadro de diálogo **Formato de archivo plano** tiene una cuarta opción, **Ancho fijo con delimitadores de fila**.</span><span class="sxs-lookup"><span data-stu-id="2346c-112">In addition to the standard flat file formats of delimited, fixed width, and ragged right, the **Flat File Format** dialog box has a fourth option, **Fixed width with row delimiters**.</span></span> <span data-ttu-id="2346c-113">Esta opción representa un caso especial del formato derecho desigual en el que [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] agrega una columna ficticia como última columna de datos.</span><span class="sxs-lookup"><span data-stu-id="2346c-113">This option represents a special case of the ragged-right format in which [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] adds a dummy column as the final column of data.</span></span> <span data-ttu-id="2346c-114">Esta columna ficticia sirve para garantizar que la última columna tenga un ancho fijo.</span><span class="sxs-lookup"><span data-stu-id="2346c-114">This dummy column ensures that the final column has a fixed width.</span></span>  
  
 <span data-ttu-id="2346c-115">La opción **Ancho fijo con delimitadores de fila** no está disponible en el **Editor del administrador de conexiones de archivos planos**.</span><span class="sxs-lookup"><span data-stu-id="2346c-115">The **Fixed width with row delimiters** option is not available in the **Flat File Connection Manager Editor**.</span></span> <span data-ttu-id="2346c-116">Si es necesario, puede emular esta opción en el editor.</span><span class="sxs-lookup"><span data-stu-id="2346c-116">If necessary, you can emulate this option in the editor.</span></span> <span data-ttu-id="2346c-117">Para emular esta opción, en la página **General** del **Editor del administrador de conexiones de archivos planos**seleccione **Desigual a la derecha**en **Formato**, .</span><span class="sxs-lookup"><span data-stu-id="2346c-117">To emulate this option, on the **General** page of the **Flat File Connection Manager Editor**, for **Format**, select **Ragged right**.</span></span> <span data-ttu-id="2346c-118">A continuación en la página **Avanzadas** del editor, agregue una nueva columna ficticia como última columna de datos.</span><span class="sxs-lookup"><span data-stu-id="2346c-118">Then on the **Advanced** page of the editor, add a new dummy column as the final column of data.</span></span>  
  
 <span data-ttu-id="2346c-119">**Sobrescribir los datos del archivo**</span><span class="sxs-lookup"><span data-stu-id="2346c-119">**Overwrite data in the file**</span></span>  
 <span data-ttu-id="2346c-120">Indique si desea sobrescribir un archivo existente o anexar datos en él.</span><span class="sxs-lookup"><span data-stu-id="2346c-120">Indicate whether to overwrite an existing file, or to append data to it.</span></span>  
  
 <span data-ttu-id="2346c-121">**Encabezado**</span><span class="sxs-lookup"><span data-stu-id="2346c-121">**Header**</span></span>  
 <span data-ttu-id="2346c-122">Escriba un bloque de texto para insertarlo en el archivo antes de que se escriban datos.</span><span class="sxs-lookup"><span data-stu-id="2346c-122">Type a block of text to insert into the file before any data is written.</span></span> <span data-ttu-id="2346c-123">Utilice esta opción para incluir información adicional, como encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="2346c-123">Use this option to include additional information, such as column headings.</span></span>  
  
 <span data-ttu-id="2346c-124">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="2346c-124">**Preview**</span></span>  
 <span data-ttu-id="2346c-125">Muestra una vista previa de los resultados mediante el cuadro de diálogo **Vista de datos** .</span><span class="sxs-lookup"><span data-stu-id="2346c-125">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="2346c-126">La vista previa puede mostrar hasta 200 filas.</span><span class="sxs-lookup"><span data-stu-id="2346c-126">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2346c-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2346c-127">See Also</span></span>  
 <span data-ttu-id="2346c-128">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2346c-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="2346c-129">Editor de destino de archivos planos &#40;página Asignaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="2346c-129">Flat File Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/flat-file-destination-editor-mappings-page.md)  
  
  
