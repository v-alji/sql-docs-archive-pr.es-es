---
title: Editor de origen de XML (página Administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.xmlsourceadapter.connectionmanager.f1
helpviewer_keywords:
- XML Source Editor
ms.assetid: e6507403-a3ce-4b6f-91fc-a7de9f7b6283
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e40ca6ef2d8fbcd10b756a2ce15f33730c367d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677200"
---
# <a name="xml-source-editor-connection-manager-page"></a><span data-ttu-id="d7411-102">Editor de origen de XML (página Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="d7411-102">XML Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="d7411-103">Utilice la página **Administrador de conexiones** del **Editor de origen de XML** para especificar un archivo XML y el XSD que transforma los datos XML.</span><span class="sxs-lookup"><span data-stu-id="d7411-103">Use the **Connection Manager** page of the **XML Source Editor** to specify an XML file and the XSD that transforms the XML data.</span></span>  
  
 <span data-ttu-id="d7411-104">Para obtener más información acerca del origen XML, vea [XML Source](data-flow/xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="d7411-104">For more information about the XML source, see [XML Source](data-flow/xml-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="d7411-105">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="d7411-105">Static Options</span></span>  
 <span data-ttu-id="d7411-106">**Modo de acceso a datos**</span><span class="sxs-lookup"><span data-stu-id="d7411-106">**Data access mode**</span></span>  
 <span data-ttu-id="d7411-107">Especifique el método para seleccionar datos del origen.</span><span class="sxs-lookup"><span data-stu-id="d7411-107">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="d7411-108">Value</span><span class="sxs-lookup"><span data-stu-id="d7411-108">Value</span></span>|<span data-ttu-id="d7411-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7411-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d7411-110">Ubicación del archivo XML</span><span class="sxs-lookup"><span data-stu-id="d7411-110">XML file location</span></span>|<span data-ttu-id="d7411-111">Recupera datos de un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="d7411-111">Retrieve data from an XML file.</span></span>|  
|<span data-ttu-id="d7411-112">Archivo XML de variable</span><span class="sxs-lookup"><span data-stu-id="d7411-112">XML file from variable</span></span>|<span data-ttu-id="d7411-113">Especifica el nombre de archivo XML en una variable.</span><span class="sxs-lookup"><span data-stu-id="d7411-113">Specify the XML file name in a variable.</span></span><br /><br /> <span data-ttu-id="d7411-114">**Información relacionada**: [Usar variables en paquetes](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="d7411-114">**Related information**: [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="d7411-115">Datos XML de variable</span><span class="sxs-lookup"><span data-stu-id="d7411-115">XML data from variable</span></span>|<span data-ttu-id="d7411-116">Recupera datos XML de una variable.</span><span class="sxs-lookup"><span data-stu-id="d7411-116">Retrieve XML data from a variable.</span></span>|  
  
 <span data-ttu-id="d7411-117">**Utilizar esquema insertado**</span><span class="sxs-lookup"><span data-stu-id="d7411-117">**Use inline schema**</span></span>  
 <span data-ttu-id="d7411-118">Especifique si los datos de origen XML contienen el esquema XSD que define y valida su estructura y sus datos.</span><span class="sxs-lookup"><span data-stu-id="d7411-118">Specify whether the XML source data itself contains the XSD schema that defines and validates its structure and data.</span></span>  
  
 <span data-ttu-id="d7411-119">**Ubicación de XSD**</span><span class="sxs-lookup"><span data-stu-id="d7411-119">**XSD location**</span></span>  
 <span data-ttu-id="d7411-120">Especifique la ruta de acceso y el nombre de archivo del archivo de esquema XSD, o busque el archivo haciendo clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="d7411-120">Type the path and file name of the XSD schema file, or locate the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="d7411-121">**Browse**</span><span class="sxs-lookup"><span data-stu-id="d7411-121">**Browse**</span></span>  
 <span data-ttu-id="d7411-122">Use el cuadro de diálogo **Abrir** para buscar el archivo de esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="d7411-122">Use the **Open** dialog box to locate the XSD schema file.</span></span>  
  
 <span data-ttu-id="d7411-123">**Generar XSD**</span><span class="sxs-lookup"><span data-stu-id="d7411-123">**Generate XSD**</span></span>  
 <span data-ttu-id="d7411-124">Use el cuadro de diálogo **Guardar como** para seleccionar una ubicación para el archivo de esquema XSD generado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d7411-124">Use the **Save As** dialog box to select a location for the auto-generated XSD schema file.</span></span> <span data-ttu-id="d7411-125">El editor deduce el esquema de la estructura de los datos XML.</span><span class="sxs-lookup"><span data-stu-id="d7411-125">The editor infers the schema from the structure of the XML data.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="d7411-126">Opciones dinámicas del modo de acceso a datos</span><span class="sxs-lookup"><span data-stu-id="d7411-126">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--xml-file-location"></a><span data-ttu-id="d7411-127">Modo de acceso a datos = Ubicación del archivo XML</span><span class="sxs-lookup"><span data-stu-id="d7411-127">Data access mode = XML file location</span></span>  
 <span data-ttu-id="d7411-128">**Ubicación de XML**</span><span class="sxs-lookup"><span data-stu-id="d7411-128">**XML location**</span></span>  
 <span data-ttu-id="d7411-129">Especifique la ruta de acceso y el nombre de archivo del archivo de datos XML, o busque el archivo haciendo clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="d7411-129">Type the path and file name of the XML data file, or locate the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="d7411-130">**Browse**</span><span class="sxs-lookup"><span data-stu-id="d7411-130">**Browse**</span></span>  
 <span data-ttu-id="d7411-131">Use el cuadro de diálogo **Abrir** para buscar el archivo de datos XML.</span><span class="sxs-lookup"><span data-stu-id="d7411-131">Use the **Open** dialog box to locate the XML data file.</span></span>  
  
### <a name="data-access-mode--xml-file-from-variable"></a><span data-ttu-id="d7411-132">Modo de acceso a datos = Datos XML de variable</span><span class="sxs-lookup"><span data-stu-id="d7411-132">Data access mode = XML file from variable</span></span>  
 <span data-ttu-id="d7411-133">**Nombre de variable**</span><span class="sxs-lookup"><span data-stu-id="d7411-133">**Variable name**</span></span>  
 <span data-ttu-id="d7411-134">Seleccione la variable que contiene la ruta de acceso y el nombre del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="d7411-134">Select the variable that contains the path and file name of the XML file.</span></span>  
  
### <a name="data-access-mode--xml-data-from-variable"></a><span data-ttu-id="d7411-135">Modo de acceso a datos = Datos XML de variable</span><span class="sxs-lookup"><span data-stu-id="d7411-135">Data access mode = XML data from variable</span></span>  
 <span data-ttu-id="d7411-136">**Nombre de variable**</span><span class="sxs-lookup"><span data-stu-id="d7411-136">**Variable name**</span></span>  
 <span data-ttu-id="d7411-137">Seleccione la variable que contiene los datos XML.</span><span class="sxs-lookup"><span data-stu-id="d7411-137">Select the variable that contains the XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7411-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7411-138">See Also</span></span>  
 <span data-ttu-id="d7411-139">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d7411-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d7411-140">[Editor de origen de XML &#40;página columnas&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="d7411-140">[XML Source Editor &#40;Columns Page&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="d7411-141">[Editor de origen de XML &#40;página salida de error&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="d7411-141">[XML Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="d7411-142">Extraer datos mediante el origen de XML</span><span class="sxs-lookup"><span data-stu-id="d7411-142">Extract Data by Using the XML Source</span></span>](data-flow/extract-data-by-using-the-xml-source.md)  
  
  
