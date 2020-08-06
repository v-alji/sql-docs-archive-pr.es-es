---
title: Uso de índices de almacén de columnas no agrupados | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
ms.assetid: 4c341fb8-7cb1-4cab-921b-e80b751d6c19
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c876eb6fdd466349ac369dcff8e292bc0839c669
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745959"
---
# <a name="using-nonclustered-columnstore-indexes"></a><span data-ttu-id="5b29e-102">Usar índices no clúster de almacén de columnas</span><span class="sxs-lookup"><span data-stu-id="5b29e-102">Using Nonclustered Columnstore Indexes</span></span>
  <span data-ttu-id="5b29e-103">Describe las tareas clave para utilizar un índice no clúster de almacén de columnas en una tabla de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b29e-103">Describes key tasks for using a nonclustered columnstore index on a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table.</span></span>

 <span data-ttu-id="5b29e-104">Para obtener información general acerca de los índices de almacén de columnas, vea [Columnstore Indexes Described](../relational-databases/indexes/columnstore-indexes-described.md).</span><span class="sxs-lookup"><span data-stu-id="5b29e-104">For an overview of columnstore indexes, see [Columnstore Indexes Described](../relational-databases/indexes/columnstore-indexes-described.md).</span></span>

 <span data-ttu-id="5b29e-105">Para obtener información acerca de los índices clúster de almacén de columnas, vea [Using Clustered Columnstore Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="5b29e-105">For information about clustered columnstore indexes, see [Using Clustered Columnstore Indexes](../relational-databases/indexes/indexes.md).</span></span>

## <a name="contents"></a><span data-ttu-id="5b29e-106">Contenido</span><span class="sxs-lookup"><span data-stu-id="5b29e-106">Contents</span></span>

-   [<span data-ttu-id="5b29e-107">Crear un índice no clúster de almacén de columnas</span><span class="sxs-lookup"><span data-stu-id="5b29e-107">Create a Nonclustered Columnstore Index</span></span>](../../2014/database-engine/using-nonclustered-columnstore-indexes.md#load)

-   [<span data-ttu-id="5b29e-108">Cambiar los datos de un índice de almacén de columnas no agrupado</span><span class="sxs-lookup"><span data-stu-id="5b29e-108">Change the Data in a Nonclustered Columnstore Index</span></span>](../../2014/database-engine/using-nonclustered-columnstore-indexes.md#change)

##  <a name="create-a-nonclustered-columnstore-index"></a><a name="load"></a><span data-ttu-id="5b29e-109">Crear un índice de almacén de columnas no agrupado</span><span class="sxs-lookup"><span data-stu-id="5b29e-109">Create a Nonclustered Columnstore Index</span></span>
 <span data-ttu-id="5b29e-110">Para cargar datos en un índice de almacén de columnas no agrupado, cargue primero los datos en una tabla almacén tradicional almacenada como un montón o un índice clúster y, a continuación, use [crear índice de almacén de columnas &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql) para crear un índice de almacén de columnas.</span><span class="sxs-lookup"><span data-stu-id="5b29e-110">To load data into a nonclustered columnstore index, first load data into a traditional rowstore table stored as a heap or clustered index, and then use [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql) to create a columnstore index.</span></span>

 <span data-ttu-id="5b29e-111">![Cargar datos en un índice de almacén de columnas](../../2014/database-engine/media/sql-server-pdw-columnstore-loadprocess-nonclustered.gif "Cargar datos en un índice de almacén de columnas")</span><span class="sxs-lookup"><span data-stu-id="5b29e-111">![Loading data into a columnstore index](../../2014/database-engine/media/sql-server-pdw-columnstore-loadprocess-nonclustered.gif "Loading data into a columnstore index")</span></span>

##  <a name="change-the-data-in-a-nonclustered-columnstore-index"></a><a name="change"></a><span data-ttu-id="5b29e-112">Cambiar los datos de un índice de almacén de columnas no agrupado</span><span class="sxs-lookup"><span data-stu-id="5b29e-112">Change the Data in a Nonclustered Columnstore Index</span></span>
 <span data-ttu-id="5b29e-113">Una vez creado un índice no clúster de almacén de columnas en una tabla, no puede modificar directamente los datos de esa tabla.</span><span class="sxs-lookup"><span data-stu-id="5b29e-113">Once you create a nonclustered columnstore index on a table, you cannot directly modify the data in that table.</span></span> <span data-ttu-id="5b29e-114">Una consulta con INSERT, UPDATE, DELETE o MERGE generará un error y devolverá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="5b29e-114">A query with INSERT, UPDATE, DELETE, or MERGE will fail and return an error message.</span></span> <span data-ttu-id="5b29e-115">Para agregar o modificar los datos de la tabla, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b29e-115">To add or modify the data in the table, you can do one of the following:</span></span>

-   <span data-ttu-id="5b29e-116">Deshabilite el índice de almacén de columnas.</span><span class="sxs-lookup"><span data-stu-id="5b29e-116">Disable the columnstore index.</span></span> <span data-ttu-id="5b29e-117">Después puede actualizar los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="5b29e-117">You can then update the data in the table.</span></span> <span data-ttu-id="5b29e-118">Si deshabilita el índice de almacén de columnas, puede regenerar el índice de almacén de columnas cuando termine de actualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="5b29e-118">If you disable the columnstore index, you can rebuild the columnstore index when you finish updating the data.</span></span> <span data-ttu-id="5b29e-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5b29e-119">For example:</span></span>

    ```
    ALTER INDEX mycolumnstoreindex ON mytable DISABLE;
    -- update mytable --
    ALTER INDEX mycolumnstoreindex on mytable REBUILD
    ```

-   <span data-ttu-id="5b29e-120">Quite el índice de almacén de columnas, actualice la tabla y, a continuación, vuelva a crear el índice de almacén de columnas con crear índice de almacén de columnas.</span><span class="sxs-lookup"><span data-stu-id="5b29e-120">Drop the columnstore index, update the table, and then re-create the columnstore index with CREATE COLUMNSTORE INDEX.</span></span> <span data-ttu-id="5b29e-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5b29e-121">For example:</span></span>

    ```
    DROP INDEX mycolumnstoreindex ON mytable
    -- update mytable --
    CREATE NONCLUSTERED COLUMNSTORE INDEX mycolumnstoreindex ON mytable;

    ```

-   <span data-ttu-id="5b29e-122">Cargar datos en una tabla de ensayo que no tenga un índice de almacén de columnas.</span><span class="sxs-lookup"><span data-stu-id="5b29e-122">Load data into a staging table that does not have a columnstore index.</span></span> <span data-ttu-id="5b29e-123">Genere un índice de almacén de columnas en la tabla de ensayo.</span><span class="sxs-lookup"><span data-stu-id="5b29e-123">Build a columnstore index on the staging table.</span></span> <span data-ttu-id="5b29e-124">Cambie la tabla de ensayo a una partición vacía de la tabla principal.</span><span class="sxs-lookup"><span data-stu-id="5b29e-124">Switch the staging table into an empty partition of the main table.</span></span>

-   <span data-ttu-id="5b29e-125">Cambiar una partición de la tabla con el índice de almacén de columnas a una tabla de ensayo vacía.</span><span class="sxs-lookup"><span data-stu-id="5b29e-125">Switch a partition from the table with the columnstore index into an empty staging table.</span></span> <span data-ttu-id="5b29e-126">Si hay un índice de almacén de columnas en la tabla de ensayo, deshabilítelo.</span><span class="sxs-lookup"><span data-stu-id="5b29e-126">If there is a columnstore index on the staging table, disable the columnstore index.</span></span> <span data-ttu-id="5b29e-127">Realice las actualizaciones que desee.</span><span class="sxs-lookup"><span data-stu-id="5b29e-127">Perform any updates.</span></span> <span data-ttu-id="5b29e-128">Genere (o regenere) el índice de almacén de columnas.</span><span class="sxs-lookup"><span data-stu-id="5b29e-128">Build (or rebuild) the columnstore index.</span></span> <span data-ttu-id="5b29e-129">Vuelva a cambiar la tabla de ensayo a la partición (ahora vacía) de la tabla principal.</span><span class="sxs-lookup"><span data-stu-id="5b29e-129">Switch the staging table back into the (now empty) partition of the main table.</span></span>




