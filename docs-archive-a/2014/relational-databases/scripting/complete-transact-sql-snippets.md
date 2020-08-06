---
title: Completar fragmentos de código de Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], completing snippets
- snippets [Transact-SQL], completing
- Transact-SQL snippets, completing
ms.assetid: a8316a58-bb57-485e-845f-84c23360314c
author: rothja
ms.author: jroth
ms.openlocfilehash: d90c77f72ba8ce80d26503645d9b04d795f5e503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671441"
---
# <a name="complete-transact-sql-snippets"></a><span data-ttu-id="e8e6d-102">Completar fragmentos de código de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e8e6d-102">Complete Transact-SQL Snippets</span></span>
  <span data-ttu-id="e8e6d-103">Una vez insertado un fragmento de código de [!INCLUDE[tsql](../../includes/tsql-md.md)] en un script, debe modificar el contenido del fragmento para generar una instrucción completa de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e8e6d-103">Once a [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet has been inserted into a script, you edit the contents of the snippet to build a complete [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
## <a name="completing-snippets"></a><span data-ttu-id="e8e6d-104">Completar fragmentos de código</span><span class="sxs-lookup"><span data-stu-id="e8e6d-104">Completing Snippets</span></span>  
 <span data-ttu-id="e8e6d-105">Cuando se agrega un fragmento de [!INCLUDE[tsql](../../includes/tsql-md.md)] al script, la instrucción insertada del fragmento contiene uno o más puntos de reemplazo, que aparecen resaltados.</span><span class="sxs-lookup"><span data-stu-id="e8e6d-105">When you add a [!INCLUDE[tsql](../../includes/tsql-md.md)] snippet to your script, the inserted snippet statement has one or more replacement points, which are highlighted.</span></span> <span data-ttu-id="e8e6d-106">Si coloca el puntero del mouse sobre un punto de reemplazo, aparece una información sobre herramientas con una descripción del elemento de la sintaxis que se puede especificar.</span><span class="sxs-lookup"><span data-stu-id="e8e6d-106">If you rest your mouse pointer on a replacement point, a tooltip appears with a description of the syntax element you can specify.</span></span> <span data-ttu-id="e8e6d-107">El Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] reconoce el fragmento como parte independiente del resto del script hasta el momento de cerrar el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="e8e6d-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor recognizes the snippet as separate from the surrounding script until you close the source file.</span></span> <span data-ttu-id="e8e6d-108">Los puntos de reemplazo permanecen activos hasta que se cierra el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="e8e6d-108">The replacement points remain active until you close the source file.</span></span>  
  
 <span data-ttu-id="e8e6d-109">También puede agregar elementos adicionales de la sintaxis al código de la plantilla insertado por un fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="e8e6d-109">You can also add additional syntax elements to the template code inserted by a snippet.</span></span> <span data-ttu-id="e8e6d-110">Por ejemplo, la plantilla del fragmento de creación de tabla genera dos definiciones de columna; usted deberá agregar definiciones de columna adicionales para crear una tabla con más de dos columnas.</span><span class="sxs-lookup"><span data-stu-id="e8e6d-110">For example, the Create Table snippet template generates two column definitions; you must add additional column definitions to create a table with more than two columns.</span></span>  
  
#### <a name="completing-the-snippet-statement"></a><span data-ttu-id="e8e6d-111">Completar la instrucción del fragmento de código</span><span class="sxs-lookup"><span data-stu-id="e8e6d-111">Completing the Snippet Statement</span></span>  
  
1.  <span data-ttu-id="e8e6d-112">Utilice la tecla TAB para desplazarse desde un punto de reemplazo hasta el siguiente.</span><span class="sxs-lookup"><span data-stu-id="e8e6d-112">Use the TAB key to move from one replacement point to the next.</span></span> <span data-ttu-id="e8e6d-113">Utilice MAYÚS+TAB para desplazarse hasta el punto de reemplazo anterior.</span><span class="sxs-lookup"><span data-stu-id="e8e6d-113">Use SHIFT+TAB to move to the previous replacement point.</span></span>  
  
2.  <span data-ttu-id="e8e6d-114">Haga clic en CTRL+Barra espaciadora para invocar IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="e8e6d-114">Click CTRL+SPACE to invoke IntelliSense.</span></span>  
  
3.  <span data-ttu-id="e8e6d-115">Seleccione un elemento de la lista o escriba un punto de reemplazo de su elección.</span><span class="sxs-lookup"><span data-stu-id="e8e6d-115">Select an item from the list, or type a replacement of your choice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8e6d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8e6d-116">See Also</span></span>  
 <span data-ttu-id="e8e6d-117">[Insertar fragmentos de código de Transact-SQL](insert-transact-sql-snippets.md) </span><span class="sxs-lookup"><span data-stu-id="e8e6d-117">[Insert Transact-SQL Snippets](insert-transact-sql-snippets.md) </span></span>  
 [<span data-ttu-id="e8e6d-118">Insertar fragmentos de código de Transact-SQL para rodear</span><span class="sxs-lookup"><span data-stu-id="e8e6d-118">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
