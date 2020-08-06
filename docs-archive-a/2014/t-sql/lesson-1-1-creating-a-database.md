---
title: Crear una base de datos (tutorial) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tutorial creating a database
ms.assetid: e1e2c83f-dfad-4bb8-aa7a-09d3f69517ae
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 99d5439c289b5d4e71786d4c6734f158f6bba371
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674477"
---
# <a name="creating-a-database-tutorial"></a><span data-ttu-id="49a83-102">Crear una base de datos (Tutorial)</span><span class="sxs-lookup"><span data-stu-id="49a83-102">Creating a Database (Tutorial)</span></span>
  <span data-ttu-id="49a83-103">Como muchas instrucciones de [!INCLUDE[tsql](../includes/tsql-md.md)] , la instrucción CREATE DATABASE tiene un parámetro requerido: el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="49a83-103">Like many [!INCLUDE[tsql](../includes/tsql-md.md)] statements, the CREATE DATABASE statement has a required parameter: the name of the database.</span></span> <span data-ttu-id="49a83-104">CREATE DATABASE también tiene muchos parámetros opcionales, como la ubicación de disco donde se desean colocar los archivos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="49a83-104">CREATE DATABASE also has many optional parameters, such as the disk location where you want to put the database files.</span></span> <span data-ttu-id="49a83-105">Si se ejecuta CREATE DATABASE sin los parámetros opcionales, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usa los valores predeterminados para muchos de estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="49a83-105">When you execute CREATE DATABASE without the optional parameters, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses default values for many of these parameters.</span></span> <span data-ttu-id="49a83-106">Este tutorial usa algunos de los parámetros de sintaxis opcionales.</span><span class="sxs-lookup"><span data-stu-id="49a83-106">This tutorial uses very few of the optional syntax parameters.</span></span>  
  
### <a name="to-create-a-database"></a><span data-ttu-id="49a83-107">Para crear una base de datos</span><span class="sxs-lookup"><span data-stu-id="49a83-107">To create a database</span></span>  
  
1.  <span data-ttu-id="49a83-108">En una ventana del Editor de consultas, escriba el código siguiente, pero no lo ejecute:</span><span class="sxs-lookup"><span data-stu-id="49a83-108">In a Query Editor window, type but do not execute the following code:</span></span>  
  
    ```  
    CREATE DATABASE TestData  
    GO  
    ```  
  
2.  <span data-ttu-id="49a83-109">Use el puntero para seleccionar las palabras `CREATE DATABASE`y, a continuación, presione **F1**.</span><span class="sxs-lookup"><span data-stu-id="49a83-109">Use the pointer to select the words `CREATE DATABASE`, and then press **F1**.</span></span> <span data-ttu-id="49a83-110">Debe abrirse el tema CREATE DATABASE de los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="49a83-110">The CREATE DATABASE topic in SQL Server Books Online should open.</span></span> <span data-ttu-id="49a83-111">Puede usar esta técnica para encontrar la sintaxis completa de CREATE DATABASE y de otras instrucciones que se usan en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="49a83-111">You can use this technique to find the complete syntax for CREATE DATABASE and for the other statements that are used in this tutorial.</span></span>  
  
3.  <span data-ttu-id="49a83-112">En el Editor de consultas, presione **F5** para ejecutar la instrucción y crear una base de datos con el nombre `TestData`.</span><span class="sxs-lookup"><span data-stu-id="49a83-112">In Query Editor, press **F5** to execute the statement and create a database named `TestData`.</span></span>  
  
 <span data-ttu-id="49a83-113">Al crear una base de datos, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] realiza una copia de la base de datos **model** y cambia el nombre de la copia por el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="49a83-113">When you create a database, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] makes a copy of the **model** database, and renames the copy to the database name.</span></span> <span data-ttu-id="49a83-114">Esta operación solo debería tardar algunos segundos, a menos que especifique un tamaño inicial grande de la base de datos como un parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="49a83-114">This operation should only take several seconds, unless you specify a large initial size of the database as an optional parameter.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49a83-115">La palabra clave GO separa las instrucciones cuando se envían varias instrucciones en un solo lote.</span><span class="sxs-lookup"><span data-stu-id="49a83-115">The keyword GO separates statements when more than one statement is submitted in a single batch.</span></span> <span data-ttu-id="49a83-116">GO es opcional cuando el lote solo contiene una instrucción.</span><span class="sxs-lookup"><span data-stu-id="49a83-116">GO is optional when the batch contains only one statement.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="49a83-117">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="49a83-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="49a83-118">Crear una tabla &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="49a83-118">Creating a Table &#40;Tutorial&#41;</span></span>](lesson-1-2-creating-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="49a83-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49a83-119">See Also</span></span>  
 [<span data-ttu-id="49a83-120">CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="49a83-120">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
