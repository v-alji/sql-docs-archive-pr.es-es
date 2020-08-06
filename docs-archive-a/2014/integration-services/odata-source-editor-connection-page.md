---
title: Editor de origen OData (página conexión) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- Sql12.dts.designer.odatasource.connection.f1
ms.assetid: 20bcd347-4547-4fad-b182-9571030101df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6ecd0d060ea2197ae7174325b654645fefa23505
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674196"
---
# <a name="odata-source-editor-connection-page"></a><span data-ttu-id="d2aa1-102">Editor de origen OData (página Conexión)</span><span class="sxs-lookup"><span data-stu-id="d2aa1-102">OData Source Editor (Connection Page)</span></span>
  <span data-ttu-id="d2aa1-103">Use la página **Conexión** del cuadro de diálogo **Editor de origen OData** para seleccionar el administrador de conexiones OData para el origen OData.</span><span class="sxs-lookup"><span data-stu-id="d2aa1-103">Use the **Connection** page of the **OData Source Editor** dialog box to select the OData connection manager for the OData source.</span></span> <span data-ttu-id="d2aa1-104">Esta página también permite especificar una ruta de acceso de colección o a recursos y las opciones de consulta deseadas para indicar qué datos hay que recuperar del origen OData.</span><span class="sxs-lookup"><span data-stu-id="d2aa1-104">This page also lets you specify a collection or a resource path and any query options to indicate what data needs to be retrieved from the OData source.</span></span> <span data-ttu-id="d2aa1-105">Para obtener más información acerca del origen OData, vea [OData Source](data-flow/odata-source.md).</span><span class="sxs-lookup"><span data-stu-id="d2aa1-105">To learn more about the OData source, see [OData Source](data-flow/odata-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="d2aa1-106">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="d2aa1-106">Static Options</span></span>  
 <span data-ttu-id="d2aa1-107">**Administrador de conexiones OData**</span><span class="sxs-lookup"><span data-stu-id="d2aa1-107">**OData connection manager**</span></span>  
 <span data-ttu-id="d2aa1-108">Seleccione un administrador de conexiones de la lista o cree una conexión haciendo clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d2aa1-108">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="d2aa1-109">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="d2aa1-109">**New**</span></span>  
 <span data-ttu-id="d2aa1-110">Cree un administrador de conexiones mediante el cuadro de diálogo **Editor del administrador de conexiones OData** .</span><span class="sxs-lookup"><span data-stu-id="d2aa1-110">Create a new connection manager by using the **OData Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="d2aa1-111">**Usar ruta de acceso de colección o a recursos**</span><span class="sxs-lookup"><span data-stu-id="d2aa1-111">**Use collection or resource path**</span></span>  
 <span data-ttu-id="d2aa1-112">Especifique el método para seleccionar datos del origen.</span><span class="sxs-lookup"><span data-stu-id="d2aa1-112">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="d2aa1-113">Opción</span><span class="sxs-lookup"><span data-stu-id="d2aa1-113">Option</span></span>|<span data-ttu-id="d2aa1-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2aa1-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d2aa1-115">Colección</span><span class="sxs-lookup"><span data-stu-id="d2aa1-115">Collection</span></span>|<span data-ttu-id="d2aa1-116">Recupera datos del origen OData mediante un nombre de colección.</span><span class="sxs-lookup"><span data-stu-id="d2aa1-116">Retrieve data from the OData source by using a collection name.</span></span>|  
|<span data-ttu-id="d2aa1-117">Ruta de acceso a recursos</span><span class="sxs-lookup"><span data-stu-id="d2aa1-117">Resource Path</span></span>|<span data-ttu-id="d2aa1-118">Recupera datos del origen OData mediante una ruta de acceso a recursos.</span><span class="sxs-lookup"><span data-stu-id="d2aa1-118">Retrieve data from the OData source by using a resource path.</span></span>|  
  
 <span data-ttu-id="d2aa1-119">**Opciones de consulta**</span><span class="sxs-lookup"><span data-stu-id="d2aa1-119">**Query options**</span></span>  
 <span data-ttu-id="d2aa1-120">Especifique las opciones de consulta.</span><span class="sxs-lookup"><span data-stu-id="d2aa1-120">Specify options for the query.</span></span>  <span data-ttu-id="d2aa1-121">Por ejemplo: $top=5</span><span class="sxs-lookup"><span data-stu-id="d2aa1-121">For example: $top=5</span></span>  
  
 <span data-ttu-id="d2aa1-122">**Dirección URL de fuente**</span><span class="sxs-lookup"><span data-stu-id="d2aa1-122">**Feed url**</span></span>  
 <span data-ttu-id="d2aa1-123">Muestra la dirección URL de la fuente de solo lectura según las opciones que ha seleccionado en este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d2aa1-123">Displays the read-only Feed URL based on options you selected on this dialog box.</span></span>  
  
 <span data-ttu-id="d2aa1-124">**Versión preliminar**</span><span class="sxs-lookup"><span data-stu-id="d2aa1-124">**Preview**</span></span>  
 <span data-ttu-id="d2aa1-125">Muestra una vista previa de los resultados mediante el cuadro de diálogo **Vista previa** .</span><span class="sxs-lookup"><span data-stu-id="d2aa1-125">Preview results by using the **Preview** dialog box.</span></span> <span data-ttu-id="d2aa1-126">**Vista previa** puede mostrar hasta 20 filas.</span><span class="sxs-lookup"><span data-stu-id="d2aa1-126">**Preview** can display up to 20 rows.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="d2aa1-127">Opciones dinámicas</span><span class="sxs-lookup"><span data-stu-id="d2aa1-127">Dynamic Options</span></span>  
  
### <a name="use-collection-or-resource-path--collection"></a><span data-ttu-id="d2aa1-128">Usar ruta de acceso de colección o de recurso = Colección</span><span class="sxs-lookup"><span data-stu-id="d2aa1-128">Use collection or resource path = Collection</span></span>  
 <span data-ttu-id="d2aa1-129">**Colección**</span><span class="sxs-lookup"><span data-stu-id="d2aa1-129">**Collection**</span></span>  
 <span data-ttu-id="d2aa1-130">Seleccione una colección de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d2aa1-130">Select a collection from the drop-down list.</span></span>  
  
### <a name="use-collection-or-resource-path--resource-path"></a><span data-ttu-id="d2aa1-131">Usar ruta de acceso de colección o de recurso = Ruta de acceso a recursos</span><span class="sxs-lookup"><span data-stu-id="d2aa1-131">Use collection or resource path = Resource Path</span></span>  
 <span data-ttu-id="d2aa1-132">**Ruta de acceso a recursos**</span><span class="sxs-lookup"><span data-stu-id="d2aa1-132">**Resource path**</span></span>  
 <span data-ttu-id="d2aa1-133">Escriba una ruta de acceso a recursos.</span><span class="sxs-lookup"><span data-stu-id="d2aa1-133">Type a resource path.</span></span> <span data-ttu-id="d2aa1-134">Por ejemplo: Empleados</span><span class="sxs-lookup"><span data-stu-id="d2aa1-134">For example: Employees</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2aa1-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2aa1-135">See Also</span></span>  
 <span data-ttu-id="d2aa1-136">[Editor de origen OData &#40;página columnas&#41;](../../2014/integration-services/odata-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="d2aa1-136">[OData Source Editor &#40;Columns Page&#41;](../../2014/integration-services/odata-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="d2aa1-137">[Editor de origen OData &#40;página salida de error&#41;](../../2014/integration-services/odata-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="d2aa1-137">[OData Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/odata-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="d2aa1-138">Administrador de conexiones OData</span><span class="sxs-lookup"><span data-stu-id="d2aa1-138">OData Connection Manager</span></span>](connection-manager/odata-connection-manager.md)  
  
  
