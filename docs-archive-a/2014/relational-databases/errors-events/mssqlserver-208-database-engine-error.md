---
title: MSSQLSERVER_208 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 208 (Database Engine error)
ms.assetid: 4b1895f5-3197-4da1-af86-954c93507956
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 97ab3eb220c03c3de0c95251861f3b947890b090
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662996"
---
# <a name="mssqlserver_208"></a><span data-ttu-id="bab02-102">MSSQLSERVER_208</span><span class="sxs-lookup"><span data-stu-id="bab02-102">MSSQLSERVER_208</span></span>
    
## <a name="details"></a><span data-ttu-id="bab02-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="bab02-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bab02-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="bab02-104">Product Name</span></span>|<span data-ttu-id="bab02-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bab02-105">SQL Server</span></span>|  
|<span data-ttu-id="bab02-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="bab02-106">Event ID</span></span>|<span data-ttu-id="bab02-107">208</span><span class="sxs-lookup"><span data-stu-id="bab02-107">208</span></span>|  
|<span data-ttu-id="bab02-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="bab02-108">Event Source</span></span>|<span data-ttu-id="bab02-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bab02-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bab02-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bab02-110">Component</span></span>|<span data-ttu-id="bab02-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bab02-111">SQLEngine</span></span>|  
|<span data-ttu-id="bab02-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="bab02-112">Symbolic Name</span></span>|<span data-ttu-id="bab02-113">SQ_BADOBJECT</span><span class="sxs-lookup"><span data-stu-id="bab02-113">SQ_BADOBJECT</span></span>|  
|<span data-ttu-id="bab02-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="bab02-114">Message Text</span></span>|<span data-ttu-id="bab02-115">El nombre de objeto '%.\*ls' no es válido.</span><span class="sxs-lookup"><span data-stu-id="bab02-115">Invalid object name '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bab02-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="bab02-116">Explanation</span></span>  
 <span data-ttu-id="bab02-117">No se encuentra el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="bab02-117">The specified object cannot be found.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="bab02-118">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="bab02-118">Possible Causes</span></span>  
 <span data-ttu-id="bab02-119">Este error puede deberse a uno de los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="bab02-119">This error can be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="bab02-120">No se ha especificado correctamente el objeto.</span><span class="sxs-lookup"><span data-stu-id="bab02-120">The object is not specified correctly.</span></span>  
  
-   <span data-ttu-id="bab02-121">El objeto no existe en la base de datos actual o en la base de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="bab02-121">The object does not exist in the current database or in the specified database.</span></span>  
  
-   <span data-ttu-id="bab02-122">El objeto existe, pero no ha podido mostrarse al usuario.</span><span class="sxs-lookup"><span data-stu-id="bab02-122">The object exists, but could not be exposed to the user.</span></span> <span data-ttu-id="bab02-123">Por ejemplo, puede que el usuario no tenga permisos para el objeto o que el objeto se haya creado dentro de una instrucción EXECUTE pero se tenga acceso a él fuera del ámbito de la citada instrucción.</span><span class="sxs-lookup"><span data-stu-id="bab02-123">For example, the user might not have permissions on the object or the object is created within an EXECUTE statement but accessed outside the scope of the EXECUTE statement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bab02-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="bab02-124">User Action</span></span>  
 <span data-ttu-id="bab02-125">Compruebe la información siguiente y corrija la instrucción según corresponda.</span><span class="sxs-lookup"><span data-stu-id="bab02-125">Verify the following information and correct the statement as appropriate.</span></span>  
  
-   <span data-ttu-id="bab02-126">El nombre de objeto está escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="bab02-126">The object name is spelled correctly.</span></span>  
  
-   <span data-ttu-id="bab02-127">El contexto de base de datos actual es correcto.</span><span class="sxs-lookup"><span data-stu-id="bab02-127">The current database context is correct.</span></span> <span data-ttu-id="bab02-128">Si no se especifica un nombre de base de datos para el objeto, este debe existir en la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="bab02-128">If a database name for the object is not specified, the object must exist in the current database.</span></span> <span data-ttu-id="bab02-129">Para obtener más información sobre cómo establecer el contexto de base de datos, vea [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bab02-129">For more information about setting the database context, see [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span></span>  
  
-   <span data-ttu-id="bab02-130">El objeto existe en las tablas del sistema.</span><span class="sxs-lookup"><span data-stu-id="bab02-130">The object exists in the system tables.</span></span> <span data-ttu-id="bab02-131">Para comprobar si existe una tabla u otro objeto del ámbito de esquema, vea la vista de catálogo **sys.objects**.</span><span class="sxs-lookup"><span data-stu-id="bab02-131">To verify whether a table or other schema-scoped object exists, query the **sys.objects** catalog view.</span></span> <span data-ttu-id="bab02-132">Si el objeto no está en las tablas del sistema, significa que se ha eliminado o que el usuario no tiene permisos para ver los metadatos del objeto.</span><span class="sxs-lookup"><span data-stu-id="bab02-132">If the object is not in the system tables, the object has been deleted, or the user does not have permissions to view the object metadata.</span></span> <span data-ttu-id="bab02-133">Para obtener más información sobre los permisos de visualización de los metadatos de objeto, vea [Configuración de visibilidad de los metadatos](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="bab02-133">For more information about permissions to view object metadata, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
-   <span data-ttu-id="bab02-134">El objeto está contenido en el esquema predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="bab02-134">The object is contained in the default schema of the user.</span></span> <span data-ttu-id="bab02-135">De lo contrario, el objeto se debe especificar usando el formato de dos partes *schema_name.object_name*.</span><span class="sxs-lookup"><span data-stu-id="bab02-135">If it is not, the object must be specified using the two-part format *schema_name.object_name*.</span></span> <span data-ttu-id="bab02-136">Observe que las funciones escalares siempre deben invocarse utilizando como mínimo un nombre de dos partes.</span><span class="sxs-lookup"><span data-stu-id="bab02-136">Note that scalar-valued functions must always be invoked by using at least a two-part name.</span></span>  
  
-   <span data-ttu-id="bab02-137">La distinción entre mayúsculas y minúsculas de la intercalación de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="bab02-137">The case sensitivity of the database collation.</span></span>  
  
     <span data-ttu-id="bab02-138">Cuando una base de datos utiliza una intercalación con distinción entre mayúsculas y minúsculas, las mayúsculas y minúsculas del nombre de objeto deben coincidir con las del objeto en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bab02-138">When a database uses a case-sensitive collation, the object name must match the case of the object in the database.</span></span> <span data-ttu-id="bab02-139">Por ejemplo, cuando un objeto se especifica como **MyTable** en una base de datos con una intercalación con distinción entre mayúsculas y minúsculas, las consultas que hagan referencia al objeto como **mytable** o **Mytable** harán que se devuelva el error 208 porque los nombres de objeto no coinciden.</span><span class="sxs-lookup"><span data-stu-id="bab02-139">For example, when an object is specified as **MyTable** in a database with a case sensitive collation, queries that refer to the object as **mytable** or **Mytable** will cause error 208 to return because the object names do not match.</span></span>  
  
     <span data-ttu-id="bab02-140">Puede comprobar la intercalación de bases de datos ejecutando la instrucción siguiente.</span><span class="sxs-lookup"><span data-stu-id="bab02-140">You can verify the database collation by running the following statement.</span></span>  
  
    ```  
    SELECT collation_name FROM sys.databases WHERE name = 'database_name';  
    ```  
  
     <span data-ttu-id="bab02-141">La abreviatura CS en el nombre de la intercalación indica que esta distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="bab02-141">The abbreviation CS in the collation name indicates the collation is case sensitive.</span></span> <span data-ttu-id="bab02-142">Por ejemplo, Latin1_General_CS_AS es una intercalación con distinción entre mayúsculas y minúsculas, y con distinción de acentos.</span><span class="sxs-lookup"><span data-stu-id="bab02-142">For example, Latin1_General_CS_AS is a case sensitive, accent sensitive collation.</span></span> <span data-ttu-id="bab02-143">CI indica una intercalación sin distinción entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="bab02-143">CI indicates a case insensitive collation.</span></span>  
  
-   <span data-ttu-id="bab02-144">El usuario dispone de permiso para tener acceso al objeto.</span><span class="sxs-lookup"><span data-stu-id="bab02-144">The user has permission to access the object.</span></span> <span data-ttu-id="bab02-145">Para comprobar los permisos que tiene el usuario para el objeto, use la función del sistema **Has_Perms_By_Name**.</span><span class="sxs-lookup"><span data-stu-id="bab02-145">To verify the permissions the user has on the object, use the **Has_Perms_By_Name** system function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab02-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bab02-146">See Also</span></span>  
 <span data-ttu-id="bab02-147">[USAR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bab02-147">[USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql) </span></span>  
 <span data-ttu-id="bab02-148">[Configuración de visibilidad de los metadatos](../security/metadata-visibility-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="bab02-148">[Metadata Visibility Configuration](../security/metadata-visibility-configuration.md) </span></span>  
 [<span data-ttu-id="bab02-149">HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bab02-149">HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/has-perms-by-name-transact-sql)  
  
  
