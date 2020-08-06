---
title: Propiedades del catálogo de texto completo (página general) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftcatalogproperties.general.f1
ms.assetid: d1f66762-2d40-4f24-b635-a417d22ee79a
author: rothja
ms.author: jroth
ms.openlocfilehash: 483601c53db6c8a806ea8c53f771fd4f2608293b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749430"
---
# <a name="full-text-catalog-properties-general-page"></a><span data-ttu-id="a570b-102">Propiedades del catálogo de texto completo (página General)</span><span class="sxs-lookup"><span data-stu-id="a570b-102">Full-Text Catalog Properties (General Page)</span></span>
  <span data-ttu-id="a570b-103">En esta sección se muestran las opciones y funciones disponibles en la página **General** del cuadro de diálogo **Propiedades del catálogo de texto completo** .</span><span class="sxs-lookup"><span data-stu-id="a570b-103">This section shows the options and functions available on the **General** page of the **Full-Text Catalog Properties** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a570b-104">En las bases de datos de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] , un catálogo de texto completo es un concepto lógico que hace referencia a un grupo de índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a570b-104">For [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] databases, a full-text catalog is a logical concept that refers to a group of full-text indexes.</span></span> <span data-ttu-id="a570b-105">Un catálogo de texto completo es un objeto virtual y no pertenece a ningún grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="a570b-105">The full-text catalog is a virtual object that does not belong to any filegroup.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a570b-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="a570b-106">Options</span></span>  
  
### <a name="properties"></a><span data-ttu-id="a570b-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a570b-107">Properties</span></span>  
 <span data-ttu-id="a570b-108">**Catálogo predeterminado**</span><span class="sxs-lookup"><span data-stu-id="a570b-108">**Default Catalog**</span></span>  
 <span data-ttu-id="a570b-109">Muestra si el catálogo es el predeterminado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a570b-109">Displays whether the catalog is the default catalog for the database.</span></span>  
  
 <span data-ttu-id="a570b-110">**Estado del rellenado**</span><span class="sxs-lookup"><span data-stu-id="a570b-110">**Population Status**</span></span>  
 <span data-ttu-id="a570b-111">Indica el estado del catálogo.</span><span class="sxs-lookup"><span data-stu-id="a570b-111">Indicates the status of the catalog.</span></span> <span data-ttu-id="a570b-112">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="a570b-112">Possible values are:</span></span>  
  
-   <span data-ttu-id="a570b-113">**Inactivo**</span><span class="sxs-lookup"><span data-stu-id="a570b-113">**Idle**</span></span>  
  
-   <span data-ttu-id="a570b-114">**Rastreo en curso**</span><span class="sxs-lookup"><span data-stu-id="a570b-114">**Crawl in Progress**</span></span>  
  
-   <span data-ttu-id="a570b-115">**En pausa**</span><span class="sxs-lookup"><span data-stu-id="a570b-115">**Paused**</span></span>  
  
-   <span data-ttu-id="a570b-116">**Limitado**</span><span class="sxs-lookup"><span data-stu-id="a570b-116">**Throttled**</span></span>  
  
-   <span data-ttu-id="a570b-117">**Recupera**</span><span class="sxs-lookup"><span data-stu-id="a570b-117">**Recovering**</span></span>  
  
-   <span data-ttu-id="a570b-118">**Apagar**</span><span class="sxs-lookup"><span data-stu-id="a570b-118">**Shutdown**</span></span>  
  
-   <span data-ttu-id="a570b-119">**Rellenado incremental en curso**</span><span class="sxs-lookup"><span data-stu-id="a570b-119">**Incremental population in progress**</span></span>  
  
-   <span data-ttu-id="a570b-120">**Generando índice**</span><span class="sxs-lookup"><span data-stu-id="a570b-120">**Building index**</span></span>  
  
-   <span data-ttu-id="a570b-121">**El disco está lleno en pausa**</span><span class="sxs-lookup"><span data-stu-id="a570b-121">**Disk is full-Paused**</span></span>  
  
-   <span data-ttu-id="a570b-122">**Seguimiento de cambios**</span><span class="sxs-lookup"><span data-stu-id="a570b-122">**Change tracking**</span></span>  
  
 <span data-ttu-id="a570b-123">**Número de elementos**</span><span class="sxs-lookup"><span data-stu-id="a570b-123">**Item Count**</span></span>  
 <span data-ttu-id="a570b-124">Muestra el número de elementos de texto completo del catálogo.</span><span class="sxs-lookup"><span data-stu-id="a570b-124">Displays the number of full-text items in the catalog.</span></span>  
  
 <span data-ttu-id="a570b-125">**Tamaño del catálogo**</span><span class="sxs-lookup"><span data-stu-id="a570b-125">**Catalog Size**</span></span>  
 <span data-ttu-id="a570b-126">Muestra el tamaño del catálogo de texto completo en megabytes.</span><span class="sxs-lookup"><span data-stu-id="a570b-126">Displays the size, in megabytes, of the full-text catalog.</span></span>  
  
 <span data-ttu-id="a570b-127">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="a570b-127">**Name**</span></span>  
 <span data-ttu-id="a570b-128">Nombre del catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a570b-128">The name of the full-text catalog.</span></span>  
  
 <span data-ttu-id="a570b-129">**Distinguir acentos**</span><span class="sxs-lookup"><span data-stu-id="a570b-129">**Accent Sensitive**</span></span>  
 <span data-ttu-id="a570b-130">Permite ver o modificar si el catálogo es sensible a las marcas diacríticas, como una tilde ( **~** ), un signo de acento agudo (**'**) o umlaut (**̈**).</span><span class="sxs-lookup"><span data-stu-id="a570b-130">View or modify whether the catalog is sensitive to diacritical marks, such as a tilde (**~**), acute accent mark (**´**), or umlaut (**¨**).</span></span> <span data-ttu-id="a570b-131">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="a570b-131">Valid values are:</span></span>  
  
-   <span data-ttu-id="a570b-132">**No**</span><span class="sxs-lookup"><span data-stu-id="a570b-132">**No**</span></span>  
  
-   <span data-ttu-id="a570b-133">**Sí**</span><span class="sxs-lookup"><span data-stu-id="a570b-133">**Yes**</span></span>  
  
-   <span data-ttu-id="a570b-134">Para obtener información sobre las marcas diacríticas, vea [diacríticos](https://www.merriam-webster.com/dictionary/diacritic) en el diccionario Merriam-Webster.</span><span class="sxs-lookup"><span data-stu-id="a570b-134">For information about diacritical marks, see [Diacritic](https://www.merriam-webster.com/dictionary/diacritic) in the Merriam-Webster dictionary.</span></span>  
  
 <span data-ttu-id="a570b-135">**Fecha del último rellenado**</span><span class="sxs-lookup"><span data-stu-id="a570b-135">**Last Population Date**</span></span>  
 <span data-ttu-id="a570b-136">Muestra la fecha de la última vez que se rellenó el catálogo.</span><span class="sxs-lookup"><span data-stu-id="a570b-136">Displays the date the catalog was last populated.</span></span>  
  
 <span data-ttu-id="a570b-137">**Propietario**</span><span class="sxs-lookup"><span data-stu-id="a570b-137">**Owner**</span></span>  
 <span data-ttu-id="a570b-138">Propietario del catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a570b-138">The owner of the full-text catalog.</span></span>  
  
 <span data-ttu-id="a570b-139">**Recuento de claves únicas**</span><span class="sxs-lookup"><span data-stu-id="a570b-139">**Unique Key Count**</span></span>  
 <span data-ttu-id="a570b-140">Número de palabras únicas que componen el índice de texto completo del catálogo.</span><span class="sxs-lookup"><span data-stu-id="a570b-140">The number of unique words that make up the full-text index for the catalog.</span></span>  
  
### <a name="catalog-action"></a><span data-ttu-id="a570b-141">Acción del catálogo</span><span class="sxs-lookup"><span data-stu-id="a570b-141">Catalog Action</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a570b-142">**None**</span><span class="sxs-lookup"><span data-stu-id="a570b-142">**None**</span></span>|<span data-ttu-id="a570b-143">No realiza las operaciones **Optimizar catálogo**, **Volver a generar el catálogo**ni **Volver a llenar el catálogo** .</span><span class="sxs-lookup"><span data-stu-id="a570b-143">Does not perform **Optimize catalog**, **Rebuild catalog**, or **Repopulate catalog** operations.</span></span>|  
|<span data-ttu-id="a570b-144">**Optimizar catálogo**</span><span class="sxs-lookup"><span data-stu-id="a570b-144">**Optimize catalog**</span></span>|<span data-ttu-id="a570b-145">Optimiza el uso de espacio del catálogo y mejora el rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="a570b-145">Optimizes the space utilization of the catalog and improves query performance.</span></span> <span data-ttu-id="a570b-146">También mejora la precisión de la clasificación de los aciertos de los resultados de las búsquedas.</span><span class="sxs-lookup"><span data-stu-id="a570b-146">It also improves the accuracy of relevance ranking of search results.</span></span><br /><br /> <span data-ttu-id="a570b-147">Esta acción ejecuta ALTER FULLTEXT CATALOG *catalog_name* REORGANIZE.</span><span class="sxs-lookup"><span data-stu-id="a570b-147">This action executes ALTER FULLTEXT CATALOG *catalog_name* REORGANIZE.</span></span>|  
|<span data-ttu-id="a570b-148">**Volver a generar el catálogo**</span><span class="sxs-lookup"><span data-stu-id="a570b-148">**Rebuild catalog**</span></span>|<span data-ttu-id="a570b-149">Elimina el catálogo de texto completo y lo genera de nuevo.</span><span class="sxs-lookup"><span data-stu-id="a570b-149">Deletes and rebuilds the full-text catalog.</span></span> <span data-ttu-id="a570b-150">Esta operación debe realizarse si se modifica una propiedad básica del catálogo, como la distinción de acentos.</span><span class="sxs-lookup"><span data-stu-id="a570b-150">This operation must be performed if a fundamental catalog property is changed, such as accent sensitivity.</span></span><br /><br /> <span data-ttu-id="a570b-151">Para que el catálogo se genere correctamente, el grupo de archivos en el que reside el catálogo de texto completo debe estar en línea o tener el acceso de lectura y escritura activado.</span><span class="sxs-lookup"><span data-stu-id="a570b-151">For the rebuild to succeed, the filegroup the full-text catalog resides in must be online or read-writeable.</span></span> <span data-ttu-id="a570b-152">Después de la regeneración, se volverá a llenar el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a570b-152">After the rebuild, the full-text index will be repopulated.</span></span><br /><br /> <span data-ttu-id="a570b-153">Esta acción ejecuta ALTER FULLTEXT CATALOG *catalog_name* REBUILD.</span><span class="sxs-lookup"><span data-stu-id="a570b-153">This action executes ALTER FULLTEXT CATALOG *catalog_name* REBUILD.</span></span>|  
|<span data-ttu-id="a570b-154">**Volver a llenar el catálogo**</span><span class="sxs-lookup"><span data-stu-id="a570b-154">**Repopulate catalog**</span></span>|<span data-ttu-id="a570b-155">Actualiza el catálogo con los cambios recientes realizados en los datos.</span><span class="sxs-lookup"><span data-stu-id="a570b-155">Updates the catalog with recent changes to the data.</span></span> <span data-ttu-id="a570b-156">Para esta opción, el catálogo debe estar inactivo.</span><span class="sxs-lookup"><span data-stu-id="a570b-156">This option does require catalog downtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a570b-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a570b-157">See Also</span></span>  
 [<span data-ttu-id="a570b-158">Rellenar índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="a570b-158">Populate Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
  
