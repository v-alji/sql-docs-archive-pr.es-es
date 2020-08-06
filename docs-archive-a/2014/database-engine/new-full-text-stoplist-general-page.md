---
title: Nueva lista de palabras irrelevantes de texto completo (página general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.ftstoplist.general.f1
ms.assetid: 97f8e82d-82ab-4525-91c9-1ee3ae217309
author: rothja
ms.author: jroth
ms.openlocfilehash: a6272fb570b85989f38c8187e29712966862710d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676662"
---
# <a name="new-full-text-stoplist-general-page"></a><span data-ttu-id="fffe3-102">Nueva lista de palabras irrelevantes de texto completo (página General)</span><span class="sxs-lookup"><span data-stu-id="fffe3-102">New Full-Text Stoplist (General Page)</span></span>
  <span data-ttu-id="fffe3-103">Utilice este cuadro de diálogo para crear una lista de palabras irrelevantes de texto completo.</span><span class="sxs-lookup"><span data-stu-id="fffe3-103">Use this dialog box to create a full-text stoplist.</span></span> <span data-ttu-id="fffe3-104">Una *lista de palabras irrelevantes* es un conjunto de palabras que se usan habitualmente, denominadas *palabras irrelevantes*, que se omiten de la indización de texto completo para las tablas que utilizan dicha lista.</span><span class="sxs-lookup"><span data-stu-id="fffe3-104">A *stoplist* is a set of commonly used words, called *stopwords*, that are omitted from full-text indexing for tables that use the stoplist.</span></span> <span data-ttu-id="fffe3-105">Para obtener más información, vea [Configurar y administrar palabras irrelevantes y listas de palabras irrelevantes para la búsqueda de texto completo](../relational-databases/search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="fffe3-105">For more information, see [Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="fffe3-106">**Para utilizar SQL Server Management Studio a fin de crear una lista de palabras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="fffe3-106">**To use SQL Server Management Studio to create a stoplist**</span></span>  
  
-   [<span data-ttu-id="fffe3-107">Configurar y administrar palabras irrelevantes y listas de palabras irrelevantes para la búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="fffe3-107">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
## <a name="options"></a><span data-ttu-id="fffe3-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="fffe3-108">Options</span></span>  
 <span data-ttu-id="fffe3-109">**Nombre de lista de palabras irrelevantes de texto completo**</span><span class="sxs-lookup"><span data-stu-id="fffe3-109">**Full-text stoplist name**</span></span>  
 <span data-ttu-id="fffe3-110">Escriba el nombre de la lista de palabras irrelevantes de texto completo.</span><span class="sxs-lookup"><span data-stu-id="fffe3-110">Enter the name of the full-text stoplist.</span></span>  
  
 <span data-ttu-id="fffe3-111">**Propietario**</span><span class="sxs-lookup"><span data-stu-id="fffe3-111">**Owner**</span></span>  
 <span data-ttu-id="fffe3-112">Especifique el propietario de la lista de palabras irrelevantes de texto completo.</span><span class="sxs-lookup"><span data-stu-id="fffe3-112">Specify the owner of the full-text stoplist.</span></span> <span data-ttu-id="fffe3-113">Si desea que la propiedad se asigne a usted, es decir, al usuario actual, deje vacío este campo.</span><span class="sxs-lookup"><span data-stu-id="fffe3-113">If you want ownership to be assigned to yourself, that is, to the current user, leave this field empty.</span></span>  
  
 <span data-ttu-id="fffe3-114">Para especificar un usuario diferente, haga clic en el botón para examinar.</span><span class="sxs-lookup"><span data-stu-id="fffe3-114">To specify a different user, click the browse button.</span></span>  
  
### <a name="create-stoplist-options"></a><span data-ttu-id="fffe3-115">Crear opciones de la lista de palabras irrelevantes</span><span class="sxs-lookup"><span data-stu-id="fffe3-115">Create stoplist options</span></span>  
 <span data-ttu-id="fffe3-116">Haga clic en una de las opciones siguientes de creación:</span><span class="sxs-lookup"><span data-stu-id="fffe3-116">Click one of the following create options:</span></span>  
  
 <span data-ttu-id="fffe3-117">**Crear una lista de palabras irrelevantes vacía**</span><span class="sxs-lookup"><span data-stu-id="fffe3-117">**Create an empty stoplist**</span></span>  
 <span data-ttu-id="fffe3-118">La nueva lista de palabras irrelevantes no contendrá ninguna palabra irrelevante.</span><span class="sxs-lookup"><span data-stu-id="fffe3-118">The new stoplist will not contain any stopwords.</span></span>  
  
 <span data-ttu-id="fffe3-119">**Crear a partir de la lista de palabras irrelevantes del sistema**</span><span class="sxs-lookup"><span data-stu-id="fffe3-119">**Create from the system stoplist**</span></span>  
 <span data-ttu-id="fffe3-120">La nueva lista de palabras irrelevantes se crea a partir de la lista predeterminada que hay en la base de datos [Resource](../relational-databases/databases/resource-database.md).</span><span class="sxs-lookup"><span data-stu-id="fffe3-120">The new stoplist is created from the stoplist that exists by default in the [Resource database](../relational-databases/databases/resource-database.md).</span></span>  
  
 <span data-ttu-id="fffe3-121">**Crear a partir de una lista de palabras irrelevantes de texto completo existente**</span><span class="sxs-lookup"><span data-stu-id="fffe3-121">**Create from an existing full-text stoplist**</span></span>  
 <span data-ttu-id="fffe3-122">La nueva lista de palabras irrelevantes se crea copiando una lista existente.</span><span class="sxs-lookup"><span data-stu-id="fffe3-122">The new stoplist is created by copying an existing stoplist.</span></span>  
  
 <span data-ttu-id="fffe3-123">**Base de datos de origen**</span><span class="sxs-lookup"><span data-stu-id="fffe3-123">**Source database**</span></span>  
 <span data-ttu-id="fffe3-124">Especifica el nombre de la base de datos a la que pertenece la lista de palabras irrelevantes existente.</span><span class="sxs-lookup"><span data-stu-id="fffe3-124">Specifies the name of the database to which the existing stoplist belongs.</span></span> <span data-ttu-id="fffe3-125">De manera predeterminada, se selecciona la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="fffe3-125">The current database is selected by default.</span></span> <span data-ttu-id="fffe3-126">Si lo desea, seleccione otra base de datos en el cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="fffe3-126">Optionally, select a different database from the list box.</span></span>  
  
 <span data-ttu-id="fffe3-127">**Lista de palabras irrelevantes de origen**</span><span class="sxs-lookup"><span data-stu-id="fffe3-127">**Source stoplist**</span></span>  
 <span data-ttu-id="fffe3-128">Especifica el nombre de una lista de palabras irrelevantes existente.</span><span class="sxs-lookup"><span data-stu-id="fffe3-128">Specifies the name of an existing stoplist.</span></span> <span data-ttu-id="fffe3-129">En la lista de listas de palabras irrelevantes disponibles, seleccione la que desea utilizar como origen.</span><span class="sxs-lookup"><span data-stu-id="fffe3-129">From the list of available stoplists, select the one to use as the source.</span></span> <span data-ttu-id="fffe3-130">Las listas de palabras irrelevantes disponibles se enumeran en el orden en que aparecen en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="fffe3-130">The available stoplists are listed in the order in which they appear in Object Explorer.</span></span>  
  
 <span data-ttu-id="fffe3-131">Si alguno de los idiomas especificados en las palabras irrelevantes de la lista de palabras irrelevantes de origen no está registrado en la base de datos actual, CREATE FULLTEXT STOPLIST crea correctamente la lista, pero se devuelven advertencias y no se agregan las palabras irrelevantes correspondientes.</span><span class="sxs-lookup"><span data-stu-id="fffe3-131">If any languages specified in the stop words of the source stoplist are not registered in the current database, CREATE FULLTEXT STOPLIST succeeds, but warning(s) are returned and the corresponding stop words are not added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fffe3-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fffe3-132">See Also</span></span>  
 <span data-ttu-id="fffe3-133">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fffe3-133">[ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="fffe3-134">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fffe3-134">[CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="fffe3-135">[DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fffe3-135">[DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql) </span></span>  
 <span data-ttu-id="fffe3-136">[Configurar y administrar palabras irrelevantes y palabras irrelevantes para la búsqueda de texto completo](../relational-databases/search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="fffe3-136">[Configure and Manage Stopwords and Stoplists for Full-Text Search](../relational-databases/search/full-text-search.md) </span></span>  
 [<span data-ttu-id="fffe3-137">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fffe3-137">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
  
