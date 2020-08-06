---
title: Origen OData| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.ODATASOURCE.F1
ms.assetid: cc9003c9-638e-432b-867e-e949d50cec90
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 98b14ef034597f6098f70386ca41c1b90be86500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750037"
---
# <a name="odata-source"></a><span data-ttu-id="aa250-102">Origen OData</span><span class="sxs-lookup"><span data-stu-id="aa250-102">OData Source</span></span>
  <span data-ttu-id="aa250-103">Use el componente de origen OData en un paquete SSIS para consumir datos de servicios de Open Data Protocol (OData).</span><span class="sxs-lookup"><span data-stu-id="aa250-103">You use the OData Source component in an SSIS package to consume data from Open Data Protocol (OData) services.</span></span> <span data-ttu-id="aa250-104">El componente admite los protocolos OData v2 y v3, así como los formatos de datos ATOM y JSON.</span><span class="sxs-lookup"><span data-stu-id="aa250-104">The component supports the OData v2 and v3 protocols, as well as the ATOM and JSON data formats.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa250-105">El origen OData se puede usar para leer listas de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="aa250-105">The OData Source can be used to read from SharePoint lists.</span></span> <span data-ttu-id="aa250-106">Para ver todas las listas del servidor de SharePoint, use la siguiente dirección URL: http:// \<server> /_vti_bin/listdata.SVC.</span><span class="sxs-lookup"><span data-stu-id="aa250-106">To see all lists on your SharePoint server, use the following URL: http://\<server>/_vti_bin/ListData.svc.</span></span> <span data-ttu-id="aa250-107">Para obtener más información sobre las convenciones de direcciones URL de SharePoint, vea [Interfaz de REST de SharePoint Foundation](https://msdn.microsoft.com/library/ff521587.aspx).</span><span class="sxs-lookup"><span data-stu-id="aa250-107">For more information about SharePoint URL conventions, see [SharePoint Foundation REST Interface](https://msdn.microsoft.com/library/ff521587.aspx).</span></span>  
  
## <a name="odata-format"></a><span data-ttu-id="aa250-108">Formato OData</span><span class="sxs-lookup"><span data-stu-id="aa250-108">OData Format</span></span>  
 <span data-ttu-id="aa250-109">La mayoría de los servicios OData devuelven resultados en varios formatos.</span><span class="sxs-lookup"><span data-stu-id="aa250-109">Most OData services return results in multiple formats.</span></span> <span data-ttu-id="aa250-110">Puede especificar el formato del conjunto de resultados mediante la opción de consulta $format.</span><span class="sxs-lookup"><span data-stu-id="aa250-110">You can specify the format of the result set by using the $format query option.</span></span> <span data-ttu-id="aa250-111">Los formatos como JSON y JSON Light son más eficaces que ATOM/XML, y pueden conseguir mejor rendimiento cuando se transfieren grandes cantidades de datos.</span><span class="sxs-lookup"><span data-stu-id="aa250-111">Formats such as JSON and JSON Light are more efficient than ATOM/XML, and may give you better performance when transferring large amounts of data.</span></span> <span data-ttu-id="aa250-112">En la tabla siguiente se muestran resultados de pruebas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="aa250-112">The following table provides results from sample tests.</span></span> <span data-ttu-id="aa250-113">Como puede ver, hubo una mejora del rendimiento del 30-53 % al cambiar de ATOM a JSON y del 67 % cuando se cambió de ATOM al nuevo formato JSON Light (disponible en WCF Data Services 5.1).</span><span class="sxs-lookup"><span data-stu-id="aa250-113">As you can see, there was a 30-53% performance gain when switching from ATOM to JSON and 67% performance gain when switching from ATOM to the new JSON light format (available in WCF Data Services 5.1).</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="aa250-114">Filas</span><span class="sxs-lookup"><span data-stu-id="aa250-114">Rows</span></span>|<span data-ttu-id="aa250-115">ATOM</span><span class="sxs-lookup"><span data-stu-id="aa250-115">ATOM</span></span>|<span data-ttu-id="aa250-116">JSON</span><span class="sxs-lookup"><span data-stu-id="aa250-116">JSON</span></span>|<span data-ttu-id="aa250-117">JSON (Light)</span><span class="sxs-lookup"><span data-stu-id="aa250-117">JSON (Light)</span></span>|  
|<span data-ttu-id="aa250-118">10000</span><span class="sxs-lookup"><span data-stu-id="aa250-118">10000</span></span>|<span data-ttu-id="aa250-119">113 segundos</span><span class="sxs-lookup"><span data-stu-id="aa250-119">113 seconds</span></span>|<span data-ttu-id="aa250-120">74 segundos</span><span class="sxs-lookup"><span data-stu-id="aa250-120">74 seconds</span></span>|<span data-ttu-id="aa250-121">68 segundos</span><span class="sxs-lookup"><span data-stu-id="aa250-121">68 seconds</span></span>|  
|<span data-ttu-id="aa250-122">1000000</span><span class="sxs-lookup"><span data-stu-id="aa250-122">1000000</span></span>|<span data-ttu-id="aa250-123">1110 segundos</span><span class="sxs-lookup"><span data-stu-id="aa250-123">1110 seconds</span></span>|<span data-ttu-id="aa250-124">853 segundos</span><span class="sxs-lookup"><span data-stu-id="aa250-124">853 seconds</span></span>|<span data-ttu-id="aa250-125">665 segundos</span><span class="sxs-lookup"><span data-stu-id="aa250-125">665 seconds</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="aa250-126">El origen OData de SSIS usa ODataLib 5.5.0 para analizar las fuentes OData y puede leer todos los formatos admitidos por esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="aa250-126">The SSIS OData Source uses ODataLib 5.5.0 to parse OData feeds and it can read all formats supported by this library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aa250-127">En esta sección</span><span class="sxs-lookup"><span data-stu-id="aa250-127">In This Section</span></span>  
  
-   [<span data-ttu-id="aa250-128">Instalar y desinstalar el Componente de origen OData</span><span class="sxs-lookup"><span data-stu-id="aa250-128">Install and Uninstall OData Source Component</span></span>](../install-and-uninstall-odata-source-component.md)  
  
-   [<span data-ttu-id="aa250-129">Tutorial: usar el origen OData &#91;SSIS&#93;</span><span class="sxs-lookup"><span data-stu-id="aa250-129">Tutorial: Using the OData Source &#91;SSIS&#93;</span></span>](tutorial-using-the-odata-source.md)  
  
-   [<span data-ttu-id="aa250-130">Modificar una consulta de origen OData en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="aa250-130">Modify OData Source Query at Runtime</span></span>](modify-odata-source-query-at-runtime.md)  
  
-   [<span data-ttu-id="aa250-131">Editor de origen OData &#40;página Conexión&#41;</span><span class="sxs-lookup"><span data-stu-id="aa250-131">OData Source Editor &#40;Connection Page&#41;</span></span>](../odata-source-editor-connection-page.md)  
  
-   [<span data-ttu-id="aa250-132">Editor de origen OData &#40;página Columnas&#41;</span><span class="sxs-lookup"><span data-stu-id="aa250-132">OData Source Editor &#40;Columns Page&#41;</span></span>](../odata-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="aa250-133">Editor de origen OData &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="aa250-133">OData Source Editor &#40;Error Output Page&#41;</span></span>](../odata-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="aa250-134">Propiedades de orígenes OData</span><span class="sxs-lookup"><span data-stu-id="aa250-134">OData Source Properties</span></span>](odata-source-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="aa250-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa250-135">See Also</span></span>  
 [<span data-ttu-id="aa250-136">Administrador de conexiones OData</span><span class="sxs-lookup"><span data-stu-id="aa250-136">OData Connection Manager</span></span>](../connection-manager/odata-connection-manager.md)  
  
  
