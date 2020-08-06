---
title: Ejecución de un comando | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- commands [SQL Server Native Client]
- OLE DB, executing commands
- sessions [SQL Server Native Client]
- OLE DB extensions for XML
- SQL Server Native Client OLE DB provider, command execution
ms.assetid: bb0b3cbf-fe45-46ba-b2ec-c5a39e3c7081
author: rothja
ms.author: jroth
ms.openlocfilehash: 41e8da036d5a4b6469a31213247ad7d4edb7dbfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675826"
---
# <a name="executing-a-command"></a><span data-ttu-id="5f510-102">Ejecutar un comando</span><span class="sxs-lookup"><span data-stu-id="5f510-102">Executing a Command</span></span>
  <span data-ttu-id="5f510-103">Una vez establecida la conexión a un origen de datos, el consumidor llama al método **IDBCreateSession::CreateSession** para crear una sesión.</span><span class="sxs-lookup"><span data-stu-id="5f510-103">After the connection to a data source is established, the consumer calls the **IDBCreateSession::CreateSession** method to create a session.</span></span> <span data-ttu-id="5f510-104">La sesión actúa como un comando, conjunto de filas o fábrica de transacciones.</span><span class="sxs-lookup"><span data-stu-id="5f510-104">The session acts as a command, rowset, or transaction factory.</span></span>  
  
 <span data-ttu-id="5f510-105">Para trabajar directamente con índices o tablas individuales, el consumidor solicita la interfaz `IOpenRowset`.</span><span class="sxs-lookup"><span data-stu-id="5f510-105">To work directly with individual tables or indexes, the consumer requests the `IOpenRowset` interface.</span></span> <span data-ttu-id="5f510-106">El método `IOpenRowset::OpenRowset` se abre y devuelve un conjunto de filas que incluye todas las filas de un índice o tabla base única.</span><span class="sxs-lookup"><span data-stu-id="5f510-106">The `IOpenRowset::OpenRowset` method opens and returns a rowset that includes all rows from a single base table or index.</span></span>  
  
 <span data-ttu-id="5f510-107">Para ejecutar un comando (como SELECT \* from authors), el consumidor solicita la `IDBCreateCommand` interfaz.</span><span class="sxs-lookup"><span data-stu-id="5f510-107">To execute a command (such as SELECT \* FROM Authors), the consumer requests the `IDBCreateCommand` interface.</span></span> <span data-ttu-id="5f510-108">El consumidor puede ejecutar el método `IDBCreateCommand::CreateCommand` para crear un objeto de comando y solicitar la interfaz `ICommandText`.</span><span class="sxs-lookup"><span data-stu-id="5f510-108">The consumer can execute the `IDBCreateCommand::CreateCommand` method to create a command object and request for the `ICommandText` interface.</span></span> <span data-ttu-id="5f510-109">El método `ICommandText::SetCommandText` se usa para especificar el comando que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="5f510-109">The `ICommandText::SetCommandText` method is used to specify the command that is to be executed.</span></span>  
  
 <span data-ttu-id="5f510-110">El comando `Execute` se utiliza para ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="5f510-110">The `Execute` command is used to execute the command.</span></span> <span data-ttu-id="5f510-111">El comando puede ser cualquier instrucción SQL o nombre de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5f510-111">The command can be any SQL statement or procedure name.</span></span> <span data-ttu-id="5f510-112">No todos los comandos generan un objeto de conjunto de resultados (conjunto de filas).</span><span class="sxs-lookup"><span data-stu-id="5f510-112">Not all commands produce a result set (rowset) object.</span></span> <span data-ttu-id="5f510-113">Comandos como SELECT \* FROM Autores generan un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="5f510-113">Commands such as SELECT \* FROM Authors produce a result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f510-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f510-114">See Also</span></span>  
 [<span data-ttu-id="5f510-115">Crear una aplicación de proveedor OLE DB de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="5f510-115">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
