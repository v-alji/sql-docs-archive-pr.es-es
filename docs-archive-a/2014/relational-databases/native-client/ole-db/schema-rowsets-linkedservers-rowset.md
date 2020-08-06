---
title: Conjunto de filas LINKEDSERVERS (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- LINKEDSERVERS rowset
- enumerating data sources [OLE DB]
ms.assetid: 2633fd8a-65e7-498d-9aed-8e4b1cca2381
author: rothja
ms.author: jroth
ms.openlocfilehash: 80eded31ebae744e272757a53a7fd1f4b56bf358
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669645"
---
# <a name="linkedservers-rowset-ole-db"></a><span data-ttu-id="92c0c-102">Conjunto de filas LINKEDSERVERS (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="92c0c-102">LINKEDSERVERS Rowset (OLE DB)</span></span>
  <span data-ttu-id="92c0c-103">El conjunto de filas **LINKEDSERVERS** enumera los orígenes de datos de la organización que pueden participar en consultas distribuidas de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92c0c-103">The **LINKEDSERVERS** rowset enumerates organization data sources that can participate in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] distributed queries.</span></span>  
  
 <span data-ttu-id="92c0c-104">El conjunto de filas **LINKEDSERVERS** contiene las siguientes columnas.</span><span class="sxs-lookup"><span data-stu-id="92c0c-104">The **LINKEDSERVERS** rowset contains the following columns.</span></span>  
  
|<span data-ttu-id="92c0c-105">Nombre de la columna</span><span class="sxs-lookup"><span data-stu-id="92c0c-105">Column name</span></span>|<span data-ttu-id="92c0c-106">Indicador de tipo</span><span class="sxs-lookup"><span data-stu-id="92c0c-106">Type indicator</span></span>|<span data-ttu-id="92c0c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="92c0c-107">Description</span></span>|  
|-----------------|--------------------|-----------------|  
|<span data-ttu-id="92c0c-108">SVR_NAME</span><span class="sxs-lookup"><span data-stu-id="92c0c-108">SVR_NAME</span></span>|<span data-ttu-id="92c0c-109">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="92c0c-109">DBTYPE_WSTR</span></span>|<span data-ttu-id="92c0c-110">Nombre de un servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="92c0c-110">Name of a linked server.</span></span>|  
|<span data-ttu-id="92c0c-111">SVR_PRODUCT</span><span class="sxs-lookup"><span data-stu-id="92c0c-111">SVR_PRODUCT</span></span>|<span data-ttu-id="92c0c-112">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="92c0c-112">DBTYPE_WSTR</span></span>|<span data-ttu-id="92c0c-113">Fabricante u otro nombre que identifica el tipo de almacén de datos representado por el nombre del servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="92c0c-113">Manufacturer or other name identifying the type of data store represented by the name of the linked server.</span></span>|  
|<span data-ttu-id="92c0c-114">SVR_PROVIDERNAME</span><span class="sxs-lookup"><span data-stu-id="92c0c-114">SVR_PROVIDERNAME</span></span>|<span data-ttu-id="92c0c-115">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="92c0c-115">DBTYPE_WSTR</span></span>|<span data-ttu-id="92c0c-116">Nombre descriptivo del proveedor OLE DB que se usa para consumir datos del servidor.</span><span class="sxs-lookup"><span data-stu-id="92c0c-116">Friendly name of the OLE DB provider used to consume data from the server.</span></span>|  
|<span data-ttu-id="92c0c-117">SVR_DATASOURCE</span><span class="sxs-lookup"><span data-stu-id="92c0c-117">SVR_DATASOURCE</span></span>|<span data-ttu-id="92c0c-118">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="92c0c-118">DBTYPE_WSTR</span></span>|<span data-ttu-id="92c0c-119">Cadena DBPROP_INIT_DATASOURCE de OLE DB que se usa para adquirir un origen de datos del proveedor.</span><span class="sxs-lookup"><span data-stu-id="92c0c-119">OLE DB DBPROP_INIT_DATASOURCE string used to acquire a data source from the provider.</span></span>|  
|<span data-ttu-id="92c0c-120">SVR_PROVIDERSTRING</span><span class="sxs-lookup"><span data-stu-id="92c0c-120">SVR_PROVIDERSTRING</span></span>|<span data-ttu-id="92c0c-121">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="92c0c-121">DBTYPE_WSTR</span></span>|<span data-ttu-id="92c0c-122">Valor DBPROP_INIT_PROVIDERSTRING de OLE DB que se usa para adquirir un origen de datos del proveedor.</span><span class="sxs-lookup"><span data-stu-id="92c0c-122">OLE DB DBPROP_INIT_PROVIDERSTRING value used to acquire a data source from the provider.</span></span>|  
|<span data-ttu-id="92c0c-123">SVR_LOCATION</span><span class="sxs-lookup"><span data-stu-id="92c0c-123">SVR_LOCATION</span></span>|<span data-ttu-id="92c0c-124">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="92c0c-124">DBTYPE_WSTR</span></span>|<span data-ttu-id="92c0c-125">Cadena OLE DB DBPROP_INIT_LOCATION de OLE DB que se usa para adquirir un origen de datos del proveedor.</span><span class="sxs-lookup"><span data-stu-id="92c0c-125">OLE DB DBPROP_INIT_LOCATION string used to acquire a data source from the provider.</span></span>|  
  
 <span data-ttu-id="92c0c-126">El conjunto de filas está ordenado en SRV_NAME y se admite una restricción única en SRV_NAME.</span><span class="sxs-lookup"><span data-stu-id="92c0c-126">The rowset is sorted on SRV_NAME and a single restriction is supported on SRV_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92c0c-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92c0c-127">See Also</span></span>  
 [<span data-ttu-id="92c0c-128">Compatibilidad con conjuntos de filas de esquema &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="92c0c-128">Schema Rowset Support &#40;OLE DB&#41;</span></span>](schema-rowset-support-ole-db.md)  
  
  
