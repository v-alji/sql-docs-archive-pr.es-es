---
title: Editor de lista de propiedades de búsqueda | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.spl.searchpropertylisteditor.f1
ms.assetid: 0f3ced6e-0dfd-49fc-b175-82378c3d668e
author: rothja
ms.author: jroth
ms.openlocfilehash: 6c68ec986e2c6f4f53dfec7f188ba2a120532ae4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671664"
---
# <a name="search-property-list-editor"></a><span data-ttu-id="e267c-102">Editor de lista de propiedades de búsqueda</span><span class="sxs-lookup"><span data-stu-id="e267c-102">Search Property List Editor</span></span>
  <span data-ttu-id="e267c-103">Use este cuadro de diálogo para agregar o eliminar propiedades de búsqueda en una lista de propiedades de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e267c-103">Use this dialog box to add or delete search properties in a search property list.</span></span>  
  
## <a name="to-use-sql-server-management-studio-to-manage-search-property-lists"></a><span data-ttu-id="e267c-104">Para usar SQL Server Management Studio con el fin de administrar listas de propiedades de búsqueda</span><span class="sxs-lookup"><span data-stu-id="e267c-104">To Use SQL Server Management Studio to Manage Search Property Lists</span></span>  
 <span data-ttu-id="e267c-105">Para obtener información sobre cómo crear, ver o eliminar una lista de propiedades de búsqueda, y sobre cómo configurar un índice de texto completo para la búsqueda de propiedades, vea [Buscar propiedades de documento con listas de propiedades de búsqueda](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span><span class="sxs-lookup"><span data-stu-id="e267c-105">For information about how to create, view, or delete a search property list, and about how to configure a full-text index for property searching, see [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e267c-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="e267c-106">Options</span></span>  
 <span data-ttu-id="e267c-107">**Nombre de la propiedad**</span><span class="sxs-lookup"><span data-stu-id="e267c-107">**Property Name**</span></span>  
 <span data-ttu-id="e267c-108">Especifique el nombre que se va a usar para identificar la propiedad en consultas de texto completo.</span><span class="sxs-lookup"><span data-stu-id="e267c-108">Specify the name to be used to identify the property in full-text queries.</span></span> <span data-ttu-id="e267c-109">El nombre de una propiedad puede contener espacios internos.</span><span class="sxs-lookup"><span data-stu-id="e267c-109">A property name can contain internal spaces.</span></span> <span data-ttu-id="e267c-110">La longitud máxima del atributo **Property Name** es de 256 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e267c-110">The maximum length of **Property Name** is 256 characters.</span></span> <span data-ttu-id="e267c-111">Este nombre puede ser un nombre descriptivo, como "Autor" o "Dirección particular", o bien el nombre canónico de Windows de la propiedad, como `System.Author` o `System.Contact.HomeAddress`.</span><span class="sxs-lookup"><span data-stu-id="e267c-111">This name can be a user-friendly name, such as "Author" or "Home Address", or it can be the Windows canonical name of the property, such as `System.Author` or `System.Contact.HomeAddress`.</span></span> <span data-ttu-id="e267c-112">**Nombre de propiedad** debe identificar exclusivamente la propiedad en el conjunto de propiedades.</span><span class="sxs-lookup"><span data-stu-id="e267c-112">**Property Name** must uniquely identify the property within the property set.</span></span>  
  
 <span data-ttu-id="e267c-113">Los desarrolladores usan el nombre de propiedad para identificar la propiedad en el predicado [CONTAINS](/sql/t-sql/queries/contains-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="e267c-113">Developers use the property name to identify the property in the [CONTAINS](/sql/t-sql/queries/contains-transact-sql) predicate.</span></span> <span data-ttu-id="e267c-114">Por tanto, cuando se agregue una propiedad es importante especificar un valor que represente significativamente la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e267c-114">Therefore, when adding a property it is important to specify a value that meaningfully represents the property.</span></span>  
  
 <span data-ttu-id="e267c-115">**GUID del conjunto de propiedades**</span><span class="sxs-lookup"><span data-stu-id="e267c-115">**Property Set GUID**</span></span>  
 <span data-ttu-id="e267c-116">Especifique el identificador del conjunto de propiedades al que pertenece la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e267c-116">Specify the identifier of the property set to which the property belongs.</span></span> <span data-ttu-id="e267c-117">Se trata de un identificador único global (GUID).</span><span class="sxs-lookup"><span data-stu-id="e267c-117">This is a globally unique identifier (GUID).</span></span> <span data-ttu-id="e267c-118">Un conjunto de propiedades es un grupo de propiedades relacionadas lógicamente.</span><span class="sxs-lookup"><span data-stu-id="e267c-118">A property set is a group of logically related properties.</span></span> <span data-ttu-id="e267c-119">Para obtener más información cómo obtener este valor, vea la sección "Comentarios" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e267c-119">For information about obtaining this value, see "Remarks," later in this topic.</span></span>  
  
 <span data-ttu-id="e267c-120">**Property Int ID**</span><span class="sxs-lookup"><span data-stu-id="e267c-120">**Property Int ID**</span></span>  
 <span data-ttu-id="e267c-121">Especifique el identificador entero de la propiedad de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e267c-121">Specify the property integer identifier of the property.</span></span> <span data-ttu-id="e267c-122">Este valor preasignado es un entero positivo que es único en el conjunto de propiedades.</span><span class="sxs-lookup"><span data-stu-id="e267c-122">This pre-assigned value is a positive integer that is unique within the property set.</span></span> <span data-ttu-id="e267c-123">Para obtener más información cómo obtener este valor, vea la sección "Comentarios" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="e267c-123">For information about obtaining this value, see "Remarks," later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e267c-124">Las propiedades de documento que usan identificadores de cadena no son compatibles con la búsqueda de texto completo.</span><span class="sxs-lookup"><span data-stu-id="e267c-124">Document properties that use string identifiers are not supported by full-text search.</span></span>  
  
 <span data-ttu-id="e267c-125">**Descripción de la propiedad**</span><span class="sxs-lookup"><span data-stu-id="e267c-125">**Property Description**</span></span>  
 <span data-ttu-id="e267c-126">Si lo desea, especifique una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e267c-126">Optionally, specify a description of the property.</span></span> <span data-ttu-id="e267c-127">Se trata de una cadena de hasta 512 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e267c-127">This is a string of up to 512 characters.</span></span> <span data-ttu-id="e267c-128">Por ejemplo, una descripción podría contener información sobre el conjunto de propiedades o sobre una propiedad que no sea evidente a partir de su nombre.</span><span class="sxs-lookup"><span data-stu-id="e267c-128">For example, a description could contain information about the property set of the property or information about a property that is not evident from its name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e267c-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e267c-129">Remarks</span></span>  
 <span data-ttu-id="e267c-130">Para agregar una propiedad de búsqueda a una lista de propiedades de búsqueda, debe especificar el identificador único global (GUID) del conjunto de propiedades al que pertenezca la propiedad y el identificador entero de propiedad.</span><span class="sxs-lookup"><span data-stu-id="e267c-130">To add a search property to a search property list, you must specify the globally unique identifier (GUID) of the property set to which the property belongs and the property integer identifier of the property.</span></span> <span data-ttu-id="e267c-131">Una combinación dada de estos debe ser única en una lista de propiedades de búsqueda determinada.</span><span class="sxs-lookup"><span data-stu-id="e267c-131">A given combination of these must be unique in a given search property list.</span></span> <span data-ttu-id="e267c-132">Si intenta agregar una combinación existente, se produce un error en la operación y se emite un error.</span><span class="sxs-lookup"><span data-stu-id="e267c-132">If you try to add an existing combination, the operation fails and issues an error.</span></span> <span data-ttu-id="e267c-133">Es decir, puede configurar solo un nombre para una propiedad dada.</span><span class="sxs-lookup"><span data-stu-id="e267c-133">This means that you can configure only one name for a given property.</span></span>  
  
 <span data-ttu-id="e267c-134">La descripción de la propiedad es opcional.</span><span class="sxs-lookup"><span data-stu-id="e267c-134">The property description is optional.</span></span>  
  
 <span data-ttu-id="e267c-135">**Para configurar una lista de propiedades de búsqueda para un índice de texto completo**</span><span class="sxs-lookup"><span data-stu-id="e267c-135">**To configure a search property list for a full-text index**</span></span>  
  
-   [<span data-ttu-id="e267c-136">Buscar propiedades de documento con listas de propiedades de búsqueda</span><span class="sxs-lookup"><span data-stu-id="e267c-136">Search Document Properties with Search Property Lists</span></span>](../relational-databases/search/search-document-properties-with-search-property-lists.md)  
  
## <a name="permissions"></a><span data-ttu-id="e267c-137">Permisos</span><span class="sxs-lookup"><span data-stu-id="e267c-137">Permissions</span></span>  
 <span data-ttu-id="e267c-138">Vea [ALTER Search Property LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-search-property-list-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e267c-138">See [ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-search-property-list-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e267c-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e267c-139">See Also</span></span>  
 <span data-ttu-id="e267c-140">[ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-search-property-list-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e267c-140">[ALTER SEARCH PROPERTY LIST &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-search-property-list-transact-sql) </span></span>  
 <span data-ttu-id="e267c-141">[Buscar propiedades de documento con listas de propiedades de búsqueda](../relational-databases/search/search-document-properties-with-search-property-lists.md) </span><span class="sxs-lookup"><span data-stu-id="e267c-141">[Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md) </span></span>  
 [<span data-ttu-id="e267c-142">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e267c-142">sys.registered_search_property_lists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-registered-search-property-lists-transact-sql)  
  
  
