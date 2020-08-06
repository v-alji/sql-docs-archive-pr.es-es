---
title: Cambio del orden de las columnas en una tabla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], change order in a table
- column order, change
ms.assetid: cd99ef56-9085-431a-a0fc-58e7add5399f
author: stevestein
ms.author: sstein
ms.openlocfilehash: d162f9dc793ceb9ea423d94922f7358f1729712e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672876"
---
# <a name="change-column-order-in-a-table"></a><span data-ttu-id="857c3-102">Cambiar el orden de las columnas de una tabla</span><span class="sxs-lookup"><span data-stu-id="857c3-102">Change Column Order in a Table</span></span>
  <span data-ttu-id="857c3-103">Puede cambiar el orden de las columnas en el Diseñador de tablas en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="857c3-103">You can change the order of columns in Table Designer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="857c3-104">Si cambia el orden de las columnas de una tabla, el código y las aplicaciones que dependen de un orden de columnas determinado pueden verse afectados.</span><span class="sxs-lookup"><span data-stu-id="857c3-104">Changing the column order of a table may affect code and applications that depend on the specific order of columns.</span></span> <span data-ttu-id="857c3-105">Los elementos afectados pueden ser consultas, vistas, procedimientos almacenados, funciones definidas por el usuario y aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="857c3-105">These include queries, views, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="857c3-106">Tenga en cuenta las consecuencias antes de realizar cualquier cambio en el orden de las columnas.</span><span class="sxs-lookup"><span data-stu-id="857c3-106">Carefully consider any changes you want to make to column order before making it.</span></span> <span data-ttu-id="857c3-107">El procedimiento recomendado es especificar el orden en que las columnas se devuelven en el nivel de aplicación y de consulta.</span><span class="sxs-lookup"><span data-stu-id="857c3-107">Best practice is to specify the order in which the columns are returned at the application and query level.</span></span> <span data-ttu-id="857c3-108">No debe confiar en el uso de SELECT \* para devolver todas las columnas en un orden esperado según el orden en que están definidos en la tabla.</span><span class="sxs-lookup"><span data-stu-id="857c3-108">You should not rely on the use of SELECT \* to return all columns in an expected order based on the order in which they are defined in the table.</span></span> <span data-ttu-id="857c3-109">Especifique siempre las columnas por nombre en las consultas y aplicaciones en el orden en que desea que aparezcan.</span><span class="sxs-lookup"><span data-stu-id="857c3-109">Always specify the columns by name in your queries and applications in the order in which you would like them to appear.</span></span>  
  
 <span data-ttu-id="857c3-110">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="857c3-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="857c3-111">**Para cambiar el orden de las columnas con:**</span><span class="sxs-lookup"><span data-stu-id="857c3-111">**To change the column order, using:**</span></span>  
  
     [<span data-ttu-id="857c3-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="857c3-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="857c3-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="857c3-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="857c3-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="857c3-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-column-order"></a><span data-ttu-id="857c3-115">Para cambiar el orden de las columnas</span><span class="sxs-lookup"><span data-stu-id="857c3-115">To change the column order</span></span>  
  
1.  <span data-ttu-id="857c3-116">En el **Explorador de objetos**, haga clic con el botón derecho en la tabla cuyas columnas quiera reordenar y seleccione **Diseñar**.</span><span class="sxs-lookup"><span data-stu-id="857c3-116">In **Object Explorer**, right-click the table with columns you want to reorder and click **Design**.</span></span>  
  
2.  <span data-ttu-id="857c3-117">Seleccione la casilla que hay a la izquierda del nombre de la columna cuyo orden desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="857c3-117">Select the box to the left of the column name that you want to reorder.</span></span>  
  
3.  <span data-ttu-id="857c3-118">Arrastre la columna a otra ubicación en la tabla.</span><span class="sxs-lookup"><span data-stu-id="857c3-118">Drag the column to another location within the table.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="857c3-119">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="857c3-119">Using Transact-SQL</span></span>  
 <span data-ttu-id="857c3-120">**Para cambiar el orden de las columnas**</span><span class="sxs-lookup"><span data-stu-id="857c3-120">**To change the column order**</span></span>  
  
 <span data-ttu-id="857c3-121">Esta tarea no se puede realizar mediante instrucciones Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="857c3-121">This task cannot be performed using Transact-SQL statements.</span></span>  
  
###  <a name="TsqlExample"></a>  
