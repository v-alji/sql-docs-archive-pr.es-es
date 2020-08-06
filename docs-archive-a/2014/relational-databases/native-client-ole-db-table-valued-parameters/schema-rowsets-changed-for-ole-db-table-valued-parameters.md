---
title: Conjuntos de filas de esquema cambiados para los parámetros con valores de tabla de OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- schema rowsets [OLE DB]
- table-valued parameters (OLE DB), schema rowsets changed for (OLE DB)
ms.assetid: 581e3ead-53db-44da-8718-f3fc4b5108f1
author: rothja
ms.author: jroth
ms.openlocfilehash: e09d5127f332c8b6cc948be3eeb74e600bb856f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749262"
---
# <a name="schema-rowsets-changed-for-ole-db-table-valued-parameters"></a><span data-ttu-id="a5404-102">Conjuntos de filas de esquema cambiados para los parámetros con valores de tabla de OLE DB</span><span class="sxs-lookup"><span data-stu-id="a5404-102">Schema Rowsets Changed for OLE DB Table-Valued Parameters</span></span>
  <span data-ttu-id="a5404-103">A continuación figuran los conjuntos de filas de esquema que se han cambiado o agregado para admitir los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="a5404-103">The following are the schema rowsets that have been changed or added to support table-valued parameters.</span></span>  
  
|<span data-ttu-id="a5404-104">Conjunto de filas de esquema</span><span class="sxs-lookup"><span data-stu-id="a5404-104">Schema rowset</span></span>|<span data-ttu-id="a5404-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5404-105">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="a5404-106">DBSCHEMA_PROCEDURE_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a5404-106">DBSCHEMA_PROCEDURE_PARAMETERS</span></span>|<span data-ttu-id="a5404-107">Se han agregado dos nuevas columnas al final del conjunto de filas denominadas SS_TYPE_CATALOG_NAME y SS_TYPE_SCHEMANAME.</span><span class="sxs-lookup"><span data-stu-id="a5404-107">Two new columns were added at the end of the rowset named SS_TYPE_CATALOG_NAME and SS_TYPE_SCHEMANAME.</span></span> <span data-ttu-id="a5404-108">Estas columnas se podrían volver a usar para tipos futuros.</span><span class="sxs-lookup"><span data-stu-id="a5404-108">These columns could be re-used for future types.</span></span> <span data-ttu-id="a5404-109">Las columnas TYPE_NAME y LOCAL_TYPE_NAME contendrán el nombre del parámetro con valores de tabla de tipo TABLE.</span><span class="sxs-lookup"><span data-stu-id="a5404-109">The TYPE_NAME and LOCAL_TYPE_NAME columns will contain the name of the table-valued parameter TABLE type.</span></span> <span data-ttu-id="a5404-110">La columna DATA_TYPE tendrá el valor DBTYPE_TABLE = 143 para los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="a5404-110">The DATA_TYPE column will have value DBTYPE_TABLE = 143 for table-valued parameters.</span></span>|  
|<span data-ttu-id="a5404-111">DBSCHEMA_TABLE_TYPES</span><span class="sxs-lookup"><span data-stu-id="a5404-111">DBSCHEMA_TABLE_TYPES</span></span>|<span data-ttu-id="a5404-112">Se ha agregado este conjunto de filas para admitir los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="a5404-112">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="a5404-113">Es idéntico a DBSCHEMA_TABLES, salvo que únicamente devuelve los metadatos para los tipos de tabla, en lugar de para las tablas, las vistas o los sinónimos.</span><span class="sxs-lookup"><span data-stu-id="a5404-113">It is identical to DBSCHEMA_TABLES, except that it returns metadata only for table types, rather than for tables, views, or synonyms.</span></span> <span data-ttu-id="a5404-114">La columna TABLE_TYPE tendrá el valor 'TABLE TYPE'.</span><span class="sxs-lookup"><span data-stu-id="a5404-114">The TABLE_TYPE column will have the value 'TABLE TYPE'.</span></span>|  
|<span data-ttu-id="a5404-115">DBSCHEMA_TABLE_TYPE_PRIMARY_KEYS</span><span class="sxs-lookup"><span data-stu-id="a5404-115">DBSCHEMA_TABLE_TYPE_PRIMARY_KEYS</span></span>|<span data-ttu-id="a5404-116">Se ha agregado este conjunto de filas para admitir los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="a5404-116">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="a5404-117">Es idéntico a DBSCHEMA_PRIMARY_KEYS, salvo que únicamente devuelve los metadatos de las claves principales para los tipos de tabla, en lugar de para las tablas.</span><span class="sxs-lookup"><span data-stu-id="a5404-117">It is identical to DBSCHEMA_PRIMARY_KEYS, except that it returns primary keys metadata only for table types, rather than for tables.</span></span>|  
|<span data-ttu-id="a5404-118">DBSCHEMA_TABLE_TYPE_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="a5404-118">DBSCHEMA_TABLE_TYPE_COLUMNS</span></span>|<span data-ttu-id="a5404-119">Se ha agregado este conjunto de filas para admitir los parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="a5404-119">This rowset was added to support table-valued parameters.</span></span> <span data-ttu-id="a5404-120">Es idéntico a DBSCHEMA_COLUMNS, salvo que únicamente devuelve los metadatos de columna para los tipos de tabla, en lugar de para las tablas, las vistas o los sinónimos.</span><span class="sxs-lookup"><span data-stu-id="a5404-120">It is identical to DBSCHEMA_COLUMNS, except that it returns column metadata only for table types, rather than for tables, views, or synonyms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5404-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5404-121">See Also</span></span>  
 <span data-ttu-id="a5404-122">[Parámetros con valores de tabla &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="a5404-122">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="a5404-123">Usar parámetros con valores de tabla &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="a5404-123">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
