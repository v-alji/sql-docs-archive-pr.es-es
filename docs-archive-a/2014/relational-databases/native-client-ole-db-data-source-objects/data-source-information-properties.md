---
title: Propiedades de información de orígenes de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, data source properties
- properties [OLE DB]
- data source properties [OLE DB]
- information properties [OLE DB]
- OLE DB data source properties [SQL Server Native Client]
ms.assetid: 7fd80e47-5bd9-41e2-a3d3-091a7c8c5f2b
author: rothja
ms.author: jroth
ms.openlocfilehash: c10a4e762bbe3421e720753941f5e0a5702832ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749777"
---
# <a name="data-source-information-properties"></a><span data-ttu-id="55961-102">Propiedades de información de orígenes de datos</span><span class="sxs-lookup"><span data-stu-id="55961-102">Data Source Information Properties</span></span>
  <span data-ttu-id="55961-103">En el conjunto de propiedades específico del proveedor DBPROPSET_SQLSERVERDATASOURCE, el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client define las siguientes propiedades de información del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="55961-103">In the provider-specific property set DBPROPSET_SQLSERVERDATASOURCEINFO, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following data source information properties.</span></span>  
  
|<span data-ttu-id="55961-104">Id. de propiedad</span><span class="sxs-lookup"><span data-stu-id="55961-104">Property ID</span></span>|<span data-ttu-id="55961-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="55961-105">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="55961-106">SSPROP_COLUMNLEVELCOLLATION</span><span class="sxs-lookup"><span data-stu-id="55961-106">SSPROP_COLUMNLEVELCOLLATION</span></span>|<span data-ttu-id="55961-107">Escriba:  VT_BOOL</span><span class="sxs-lookup"><span data-stu-id="55961-107">Type: VT_BOOL</span></span><br /><br /> <span data-ttu-id="55961-108">L/E: Lectura</span><span class="sxs-lookup"><span data-stu-id="55961-108">R/W: Read</span></span><br /><br /> <span data-ttu-id="55961-109">Valor predeterminado: VARIANT_TRUE</span><span class="sxs-lookup"><span data-stu-id="55961-109">Default: VARIANT_TRUE</span></span><br /><br /> <span data-ttu-id="55961-110">Descripción: Se utiliza para determinar si se admite la intercalación de columnas.</span><span class="sxs-lookup"><span data-stu-id="55961-110">Description: Used to determine if column collation is supported.</span></span><br /><br /> <span data-ttu-id="55961-111">VARIANT_TRUE: Se admite la intercalación de columnas.</span><span class="sxs-lookup"><span data-stu-id="55961-111">VARIANT_TRUE: Column level collation is supported.</span></span><br /><br /> <span data-ttu-id="55961-112">VARIANT_FALSE: No se admite la intercalación de columnas.</span><span class="sxs-lookup"><span data-stu-id="55961-112">VARIANT_FALSE: Column level collation is not supported.</span></span>|  
|<span data-ttu-id="55961-113">SSPROP_UNICODELCID</span><span class="sxs-lookup"><span data-stu-id="55961-113">SSPROP_UNICODELCID</span></span>|<span data-ttu-id="55961-114">Tipo: VT_I4 L/E: Lectura</span><span class="sxs-lookup"><span data-stu-id="55961-114">Type: VT_I4 R/W: Read</span></span><br /><br /> <span data-ttu-id="55961-115">Descripción: Id. de configuración regional de Unicode.</span><span class="sxs-lookup"><span data-stu-id="55961-115">Description: Unicode locale ID.</span></span><br /><br /> <span data-ttu-id="55961-116">Se trata de la configuración regional utilizada para ordenar datos Unicode.</span><span class="sxs-lookup"><span data-stu-id="55961-116">This is the locale used for Unicode data sorting.</span></span>|  
|<span data-ttu-id="55961-117">SSPROP_UNICODECOMPARISONSTYLE</span><span class="sxs-lookup"><span data-stu-id="55961-117">SSPROP_UNICODECOMPARISONSTYLE</span></span>|<span data-ttu-id="55961-118">Tipo: VT_I4 L/E: Lectura</span><span class="sxs-lookup"><span data-stu-id="55961-118">Type: VT_I4 R/W: Read</span></span><br /><br /> <span data-ttu-id="55961-119">Descripción: Estilo de comparación Unicode.</span><span class="sxs-lookup"><span data-stu-id="55961-119">Description: Unicode comparison style.</span></span><br /><br /> <span data-ttu-id="55961-120">Las opciones de ordenación utilizadas para ordenar datos Unicode.</span><span class="sxs-lookup"><span data-stu-id="55961-120">The sorting options used for Unicode data sorting.</span></span>|  
  
 <span data-ttu-id="55961-121">En el conjunto de propiedades específico del proveedor DBPROPSET_SQLSERVERSESSION, el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client define la propiedad adicional siguiente.</span><span class="sxs-lookup"><span data-stu-id="55961-121">In the provider-specific property set DBPROPSET_SQLSERVERSTREAM, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following additional property.</span></span>  
  
|<span data-ttu-id="55961-122">Id. de propiedad</span><span class="sxs-lookup"><span data-stu-id="55961-122">Property ID</span></span>|<span data-ttu-id="55961-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="55961-123">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="55961-124">SSPROP_STREAM_XMLROOT</span><span class="sxs-lookup"><span data-stu-id="55961-124">SSPROP_STREAM_XMLROOT</span></span>|<span data-ttu-id="55961-125">Tipo: VT_BSTR L/E: Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="55961-125">Type: VT_BSTR R/W: Read/Write</span></span><br /><br /> <span data-ttu-id="55961-126">Descripción: El resultado de una consulta FOR XML podría no ser un documento bien formado.</span><span class="sxs-lookup"><span data-stu-id="55961-126">Description: The result of a FOR XML query may not be a well-formed document.</span></span> <span data-ttu-id="55961-127">Cuando se especifica esta propiedad, se incluye el resultado de una consulta 'select ... for XML' en la etiqueta proporcionada por la propiedad para devolver un documento XML bien formado.</span><span class="sxs-lookup"><span data-stu-id="55961-127">When this property is specified, the result of a 'select ... for XML' query is wrapped in the root tag provided by this property to return a well formed XML document.</span></span> <span data-ttu-id="55961-128">Si la consulta se ejecuta en el explorador, puede hacer que el explorador muestre los errores de análisis al cargar el resultado.</span><span class="sxs-lookup"><span data-stu-id="55961-128">If the query is executed in the browser it may cause the browser to display parser errors when loading the result.</span></span> <span data-ttu-id="55961-129">Para evitar el error, SQL ISAPI admite la palabra clave ROOT.</span><span class="sxs-lookup"><span data-stu-id="55961-129">To avoid the error, SQL ISAPI supports the keyword ROOT.</span></span> <span data-ttu-id="55961-130">Esta palabra clave se asigna a la propiedad SSPROP_STREAM_XMLROOT.</span><span class="sxs-lookup"><span data-stu-id="55961-130">This keyword maps to SSPROP_STREAM_XMLROOT property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55961-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55961-131">See Also</span></span>  
 [<span data-ttu-id="55961-132">Objetos de origen de datos &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="55961-132">Data Source Objects &#40;OLE DB&#41;</span></span>](data-source-objects-ole-db.md)  
  
  
