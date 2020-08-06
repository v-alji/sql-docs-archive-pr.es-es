---
title: Crear autocombinaciones de forma automática (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- automatic joins
- self-joins
- joins [SQL Server], self
ms.assetid: f9ec90e8-3aad-415c-a5c4-8dfa9540e37f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a428a44d33b5990e849772b43841df472ca7f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662463"
---
# <a name="create-self-joins-automatically-visual-database-tools"></a><span data-ttu-id="49108-102">Crear autocombinaciones de forma automática (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="49108-102">Create Self-Joins Automatically (Visual Database Tools)</span></span>
  <span data-ttu-id="49108-103">Si una tabla tiene una relación reflexiva en la base de datos, puede combinarla consigo misma automáticamente.</span><span class="sxs-lookup"><span data-stu-id="49108-103">If a table has a reflexive relationship in the database, you can join it to itself automatically.</span></span>  
  
### <a name="to-create-a-self-join-automatically"></a><span data-ttu-id="49108-104">Para crear una autocombinación automáticamente</span><span class="sxs-lookup"><span data-stu-id="49108-104">To create a self-join automatically</span></span>  
  
1.  <span data-ttu-id="49108-105">Agregue al [panel Diagrama](visual-database-tools.md) la tabla con la que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="49108-105">Add to the [Diagram pane](visual-database-tools.md) the table you want to work with.</span></span>  
  
2.  <span data-ttu-id="49108-106">Vuelva a agregar la misma tabla, de forma que en el panel Diagrama se muestre la misma tabla dos veces.</span><span class="sxs-lookup"><span data-stu-id="49108-106">Add the same table again, so that the Diagram pane shows the same table twice within the Diagram pane.</span></span>  
  
     <span data-ttu-id="49108-107">El [Diseñador de consultas y vistas](query-and-view-designer-tools-visual-database-tools.md) asigna un alias a la segunda instancia mediante la adición de un número consecutivo al nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="49108-107">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) assigns an alias to the second instance by adding a sequential number to the table name.</span></span> <span data-ttu-id="49108-108">Asimismo, el Diseñador de consultas y vistas crea una línea de combinación entre los dos rectángulos que representan los dos modos diferentes en los que la tabla interviene en la consulta.</span><span class="sxs-lookup"><span data-stu-id="49108-108">In addition, the Query and View Designer creates a join line between the two rectangles representing the two different ways the table participates in the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49108-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49108-109">See Also</span></span>  
 [<span data-ttu-id="49108-110">Realizar consultas con combinaciones &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="49108-110">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
