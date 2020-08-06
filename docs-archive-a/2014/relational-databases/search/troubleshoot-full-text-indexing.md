---
title: Solucionar problemas de indización de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- indexes [full-text search]
- troubleshooting [SQL Server], full-text search
- troubleshooting [full-text search]
ms.assetid: 964c43a8-5019-4179-82aa-63cd0ef592ef
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: eaca5fcf2dfbac57fc6d3ba6178251927d15aba9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677509"
---
# <a name="troubleshoot-full-text-indexing"></a><span data-ttu-id="a0a7a-102">Solucionar problemas de indización de texto completo</span><span class="sxs-lookup"><span data-stu-id="a0a7a-102">Troubleshoot Full-Text Indexing</span></span>
     
##  <a name="troubleshoot-full-text-indexing-failures"></a><a name="failure"></a> <span data-ttu-id="a0a7a-103">Solucionar errores de indización de texto completo</span><span class="sxs-lookup"><span data-stu-id="a0a7a-103">Troubleshoot Full-Text Indexing Failures</span></span>  
 <span data-ttu-id="a0a7a-104">Al rellenar o mantener un índice de texto completo, es posible que el indizador de texto completo no pueda indizar una o varias filas por las razones que se explican a continuación.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-104">While populating or maintaining a full-text index, the full-text indexer, for reasons described below, might fail to index one or more rows.</span></span> <span data-ttu-id="a0a7a-105">Estos errores de nivel de fila no impiden que se realice el llenado.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-105">These row-level errors do not prevent the population from completing.</span></span> <span data-ttu-id="a0a7a-106">El indizador omite estas filas, lo que significa que no se pueden realizar consultas del contenido de estas filas.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-106">The indexer skips these rows, which means that you are not able to query for content contained in these rows.</span></span>  
  
 <span data-ttu-id="a0a7a-107">Pueden producirse errores de indización cuando:</span><span class="sxs-lookup"><span data-stu-id="a0a7a-107">Indexing failures can occur when:</span></span>  
  
-   <span data-ttu-id="a0a7a-108">El indizador no puede encontrar o cargar un componente de un filtro o separador de palabras.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-108">The indexer cannot find or load a filter or word breaker component.</span></span> <span data-ttu-id="a0a7a-109">Este error puede producirse si la fila de la tabla contiene un formato de documento o un contenido en un idioma que no se ha registrado para la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0a7a-109">This failure can occur if the table row contains a document format or content in a language that has not been registered with the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a0a7a-110">Este error también puede darse si el componente del separador de palabras o del filtro no se firmó o si no superó la comprobación de firmas al cargarse.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-110">This failure can also happen if the registered word breaker or filter component was not signed or failed signature verification when it was being loaded.</span></span>  
  
-   <span data-ttu-id="a0a7a-111">Un componente, como un separador de palabras o un filtro, devuelve un error al indizador.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-111">A component, such as a word breaker or filter, fails and returns an error to the indexer.</span></span> <span data-ttu-id="a0a7a-112">Esto puede ocurrir si el documento que se está indizando está dañado y el filtro no puede extraer texto del documento.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-112">This can happen if the document being indexed is corrupt and the filter is unable to extract text from the document.</span></span> <span data-ttu-id="a0a7a-113">También puede suceder cuando un componente no puede administrar el contenido de una sola fila que supere cierto tamaño, debido a los límites de memoria del host de demonio de filtro de texto completo (fdhost.exe).</span><span class="sxs-lookup"><span data-stu-id="a0a7a-113">This can also occur when a component is unable to handle the content of a single row above a certain size, due to memory limits on the full-text filter daemon host (fdhost.exe).</span></span>  
  
 <span data-ttu-id="a0a7a-114">El registro de rastreo contiene información relativa al motivo del error para cada error de nivel de fila.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-114">For each row-level failure, the crawl log contains details on the reason for the failure.</span></span> <span data-ttu-id="a0a7a-115">Los recuentos de errores se encuentran resumidos al final de un llenado completo o incremental.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-115">The error counts are summarized at the end of a full or incremental population.</span></span>  
  
 <span data-ttu-id="a0a7a-116">Existen otros errores que pueden afectar al proceso de indización en sí e impedir que se realice el llenado:</span><span class="sxs-lookup"><span data-stu-id="a0a7a-116">There are other failures that can impact the indexing process itself and prevent the population from completing:</span></span>  
  
-   <span data-ttu-id="a0a7a-117">El índice de texto completo supera el límite del número de filas que puede contener un catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-117">The full-text index exceeds the limit for the number of rows that can be contained in a full-text catalog.</span></span>  
  
-   <span data-ttu-id="a0a7a-118">Se modifica, se quita o vuelve a generarse un índice clúster o un índice de clave de texto completo de la tabla que se está indizando.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-118">A clustered index or full-text key index on the table being indexed gets altered, dropped, or rebuilt.</span></span>  
  
-   <span data-ttu-id="a0a7a-119">El catálogo de texto completo queda dañado debido a un error de hardware o a que el disco está dañado.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-119">A hardware failure or disk corruption results in the corruption of the full-text catalog.</span></span>  
  
-   <span data-ttu-id="a0a7a-120">Un grupo de archivos que contiene la tabla cuyo texto completo se está indizando se queda sin conexión o pasa a ser de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-120">A file group that contains the table being full-text indexed goes offline, or is made read-only.</span></span>  
  
 <span data-ttu-id="a0a7a-121">Debe consultar el registro de rastreo al final de cualquier operación de llenado de índice de texto completo importante o cuando el llenado no llega a completarse.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-121">You should view the crawl log at the end of any significant full-text index population operation, or when you find that a population did not complete.</span></span>  
  
### <a name="unsigned-components"></a><span data-ttu-id="a0a7a-122">Componentes sin firmar</span><span class="sxs-lookup"><span data-stu-id="a0a7a-122">Unsigned Components</span></span>  
 <span data-ttu-id="a0a7a-123">De forma predeterminada, el indizador de texto completo necesita los filtros y los separadores de palabras que carga para firmarse.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-123">By default, the full-text indexer requires the filters and word breakers that it loads to be signed.</span></span> <span data-ttu-id="a0a7a-124">Si no están firmados, lo cual puede ocurrir cuando se instalan componentes personalizados, debe configurar el indizador de texto completo para que omita la comprobación de firmas.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-124">If they are not signed, which is the case sometimes when custom components are installed, you must configure the full-text indexer to ignore signature verification.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a0a7a-125">Si se omite la comprobación de firmas, la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es menos segura.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-125">Ignoring signature verification makes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] less secure.</span></span> <span data-ttu-id="a0a7a-126">Se recomienda que firme todo componente que implemente o que se asegure de que todo componente que adquiera esté firmado.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-126">We recommend that you sign any components that you implement or ensure that any components that you acquire are signed.</span></span> <span data-ttu-id="a0a7a-127">Para obtener más información sobre cómo firmar componentes, vea [sp_fulltext_service &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a0a7a-127">For information about signing components, see [sp_fulltext_service &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span></span>  
  

  
##  <a name="full-text-index-in-inconsistent-state-after-transaction-log-restored"></a><a name="state"></a> <span data-ttu-id="a0a7a-128">Índice de texto completo en estado incoherente después de la restauración del registro de transacciones</span><span class="sxs-lookup"><span data-stu-id="a0a7a-128">Full-Text Index in Inconsistent State after Transaction Log Restored</span></span>  
 <span data-ttu-id="a0a7a-129">Al restaurar el registro de transacciones de una base de datos, es posible que aparezca una advertencia que indica que el índice de texto completo no es coherente.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-129">When restoring the transaction log of a database, you might see a warning indicating that the full-text index is not in a consistent state.</span></span> <span data-ttu-id="a0a7a-130">El motivo es que se ha modificado el índice de texto completo en una tabla después de realizar la copia de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-130">The reason for this is that the full-text index on a table was modified after the database was backed up.</span></span> <span data-ttu-id="a0a7a-131">Si esto ocurre, deberá ejecutar un rellenado completo (rastreo) en la tabla para devolver la coherencia al índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="a0a7a-131">To bring the full-text index to a consistent state, you must run a full population (crawl) on the table.</span></span> <span data-ttu-id="a0a7a-132">Para obtener más información, vea [Rellenar índices de texto completo](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="a0a7a-132">For more information, see [Populate Full-Text Indexes](../indexes/indexes.md).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="a0a7a-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0a7a-133">See Also</span></span>  
 <span data-ttu-id="a0a7a-134">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a0a7a-134">[ALTER FULLTEXT CATALOG &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-catalog-transact-sql) </span></span>  
 [<span data-ttu-id="a0a7a-135">Rellenar índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="a0a7a-135">Populate Full-Text Indexes</span></span>](../indexes/indexes.md)  
  
  
