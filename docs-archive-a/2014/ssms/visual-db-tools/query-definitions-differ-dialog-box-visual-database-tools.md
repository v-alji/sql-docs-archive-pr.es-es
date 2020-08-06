---
title: Cuadro de diálogo Definiciones de consulta diferentes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69639
- vdtsql.chm:69640
- vdt.dlgbox.querydefinitionsdiffer
ms.assetid: 90383473-2922-40e5-9682-3850849aa856
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9a39d5d6b739fa4ab1a96ea95b513ecb7f6682f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747868"
---
# <a name="query-definitions-differ-dialog-box-visual-database-tools"></a><span data-ttu-id="133cc-102">Definiciones de consulta diferentes (cuadro de diálogo, Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="133cc-102">Query Definitions Differ Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="133cc-103">Este cuadro de diálogo notifica que no se puede representar gráficamente la consulta en los paneles Diagrama y Criterios, y que solo se puede modificar la consulta en el panel SQL.</span><span class="sxs-lookup"><span data-stu-id="133cc-103">This dialog box notifies you that your query cannot be represented graphically in the Diagram and Criteria panes, and that you can edit your query only in the SQL pane.</span></span>  
  
 <span data-ttu-id="133cc-104">Este cuadro de diálogo puede aparecer cuando escriba o modifique una instrucción SQL en el panel SQL; a continuación, si se desplaza a otro panel, comprueba la consulta o intenta ejecutarla, se producirá una de las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="133cc-104">This dialog box may appear when you enter or edit an SQL statement in the SQL pane; you then move to another pane, verify the query, or attempt to execute the query; and one of the following conditions applies:</span></span>  
  
-   <span data-ttu-id="133cc-105">La instrucción SQL no está completa o contiene uno o varios errores de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="133cc-105">The SQL statement is incomplete or contains one or more syntax errors.</span></span>  
  
-   <span data-ttu-id="133cc-106">La instrucción SQL es válida, pero no se admite en los paneles gráficos (por ejemplo, una consulta Union).</span><span class="sxs-lookup"><span data-stu-id="133cc-106">The SQL statement is valid but is not supported in the graphical panes (for example, a Union query).</span></span>  
  
-   <span data-ttu-id="133cc-107">La instrucción SQL es válida, pero contiene una sintaxis específica de la conexión de datos utilizada.</span><span class="sxs-lookup"><span data-stu-id="133cc-107">The SQL statement is valid but contains syntax specific to the data connection you are using.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="133cc-108">Puede comprobar la validez de una instrucción mediante el botón **Comprobar instrucción SQL** de la barra de herramientas **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="133cc-108">You can check whether a statement is valid using the **Verify SQL Statement** button on the **Query** toolbar.</span></span>  
  
 <span data-ttu-id="133cc-109">El cuadro de diálogo muestra un mensaje que indica el motivo por el que no se puede representar la instrucción SQL y, a continuación, le pregunta qué desea hacer.</span><span class="sxs-lookup"><span data-stu-id="133cc-109">The dialog box displays a message with the reason that the SQL statement cannot be represented, and then asks how you want to proceed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="133cc-110">Si los paneles Diagrama y Criterios están ocultos, el cuadro de diálogo **Definiciones de consulta diferentes** no aparecerá.</span><span class="sxs-lookup"><span data-stu-id="133cc-110">The **Query Definitions Differ** dialog box does not appear if you have hidden the Diagram and Criteria panes.</span></span>  
  
## <a name="options"></a><span data-ttu-id="133cc-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="133cc-111">Options</span></span>  
 <span data-ttu-id="133cc-112">**Omitir (Botón)**</span><span class="sxs-lookup"><span data-stu-id="133cc-112">**Ignore Button**</span></span>  
 <span data-ttu-id="133cc-113">Haga clic en este botón para especificar que desea aceptar la instrucción SQL, con el fin de ejecutarla o realizar una nueva modificación.</span><span class="sxs-lookup"><span data-stu-id="133cc-113">Choose this button to specify that you want to accept the SQL statement, either to edit it further or to execute it.</span></span> <span data-ttu-id="133cc-114">Si acepta la instrucción, los paneles Diagrama y Criterios se mostrarán atenuados para indicar que no representan la instrucción en el panel SQL.</span><span class="sxs-lookup"><span data-stu-id="133cc-114">If you accept the statement, the Diagram and Criteria panes appear dimmed to indicate that they do not represent the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="133cc-115">**Deshacer (Botón)**</span><span class="sxs-lookup"><span data-stu-id="133cc-115">**Undo Button**</span></span>  
 <span data-ttu-id="133cc-116">Haga clic en este botón para descartar los cambios realizados en el panel SQL.</span><span class="sxs-lookup"><span data-stu-id="133cc-116">Choose this button to discard your changes to the SQL pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="133cc-117">Si la instrucción es correcta, pero el Diseñador de consultas y vistas no la admite gráficamente, podrá ejecutarla aunque no se pueda representar en los paneles Diagrama y Criterios.</span><span class="sxs-lookup"><span data-stu-id="133cc-117">If the statement is correct but not supported graphically by the Query and View Designer, you can execute it even though it cannot be represented in the Diagram and Criteria panes.</span></span> <span data-ttu-id="133cc-118">Por ejemplo, si indica una consulta de unión, se podrá ejecutar la instrucción, pero no se podrá representar en los otros paneles.</span><span class="sxs-lookup"><span data-stu-id="133cc-118">For example, if you enter a Union query, the statement can be executed but not represented in the other panes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="133cc-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="133cc-119">See Also</span></span>  
 [<span data-ttu-id="133cc-120">Herramientas Diseñador de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="133cc-120">Query and View Designer Tools &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
