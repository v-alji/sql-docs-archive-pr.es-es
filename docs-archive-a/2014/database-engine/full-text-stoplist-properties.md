---
title: Propiedades de lista de palabras irrelevantes de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftstoplistproperties.general.f1
- sql12.swb.fulltextsearch.ftstoplistproperties.schedule.f1
ms.assetid: 2e907f5b-0cf9-484a-afcf-a4e7f1e2f87f
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ff27a1258d5164e3e93d34b6ff757993d6f6363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677827"
---
# <a name="full-text-stoplist-properties"></a><span data-ttu-id="fbb30-102">Propiedades de lista de palabras irrelevantes de texto completo</span><span class="sxs-lookup"><span data-stu-id="fbb30-102">Full-Text Stoplist Properties</span></span>
  <span data-ttu-id="fbb30-103">Use este cuadro de diálogo para agregar o eliminar palabras irrelevantes individuales, eliminar todas las palabras irrelevantes para un idioma concreto o borrar la lista de palabras irrelevantes actual.</span><span class="sxs-lookup"><span data-stu-id="fbb30-103">Use this dialog box to add or delete individual stopwords, delete all stopwords for a specific language, or clear the current stoplist.</span></span> <span data-ttu-id="fbb30-104">Una palabra irrelevante es una palabra de uso frecuente que se incluye en una lista de palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="fbb30-104">A stopword is a commonly used word that is included in a stoplist.</span></span> <span data-ttu-id="fbb30-105">Las palabras irrelevantes de una lista de palabras irrelevantes se omiten en la indización de texto completo para las tablas que usan dicha lista.</span><span class="sxs-lookup"><span data-stu-id="fbb30-105">The stopwords in a stoplist are omitted from full-text indexing for tables that use the stoplist.</span></span> <span data-ttu-id="fbb30-106">Para obtener más información, vea [Configurar y administrar palabras irrelevantes y listas de palabras irrelevantes para la búsqueda de texto completo](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="fbb30-106">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="fbb30-107">**Para usar SQL Server Management Studio a fin de modificar las propiedades de la lista de palabras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="fbb30-107">**To use SQL Server Management Studio to change stoplist properties**</span></span>  
  
-   [<span data-ttu-id="fbb30-108">Configurar y administrar palabras irrelevantes y listas de palabras irrelevantes para la búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="fbb30-108">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
## <a name="options"></a><span data-ttu-id="fbb30-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="fbb30-109">Options</span></span>  
 <span data-ttu-id="fbb30-110">**Acción**</span><span class="sxs-lookup"><span data-stu-id="fbb30-110">**Action**</span></span>  
 <span data-ttu-id="fbb30-111">Especifica la acción que desea realizar.</span><span class="sxs-lookup"><span data-stu-id="fbb30-111">Specifies the action that you want to perform.</span></span>  
  
 <span data-ttu-id="fbb30-112">**Agregar palabra irrelevante**</span><span class="sxs-lookup"><span data-stu-id="fbb30-112">**Add stopword**</span></span>  
 <span data-ttu-id="fbb30-113">Agrega una palabra de uso frecuente a la lista de palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="fbb30-113">Add a commonly used word to the stoplist.</span></span>  
  
 <span data-ttu-id="fbb30-114">**Eliminar palabra irrelevante**</span><span class="sxs-lookup"><span data-stu-id="fbb30-114">**Delete stopword**</span></span>  
 <span data-ttu-id="fbb30-115">Elimina una palabra irrelevante de la lista de palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="fbb30-115">Delete a stopword from the stoplist.</span></span>  
  
 <span data-ttu-id="fbb30-116">**Eliminar todas las palabras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="fbb30-116">**Delete all stopwords**</span></span>  
 <span data-ttu-id="fbb30-117">Elimina todas las palabras irrelevantes para un idioma concreto.</span><span class="sxs-lookup"><span data-stu-id="fbb30-117">Delete all the stopwords for a specific language.</span></span>  
  
 <span data-ttu-id="fbb30-118">**Borrar lista de palabras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="fbb30-118">**Clear stoplist**</span></span>  
 <span data-ttu-id="fbb30-119">Borra la lista de palabras irrelevantes eliminando todas las palabras irrelevantes para todos los idiomas.</span><span class="sxs-lookup"><span data-stu-id="fbb30-119">Clear the stoplist by deleting all the stopwords for all languages.</span></span>  
  
 <span data-ttu-id="fbb30-120">**Palabra irrelevante**</span><span class="sxs-lookup"><span data-stu-id="fbb30-120">**Stopword**</span></span>  
 <span data-ttu-id="fbb30-121">Si seleccionó **Agregar palabra irrelevante** o **Eliminar palabra irrelevante**, escriba la palabra irrelevante en el campo **Palabra irrelevante** .</span><span class="sxs-lookup"><span data-stu-id="fbb30-121">If you selected **Add stopword** or **Delete stopword**, enter the stopword in the **Stopword** field.</span></span> <span data-ttu-id="fbb30-122">Una nueva palabra irrelevante debe ser única; es decir, no debe estar todavía en esta lista de palabras irrelevantes para el idioma que seleccione.</span><span class="sxs-lookup"><span data-stu-id="fbb30-122">A new stopword must be unique; that is, not yet in this stoplist for the language that you select.</span></span>  
  
 <span data-ttu-id="fbb30-123">**Idioma de texto completo**</span><span class="sxs-lookup"><span data-stu-id="fbb30-123">**Full-text language**</span></span>  
 <span data-ttu-id="fbb30-124">Si seleccionó **Agregar palabra irrelevante**, **Eliminar palabra irrelevante**o **Eliminar todas las palabras irrelevantes**, seleccione el idioma de la palabra o palabras irrelevantes en el cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="fbb30-124">If you selected **Add stopword**, **Delete stopword**, or **Delete all stopwords**, select the language of the stopword or stopwords from the list box.</span></span> <span data-ttu-id="fbb30-125">Este cuadro incluye todos los idiomas de texto completo compatibles con la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="fbb30-125">This lists all the full-text languages that are supported by the server instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbb30-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fbb30-126">See Also</span></span>  
 <span data-ttu-id="fbb30-127">[Sys. fulltext_stopwords &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fbb30-127">[sys.fulltext_stopwords &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql) </span></span>  
 <span data-ttu-id="fbb30-128">[Sys. fulltext_stoplists &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fbb30-128">[sys.fulltext_stoplists &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql) </span></span>  
 <span data-ttu-id="fbb30-129">[Configurar y administrar palabras irrelevantes y palabras irrelevantes para la búsqueda de texto completo](../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="fbb30-129">[Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md) </span></span>  
 <span data-ttu-id="fbb30-130">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fbb30-130">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="fbb30-131">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fbb30-131">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span></span>  
 [<span data-ttu-id="fbb30-132">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fbb30-132">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
  
