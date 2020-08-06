---
title: Conjuntos de filas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [OLE DB], about rowsets
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets
- OLE DB rowsets, about rowsets
- rowsets [OLE DB]
ms.assetid: 5e7b3cbe-3670-4e18-8172-2226e0b6b142
author: rothja
ms.author: jroth
ms.openlocfilehash: 1245d17dc0f3757b3c212146c8c162de6e48a483
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670371"
---
# <a name="rowsets"></a><span data-ttu-id="88bee-102">Conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="88bee-102">Rowsets</span></span>
  <span data-ttu-id="88bee-103">Un conjunto de filas es el que contiene columnas de datos.</span><span class="sxs-lookup"><span data-stu-id="88bee-103">A rowset is a set of rows that contain columns of data.</span></span> <span data-ttu-id="88bee-104">Los conjuntos de filas son objetos centrales que permiten a todos los proveedores de datos OLE DB exponer los datos del conjunto de resultados en formato tabular.</span><span class="sxs-lookup"><span data-stu-id="88bee-104">Rowsets are central objects that enable all OLE DB data providers to expose result set data in tabular form.</span></span>  
  
 <span data-ttu-id="88bee-105">Después de que un consumidor crea una sesión mediante el método **IDBCreateSession::CreateSession**, el consumidor puede usar la interfaz **IDBCreateCommand** o **IOpenRowset** en la sesión para crear un conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="88bee-105">After a consumer creates a session by using the **IDBCreateSession::CreateSession** method, the consumer can use either the **IOpenRowset** or **IDBCreateCommand** interface on the session to create a rowset.</span></span> <span data-ttu-id="88bee-106">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client es compatible con ambas interfaces.</span><span class="sxs-lookup"><span data-stu-id="88bee-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports both of these interfaces.</span></span> <span data-ttu-id="88bee-107">Los dos métodos se describen aquí.</span><span class="sxs-lookup"><span data-stu-id="88bee-107">Both of these methods are described here.</span></span>  
  
-   <span data-ttu-id="88bee-108">Cree un conjunto de filas mediante una llamada al método **IOpenRowset::OpenRowset**.</span><span class="sxs-lookup"><span data-stu-id="88bee-108">Create a rowset by calling the **IOpenRowset::OpenRowset** method.</span></span>  
  
     <span data-ttu-id="88bee-109">Esto es equivalente a crear un conjunto de filas sobre una tabla única.</span><span class="sxs-lookup"><span data-stu-id="88bee-109">This is equivalent to creating a rowset over a single table.</span></span> <span data-ttu-id="88bee-110">Este método se abre y devuelve un conjunto de filas que incluye todas las filas de una tabla base única.</span><span class="sxs-lookup"><span data-stu-id="88bee-110">This method opens and returns a rowset that includes all of the rows from a single base table.</span></span> <span data-ttu-id="88bee-111">Uno de los argumentos de **OpenRowset** es un identificador de tabla que identifica la tabla desde la que se va a crear el conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="88bee-111">One of the arguments to **OpenRowset** is a table ID that identifies the table from which to create the rowset.</span></span>  
  
-   <span data-ttu-id="88bee-112">Cree un objeto de comando mediante una llamada al método **IDBCreateCommand::CreateCommand**.</span><span class="sxs-lookup"><span data-stu-id="88bee-112">Create a command object by calling the **IDBCreateCommand::CreateCommand** method.</span></span>  
  
     <span data-ttu-id="88bee-113">El objeto de comando ejecuta los comandos que el proveedor admite.</span><span class="sxs-lookup"><span data-stu-id="88bee-113">The command object executes commands that the provider supports.</span></span> <span data-ttu-id="88bee-114">Con el proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, el consumidor puede especificar cualquier instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)], como una instrucción SELECT o una llamada a un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="88bee-114">With the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the consumer can specify any [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, such as a SELECT statement or a call to a stored procedure.</span></span> <span data-ttu-id="88bee-115">Los pasos para crear un conjunto de filas utilizando un objeto de comando son:</span><span class="sxs-lookup"><span data-stu-id="88bee-115">The steps for creating a rowset by using a command object are:</span></span>  
  
    1.  <span data-ttu-id="88bee-116">El consumidor llama al método **IDBCreateCommand::CreateCommand** en la sesión para obtener un objeto de comando que solicita la interfaz **ICommandText** en el objeto de comando.</span><span class="sxs-lookup"><span data-stu-id="88bee-116">The consumer calls the **IDBCreateCommand::CreateCommand** method on the session to get a command object requesting the **ICommandText** interface on the command object.</span></span> <span data-ttu-id="88bee-117">Esta interfaz **ICommandText** establece y recupera el texto del comando real.</span><span class="sxs-lookup"><span data-stu-id="88bee-117">This **ICommandText** interface sets and retrieves the actual command text.</span></span> <span data-ttu-id="88bee-118">El consumidor rellena el comando de texto mediante una llamada al método **ICommandText::SetCommandText**.</span><span class="sxs-lookup"><span data-stu-id="88bee-118">The consumer fills in the text command by calling the **ICommandText::SetCommandText** method.</span></span>  
  
    2.  <span data-ttu-id="88bee-119">El usuario llama al método **ICommand::Execute** en el comando.</span><span class="sxs-lookup"><span data-stu-id="88bee-119">The user calls the **ICommand::Execute** method on the command.</span></span> <span data-ttu-id="88bee-120">El objeto de conjunto de filas generado cuando se ejecuta el comando contiene el conjunto de resultados del comando.</span><span class="sxs-lookup"><span data-stu-id="88bee-120">The rowset object built when the command executes contains the result set from the command.</span></span>  
  
 <span data-ttu-id="88bee-121">El consumidor puede usar la interfaz **ICommandProperties** para obtener o establecer las propiedades del conjunto de filas devuelto por el comando ejecutado por las interfaces **ICommand::Execute**.</span><span class="sxs-lookup"><span data-stu-id="88bee-121">The consumer can use the **ICommandProperties** interface to get or set the properties for the rowset returned by the command executed by the **ICommand::Execute** interfaces.</span></span> <span data-ttu-id="88bee-122">Las propiedades solicitadas normalmente son las interfaces que el conjunto de filas debe admitir.</span><span class="sxs-lookup"><span data-stu-id="88bee-122">The most commonly requested properties are the interfaces the rowset must support.</span></span> <span data-ttu-id="88bee-123">Además de las interfaces, el consumidor puede solicitar propiedades que modifican el comportamiento del conjunto de filas o la interfaz.</span><span class="sxs-lookup"><span data-stu-id="88bee-123">In addition to interfaces, the consumer can request properties that modify the behavior of the rowset or interface.</span></span>  
  
 <span data-ttu-id="88bee-124">Los consumidores liberan los conjuntos de filas con el método **IRowset::Release**.</span><span class="sxs-lookup"><span data-stu-id="88bee-124">Consumers release rowsets with the **IRowset::Release** method.</span></span> <span data-ttu-id="88bee-125">Al liberar un conjunto de filas se liberan los identificadores de fila mantenidos por el consumidor en ese conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="88bee-125">Releasing a rowset releases any row handles held by the consumer on that rowset.</span></span> <span data-ttu-id="88bee-126">Al liberar un conjunto de filas no se liberan los descriptores de acceso.</span><span class="sxs-lookup"><span data-stu-id="88bee-126">Releasing a rowset does not release the accessors.</span></span> <span data-ttu-id="88bee-127">Si tiene una interfaz **IAccessor**, todavía tiene que liberarse.</span><span class="sxs-lookup"><span data-stu-id="88bee-127">If you have an **IAccessor** interface, it still has to be released.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88bee-128">En esta sección</span><span class="sxs-lookup"><span data-stu-id="88bee-128">In This Section</span></span>  
  
-   [<span data-ttu-id="88bee-129">Crear un conjunto de filas con IOpenRowset</span><span class="sxs-lookup"><span data-stu-id="88bee-129">Creating a Rowset with IOpenRowset</span></span>](creating-a-rowset-with-iopenrowset.md)  
  
-   [<span data-ttu-id="88bee-130">Crear conjuntos de filas con ICommand::Execute</span><span class="sxs-lookup"><span data-stu-id="88bee-130">Creating Rowsets with ICommand::Execute</span></span>](creating-rowsets-with-icommand-execute.md)  
  
-   [<span data-ttu-id="88bee-131">Propiedades y comportamientos de conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="88bee-131">Rowset Properties and Behaviors</span></span>](rowset-properties-and-behaviors.md)  
  
-   [<span data-ttu-id="88bee-132">Conjuntos de filas y cursores de servidor de SQL Server</span><span class="sxs-lookup"><span data-stu-id="88bee-132">Rowsets and SQL Server Cursors</span></span>](rowsets-and-sql-server-cursors.md)  
  
-   [<span data-ttu-id="88bee-133">Capturar filas</span><span class="sxs-lookup"><span data-stu-id="88bee-133">Fetching Rows</span></span>](fetching-rows.md)  
  
-   [<span data-ttu-id="88bee-134">Capturar una única fila con IRow</span><span class="sxs-lookup"><span data-stu-id="88bee-134">Fetching a Single Row with IRow</span></span>](fetching-a-single-row-with-irow.md)  
  
-   [<span data-ttu-id="88bee-135">Marcadores</span><span class="sxs-lookup"><span data-stu-id="88bee-135">Bookmarks</span></span>](bookmarks.md)  
  
-   [<span data-ttu-id="88bee-136">Actualizar datos en conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="88bee-136">Updating Data in Rowsets</span></span>](updating-data-in-rowsets.md)  
  
## <a name="see-also"></a><span data-ttu-id="88bee-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88bee-137">See Also</span></span>  
 [<span data-ttu-id="88bee-138">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="88bee-138">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
