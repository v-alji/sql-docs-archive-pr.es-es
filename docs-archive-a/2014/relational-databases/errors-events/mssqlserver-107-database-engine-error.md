---
title: MSSQLSERVER_107 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 107 (Database Engine error)
ms.assetid: f33f514c-56aa-42e2-841b-e91244da90e2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b9388bbda6f00b1aafd02caee1b6a7b8387564f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675439"
---
# <a name="mssqlserver_107"></a><span data-ttu-id="4a8a7-102">MSSQLSERVER_107</span><span class="sxs-lookup"><span data-stu-id="4a8a7-102">MSSQLSERVER_107</span></span>
    
## <a name="details"></a><span data-ttu-id="4a8a7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4a8a7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4a8a7-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="4a8a7-104">Product Name</span></span>|<span data-ttu-id="4a8a7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4a8a7-105">SQL Server</span></span>|  
|<span data-ttu-id="4a8a7-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4a8a7-106">Event ID</span></span>|<span data-ttu-id="4a8a7-107">107</span><span class="sxs-lookup"><span data-stu-id="4a8a7-107">107</span></span>|  
|<span data-ttu-id="4a8a7-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="4a8a7-108">Event Source</span></span>|<span data-ttu-id="4a8a7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4a8a7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4a8a7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4a8a7-110">Component</span></span>|<span data-ttu-id="4a8a7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4a8a7-111">SQLEngine</span></span>|  
|<span data-ttu-id="4a8a7-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4a8a7-112">Symbolic Name</span></span>|<span data-ttu-id="4a8a7-113">P_NOCORRMATCH</span><span class="sxs-lookup"><span data-stu-id="4a8a7-113">P_NOCORRMATCH</span></span>|  
|<span data-ttu-id="4a8a7-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4a8a7-114">Message Text</span></span>|<span data-ttu-id="4a8a7-115">El prefijo de columna '%.\*ls' no coincide con un nombre de tabla o un nombre de alias utilizado en la consulta.</span><span class="sxs-lookup"><span data-stu-id="4a8a7-115">The column prefix '%.\*ls' does not match with a table name or alias name used in the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4a8a7-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="4a8a7-116">Explanation</span></span>  
 <span data-ttu-id="4a8a7-117">La lista de selección de la consulta contiene un asterisco (\*) que se califica incorrectamente con un prefijo de columna.</span><span class="sxs-lookup"><span data-stu-id="4a8a7-117">The select list of the query contains an asterisk (\*) that is incorrectly qualified with a column prefix.</span></span> <span data-ttu-id="4a8a7-118">Este error se puede devolver en las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4a8a7-118">This error can be returned under the following conditions:</span></span>  
  
-   <span data-ttu-id="4a8a7-119">El prefijo de columna no se corresponde con ningún nombre de tabla o de alias utilizado en la consulta.</span><span class="sxs-lookup"><span data-stu-id="4a8a7-119">The column prefix does not correspond to any table or alias name used in the query.</span></span> <span data-ttu-id="4a8a7-120">Por ejemplo, la instrucción siguiente utiliza un nombre de alias (`T1`) como prefijo de columna, pero el alias no está definido en la cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="4a8a7-120">For example, the following statement uses an alias name (`T1`) as a column prefix, but the alias is not defined in the FROM clause.</span></span>  
  
    ```  
    SELECT T1.* FROM dbo.ErrorLog;  
    ```  
  
-   <span data-ttu-id="4a8a7-121">Se especifica un nombre de tabla como prefijo de columna cuando se proporciona un nombre de alias para la tabla en la cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="4a8a7-121">A table name is specified as a column prefix when an alias name for the table is supplied in the FROM clause.</span></span> <span data-ttu-id="4a8a7-122">Por ejemplo, la instrucción siguiente utiliza el nombre de tabla `ErrorLog` como prefijo de columna; sin embargo, la tabla tiene definido un alias (`T1`) en la cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="4a8a7-122">For example, the following statement uses the table name `ErrorLog` as the column prefix; however, the table has an alias (`T1`) defined in the FROM clause.</span></span>  
  
    ```  
    SELECT ErrorLog.* FROM dbo.ErrorLog AS T1;  
    ```  
  
     <span data-ttu-id="4a8a7-123">Si se ha proporcionado un alias para un nombre de tabla en la cláusula FROM, solo puede utilizar el alias como prefijo de las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="4a8a7-123">If an alias has been provided for a table name in the FROM clause, you can only use the alias to prefix columns from the table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4a8a7-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4a8a7-124">User Action</span></span>  
 <span data-ttu-id="4a8a7-125">Haga coincidir los prefijos de columna con los nombres de tabla o con los nombres de alias especificados en la cláusula FROM de la consulta.</span><span class="sxs-lookup"><span data-stu-id="4a8a7-125">Match the column prefixes against the table names or alias names specified in the FROM clause of the query.</span></span> <span data-ttu-id="4a8a7-126">Por ejemplo, las instrucciones anteriores se pueden corregir de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="4a8a7-126">For example, the statements above can be corrected as follows:</span></span>  
  
```  
SELECT T1.* FROM dbo.ErrorLog AS T1;  
```  
  
 <span data-ttu-id="4a8a7-127">or</span><span class="sxs-lookup"><span data-stu-id="4a8a7-127">or</span></span>  
  
```  
SELECT ErrorLog.* FROM dbo.ErrorLog;  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a8a7-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a8a7-128">See Also</span></span>  
 [<span data-ttu-id="4a8a7-129">MSSQLSERVER_4104</span><span class="sxs-lookup"><span data-stu-id="4a8a7-129">MSSQLSERVER_4104</span></span>](mssqlserver-4104-database-engine-error.md)  
  
  
