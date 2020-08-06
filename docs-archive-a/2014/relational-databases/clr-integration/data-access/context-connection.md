---
title: Conexión de contexto | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- context connections [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- context [CLR integration]
ms.assetid: 67dd1925-d672-4986-a85f-bce4fe832ef7
author: rothja
ms.author: jroth
ms.openlocfilehash: 82c739aa9c1952c71e9a16aaa68ec999851b3202
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672113"
---
# <a name="context-connection"></a><span data-ttu-id="0623f-102">Conexión de contexto</span><span class="sxs-lookup"><span data-stu-id="0623f-102">Context Connection</span></span>
  <span data-ttu-id="0623f-103">El problema de acceso interno a los datos es un escenario bastante común.</span><span class="sxs-lookup"><span data-stu-id="0623f-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="0623f-104">Es decir, desea tener acceso al mismo servidor en que se ejecuta el procedimiento almacenado o función de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0623f-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="0623f-105">Una opción es crear una conexión mediante `System.Data.SqlClient.SqlConnection`, especificar una cadena de conexión que señale al servidor local y abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="0623f-105">One option is to create a connection using `System.Data.SqlClient.SqlConnection`, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="0623f-106">Esto requiere especificar las credenciales para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="0623f-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="0623f-107">La conexión está en una sesión de base de datos distinta que el procedimiento almacenado o función, puede tener opciones `SET` distintas, está en una transacción aparte, no ve las tablas temporales, etc.</span><span class="sxs-lookup"><span data-stu-id="0623f-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="0623f-108">Si el código del procedimiento almacenado administrado o de la función está en ejecución en el proceso de SQL Server, es porque alguien se ha conectado a ese servidor y ha ejecutado una instrucción SQL para invocarlo.</span><span class="sxs-lookup"><span data-stu-id="0623f-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="0623f-109">Probablemente desea que el procedimiento almacenado o función se ejecute en el contexto de esa conexión, junto con la transacción, las opciones `SET`, etc.</span><span class="sxs-lookup"><span data-stu-id="0623f-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="0623f-110">Esto se denomina la conexión de contexto.</span><span class="sxs-lookup"><span data-stu-id="0623f-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="0623f-111">La conexión de contexto le permite ejecutar las instrucciones Transact-SQL en el mismo contexto que se invocó el código en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="0623f-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="0623f-112">Para obtener la conexión de contexto, debe utilizar la palabra clave de cadena de conexión "context connection", como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0623f-112">In order to obtain the context connection, you must use the "context connection" connection string keyword, as in the example below:</span></span>  
  
 <span data-ttu-id="0623f-113">[C#]</span><span class="sxs-lookup"><span data-stu-id="0623f-113">[C#]</span></span>  
  
```  
using(SqlConnection connection = new SqlConnection("context connection=true"))   
{  
    connection.Open();  
    // Use the connection  
}  
```  
  
 <span data-ttu-id="0623f-114">[Visual Basic]</span><span class="sxs-lookup"><span data-stu-id="0623f-114">[Visual Basic]</span></span>  
  
```  
Using connection as new SqlConnection("context connection=true")  
    connection.Open()  
    ' Use the connection  
End Using  
  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="0623f-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0623f-115">In This Section</span></span>  
 [<span data-ttu-id="0623f-116">Conexiones normales y conexiones de contexto</span><span class="sxs-lookup"><span data-stu-id="0623f-116">Regular vs. Context Connections</span></span>](context-connections-vs-regular-connections.md)  
 <span data-ttu-id="0623f-117">Describe las diferencias que existen entre las conexiones normales y las conexiones de contexto.</span><span class="sxs-lookup"><span data-stu-id="0623f-117">Describes the differences between regular and context connections.</span></span>  
  
 [<span data-ttu-id="0623f-118">Conexiones de contexto y conexiones normales: restricciones</span><span class="sxs-lookup"><span data-stu-id="0623f-118">Restrictions on Regular and Context Connections</span></span>](context-connections-and-regular-connections-restrictions.md)  
 <span data-ttu-id="0623f-119">Describe las restricciones en las conexiones normales y de contexto.</span><span class="sxs-lookup"><span data-stu-id="0623f-119">Describes the restrictions on regular and context connections.</span></span>  
  
  
