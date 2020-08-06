---
title: Comparar opciones para almacenar objetos Blob (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
ms.assetid: 6038697b-36a9-49e8-a02a-2ad9e2e60e5a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c7f0d15950a8663852c84c4edbb8177e918a8895
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676017"
---
# <a name="compare-options-for-storing-blobs-sql-server"></a><span data-ttu-id="60047-102">Comparar opciones para almacenar objetos Blob (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60047-102">Compare Options for Storing Blobs (SQL Server)</span></span>
  <span data-ttu-id="60047-103">Explica y compara las opciones que están disponibles para almacenar archivos y documentos en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60047-103">Discusses and compares the options that are available for storing files and documents in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="storing-files-in-the-database---benefits-and-expectations"></a><a name="Expectations"></a> <span data-ttu-id="60047-104">Almacenamiento de archivos en la base de datos - Ventajas y expectativas</span><span class="sxs-lookup"><span data-stu-id="60047-104">Storing Files in the Database - Benefits and Expectations</span></span>  
 <span data-ttu-id="60047-105">Un porcentaje alto de los datos empresariales no se estructuran por naturaleza y se suelen almacenar como archivos y documentos en los sistemas de archivos.</span><span class="sxs-lookup"><span data-stu-id="60047-105">A large percentage of enterprise data is unstructured in nature, and is typically stored as files and documents in file systems.</span></span> <span data-ttu-id="60047-106">Las aplicaciones que tienen acceso a los archivos a través de las API de Windows generan, administran y consumen la mayor parte de los datos.</span><span class="sxs-lookup"><span data-stu-id="60047-106">Most of this data is produced, managed and consumed by applications that access the files through Windows APIs.</span></span> <span data-ttu-id="60047-107">Las empresas suelen mantener estos datos en el sistema de archivos, mientras que almacenan los metadatos relacionados de los archivos en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="60047-107">Enterprises typically keep this data in the file system, while storing the related metadata for the files in a relational database.</span></span>  
  
 <span data-ttu-id="60047-108">Integrar los datos no estructurados en la base de datos relacional proporciona beneficios significativos.</span><span class="sxs-lookup"><span data-stu-id="60047-108">Integrating unstructured data into the relational database provides significant benefits.</span></span> <span data-ttu-id="60047-109">Entre estos beneficios, se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="60047-109">These benefits include the following:</span></span>  
  
-   <span data-ttu-id="60047-110">Capacidades de almacenamiento integrado y administración de datos como la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="60047-110">Integrated storage and data management capabilities such as backup.</span></span>  
  
-   <span data-ttu-id="60047-111">Servicios integrados como la búsqueda de texto completo y la búsqueda semántica en datos y metadatos.</span><span class="sxs-lookup"><span data-stu-id="60047-111">Integrated services such as full-text search and semantic search over data and metadata.</span></span>  
  
-   <span data-ttu-id="60047-112">Facilidad de administración y administración de directivas en datos no estructurados.</span><span class="sxs-lookup"><span data-stu-id="60047-112">Ease of administration and policy management over the unstructured data.</span></span>  
  
 <span data-ttu-id="60047-113">En su mayor parte, sin embargo, no ha sido cómodo almacenar los datos no estructurados en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="60047-113">For the most part, however, it has not been convenient to store unstructured data in a relational database.</span></span> <span data-ttu-id="60047-114">Hasta ahora no ha sido posible ejecutar sobre sistemas relacionales las aplicaciones existentes basadas Windows.</span><span class="sxs-lookup"><span data-stu-id="60047-114">It has not previously been possible to run existing Windows-based applications on top of relational systems.</span></span> <span data-ttu-id="60047-115">No es práctico volver a escribir aplicaciones establecidas (como Microsoft Word o Adobe Reader) para que se ejecuten en las API de bases de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="60047-115">It is not practical to rewrite established applications (such as Microsoft Word or Adobe Reader) to run on top relational database APIs.</span></span> <span data-ttu-id="60047-116">Estas aplicaciones esperan simplemente que se acceda a los datos a través de las API de Windows.</span><span class="sxs-lookup"><span data-stu-id="60047-116">These applications simply expect the data to be accessible through Windows APIs.</span></span> <span data-ttu-id="60047-117">Es decir, las expectativas incluyen:</span><span class="sxs-lookup"><span data-stu-id="60047-117">In other words, the expectations include the following:</span></span>  
  
-   <span data-ttu-id="60047-118">Las aplicaciones Windows no tienen en cuenta las transacciones de la base de datos y no las necesitan.</span><span class="sxs-lookup"><span data-stu-id="60047-118">Windows applications are not aware of database transactions and do not require them.</span></span>  
  
-   <span data-ttu-id="60047-119">Las aplicaciones Windows requieren compatibilidad con las API del sistema de archivos para los datos de archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="60047-119">Windows applications require compatibility with file system APIs for file and directory data.</span></span>  
  
##  <a name="filestream"></a><a name="Filestream"></a> <span data-ttu-id="60047-120">FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="60047-120">FILESTREAM</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="60047-121">ya incluye la característica FILESTREAM, que proporciona almacenamiento, administración y transmisión de datos eficaces de los datos no estructurados almacenados como archivos en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="60047-121">already has the FILESTREAM feature, which provides efficient storage, management and streaming of unstructured data stored as files on the file system.</span></span> <span data-ttu-id="60047-122">Sin embargo, una solución FILESTREAM requiere la programación personalizada y no satisface el requisito de compatibilidad completa de las aplicaciones Windows descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="60047-122">However, a FILESTREAM solution requires custom programming, and does not satisfy the requirement for full Windows application compatibility described above.</span></span>  
  
##  <a name="filetables"></a><a name="FileTables"></a> <span data-ttu-id="60047-123">FileTables</span><span class="sxs-lookup"><span data-stu-id="60047-123">FileTables</span></span>  
 <span data-ttu-id="60047-124">La característica FileTable se basa en las capacidades existentes de FILESTREAM para habilitar que los clientes de empresa almacenen los datos de archivos no estructurados y las jerarquías de directorio en una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], abordando los requisitos de acceso no transaccional y la compatibilidad de las aplicaciones Windows con datos basados en archivos.</span><span class="sxs-lookup"><span data-stu-id="60047-124">The FileTable feature builds on top of existing FILESTREAM capabilities to enable enterprise customers to store unstructured file data and directory hierarchies in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, by addressing the requirements for non-transactional access and Windows application compatibility for file-based data.</span></span>  
  
##  <a name="comparing-filestream-and-filetable"></a><a name="CompareFileTable"></a> <span data-ttu-id="60047-125">Comparar FILESTREAM y FileTable</span><span class="sxs-lookup"><span data-stu-id="60047-125">Comparing FILESTREAM and FileTable</span></span>  
  
|<span data-ttu-id="60047-126">Característica</span><span class="sxs-lookup"><span data-stu-id="60047-126">Feature</span></span>|<span data-ttu-id="60047-127">Servidor de archivos y solución de base de datos</span><span class="sxs-lookup"><span data-stu-id="60047-127">File Server and Database Solution</span></span>|<span data-ttu-id="60047-128">Solución de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="60047-128">FILESTREAM Solution</span></span>|<span data-ttu-id="60047-129">Solución de FileTable</span><span class="sxs-lookup"><span data-stu-id="60047-129">FileTable Solution</span></span>|  
|-------------|---------------------------------------|-------------------------|------------------------|  
|<span data-ttu-id="60047-130">**Un solo artículo para tareas de administración**</span><span class="sxs-lookup"><span data-stu-id="60047-130">**Single story for management tasks**</span></span>|<span data-ttu-id="60047-131">No</span><span class="sxs-lookup"><span data-stu-id="60047-131">No</span></span>|<span data-ttu-id="60047-132">Sí</span><span class="sxs-lookup"><span data-stu-id="60047-132">Yes</span></span>|<span data-ttu-id="60047-133">**Sí**</span><span class="sxs-lookup"><span data-stu-id="60047-133">**Yes**</span></span>|  
|<span data-ttu-id="60047-134">**Un solo conjunto de servicios**: búsquedas, informes, consultas, etc.</span><span class="sxs-lookup"><span data-stu-id="60047-134">**Single set of services**: search, reporting, querying, and so forth</span></span>|<span data-ttu-id="60047-135">No</span><span class="sxs-lookup"><span data-stu-id="60047-135">No</span></span>|<span data-ttu-id="60047-136">Sí</span><span class="sxs-lookup"><span data-stu-id="60047-136">Yes</span></span>|<span data-ttu-id="60047-137">**Sí**</span><span class="sxs-lookup"><span data-stu-id="60047-137">**Yes**</span></span>|  
|<span data-ttu-id="60047-138">**Modelo de seguridad integrada**</span><span class="sxs-lookup"><span data-stu-id="60047-138">**Integrated security model**</span></span>|<span data-ttu-id="60047-139">No</span><span class="sxs-lookup"><span data-stu-id="60047-139">No</span></span>|<span data-ttu-id="60047-140">Sí</span><span class="sxs-lookup"><span data-stu-id="60047-140">Yes</span></span>|<span data-ttu-id="60047-141">**Sí**</span><span class="sxs-lookup"><span data-stu-id="60047-141">**Yes**</span></span>|  
|<span data-ttu-id="60047-142">**Actualizaciones en contexto de datos FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="60047-142">**In-place updates of FILESTREAM data**</span></span>|<span data-ttu-id="60047-143">Sí</span><span class="sxs-lookup"><span data-stu-id="60047-143">Yes</span></span>|<span data-ttu-id="60047-144">No</span><span class="sxs-lookup"><span data-stu-id="60047-144">No</span></span>|<span data-ttu-id="60047-145">**Sí**</span><span class="sxs-lookup"><span data-stu-id="60047-145">**Yes**</span></span>|  
|<span data-ttu-id="60047-146">**Jerarquía de archivos y de directorios que se mantiene en la base de datos**</span><span class="sxs-lookup"><span data-stu-id="60047-146">**File and directory hierarchy maintained in the database**</span></span>|<span data-ttu-id="60047-147">No</span><span class="sxs-lookup"><span data-stu-id="60047-147">No</span></span>|<span data-ttu-id="60047-148">No</span><span class="sxs-lookup"><span data-stu-id="60047-148">No</span></span>|<span data-ttu-id="60047-149">**Sí**</span><span class="sxs-lookup"><span data-stu-id="60047-149">**Yes**</span></span>|  
|<span data-ttu-id="60047-150">**Compatibilidad con aplicaciones Windows**</span><span class="sxs-lookup"><span data-stu-id="60047-150">**Windows application compatibility**</span></span>|<span data-ttu-id="60047-151">Sí</span><span class="sxs-lookup"><span data-stu-id="60047-151">Yes</span></span>|<span data-ttu-id="60047-152">No</span><span class="sxs-lookup"><span data-stu-id="60047-152">No</span></span>|<span data-ttu-id="60047-153">**Sí**</span><span class="sxs-lookup"><span data-stu-id="60047-153">**Yes**</span></span>|  
|<span data-ttu-id="60047-154">**Acceso relacional a los atributos de archivo**</span><span class="sxs-lookup"><span data-stu-id="60047-154">**Relational access to file attributes**</span></span>|<span data-ttu-id="60047-155">No</span><span class="sxs-lookup"><span data-stu-id="60047-155">No</span></span>|<span data-ttu-id="60047-156">No</span><span class="sxs-lookup"><span data-stu-id="60047-156">No</span></span>|<span data-ttu-id="60047-157">**Sí**</span><span class="sxs-lookup"><span data-stu-id="60047-157">**Yes**</span></span>|  
  
##  <a name="comparing-filestream-and-remote-blob-store-rbs"></a><a name="CompareRBS"></a> <span data-ttu-id="60047-158">Comparar FILESTREAM y el almacén remoto de BLOBS (RBS)</span><span class="sxs-lookup"><span data-stu-id="60047-158">Comparing FILESTREAM and Remote BLOB Store (RBS)</span></span>  
 <span data-ttu-id="60047-159">Para obtener una comparación de estas dos características, vea este artículo del blog del equipo RBS: comparación de características  [del almacén remoto de blobs y FILESTREAM de SQL Server](https://go.microsoft.com/fwlink/?LinkId=210317).</span><span class="sxs-lookup"><span data-stu-id="60047-159">For a comparison of these two features, see this blog post from the RBS team: [SQL Server Remote BLOB Store and FILESTREAM feature comparison](https://go.microsoft.com/fwlink/?LinkId=210317).</span></span>  
  
##  <a name="more-information"></a><a name="more"></a> <span data-ttu-id="60047-160">Más información</span><span class="sxs-lookup"><span data-stu-id="60047-160">More Information</span></span>  
 [<span data-ttu-id="60047-161">FILESTREAM &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60047-161">FILESTREAM &#40;SQL Server&#41;</span></span>](filestream-sql-server.md)  
 [<span data-ttu-id="60047-162">FileTables &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60047-162">FileTables &#40;SQL Server&#41;</span></span>](filetables-sql-server.md)  
 [<span data-ttu-id="60047-163">Almacén remoto de blobs &#40;RBS&#41; &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60047-163">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span></span>](remote-blob-store-rbs-sql-server.md)  
  