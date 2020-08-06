---
title: Formatos de datos para importación o exportación masivas (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- data formats [SQL Server], choosing
- bulk importing [SQL Server], data formats
ms.assetid: 73fe6741-9437-4b26-b030-28b863e74399
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b92ac8c038362ff18a1459a8bf3c55b6b596a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662025"
---
# <a name="data-formats-for-bulk-import-or-bulk-export-sql-server"></a><span data-ttu-id="8b403-102">Formatos de datos para importación o exportación masivas (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8b403-102">Data Formats for Bulk Import or Bulk Export (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8b403-103">puede aceptar datos en formato de datos de caracteres o binarios nativos.</span><span class="sxs-lookup"><span data-stu-id="8b403-103">can accept data in character data format or native binary data format.</span></span> <span data-ttu-id="8b403-104">Use el formato de caracteres al mover datos entre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y otra aplicación (como [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel) u otro servidor de bases de datos (como Oracle o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="8b403-104">Use character format when you move data between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and another application (such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel) or another database server (such as Oracle or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span></span> <span data-ttu-id="8b403-105">Solo puede usar el formato nativo al transferir datos entre instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b403-105">You can use native format only when you transfer data between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8b403-106">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="8b403-106">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="8b403-107">Formatos de datos para importación o exportación masivas</span><span class="sxs-lookup"><span data-stu-id="8b403-107">Data Formats for Bulk Import or Export</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="8b403-108">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="8b403-108">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="data-formats-for-bulk-import-or-export"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="8b403-109">Formatos de datos para importación o exportación masivas</span><span class="sxs-lookup"><span data-stu-id="8b403-109">Data Formats for Bulk Import or Export</span></span>  
 <span data-ttu-id="8b403-110">En la siguiente tabla se indica el formato de datos que resulta adecuado, de forma general, para usar dependiendo del modo en que los datos estén representados y el origen o el destino de la operación.</span><span class="sxs-lookup"><span data-stu-id="8b403-110">The following table indicates what data format is generally appropriate to use depending on how the data is represented and the source or target of the operation.</span></span>  
  
|<span data-ttu-id="8b403-111">Operación</span><span class="sxs-lookup"><span data-stu-id="8b403-111">Operation</span></span>|<span data-ttu-id="8b403-112">Nativa</span><span class="sxs-lookup"><span data-stu-id="8b403-112">Native</span></span>|<span data-ttu-id="8b403-113">Unicode nativo</span><span class="sxs-lookup"><span data-stu-id="8b403-113">Unicode native</span></span>|<span data-ttu-id="8b403-114">Carácter</span><span class="sxs-lookup"><span data-stu-id="8b403-114">Character</span></span>|<span data-ttu-id="8b403-115">carácter Unicode</span><span class="sxs-lookup"><span data-stu-id="8b403-115">Unicode character</span></span>|  
|---------------|------------|--------------------|---------------|-----------------------|  
|<span data-ttu-id="8b403-116">Transferencias masivas de datos entre varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante un archivo de datos que no contenga caracteres del juego de caracteres de doble byte (DBCS).</span><span class="sxs-lookup"><span data-stu-id="8b403-116">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that does not contain any extended or double-byte character set (DBCS) characters.</span></span> <span data-ttu-id="8b403-117">A menos que se use un archivo de formato, estas tablas deben definirse de forma idéntica.</span><span class="sxs-lookup"><span data-stu-id="8b403-117">Unless a format file is used, these tables must be identically defined.</span></span>|<span data-ttu-id="8b403-118">Sí<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8b403-118">Yes<sup>1</sup></span></span>|-|-|-|  
|<span data-ttu-id="8b403-119">Para las columnas `sql_variant`, es mejor el uso del formato de datos nativo, ya que preserva los metadatos de cada valor `sql_variant`, a diferencia de los formatos de caracteres o Unicode.</span><span class="sxs-lookup"><span data-stu-id="8b403-119">For `sql_variant` columns, use of native data format is best, because native data format preserves the metadata for each `sql_variant` value, unlike character or Unicode formats.</span></span>|<span data-ttu-id="8b403-120">Sí</span><span class="sxs-lookup"><span data-stu-id="8b403-120">Yes</span></span>|-|-|-|  
|<span data-ttu-id="8b403-121">Transferencias masivas de datos entre varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante un archivo de datos que contenga caracteres DBCS o extendidos.</span><span class="sxs-lookup"><span data-stu-id="8b403-121">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters.</span></span>|-|<span data-ttu-id="8b403-122">Sí</span><span class="sxs-lookup"><span data-stu-id="8b403-122">Yes</span></span>|-|-|  
|<span data-ttu-id="8b403-123">Importación masiva de datos desde un archivo de texto generado por otro programa.</span><span class="sxs-lookup"><span data-stu-id="8b403-123">Bulk import of data from a text file that is generated by another program.</span></span>|-|-|<span data-ttu-id="8b403-124">Sí</span><span class="sxs-lookup"><span data-stu-id="8b403-124">Yes</span></span>|-|  
|<span data-ttu-id="8b403-125">Exportación masiva de datos a un archivo de texto para usarlo en otro programa.</span><span class="sxs-lookup"><span data-stu-id="8b403-125">Bulk export of data to a text file that is to be used in another program.</span></span>|-|-|<span data-ttu-id="8b403-126">Sí</span><span class="sxs-lookup"><span data-stu-id="8b403-126">Yes</span></span>|-|  
|<span data-ttu-id="8b403-127">Transferencias masivas de datos entre varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante un archivo de datos que contenga datos Unicode y no contenga caracteres DBCS o extendidos.</span><span class="sxs-lookup"><span data-stu-id="8b403-127">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains Unicode data and does not contain any extended or DBCS characters.</span></span>|-|-|-|<span data-ttu-id="8b403-128">Sí</span><span class="sxs-lookup"><span data-stu-id="8b403-128">Yes</span></span>|  
  
 <span data-ttu-id="8b403-129"><sup>1</sup> método más rápido para la exportación masiva de datos desde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuando se usa **BCP**.</span><span class="sxs-lookup"><span data-stu-id="8b403-129"><sup>1</sup> Fastest method for the bulk export of data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when using **bcp**.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="8b403-130">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="8b403-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="8b403-131">Usar el formato nativo para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8b403-131">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="8b403-132">Usar el formato de caracteres para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8b403-132">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="8b403-133">Usar el formato nativo Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8b403-133">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="8b403-134">Usar el formato de caracteres Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8b403-134">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="8b403-135">Importar datos con formato nativo y de caracteres de versiones anteriores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="8b403-135">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="8b403-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b403-136">See Also</span></span>  
 <span data-ttu-id="8b403-137">[Tipos de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b403-137">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 [<span data-ttu-id="8b403-138">Especificar formatos de datos por razones de compatibilidad mediante bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8b403-138">Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;</span></span>](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md)  
  
  
