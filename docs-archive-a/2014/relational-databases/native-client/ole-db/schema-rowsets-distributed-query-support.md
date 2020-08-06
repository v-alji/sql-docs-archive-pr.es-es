---
title: Compatibilidad con consultas distribuidas en conjuntos de filas de esquema | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- DBPROPSET_SQLSERVERSESSION property
- schema rowsets [OLE DB]
- distributed queries [SQL Server], SQL Server Native Client OLE DB provider
- OLE DB, schema rowsets
- OLE DB rowsets, schema
- rowsets [OLE DB], schema
ms.assetid: 11354bb6-be42-4d8d-854c-42dd3dc38656
author: rothja
ms.author: jroth
ms.openlocfilehash: 48b57bbf40590f8ad5c049268f25fe66d2f94357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669647"
---
# <a name="distributed-query-support-in-schema-rowsets"></a><span data-ttu-id="a01f1-102">Compatibilidad con consultas distribuidas en conjuntos de filas de esquema</span><span class="sxs-lookup"><span data-stu-id="a01f1-102">Distributed Query Support in Schema Rowsets</span></span>
  <span data-ttu-id="a01f1-103">Para admitir [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] las consultas distribuidas, la [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] interfaz **IDBSchemaRowset** del proveedor de OLE DB de Native Client devuelve metadatos en servidores vinculados.</span><span class="sxs-lookup"><span data-stu-id="a01f1-103">To support [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] distributed queries, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider **IDBSchemaRowset** interface returns metadata on linked servers.</span></span>  
  
 <span data-ttu-id="a01f1-104">Si la propiedad SSPROP_QUOTEDCATALOGNAMES de DBPROPSET_SQLSERVERSESSION es VARIANT_TRUE, puede especificarse un identificador entrecomillado para el nombre del catálogo (por ejemplo, "my.catalog").</span><span class="sxs-lookup"><span data-stu-id="a01f1-104">If the DBPROPSET_SQLSERVERSESSION property SSPROP_QUOTEDCATALOGNAMES is VARIANT_TRUE, a quoted identifier can be specified for the catalog name (for example "my.catalog").</span></span> <span data-ttu-id="a01f1-105">Al restringir la salida del conjunto de filas de esquema por catálogo, el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client reconoce un nombre de dos partes que contiene el nombre del servidor vinculado y del catálogo.</span><span class="sxs-lookup"><span data-stu-id="a01f1-105">When restricting schema rowset output by catalog, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes a two-part name containing the linked server and catalog name.</span></span> <span data-ttu-id="a01f1-106">Para los conjuntos de filas de esquema en la tabla siguiente, especifique un nombre de catálogo de dos partes como _linked_server_**.** _Catalog_ restringe la salida al catálogo aplicable del servidor vinculado con nombre.</span><span class="sxs-lookup"><span data-stu-id="a01f1-106">For the schema rowsets in the table below, specifying a two-part catalog name as _linked_server_**.**_catalog_ restricts output to the applicable catalog of the named linked server.</span></span>  
  
|<span data-ttu-id="a01f1-107">Conjunto de filas de esquema</span><span class="sxs-lookup"><span data-stu-id="a01f1-107">Schema rowset</span></span>|<span data-ttu-id="a01f1-108">Restricción de catálogo</span><span class="sxs-lookup"><span data-stu-id="a01f1-108">Catalog restriction</span></span>|  
|-------------------|-------------------------|  
|<span data-ttu-id="a01f1-109">DBSCHEMA_CATALOGS</span><span class="sxs-lookup"><span data-stu-id="a01f1-109">DBSCHEMA_CATALOGS</span></span>|<span data-ttu-id="a01f1-110">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="a01f1-110">CATALOG_NAME</span></span>|  
|<span data-ttu-id="a01f1-111">DBSCHEMA_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="a01f1-111">DBSCHEMA_COLUMNS</span></span>|<span data-ttu-id="a01f1-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a01f1-112">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="a01f1-113">DBSCHEMA_PRIMARY_KEYS</span><span class="sxs-lookup"><span data-stu-id="a01f1-113">DBSCHEMA_PRIMARY_KEYS</span></span>|<span data-ttu-id="a01f1-114">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a01f1-114">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="a01f1-115">DBSCHEMA_TABLES</span><span class="sxs-lookup"><span data-stu-id="a01f1-115">DBSCHEMA_TABLES</span></span>|<span data-ttu-id="a01f1-116">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a01f1-116">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="a01f1-117">DBSCHEMA_FOREIGN_KEYS</span><span class="sxs-lookup"><span data-stu-id="a01f1-117">DBSCHEMA_FOREIGN_KEYS</span></span>|<span data-ttu-id="a01f1-118">PK_TABLE_CATALOG FK_TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a01f1-118">PK_TABLE_CATALOG FK_TABLE_CATALOG</span></span>|  
|<span data-ttu-id="a01f1-119">DBSCHEMA_INDEXES</span><span class="sxs-lookup"><span data-stu-id="a01f1-119">DBSCHEMA_INDEXES</span></span>|<span data-ttu-id="a01f1-120">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a01f1-120">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="a01f1-121">DBSCHEMA_COLUMN_PRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="a01f1-121">DBSCHEMA_COLUMN_PRIVILEGES</span></span>|<span data-ttu-id="a01f1-122">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a01f1-122">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="a01f1-123">DBSCHEMA_TABLE_PRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="a01f1-123">DBSCHEMA_TABLE_PRIVILEGES</span></span>|<span data-ttu-id="a01f1-124">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="a01f1-124">TABLE_CATALOG</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="a01f1-125">Para restringir un conjunto de filas de esquema a todos los catálogos de un servidor vinculado, use la sintaxis *linked_server* (donde el separador de punto forma parte de la especificación del nombre).</span><span class="sxs-lookup"><span data-stu-id="a01f1-125">To restrict a schema rowset to all catalogs from a linked server, use the syntax *linked_server* (where the period separator is part of the name specification).</span></span> <span data-ttu-id="a01f1-126">Esta sintaxis equivale a especificar NULL para la restricción del nombre de catálogo y también se utiliza cuando el servidor vinculado indica un origen de datos que no admite catálogos.</span><span class="sxs-lookup"><span data-stu-id="a01f1-126">This syntax is equivalent to specifying NULL for the catalog name restriction and is also used when the linked server indicates a data source that does not support catalogs.</span></span>  
  
 <span data-ttu-id="a01f1-127">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client define el conjunto de filas de esquema LINKEDSERVERS, y devuelve una lista de OLE DB orígenes de datos registrados como servidores vinculados.</span><span class="sxs-lookup"><span data-stu-id="a01f1-127">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the schema rowset LINKEDSERVERS, returning a list of OLE DB data sources registered as linked servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a01f1-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a01f1-128">See Also</span></span>  
 <span data-ttu-id="a01f1-129">[Compatibilidad de conjunto de filas de esquema &#40;OLE DB&#41;](schema-rowset-support-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="a01f1-129">[Schema Rowset Support &#40;OLE DB&#41;](schema-rowset-support-ole-db.md) </span></span>  
 [<span data-ttu-id="a01f1-130">LINKEDSERVERS Rowset &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="a01f1-130">LINKEDSERVERS Rowset &#40;OLE DB&#41;</span></span>](schema-rowsets-linkedservers-rowset.md)  
  
  
