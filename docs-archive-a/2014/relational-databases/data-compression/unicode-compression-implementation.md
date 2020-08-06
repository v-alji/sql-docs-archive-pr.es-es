---
title: Implementación de la compresión Unicode | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Unicode data compression
- compression [SQL Server], Unicode data
ms.assetid: 44e69e60-9b35-43fe-b9c7-8cf34eaea62a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4c928062169ed7feb03f1031362530474109976a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675986"
---
# <a name="unicode-compression-implementation"></a><span data-ttu-id="49022-102">Implementación de la compresión Unicode</span><span class="sxs-lookup"><span data-stu-id="49022-102">Unicode Compression Implementation</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="49022-103">usa una implementación del algoritmo del esquema de compresión estándar para Unicode (SCSU) para comprimir los valores Unicode que están almacenados en objetos comprimidos de fila o página.</span><span class="sxs-lookup"><span data-stu-id="49022-103">uses an implementation of the Standard Compression Scheme for Unicode (SCSU) algorithm to compress Unicode values that are stored in row or page compressed objects.</span></span> <span data-ttu-id="49022-104">Para estos objetos comprimidos, la compresión Unicode es automática para columnas `nchar(n)` y `nvarchar(n)`.</span><span class="sxs-lookup"><span data-stu-id="49022-104">For these compressed objects, Unicode compression is automatic for `nchar(n)` and `nvarchar(n)` columns.</span></span> <span data-ttu-id="49022-105">[!INCLUDE[ssDE](../../includes/ssde-md.md)] almacena los datos Unicode como 2 bytes, independientemente de la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="49022-105">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] stores Unicode data as 2 bytes, regardless of locale.</span></span> <span data-ttu-id="49022-106">Esto se denomina codificación UCS-2.</span><span class="sxs-lookup"><span data-stu-id="49022-106">This is known as UCS-2 encoding.</span></span> <span data-ttu-id="49022-107">Para algunas configuraciones regionales, la implementación de la compresión SCSU en SQL Server puede ahorrar hasta el 50% de espacio de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="49022-107">For some locales, the implementation of SCSU compression in SQL Server can save up to 50 percent in storage space.</span></span>  
  
## <a name="supported-data-types"></a><span data-ttu-id="49022-108">Tipos de datos admitidos</span><span class="sxs-lookup"><span data-stu-id="49022-108">Supported Data Types</span></span>  
 <span data-ttu-id="49022-109">La compresión Unicode admite los tipos de datos `nchar(n)` y `nvarchar(n)` de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="49022-109">Unicode compression supports the fixed-length `nchar(n)` and `nvarchar(n)` data types.</span></span> <span data-ttu-id="49022-110">Los valores de datos que no están almacenados de forma consecutiva o en columnas `nvarchar(max)` no se comprimen.</span><span class="sxs-lookup"><span data-stu-id="49022-110">Data values that are stored off row or in `nvarchar(max)` columns are not compressed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49022-111">La compresión Unicode no se admite para los datos de `nvarchar(max)` aunque estén almacenados de forma consecutiva.</span><span class="sxs-lookup"><span data-stu-id="49022-111">Unicode compression is not supported for `nvarchar(max)` data even if it is stored in row.</span></span> <span data-ttu-id="49022-112">Sin embargo, este tipo de datos puede seguir beneficiándose de la compresión de página.</span><span class="sxs-lookup"><span data-stu-id="49022-112">However, this data type can still benefit from page compression.</span></span>  
  
## <a name="upgrading-from-earlier-versions-of-sql-server"></a><span data-ttu-id="49022-113">Actualizar de versiones anteriores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="49022-113">Upgrading from Earlier Versions of SQL Server</span></span>  
 <span data-ttu-id="49022-114">Cuando una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se actualiza a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], los cambios relacionados con la compresión Unicode no se llevan a cabo en ningún objeto de base de datos, tanto si está comprimido como si no.</span><span class="sxs-lookup"><span data-stu-id="49022-114">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], Unicode compression-related changes are not made to any database object, compressed or uncompressed.</span></span> <span data-ttu-id="49022-115">Una vez actualizada la base de datos, los objetos se ven afectados de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="49022-115">After the database is upgraded, objects are affected as follows:</span></span>  
  
-   <span data-ttu-id="49022-116">Si el objeto no está comprimido, no se realiza ningún cambio y sigue funcionando como lo hacía anteriormente.</span><span class="sxs-lookup"><span data-stu-id="49022-116">If the object is not compressed, no changes are made and the object continues to function as it did previously.</span></span>  
  
-   <span data-ttu-id="49022-117">Los objetos comprimidos de fila o página siguen funcionando como lo hacían anteriormente.</span><span class="sxs-lookup"><span data-stu-id="49022-117">Row- or page-compressed objects continue to function as they did previously.</span></span> <span data-ttu-id="49022-118">Los datos sin comprimir permanecen sin comprimir hasta que se actualiza su valor.</span><span class="sxs-lookup"><span data-stu-id="49022-118">Uncompressed data remains in uncompressed form until its value is updated.</span></span>  
  
-   <span data-ttu-id="49022-119">Las nuevas filas que se insertan en una tabla comprimida de fila o página se comprimen con la compresión Unicode.</span><span class="sxs-lookup"><span data-stu-id="49022-119">New rows that are inserted into a row- or page-compressed table are compressed using Unicode compression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="49022-120">Para aprovechar al máximo las ventajas de la compresión Unicode, el objeto se debe regenerar con la compresión de página o fila.</span><span class="sxs-lookup"><span data-stu-id="49022-120">To take full advantage of the benefits of Unicode compression, the object must be rebuilt with page or row compression.</span></span>  
  
## <a name="how-unicode-compression-affects-data-storage"></a><span data-ttu-id="49022-121">Cómo afecta la compresión Unicode al almacenamiento de datos</span><span class="sxs-lookup"><span data-stu-id="49022-121">How Unicode Compression Affects Data Storage</span></span>  
 <span data-ttu-id="49022-122">Cuando un índice se crea o regenera, o bien cuando un valor se cambia en una tabla que se comprimió con compresión de fila o página, el índice o el valor afectado se almacena comprimido solo si su tamaño comprimido es menor que su tamaño actual.</span><span class="sxs-lookup"><span data-stu-id="49022-122">When an index is created or rebuilt or when a value is changed in a table that was compressed with row or page compression, the affected index or value is stored compressed only if its compressed size is less than its current size.</span></span> <span data-ttu-id="49022-123">De este modo se evita que las filas de una tabla o índice aumenten de tamaño debido a la compresión Unicode.</span><span class="sxs-lookup"><span data-stu-id="49022-123">This prevents rows in a table or index from increasing in size because of Unicode compression.</span></span>  
  
 <span data-ttu-id="49022-124">El espacio de almacenamiento que la compresión ahorra depende de las características de los datos que se vayan a comprimir y la configuración regional de dichos datos.</span><span class="sxs-lookup"><span data-stu-id="49022-124">The storage space that compression saves depends on the characteristics of the data that is being compressed and the locale of the data.</span></span> <span data-ttu-id="49022-125">En la tabla siguiente se enumeran los ahorros de espacio que se pueden conseguir para diferentes configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="49022-125">The following table lists the space savings that can be achieved for several locales.</span></span>  
  
|<span data-ttu-id="49022-126">Configuración regional</span><span class="sxs-lookup"><span data-stu-id="49022-126">Locale</span></span>|<span data-ttu-id="49022-127">Porcentaje de compresión</span><span class="sxs-lookup"><span data-stu-id="49022-127">Compression percent</span></span>|  
|------------|-------------------------|  
|<span data-ttu-id="49022-128">Inglés</span><span class="sxs-lookup"><span data-stu-id="49022-128">English</span></span>|<span data-ttu-id="49022-129">50 %</span><span class="sxs-lookup"><span data-stu-id="49022-129">50%</span></span>|  
|<span data-ttu-id="49022-130">Alemán</span><span class="sxs-lookup"><span data-stu-id="49022-130">German</span></span>|<span data-ttu-id="49022-131">50 %</span><span class="sxs-lookup"><span data-stu-id="49022-131">50%</span></span>|  
|<span data-ttu-id="49022-132">Hindi</span><span class="sxs-lookup"><span data-stu-id="49022-132">Hindi</span></span>|<span data-ttu-id="49022-133">50 %</span><span class="sxs-lookup"><span data-stu-id="49022-133">50%</span></span>|  
|<span data-ttu-id="49022-134">Turco</span><span class="sxs-lookup"><span data-stu-id="49022-134">Turkish</span></span>|<span data-ttu-id="49022-135">48%</span><span class="sxs-lookup"><span data-stu-id="49022-135">48%</span></span>|  
|<span data-ttu-id="49022-136">Vietnamita</span><span class="sxs-lookup"><span data-stu-id="49022-136">Vietnamese</span></span>|<span data-ttu-id="49022-137">39 %</span><span class="sxs-lookup"><span data-stu-id="49022-137">39%</span></span>|  
|<span data-ttu-id="49022-138">Japonés</span><span class="sxs-lookup"><span data-stu-id="49022-138">Japanese</span></span>|<span data-ttu-id="49022-139">15 %</span><span class="sxs-lookup"><span data-stu-id="49022-139">15%</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49022-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49022-140">See Also</span></span>  
 <span data-ttu-id="49022-141">[Comprimir datos](data-compression.md) </span><span class="sxs-lookup"><span data-stu-id="49022-141">[Data Compression](data-compression.md) </span></span>  
 <span data-ttu-id="49022-142">[sp_estimate_data_compression_savings &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="49022-142">[sp_estimate_data_compression_savings &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-estimate-data-compression-savings-transact-sql) </span></span>  
 <span data-ttu-id="49022-143">[Implementación de la compresión de página](page-compression-implementation.md) </span><span class="sxs-lookup"><span data-stu-id="49022-143">[Page Compression Implementation](page-compression-implementation.md) </span></span>  
 [<span data-ttu-id="49022-144">sys.dm_db_persisted_sku_features &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="49022-144">sys.dm_db_persisted_sku_features &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-persisted-sku-features-transact-sql)  
  
  
