---
title: Datos de objeto binario grande (Blob) (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], design and implementation
ms.assetid: 97509274-c3f8-43e5-a37c-52f1ffe0961a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a663dedf34d75a21ee8df6b97979548c04abf7ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676022"
---
# <a name="binary-large-object-blob-data-sql-server"></a><span data-ttu-id="5f6f7-102">Datos de objeto binario grande (Blob) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5f6f7-102">Binary Large Object (Blob) Data (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5f6f7-103">proporciona soluciones para almacenar archivos y documentos en la base de datos o en dispositivos de almacenamiento remoto.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-103">provides solutions for storing files and documents in the database or on remote storage devices.</span></span>  
  
##  <a name="in-this-section"></a><a name="section"></a> <span data-ttu-id="5f6f7-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5f6f7-104">In This Section</span></span>  
 [<span data-ttu-id="5f6f7-105">Comparar opciones para almacenar blobs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5f6f7-105">Compare Options for Storing Blobs &#40;SQL Server&#41;</span></span>](compare-options-for-storing-blobs-sql-server.md)  
 <span data-ttu-id="5f6f7-106">Comparar las ventanas de FILESTREAM, FileTables y almacén remoto de blobs.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-106">Compare the advantages of FILESTREAM, FileTables, and Remote Blob Store.</span></span>  
  
 [<span data-ttu-id="5f6f7-107">FILESTREAM &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5f6f7-107">FILESTREAM &#40;SQL Server&#41;</span></span>](filestream-sql-server.md)  
 <span data-ttu-id="5f6f7-108">FILESTREAM permite a las aplicaciones basadas en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] almacenar datos no estructurados, como documentos e imágenes, en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-108">FILESTREAM enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-based applications to store unstructured data, such as documents and images, on the file system.</span></span> <span data-ttu-id="5f6f7-109">Las aplicaciones pueden aprovechar las API de transmisión de datos enriquecidas y el rendimiento del sistema de archivos al mismo tiempo que mantienen la coherencia transaccional entre los datos no estructurados y los datos estructurados correspondientes.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-109">Applications can leverage the rich streaming APIs and performance of the file system and at the same time maintain transactional consistency between the unstructured data and corresponding structured data.</span></span>  
  
 [<span data-ttu-id="5f6f7-110">FileTables &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5f6f7-110">FileTables &#40;SQL Server&#41;</span></span>](filetables-sql-server.md)  
 <span data-ttu-id="5f6f7-111">La característica FileTable proporciona compatibilidad con el espacio de nombres de archivo de Windows y con las aplicaciones Windows para los datos de archivo almacenados en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f6f7-111">The FileTable feature brings support for the Windows file namespace and compatibility with Windows applications to the file data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5f6f7-112">FileTable permite que una aplicación pueda integrar sus componentes de administración de datos y almacenamiento, así como proporcionar servicios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integrados (incluidas la búsqueda de texto completo y la búsqueda semántica) en datos y metadatos no estructurados.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-112">FileTable lets an application integrate its storage and data management components, and provides integrated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services - including full-text search and semantic search - over unstructured data and metadata.</span></span>  
  
 <span data-ttu-id="5f6f7-113">Es decir, ahora puede almacenar archivos y documentos en tablas especiales de FileTables denominadas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y tener acceso a ellos desde las aplicaciones Windows como si estuviesen almacenados en el sistema de archivos, sin efectuar cambios en las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-113">In other words, you can store files and documents in special tables in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] called FileTables, but access them from Windows applications as if they were stored in the file system, without making any changes to your client applications.</span></span>  
  
 [<span data-ttu-id="5f6f7-114">Almacén remoto de blobs &#40;RBS&#41; &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5f6f7-114">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span></span>](remote-blob-store-rbs-sql-server.md)  
 <span data-ttu-id="5f6f7-115">El almacén remoto de blobs (RBS) para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permite a los administradores de bases de datos almacenar directamente objetos binarios grandes (blobs) en soluciones de almacenamiento estándar en lugar de directamente en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-115">Remote BLOB store (RBS) for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lets database administrators store binary large objects (BLOBs) in commodity storage solutions instead of directly on the server.</span></span> <span data-ttu-id="5f6f7-116">De este modo se ahorra una cantidad de espacio significativa y se evita malgastar los caros recursos de hardware de los servidores.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-116">This saves a significant amount of space and avoids wasting expensive server hardware resources.</span></span> <span data-ttu-id="5f6f7-117">RBS proporciona un conjunto de bibliotecas API que definen un modelo normalizado para que las aplicaciones accedan a los datos de los BLOB.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-117">RBS provides a set of API libraries that define a standardized model for applications to access BLOB data.</span></span> <span data-ttu-id="5f6f7-118">RBS también incluye herramientas de mantenimiento, como la recolección de elementos no utilizados, para ayudar a administrar los datos BLOB remotos.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-118">RBS also includes maintenance tools, such as garbage collection, to help manage remote BLOB data.</span></span>  
  
 <span data-ttu-id="5f6f7-119">RBS se incluye en el disco de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pero no lo instala el programa de instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f6f7-119">RBS is included on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media, but is not installed by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program.</span></span>  
  
  
