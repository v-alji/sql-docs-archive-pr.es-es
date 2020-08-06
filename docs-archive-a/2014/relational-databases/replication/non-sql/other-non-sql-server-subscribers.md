---
title: Otros suscriptores que no son de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- non-SQL Server Subscribers, other types
ms.assetid: 96b8beb9-38e8-4ce4-97ca-c0f8656b73b4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3849ca717e82bcf1bed5769190c9f898209a454a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661912"
---
# <a name="other-non-sql-server-subscribers"></a><span data-ttu-id="eb66c-102">Otros suscriptores que no son de SQL Server</span><span class="sxs-lookup"><span data-stu-id="eb66c-102">Other Non-SQL Server Subscribers</span></span>
  <span data-ttu-id="eb66c-103"> Para obtener una lista de suscriptores que no son de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] compatibles con [!INCLUDE[msCoName](../../../includes/msconame-md.md)], vea [Suscriptores que no son de SQL Server](non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="eb66c-103">For a list of non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers supported by [!INCLUDE[msCoName](../../../includes/msconame-md.md)], see [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span></span> <span data-ttu-id="eb66c-104">Este tema incluye información acerca de los requisitos para los controladores ODBC y los proveedores de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="eb66c-104">This topic includes information about requirements for ODBC drivers and OLE DB providers.</span></span>  
  
## <a name="odbc-driver-requirements"></a><span data-ttu-id="eb66c-105">Requisitos para los controladores ODBC</span><span class="sxs-lookup"><span data-stu-id="eb66c-105">ODBC Driver Requirements</span></span>  
 <span data-ttu-id="eb66c-106">El controlador ODBC:</span><span class="sxs-lookup"><span data-stu-id="eb66c-106">The ODBC driver:</span></span>  
  
-   <span data-ttu-id="eb66c-107">Tiene que cumplir el nivel 1 de ODBC.</span><span class="sxs-lookup"><span data-stu-id="eb66c-107">Must be ODBC level-1 compliant.</span></span>  
  
-   <span data-ttu-id="eb66c-108">Tiene que ser de subproceso seguro, y para la arquitectura de procesador (Intel o Alpha) y la plataforma (32 ó 64 bits) en la que se ejecuta el distribuidor de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb66c-108">Must be thread-safe, and for the processor architecture (Intel or Alpha) and platform (32 bit or 64 bit) on which the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributor runs.</span></span>  
  
-   <span data-ttu-id="eb66c-109">Tiene que ser compatible con las transacciones.</span><span class="sxs-lookup"><span data-stu-id="eb66c-109">Must be transaction capable.</span></span>  
  
-   <span data-ttu-id="eb66c-110">Tiene que aceptar el Lenguaje de definición de datos (DDL, Data Definition Language).</span><span class="sxs-lookup"><span data-stu-id="eb66c-110">Must support the Data Definition Language (DDL).</span></span>  
  
-   <span data-ttu-id="eb66c-111">No puede ser de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="eb66c-111">Cannot be read-only.</span></span>  
  
-   <span data-ttu-id="eb66c-112">Debe admitir nombres de tabla largos, como **MSreplication_subscriptions**.</span><span class="sxs-lookup"><span data-stu-id="eb66c-112">Must support long table names such as **MSreplication_subscriptions**.</span></span>  
  
## <a name="replicating-using-ole-db-interfaces"></a><span data-ttu-id="eb66c-113">Replicación con interfaces OLE DB</span><span class="sxs-lookup"><span data-stu-id="eb66c-113">Replicating Using OLE DB Interfaces</span></span>  
 <span data-ttu-id="eb66c-114">Los proveedores OLE DB deben ser compatibles con estos objetos para la replicación transaccional:</span><span class="sxs-lookup"><span data-stu-id="eb66c-114">OLE DB providers must support these objects for transactional replication:</span></span>  
  
-   <span data-ttu-id="eb66c-115">Objeto**DataSource**</span><span class="sxs-lookup"><span data-stu-id="eb66c-115">**DataSource** object</span></span>  
  
-   <span data-ttu-id="eb66c-116">Objeto**Session**</span><span class="sxs-lookup"><span data-stu-id="eb66c-116">**Session** object</span></span>  
  
-   <span data-ttu-id="eb66c-117">Objeto**Command**</span><span class="sxs-lookup"><span data-stu-id="eb66c-117">**Command** object</span></span>  
  
-   <span data-ttu-id="eb66c-118">Objeto**Rowset**</span><span class="sxs-lookup"><span data-stu-id="eb66c-118">**Rowset** object</span></span>  
  
-   <span data-ttu-id="eb66c-119">Objeto**Error**</span><span class="sxs-lookup"><span data-stu-id="eb66c-119">**Error** object</span></span>  
  
### <a name="datasource-object-interfaces"></a><span data-ttu-id="eb66c-120">Interfaces del objeto DataSource</span><span class="sxs-lookup"><span data-stu-id="eb66c-120">DataSource Object Interfaces</span></span>  
 <span data-ttu-id="eb66c-121">Para conectar con un origen de datos se requieren las siguientes interfaces:</span><span class="sxs-lookup"><span data-stu-id="eb66c-121">The following interfaces are required to connect to a data source:</span></span>  
  
-   `IDBInitialize`  
  
-   `IDBCreateSession`  
  
-   `IDBProperties`  
  
 <span data-ttu-id="eb66c-122">Si el proveedor admite la interfaz **IDBInfo**, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] la usa para recuperar información como el carácter de identificador entre comillas, la longitud máxima de instrucciones SQL y el número máximo de caracteres en nombres de tablas y columnas.</span><span class="sxs-lookup"><span data-stu-id="eb66c-122">If the provider supports the **IDBInfo** interface, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses the interface to retrieve information such as the quoted identifier character, maximum SQL statement length, and maximum number of characters in table and column names.</span></span>  
  
### <a name="session-object-interfaces"></a><span data-ttu-id="eb66c-123">Interfaces del objeto Session</span><span class="sxs-lookup"><span data-stu-id="eb66c-123">Session Object Interfaces</span></span>  
 <span data-ttu-id="eb66c-124">Se requieren las siguientes interfaces:</span><span class="sxs-lookup"><span data-stu-id="eb66c-124">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="eb66c-125">**IDBCreateCommand**</span><span class="sxs-lookup"><span data-stu-id="eb66c-125">**IDBCreateCommand**</span></span>  
  
-   <span data-ttu-id="eb66c-126">**ITransaction**</span><span class="sxs-lookup"><span data-stu-id="eb66c-126">**ITransaction**</span></span>  
  
-   <span data-ttu-id="eb66c-127">**ITransactionLocal**</span><span class="sxs-lookup"><span data-stu-id="eb66c-127">**ITransactionLocal**</span></span>  
  
-   <span data-ttu-id="eb66c-128">**IDBSchemaRowset**</span><span class="sxs-lookup"><span data-stu-id="eb66c-128">**IDBSchemaRowset**</span></span>  
  
### <a name="command-object-interfaces"></a><span data-ttu-id="eb66c-129">Interfaces del objeto Command</span><span class="sxs-lookup"><span data-stu-id="eb66c-129">Command Object Interfaces</span></span>  
 <span data-ttu-id="eb66c-130">Se requieren las siguientes interfaces:</span><span class="sxs-lookup"><span data-stu-id="eb66c-130">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="eb66c-131">**ICommand**</span><span class="sxs-lookup"><span data-stu-id="eb66c-131">**ICommand**</span></span>  
  
-   <span data-ttu-id="eb66c-132">**ICommandProperties**</span><span class="sxs-lookup"><span data-stu-id="eb66c-132">**ICommandProperties**</span></span>  
  
-   <span data-ttu-id="eb66c-133">**ICommandText**</span><span class="sxs-lookup"><span data-stu-id="eb66c-133">**ICommandText**</span></span>  
  
-   <span data-ttu-id="eb66c-134">**ICommandPrepare**</span><span class="sxs-lookup"><span data-stu-id="eb66c-134">**ICommandPrepare**</span></span>  
  
-   <span data-ttu-id="eb66c-135">**IColumnsInfo**</span><span class="sxs-lookup"><span data-stu-id="eb66c-135">**IColumnsInfo**</span></span>  
  
-   <span data-ttu-id="eb66c-136">**IAccessor**</span><span class="sxs-lookup"><span data-stu-id="eb66c-136">**IAccessor**</span></span>  
  
-   <span data-ttu-id="eb66c-137">**ICommandWithParameters**</span><span class="sxs-lookup"><span data-stu-id="eb66c-137">**ICommandWithParameters**</span></span>  
  
 <span data-ttu-id="eb66c-138">Se necesita**IAccessor** para crear descriptores de acceso a parámetros.</span><span class="sxs-lookup"><span data-stu-id="eb66c-138">**IAccessor** is necessary to create parameter accessors.</span></span> <span data-ttu-id="eb66c-139">Si el proveedor es compatible con **IColumnRowset**, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utiliza esa interfaz para determinar si una columna es una columna de identidad.</span><span class="sxs-lookup"><span data-stu-id="eb66c-139">If the provider supports **IColumnRowset**, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses that interface to determine whether a column is an identity column.</span></span>  
  
### <a name="rowset-object-interfaces"></a><span data-ttu-id="eb66c-140">Interfaces del objeto Rowset</span><span class="sxs-lookup"><span data-stu-id="eb66c-140">Rowset Object Interfaces</span></span>  
 <span data-ttu-id="eb66c-141">Se requieren las siguientes interfaces:</span><span class="sxs-lookup"><span data-stu-id="eb66c-141">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="eb66c-142">**IRowset**</span><span class="sxs-lookup"><span data-stu-id="eb66c-142">**IRowset**</span></span>  
  
-   <span data-ttu-id="eb66c-143">**IAccessor**</span><span class="sxs-lookup"><span data-stu-id="eb66c-143">**IAccessor**</span></span>  
  
-   <span data-ttu-id="eb66c-144">**IColumnsInfo**</span><span class="sxs-lookup"><span data-stu-id="eb66c-144">**IColumnsInfo**</span></span>  
  
 <span data-ttu-id="eb66c-145">La aplicación tiene que abrir un conjunto de filas en una tabla replicada creada en la base de datos de suscripciones.</span><span class="sxs-lookup"><span data-stu-id="eb66c-145">An application should open a rowset on a replicated table that is created in the subscription database.</span></span> <span data-ttu-id="eb66c-146">Se necesita**IColumnsInfo** e **IAccessor** para tener acceso a los datos del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="eb66c-146">**IColumnsInfo** and **IAccessor** are needed to access data in the rowset.</span></span>  
  
### <a name="error-object-interfaces"></a><span data-ttu-id="eb66c-147">Interfaces del objeto Error</span><span class="sxs-lookup"><span data-stu-id="eb66c-147">Error Object Interfaces</span></span>  
 <span data-ttu-id="eb66c-148">Para controlar los errores, utilice las siguientes interfaces:</span><span class="sxs-lookup"><span data-stu-id="eb66c-148">Use the following interfaces to manage errors:</span></span>  
  
-   <span data-ttu-id="eb66c-149">**IErrorRecords**</span><span class="sxs-lookup"><span data-stu-id="eb66c-149">**IErrorRecords**</span></span>  
  
-   <span data-ttu-id="eb66c-150">**IErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="eb66c-150">**IErrorInfo**</span></span>  
  
 <span data-ttu-id="eb66c-151">Utilice **ISQLErrorInfo** si el proveedor OLE DB es compatible.</span><span class="sxs-lookup"><span data-stu-id="eb66c-151">Use **ISQLErrorInfo** if it is supported by the OLE DB provider.</span></span>  
  
 <span data-ttu-id="eb66c-152">Para obtener más información acerca del proveedor OLE DB, vea la documentación que se suministra con el proveedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="eb66c-152">For more information about the OLE DB provider, see the documentation supplied with your OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb66c-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb66c-153">See Also</span></span>  
 [<span data-ttu-id="eb66c-154">suscriptores que no son de SQL Server</span><span class="sxs-lookup"><span data-stu-id="eb66c-154">Non-SQL Server Subscribers</span></span>](non-sql-server-subscribers.md)  
  
  
