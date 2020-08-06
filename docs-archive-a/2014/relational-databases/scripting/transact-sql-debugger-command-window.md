---
title: Ventana de comandos
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Command Window [Transact-SQL]
ms.assetid: e567ebf9-0793-451b-92c7-26193a02d9da
author: rothja
ms.author: jroth
ms.openlocfilehash: c766ed5408de96b6a2305ce377f9031947618a7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676447"
---
# <a name="command-window"></a><span data-ttu-id="005f2-102">Ventana de comandos</span><span class="sxs-lookup"><span data-stu-id="005f2-102">Command Window</span></span>
  <span data-ttu-id="005f2-103">Use la **ventana Comandos** para ejecutar comandos, como debug y edit, con el código de la ventana Editor de consultas de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="005f2-103">Use the **CommandWindow** to run commands, such as debug and edit commands, against the code in the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] Query Editor window that is currently being debugged.</span></span> <span data-ttu-id="005f2-104">Debe estar en modo de depuración para utilizar el **Ventana de comandos**.</span><span class="sxs-lookup"><span data-stu-id="005f2-104">You must be in debug mode to use the **Command Window**.</span></span> <span data-ttu-id="005f2-105">El depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] admite muchos de los comandos que también se admiten en la ventana [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **Comando**.</span><span class="sxs-lookup"><span data-stu-id="005f2-105">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger supports many of the commands that are also supported in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **Command** window.</span></span> <span data-ttu-id="005f2-106">Para obtener más información, vea [Ventana de comandos de Visual Studio](https://go.microsoft.com/fwlink/?LinkId=112007).</span><span class="sxs-lookup"><span data-stu-id="005f2-106">For more information, see [Visual Studio Command Window](https://go.microsoft.com/fwlink/?LinkId=112007).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="005f2-107">Lista de tareas</span><span class="sxs-lookup"><span data-stu-id="005f2-107">Task List</span></span>  
 <span data-ttu-id="005f2-108">**Para tener acceso a la Ventana de comandos**</span><span class="sxs-lookup"><span data-stu-id="005f2-108">**To access the Command Window**</span></span>  
  
-   <span data-ttu-id="005f2-109">En el menú **Depurar** , haga clic en **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="005f2-109">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
 <span data-ttu-id="005f2-110">**Para imprimir el valor de una variable**</span><span class="sxs-lookup"><span data-stu-id="005f2-110">**To print the value of a variable**</span></span>  
  
-   <span data-ttu-id="005f2-111">En el tipo de **CommandWindow**, escriba \*\*Debug \<VariableName> . Print \*\*y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="005f2-111">In the **CommandWindow**, type **Debug.Print \<VariableName>**, and then press ENTER.</span></span>  
  
 <span data-ttu-id="005f2-112">**Para mostrar información sobre el subproceso actual**</span><span class="sxs-lookup"><span data-stu-id="005f2-112">**To list information about the current thread**</span></span>  
  
-   <span data-ttu-id="005f2-113">En el tipo **CommandWindow**, escriba `Debug.ListThread` y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="005f2-113">In the **CommandWindow**, type `Debug.ListThread`, and then press ENTER.</span></span>  
  
 <span data-ttu-id="005f2-114">**Para agregar una variable a la ventana Inspección rápida**</span><span class="sxs-lookup"><span data-stu-id="005f2-114">**To add a variable to the QuickWatch window**</span></span>  
  
-   <span data-ttu-id="005f2-115">En el tipo de **CommandWindow**, escriba \*\*Debug \<VariableName> . Inspección rápida \*\*y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="005f2-115">In the **CommandWindow**, type **Debug.QuickWatch \<VariableName>**, and then press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="005f2-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="005f2-116">See Also</span></span>  
 [<span data-ttu-id="005f2-117">Depurador de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="005f2-117">Transact-SQL Debugger</span></span>](transact-sql-debugger.md)  
