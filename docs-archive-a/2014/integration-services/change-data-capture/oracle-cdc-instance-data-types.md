---
title: Tipos de datos de la instancia Oracle CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: eec13d8d-c15a-4542-bfc4-da66b1a6bfe0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71d4ce02db89c1bfd11fe9a3a3535fc92fbc49fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744255"
---
# <a name="oracle-cdc-instance-data-types"></a><span data-ttu-id="ace46-102">Tipos de datos de la instancia CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="ace46-102">Oracle CDC Instance Data Types</span></span>
  <span data-ttu-id="ace46-103">La instancia CDC de Oracle admite la mayoría de los tipos de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="ace46-103">The Oracle CDC Instance supports most Oracle data types.</span></span> <span data-ttu-id="ace46-104">En las secciones siguientes se describen los tipos de datos admitidos y los tipos de datos no admitidos.</span><span class="sxs-lookup"><span data-stu-id="ace46-104">The following sections describe the supported data types and the non-supported data types.</span></span>  
  
## <a name="supported-data-types"></a><span data-ttu-id="ace46-105">Tipos de datos admitidos</span><span class="sxs-lookup"><span data-stu-id="ace46-105">Supported Data Types</span></span>  
 <span data-ttu-id="ace46-106">En la tabla siguiente se describen los tipos de datos de Oracle que se pueden capturar y su asignación predeterminada a tipos de datos de SQL Server en las tablas de cambios.</span><span class="sxs-lookup"><span data-stu-id="ace46-106">The following table describes the Oracle data types that can be captured and their default mapping to SQL Server data types in the change tables.</span></span> <span data-ttu-id="ace46-107">Al agregar una instancia de captura para una tabla de Oracle de origen, puede invalidar algunas de estas asignaciones.</span><span class="sxs-lookup"><span data-stu-id="ace46-107">When adding a capture instance for a source Oracle table, you can override some of these mappings.</span></span>  
  
|<span data-ttu-id="ace46-108">Tipo de datos de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="ace46-108">Oracle Database Data Type</span></span>|<span data-ttu-id="ace46-109">Tipo de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ace46-109">SQL Server Data Type</span></span>|  
|-------------------------------|--------------------------|  
|<span data-ttu-id="ace46-110">BINARY_FLOAT</span><span class="sxs-lookup"><span data-stu-id="ace46-110">BINARY_FLOAT</span></span>|<span data-ttu-id="ace46-111">real</span><span class="sxs-lookup"><span data-stu-id="ace46-111">REAL</span></span>|  
|<span data-ttu-id="ace46-112">BINARY_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="ace46-112">BINARY_DOUBLE</span></span>|<span data-ttu-id="ace46-113">FLOAT</span><span class="sxs-lookup"><span data-stu-id="ace46-113">FLOAT</span></span>|  
|<span data-ttu-id="ace46-114">CHAR</span><span class="sxs-lookup"><span data-stu-id="ace46-114">CHAR</span></span>|<span data-ttu-id="ace46-115">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="ace46-115">NVARCHAR</span></span>|  
|<span data-ttu-id="ace46-116">DATE</span><span class="sxs-lookup"><span data-stu-id="ace46-116">DATE</span></span>|<span data-ttu-id="ace46-117">DATETIME</span><span class="sxs-lookup"><span data-stu-id="ace46-117">DATETIME</span></span>|  
|<span data-ttu-id="ace46-118">FLOAT</span><span class="sxs-lookup"><span data-stu-id="ace46-118">FLOAT</span></span>|<span data-ttu-id="ace46-119">FLOAT</span><span class="sxs-lookup"><span data-stu-id="ace46-119">FLOAT</span></span>|  
|<span data-ttu-id="ace46-120">INT</span><span class="sxs-lookup"><span data-stu-id="ace46-120">INT</span></span>|<span data-ttu-id="ace46-121">NUMERIC (38)</span><span class="sxs-lookup"><span data-stu-id="ace46-121">NUMERIC (38)</span></span>|  
|<span data-ttu-id="ace46-122">INTERVAL</span><span class="sxs-lookup"><span data-stu-id="ace46-122">INTERVAL</span></span>|<span data-ttu-id="ace46-123">DATETIME</span><span class="sxs-lookup"><span data-stu-id="ace46-123">DATETIME</span></span>|  
|<span data-ttu-id="ace46-124">NCHAR</span><span class="sxs-lookup"><span data-stu-id="ace46-124">NCHAR</span></span>|<span data-ttu-id="ace46-125">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="ace46-125">NVARCHAR</span></span>|  
|<span data-ttu-id="ace46-126">NUMBER</span><span class="sxs-lookup"><span data-stu-id="ace46-126">NUMBER</span></span>|<span data-ttu-id="ace46-127">FLOAT</span><span class="sxs-lookup"><span data-stu-id="ace46-127">FLOAT</span></span>|  
|<span data-ttu-id="ace46-128">NAVARCHAR2</span><span class="sxs-lookup"><span data-stu-id="ace46-128">NAVARCHAR2</span></span>|<span data-ttu-id="ace46-129">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="ace46-129">NVARCHAR</span></span>|  
|<span data-ttu-id="ace46-130">RAW</span><span class="sxs-lookup"><span data-stu-id="ace46-130">RAW</span></span>|<span data-ttu-id="ace46-131">VARBINARY</span><span class="sxs-lookup"><span data-stu-id="ace46-131">VARBINARY</span></span>|  
|<span data-ttu-id="ace46-132">real</span><span class="sxs-lookup"><span data-stu-id="ace46-132">REAL</span></span>|<span data-ttu-id="ace46-133">FLOAT</span><span class="sxs-lookup"><span data-stu-id="ace46-133">FLOAT</span></span>|  
|<span data-ttu-id="ace46-134">timestamp</span><span class="sxs-lookup"><span data-stu-id="ace46-134">TIMESTAMP</span></span>|<span data-ttu-id="ace46-135">DATETIME2</span><span class="sxs-lookup"><span data-stu-id="ace46-135">DATETIME2</span></span>|  
|<span data-ttu-id="ace46-136">TIMESTAMP WITH TIME ZONE</span><span class="sxs-lookup"><span data-stu-id="ace46-136">TIMESTAMP WITH TIME ZONE</span></span>|<span data-ttu-id="ace46-137">VARCHAR (37)</span><span class="sxs-lookup"><span data-stu-id="ace46-137">VARCHAR (37)</span></span>|  
|<span data-ttu-id="ace46-138">TIMESTAMP WITH LOCAL TIME ZONE</span><span class="sxs-lookup"><span data-stu-id="ace46-138">TIMESTAMP WITH LOCAL TIME ZONE</span></span>|<span data-ttu-id="ace46-139">VARCHAR (37)</span><span class="sxs-lookup"><span data-stu-id="ace46-139">VARCHAR (37)</span></span>|  
|<span data-ttu-id="ace46-140">VARCHAR2</span><span class="sxs-lookup"><span data-stu-id="ace46-140">VARCHAR2</span></span>|<span data-ttu-id="ace46-141">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="ace46-141">VARCHAR</span></span>|  
|<span data-ttu-id="ace46-142">XMLTYPE</span><span class="sxs-lookup"><span data-stu-id="ace46-142">XMLTYPE</span></span>|<span data-ttu-id="ace46-143">NVARCHAR (MAX)</span><span class="sxs-lookup"><span data-stu-id="ace46-143">NVARCHAR (MAX)</span></span>|  
  
## <a name="non-supported-data-types"></a><span data-ttu-id="ace46-144">Tipos de datos no admitidos</span><span class="sxs-lookup"><span data-stu-id="ace46-144">Non-Supported Data Types</span></span>  
 <span data-ttu-id="ace46-145">No se pueden capturar tablas de Oracle de origen con columnas que tengan los tipos de datos de Oracle siguientes.</span><span class="sxs-lookup"><span data-stu-id="ace46-145">Source Oracle tables with columns of the following Oracle data types cannot be captured.</span></span> <span data-ttu-id="ace46-146">Las columnas capturadas con estos tipos de datos se mostrarán como NULL; sin embargo, un cambio en su valor se indica en la máscara de cambio de las tablas capturadas.</span><span class="sxs-lookup"><span data-stu-id="ace46-146">Captured columns with these data types will show as null; however, a change in their value is indicated in the change mask of the captured tables.</span></span>  
  
-   <span data-ttu-id="ace46-147">LONG</span><span class="sxs-lookup"><span data-stu-id="ace46-147">LONG</span></span>  
  
-   <span data-ttu-id="ace46-148">XMLTYPE</span><span class="sxs-lookup"><span data-stu-id="ace46-148">XMLTYPE</span></span>  
  
-   <span data-ttu-id="ace46-149">BLOB</span><span class="sxs-lookup"><span data-stu-id="ace46-149">BLOB</span></span>  
  
-   <span data-ttu-id="ace46-150">CLOB</span><span class="sxs-lookup"><span data-stu-id="ace46-150">CLOB</span></span>  
  
 <span data-ttu-id="ace46-151">No se pueden capturar tablas de Oracle de origen con columnas que tengan los tipos de datos de Oracle siguientes.</span><span class="sxs-lookup"><span data-stu-id="ace46-151">Source Oracle tables with columns of the following Oracle data types cannot be captured.</span></span>  
  
-   <span data-ttu-id="ace46-152">BFILE</span><span class="sxs-lookup"><span data-stu-id="ace46-152">BFILE</span></span>  
  
-   <span data-ttu-id="ace46-153">ROWID</span><span class="sxs-lookup"><span data-stu-id="ace46-153">ROWID</span></span>  
  
-   <span data-ttu-id="ace46-154">REF</span><span class="sxs-lookup"><span data-stu-id="ace46-154">REF</span></span>  
  
-   <span data-ttu-id="ace46-155">UROWID</span><span class="sxs-lookup"><span data-stu-id="ace46-155">UROWID</span></span>  
  
-   <span data-ttu-id="ace46-156">Tabla anidada</span><span class="sxs-lookup"><span data-stu-id="ace46-156">Nested Table</span></span>  
  
 <span data-ttu-id="ace46-157">Si los tipos de datos siguientes están presentes en una tabla, impedirán que LogMiner obtenga datos de cualquier columna de la tabla:</span><span class="sxs-lookup"><span data-stu-id="ace46-157">If the following data types are present in a table they will prevent the LogMinder from getting any data for any column of the table:</span></span>  
  
-   <span data-ttu-id="ace46-158">Tipos de datos definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="ace46-158">User-defined data types</span></span>  
  
-   <span data-ttu-id="ace46-159">VARRAY</span><span class="sxs-lookup"><span data-stu-id="ace46-159">VARRAY</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace46-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ace46-160">See Also</span></span>  
 <span data-ttu-id="ace46-161">[Diseñador de captura de datos modificados para Oracle de Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span><span class="sxs-lookup"><span data-stu-id="ace46-161">[Change Data Capture Designer for Oracle by Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span></span>  
 [<span data-ttu-id="ace46-162">La instancia CDC de Oracle</span><span class="sxs-lookup"><span data-stu-id="ace46-162">The Oracle CDC Instance</span></span>](the-oracle-cdc-instance.md)  
  
  
