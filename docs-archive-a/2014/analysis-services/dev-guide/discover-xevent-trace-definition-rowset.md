---
title: DISCOVER_XEVENT_TRACE_DEFINITION conjunto de filas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: e1ce2d2d-f994-4318-801a-ee0385aecd84
author: minewiskan
ms.author: owend
ms.openlocfilehash: bedd6ec66a188738ac9a522b4802b3b431e82f36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747241"
---
# <a name="discover_xevent_trace_definition-rowset"></a><span data-ttu-id="92542-102">Conjunto de filas DISCOVER_XEVENT_TRACE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="92542-102">DISCOVER_XEVENT_TRACE_DEFINITION Rowset</span></span>
  <span data-ttu-id="92542-103">Proporciona información acerca de los seguimientos XEvent que están activos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="92542-103">Provides information about XEvent traces that are currently active on the server.</span></span>  
  
 <span data-ttu-id="92542-104">**Se aplica a:** modelos tabulares, modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="92542-104">**Applies to:** tabular models, multidimensional models</span></span>  
  
## <a name="rowset-columns"></a><span data-ttu-id="92542-105">Columnas del conjunto de filas</span><span class="sxs-lookup"><span data-stu-id="92542-105">Rowset Columns</span></span>  
 <span data-ttu-id="92542-106">El conjunto de filas `DISCOVER_XEVENT_TRACE_DEFINITION` contiene las siguientes columnas.</span><span class="sxs-lookup"><span data-stu-id="92542-106">The `DISCOVER_XEVENT_TRACE_DEFINITION` rowset contains the following columns.</span></span>  
  
|<span data-ttu-id="92542-107">Nombre de la columna</span><span class="sxs-lookup"><span data-stu-id="92542-107">Column name</span></span>|<span data-ttu-id="92542-108">Indicador de tipo</span><span class="sxs-lookup"><span data-stu-id="92542-108">Type indicator</span></span>|<span data-ttu-id="92542-109">Length</span><span class="sxs-lookup"><span data-stu-id="92542-109">Length</span></span>|<span data-ttu-id="92542-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="92542-110">Description</span></span>|  
|-----------------|--------------------|------------|-----------------|  
|`Data`|`DBTYPE_WSTR`||<span data-ttu-id="92542-111">La definición XML del seguimiento de XEvent.</span><span class="sxs-lookup"><span data-stu-id="92542-111">The XML definition of the XEvent trace.</span></span>|  
  
 <span data-ttu-id="92542-112">Este conjunto de filas de esquema no está ordenado.</span><span class="sxs-lookup"><span data-stu-id="92542-112">This schema rowset is not sorted.</span></span>  
  
## <a name="using-adomdnet-to-return-the-rowset"></a><span data-ttu-id="92542-113">Usar ADOMD.NET para devolver el conjunto de filas</span><span class="sxs-lookup"><span data-stu-id="92542-113">Using ADOMD.NET to return the rowset</span></span>  
 <span data-ttu-id="92542-114">Cuando se utilizan ADOMD.NET y el conjunto de filas de esquema para recuperar metadatos, puede utilizar el GUID o una cadena para hacer referencia a un objeto de conjunto de filas de esquema del método GetSchemaDataSet.</span><span class="sxs-lookup"><span data-stu-id="92542-114">When using ADOMD.NET and the schema rowset to retrieve metadata, you can use either the GUID or string to reference a schema rowset object in the GetSchemaDataSet method.</span></span> <span data-ttu-id="92542-115">Para obtener más información, vea [Working with Schema Rowsets in ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets).</span><span class="sxs-lookup"><span data-stu-id="92542-115">For more information, see [Working with Schema Rowsets in ADOMD.NET](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-client/retrieving-metadata-working-with-schema-rowsets).</span></span>  
  
 <span data-ttu-id="92542-116">La tabla siguiente proporciona el GUID y los valores de cadena que identifican este conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="92542-116">The following table provides the GUID and string values that identify this rowset.</span></span>  
  
|<span data-ttu-id="92542-117">Argumento</span><span class="sxs-lookup"><span data-stu-id="92542-117">Argument</span></span>|<span data-ttu-id="92542-118">Value</span><span class="sxs-lookup"><span data-stu-id="92542-118">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="92542-119">GUID</span><span class="sxs-lookup"><span data-stu-id="92542-119">GUID</span></span>|<span data-ttu-id="92542-120">a07ccd1c-8148-11d0-87bb-00c04fc33942</span><span class="sxs-lookup"><span data-stu-id="92542-120">a07ccd1c-8148-11d0-87bb-00c04fc33942</span></span>|  
|<span data-ttu-id="92542-121">String</span><span class="sxs-lookup"><span data-stu-id="92542-121">String</span></span>|<span data-ttu-id="92542-122">DISCOVER_XEVENT_TRACE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="92542-122">DISCOVER_XEVENT_TRACE_DEFINITION</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92542-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92542-123">See Also</span></span>  
 <span data-ttu-id="92542-124">[XML for Analysis conjuntos de filas de esquema](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/xml-for-analysis-schema-rowsets) </span><span class="sxs-lookup"><span data-stu-id="92542-124">[XML for Analysis Schema Rowsets](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/xml-for-analysis-schema-rowsets) </span></span>  
 <span data-ttu-id="92542-125">[Use SQL Server Extended Events &#40;XEvents&#41; para supervisar Analysis Services](../instances/monitor-analysis-services-with-sql-server-extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="92542-125">[Use SQL Server Extended Events &#40;XEvents&#41; to Monitor Analysis Services](../instances/monitor-analysis-services-with-sql-server-extended-events.md) </span></span>  
 [<span data-ttu-id="92542-126">Usar vistas de administración dinámica &#40;DMV&#41; para supervisar Analysis Services</span><span class="sxs-lookup"><span data-stu-id="92542-126">Use Dynamic Management Views &#40;DMVs&#41; to Monitor Analysis Services</span></span>](../instances/use-dynamic-management-views-dmvs-to-monitor-analysis-services.md)  
  
  
