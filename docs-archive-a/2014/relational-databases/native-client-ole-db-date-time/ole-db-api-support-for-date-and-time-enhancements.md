---
title: Compatibilidad de la API de OLE DB con las mejoras de fecha y hora | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB, date/time improvements
ms.assetid: e65c9253-bd99-4dc3-9cb8-7613f754c966
author: rothja
ms.author: jroth
ms.openlocfilehash: cdb17f0d2104373ea797ff9403cc417dfaa3d868
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675845"
---
# <a name="ole-db-api-support-for-date-and-time-enhancements"></a><span data-ttu-id="c4394-102">Compatibilidad de API de OLE DB con las mejoras de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="c4394-102">OLE DB API Support for Date and Time Enhancements</span></span>
  <span data-ttu-id="c4394-103">Las siguientes API de OLE DB son compatibles con las características mejoradas de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="c4394-103">The following OLE DB APIs support enhanced date/time features.</span></span>  
  
|<span data-ttu-id="c4394-104">Función</span><span class="sxs-lookup"><span data-stu-id="c4394-104">Function</span></span>|<span data-ttu-id="c4394-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4394-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="c4394-106">IAccessor::CreateAccessor</span><span class="sxs-lookup"><span data-stu-id="c4394-106">IAccessor::CreateAccessor</span></span>|<span data-ttu-id="c4394-107">Se agrega una marca en la estructura DBBINDING para habilitar las aplicaciones para diferenciar entre valores `datetime`, `datetime2` y `smalldatetime`.</span><span class="sxs-lookup"><span data-stu-id="c4394-107">A flag is added in the DBBINDING structure to enable applications to discriminate between `datetime`, `datetime2`, and `smalldatetime` values.</span></span> <span data-ttu-id="c4394-108">Para más información, consulte [Parámetros y metadatos de conjuntos de filas](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="c4394-108">For more information, see [Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="c4394-109">IBCPSession::BCPColFmt</span><span class="sxs-lookup"><span data-stu-id="c4394-109">IBCPSession::BCPColFmt</span></span>|<span data-ttu-id="c4394-110">Para obtener más información, vea [cambios de copia masiva para tipos de fecha y hora mejorados &#40;OLE DB y ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c4394-110">For more information, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>|  
|<span data-ttu-id="c4394-111">ICommandWithParameters::GetParameterInfo</span><span class="sxs-lookup"><span data-stu-id="c4394-111">ICommandWithParameters::GetParameterInfo</span></span>|<span data-ttu-id="c4394-112">Para más información, consulte [Parámetros y metadatos de conjuntos de filas](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="c4394-112">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="c4394-113">ICommandWithParameters::SetParameterinfo</span><span class="sxs-lookup"><span data-stu-id="c4394-113">ICommandWithParameters::SetParameterinfo</span></span>|<span data-ttu-id="c4394-114">Para más información, consulte [Parámetros y metadatos de conjuntos de filas](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="c4394-114">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="c4394-115">IColumnsRowset::GetColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="c4394-115">IColumnsRowset::GetColumnsRowset</span></span>|<span data-ttu-id="c4394-116">Para más información, consulte [Parámetros y metadatos de conjuntos de filas](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="c4394-116">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="c4394-117">IColumnsInfo::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="c4394-117">IColumnsInfo::GetColumnInfo</span></span>|<span data-ttu-id="c4394-118">Para más información, consulte [Parámetros y metadatos de conjuntos de filas](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="c4394-118">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="c4394-119">IDBSchemaRowset::GetRowset</span><span class="sxs-lookup"><span data-stu-id="c4394-119">IDBSchemaRowset::GetRowset</span></span>|<span data-ttu-id="c4394-120">Para obtener detalles de los conjuntos de filas de esquema afectados, consulte [Fecha y hora y conjuntos de filas de esquema](../native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="c4394-120">For details of the affected schema rowsets, see[Date and Time and Schema Rowsets](../native-client-ole-db-rowsets/rowsets.md).</span></span>|  
|<span data-ttu-id="c4394-121">IRowsetFastLoad</span><span class="sxs-lookup"><span data-stu-id="c4394-121">IRowsetFastLoad</span></span>|<span data-ttu-id="c4394-122">Esta interfaz admite los nuevos tipos de fecha y hora, pero no hay ningún cambio en su interfaz.</span><span class="sxs-lookup"><span data-stu-id="c4394-122">This interface supports the new date/time types, but there is no change to its interface.</span></span>|  
|<span data-ttu-id="c4394-123">ITableDefinition::CreateTable</span><span class="sxs-lookup"><span data-stu-id="c4394-123">ITableDefinition::CreateTable</span></span>|<span data-ttu-id="c4394-124">Para obtener más información [Compatibilidad con tipos de datos para mejoras de fecha y hora de OLE DB](data-type-support-for-ole-db-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="c4394-124">For more information, see [Data Type Support for OLE DB Date and Time Improvements](data-type-support-for-ole-db-date-and-time-improvements.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4394-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4394-125">See Also</span></span>  
 [<span data-ttu-id="c4394-126">Mejoras de fecha y hora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="c4394-126">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
