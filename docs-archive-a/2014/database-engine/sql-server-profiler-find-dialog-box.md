---
title: 'SQL Server Profiler: cuadro de diálogo Buscar | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.find.f1
helpviewer_keywords:
- Find dialog box
ms.assetid: dfaeec04-93d3-4214-9fc1-38b80179b36b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cedf50930c06d211ebcee0c45a249667219f392c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748238"
---
# <a name="sql-server-profiler---find-dialog-box"></a><span data-ttu-id="e6166-102">Buscar (cuadro de diálogo de SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="e6166-102">SQL Server Profiler - Find Dialog Box</span></span>
  <span data-ttu-id="e6166-103">Utilice el cuadro de diálogo **Buscar** para buscar un seguimiento para palabras o caracteres específicos.</span><span class="sxs-lookup"><span data-stu-id="e6166-103">Use the **Find** dialog box to search a trace for specific characters or words.</span></span> <span data-ttu-id="e6166-104">Para cancelar la búsqueda en curso, presione ESC.</span><span class="sxs-lookup"><span data-stu-id="e6166-104">To cancel a search in progress, press ESC.</span></span>  
  
 <span data-ttu-id="e6166-105">Para abrir este cuadro de diálogo en el [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], en el menú **Editar** , haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e6166-105">To open this dialog box in [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], on the **Edit** menu, click **Find**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e6166-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="e6166-106">Options</span></span>  
 <span data-ttu-id="e6166-107">**Buscar**</span><span class="sxs-lookup"><span data-stu-id="e6166-107">**Find what**</span></span>  
 <span data-ttu-id="e6166-108">Escriba el texto que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="e6166-108">Enter the text that you want to search for.</span></span> <span data-ttu-id="e6166-109">La búsqueda mostrará cualquier cadena que contenga la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="e6166-109">The search matches any string containing the specified string.</span></span> <span data-ttu-id="e6166-110">Por ejemplo, la búsqueda de "Completed" devolverá "SQL:BatchCompleted".</span><span class="sxs-lookup"><span data-stu-id="e6166-110">For example, searching for "Completed" matches "SQL:BatchCompleted."</span></span> <span data-ttu-id="e6166-111">No se admiten caracteres comodín (\*, ?, etc.).</span><span class="sxs-lookup"><span data-stu-id="e6166-111">Wild card characters (\*, ?, etc.) are not supported.</span></span>  
  
 <span data-ttu-id="e6166-112">**Buscar en columna**</span><span class="sxs-lookup"><span data-stu-id="e6166-112">**Search in column**</span></span>  
 <span data-ttu-id="e6166-113">Haga clic en una columna de datos para realizar la búsqueda o haga clic en **\<All columns>** para buscar en todas las columnas de datos del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e6166-113">Click a data column to search, or click **\<All columns>** to search all the data columns in the trace.</span></span>  
  
 <span data-ttu-id="e6166-114">**Coincidir mayúsculas y minúsculas**</span><span class="sxs-lookup"><span data-stu-id="e6166-114">**Match case**</span></span>  
 <span data-ttu-id="e6166-115">Busca texto en el que se usen las mismas mayúsculas y minúsculas que en el cuadro **Buscar** .</span><span class="sxs-lookup"><span data-stu-id="e6166-115">Finds text that has the same case as the **Find what** box.</span></span> <span data-ttu-id="e6166-116">Desactive esta casilla para buscar ejemplos del seguimiento que tengan caracteres tanto en mayúscula como en minúscula.</span><span class="sxs-lookup"><span data-stu-id="e6166-116">Clear this check box to find examples in the trace that are in both uppercase and lowercase text characters.</span></span>  
  
 <span data-ttu-id="e6166-117">**Solo palabras completas**</span><span class="sxs-lookup"><span data-stu-id="e6166-117">**Match whole word**</span></span>  
 <span data-ttu-id="e6166-118">Limita la búsqueda a palabras completas.</span><span class="sxs-lookup"><span data-stu-id="e6166-118">Restricts the search to entire words.</span></span> <span data-ttu-id="e6166-119">Desactive la casilla **Solo palabras completas** si desea realizar la búsqueda de algunos caracteres de una palabra.</span><span class="sxs-lookup"><span data-stu-id="e6166-119">Clear the **Match whole word** check box to search for characters within a word.</span></span>  
  
 <span data-ttu-id="e6166-120">**Buscar siguiente**</span><span class="sxs-lookup"><span data-stu-id="e6166-120">**Find Next**</span></span>  
 <span data-ttu-id="e6166-121">Busca el ejemplo siguiente de los caracteres del cuadro **Buscar** .</span><span class="sxs-lookup"><span data-stu-id="e6166-121">Finds the next example of the characters in the **Find what** box.</span></span>  
  
 <span data-ttu-id="e6166-122">**Buscar anterior**</span><span class="sxs-lookup"><span data-stu-id="e6166-122">**Find Previous**</span></span>  
 <span data-ttu-id="e6166-123">Realiza una búsqueda hacia atrás en el seguimiento, para buscar el ejemplo anterior de los caracteres del cuadro **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="e6166-123">Searches backwards in the trace, to find the previous example of the characters in the **Find what** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6166-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6166-124">See Also</span></span>  
 <span data-ttu-id="e6166-125">[Buscar un valor o una columna de datos durante el seguimiento de &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e6166-125">[Find a Value or Data Column While Tracing &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/find-a-value-or-data-column-while-tracing-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="e6166-126">[Cree un SQL Server Profiler de &#40;de seguimiento&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e6166-126">[Create a Trace &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="e6166-127">[Abra una tabla de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e6166-127">[Open a Trace Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="e6166-128">[Abra un archivo de seguimiento &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="e6166-128">[Open a Trace File &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="e6166-129">[Plantillas y permisos de SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="e6166-129">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="e6166-130">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="e6166-130">SQL Server Profiler</span></span>](../tools/sql-server-profiler/sql-server-profiler.md)  
  
  
