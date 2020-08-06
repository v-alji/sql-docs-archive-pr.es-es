---
title: MSSQLSERVER_2501 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2501 (Database Engine error)
ms.assetid: 895aafe3-a4e7-4ed8-acc5-93be76ef3664
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 200997dcfe7bf8a5933b9fce492daabd5baffd04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747007"
---
# <a name="mssqlserver_2501"></a><span data-ttu-id="eed3d-102">MSSQLSERVER_2501</span><span class="sxs-lookup"><span data-stu-id="eed3d-102">MSSQLSERVER_2501</span></span>
    
## <a name="details"></a><span data-ttu-id="eed3d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="eed3d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eed3d-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="eed3d-104">Product Name</span></span>|<span data-ttu-id="eed3d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="eed3d-105">SQL Server</span></span>|  
|<span data-ttu-id="eed3d-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="eed3d-106">Event ID</span></span>|<span data-ttu-id="eed3d-107">2501</span><span class="sxs-lookup"><span data-stu-id="eed3d-107">2501</span></span>|  
|<span data-ttu-id="eed3d-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="eed3d-108">Event Source</span></span>|<span data-ttu-id="eed3d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="eed3d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="eed3d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="eed3d-110">Component</span></span>|<span data-ttu-id="eed3d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="eed3d-111">SQLEngine</span></span>|  
|<span data-ttu-id="eed3d-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="eed3d-112">Symbolic Name</span></span>|<span data-ttu-id="eed3d-113">DBCC_NO_SUCH_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="eed3d-113">DBCC_NO_SUCH_TABLE_NAME</span></span>|  
|<span data-ttu-id="eed3d-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="eed3d-114">Message Text</span></span>|<span data-ttu-id="eed3d-115">No se encuentra una tabla o un objeto con el nombre 'NAME'.</span><span class="sxs-lookup"><span data-stu-id="eed3d-115">Cannot find a table or object with the name 'NAME'.</span></span> <span data-ttu-id="eed3d-116">Compruebe el catálogo del sistema.</span><span class="sxs-lookup"><span data-stu-id="eed3d-116">Check the system catalog.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eed3d-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="eed3d-117">Explanation</span></span>  
 <span data-ttu-id="eed3d-118">No se encuentra el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="eed3d-118">The specified object cannot be found.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="eed3d-119">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="eed3d-119">Possible Causes</span></span>  
 <span data-ttu-id="eed3d-120">Este error puede deberse a uno de los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="eed3d-120">This error can be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="eed3d-121">No se ha especificado correctamente el objeto.</span><span class="sxs-lookup"><span data-stu-id="eed3d-121">The object is not specified correctly.</span></span>  
  
-   <span data-ttu-id="eed3d-122">El objeto no existe o se ha eliminado antes de que una instrucción intentara utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="eed3d-122">The object does not exist, or the object was dropped before a statement tried to use it.</span></span>  
  
-   <span data-ttu-id="eed3d-123">Es posible que el objeto exista, pero no ha podido mostrarse al usuario.</span><span class="sxs-lookup"><span data-stu-id="eed3d-123">The object might exist, but could not be exposed to the user.</span></span> <span data-ttu-id="eed3d-124">Por ejemplo, puede que el usuario no tenga permisos para el objeto o que el objeto sea una tabla interna que no puede ver un usuario.</span><span class="sxs-lookup"><span data-stu-id="eed3d-124">For example, the user might not have permissions on the object, or the object is an internal table that could not be seen by a user.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eed3d-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="eed3d-125">User Action</span></span>  
  
-   <span data-ttu-id="eed3d-126">Compruebe que el contexto de la base de datos activa sea correcto.</span><span class="sxs-lookup"><span data-stu-id="eed3d-126">Verify the current database context is correct.</span></span> <span data-ttu-id="eed3d-127">Para obtener más información, vea [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eed3d-127">For more information, see [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span></span>  
  
-   <span data-ttu-id="eed3d-128">Compruebe que el nombre de la tabla o del objeto esté correctamente escrito.</span><span class="sxs-lookup"><span data-stu-id="eed3d-128">Verify that the table or object name is spelled correctly.</span></span>  
  
-   <span data-ttu-id="eed3d-129">Compruebe el nombre del esquema que contiene el objeto.</span><span class="sxs-lookup"><span data-stu-id="eed3d-129">Verify the schema name that contains the object.</span></span> <span data-ttu-id="eed3d-130">Si el objeto pertenece a un esquema que no sea el predeterminado (**dbo**), debe especificar el nombre de la tabla o del objeto usando el formato de dos partes *nombreDeEsquema.nombreDeObjeto*.</span><span class="sxs-lookup"><span data-stu-id="eed3d-130">If the object belongs to a schema other than the default (**dbo**) schema, you must specify the table or object name by using the two-part format *schema_name.object_name*.</span></span>  
  
-   <span data-ttu-id="eed3d-131">Compruebe que el objeto exista en las tablas del sistema.</span><span class="sxs-lookup"><span data-stu-id="eed3d-131">Verify that the object exists in the system tables.</span></span> <span data-ttu-id="eed3d-132">Para comprobar si existe una tabla u otro objeto del ámbito de esquema, vea la vista de catálogo [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eed3d-132">To verify whether a table or other schema-scoped object exists, query the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view.</span></span> <span data-ttu-id="eed3d-133">Si el objeto no está en las tablas del sistema, significa que se ha eliminado o que el usuario no tiene permisos para ver los metadatos del objeto.</span><span class="sxs-lookup"><span data-stu-id="eed3d-133">If the object is not in the system tables, the object has been deleted, or the user does not have permissions to view the object metadata.</span></span> <span data-ttu-id="eed3d-134">Para obtener más información sobre cómo ver los metadatos de objeto, vea [Configuración de visibilidad de los metadatos](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="eed3d-134">For more information about how to view object metadata, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eed3d-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eed3d-135">See Also</span></span>  
 [<span data-ttu-id="eed3d-136">Vistas de catálogo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="eed3d-136">Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql)  
  
  
