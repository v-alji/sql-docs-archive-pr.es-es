---
title: Agregar sangría | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 9dce05c1-c52f-455d-8b8d-6f303e242760
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2d0b7ee8819f98df5e5658321a3d950ca31083b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674498"
---
# <a name="adding-indentation"></a><span data-ttu-id="1fdef-102">Agregar sangría</span><span class="sxs-lookup"><span data-stu-id="1fdef-102">Adding Indentation</span></span>
  <span data-ttu-id="1fdef-103">El Editor de consultas permite aplicar sangría a grandes secciones de código en un solo paso y cambiar la extensión de la sangría.</span><span class="sxs-lookup"><span data-stu-id="1fdef-103">Query Editor allows you to indent large sections of code with a single step, and you can change the amount of the indentation.</span></span>  
  
## <a name="indenting-code"></a><span data-ttu-id="1fdef-104">Aplicar sangría a líneas de código</span><span class="sxs-lookup"><span data-stu-id="1fdef-104">Indenting Code</span></span>  
  
#### <a name="to-indent-multiple-lines-of-code"></a><span data-ttu-id="1fdef-105">Para aplicar sangría a varias líneas de código</span><span class="sxs-lookup"><span data-stu-id="1fdef-105">To indent multiple lines of code</span></span>  
  
1.  <span data-ttu-id="1fdef-106">En la barra de herramientas, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="1fdef-106">On the toolbar, click **New Query**.</span></span>  
  
2.  <span data-ttu-id="1fdef-107">Cree una segunda consulta que seleccione las columnas **BusinessEntityID**, FirstName, **MiddleName**y **LastName** de la tabla **Person** del esquema **Person** .</span><span class="sxs-lookup"><span data-stu-id="1fdef-107">Create a second query that selects the **BusinessEntityID**, FirstName, **MiddleName**, and **LastName** columns from the **Person** table of the **Person** schema.</span></span> <span data-ttu-id="1fdef-108">Coloque cada columna en una línea separada de manera que el código tenga el aspecto siguiente:</span><span class="sxs-lookup"><span data-stu-id="1fdef-108">Place each column on a separate line so the code looks like this:</span></span>  
  
    ```  
    -- Search for a contact  
    SELECT   
    BusinessEntityID,  
    FirstName,   
    MiddleName,   
    LastName  
    FROM Person.Person  
    WHERE LastName = 'Sanchez';  
    GO  
    ```  
  
3.  <span data-ttu-id="1fdef-109">Seleccione todo el texto desde `BusinessEntityID` hasta `LastName`.</span><span class="sxs-lookup"><span data-stu-id="1fdef-109">Select all text from `BusinessEntityID` to `LastName`.</span></span>  
  
4.  <span data-ttu-id="1fdef-110">En la barra de herramientas del **Editor SQL** , haga clic en **Aumentar sangría** para aplicar la sangría a todas las líneas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="1fdef-110">On the **SQL Editor** toolbar, click **Increase Indent** to indent all the lines at once.</span></span>  
  
#### <a name="to-change-the-default-indentation"></a><span data-ttu-id="1fdef-111">Para cambiar la sangría predeterminada</span><span class="sxs-lookup"><span data-stu-id="1fdef-111">To change the default indentation</span></span>  
  
1.  <span data-ttu-id="1fdef-112">En el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="1fdef-112">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="1fdef-113">Expanda **Editor de texto**, **Todos los lenguajes**, haga clic en **Pestañas** y configure los valores de sangría apropiados.</span><span class="sxs-lookup"><span data-stu-id="1fdef-113">Expand **Text Editor**, expand **All Languages**, and click **Tabs** , and set indentation values as appropriate.</span></span> <span data-ttu-id="1fdef-114">Observe que puede cambiar tanto el tamaño de la sangría como el de las pestañas y especificar si éstas deben cambiarse por espacios.</span><span class="sxs-lookup"><span data-stu-id="1fdef-114">Note that you can change the size of the indent as well as the size of tabs, and whether tabs are converted to spaces.</span></span>  
  
     <span data-ttu-id="1fdef-115">![Apariencia del cuadro de diálogo Pestañas](media/tabsdialog.gif "Apariencia del cuadro de diálogo Pestañas")</span><span class="sxs-lookup"><span data-stu-id="1fdef-115">![Appearance of the Tabs dialog box](media/tabsdialog.gif "Appearance of the Tabs dialog box")</span></span>  
  
3.  <span data-ttu-id="1fdef-116">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="1fdef-116">Click **OK**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="1fdef-117">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="1fdef-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="1fdef-118">Maximizar el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="1fdef-118">Maximizing Query Editor</span></span>](lesson-2-3-maximizing-query-editor.md)  
  
  
