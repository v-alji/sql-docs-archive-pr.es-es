---
title: Modificar la ubicación de un punto de interrupción
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint location
ms.assetid: 5c28e411-0377-4210-a7ce-2a5c13dcdf74
author: rothja
ms.author: jroth
ms.openlocfilehash: 919e62d53d5c9e8898bf1d49c4b5e5aa4c0ed107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661880"
---
# <a name="edit-a-breakpoint-location"></a><span data-ttu-id="5b302-102">Modificar la ubicación de un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="5b302-102">Edit a Breakpoint Location</span></span>
  <span data-ttu-id="5b302-103">La ubicación del punto de interrupción especifica la línea y el carácter en el que el punto de interrupción reside en un archivo de script de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b302-103">The breakpoint location specifies the line and character where the breakpoint resides in a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="5b302-104">Puede modificar la ubicación del punto de interrupción para moverlo a otra ubicación en el script o a un script diferente.</span><span class="sxs-lookup"><span data-stu-id="5b302-104">You can edit the breakpoint location to move the breakpoint to another location in the script, or to a different script.</span></span>  
  
## <a name="editing-a-location"></a><span data-ttu-id="5b302-105">Modificar una ubicación</span><span class="sxs-lookup"><span data-stu-id="5b302-105">Editing a Location</span></span>  
 <span data-ttu-id="5b302-106">Al modificar una ubicación de un punto de interrupción, este se pasa a la nueva ubicación y se lleva con él todas las propiedades existentes, como el número de llamadas o la condición.</span><span class="sxs-lookup"><span data-stu-id="5b302-106">When you edit a breakpoint location, the breakpoint moves to the new location, carrying with it all of the existing properties, such as a hit count or condition.</span></span>  
  
#### <a name="to-edit-a-breakpoint-location"></a><span data-ttu-id="5b302-107">Para modificar la ubicación de un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="5b302-107">To Edit a Breakpoint Location</span></span>  
  
1.  <span data-ttu-id="5b302-108">En la ventana del editor, haga clic con el botón derecho en el glifo de punto de interrupción y, después, en el menú contextual, haga clic en **Ubicación** .</span><span class="sxs-lookup"><span data-stu-id="5b302-108">In the editor window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="5b302-109">O bien</span><span class="sxs-lookup"><span data-stu-id="5b302-109">-or-</span></span>  
  
     <span data-ttu-id="5b302-110">En la ventana **Puntos de interrupción** , haga clic con el botón derecho en el glifo de punto de interrupción y, después, en el menú contextual, haga clic en **Ubicación** .</span><span class="sxs-lookup"><span data-stu-id="5b302-110">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Location** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="5b302-111">En el cuadro de diálogo **Punto de interrupción de archivo** , modifique **Archivo** para especificar un nuevo archivo, **Línea** para especificar una nueva línea o **Carácter** para especificar una nueva ubicación dentro de la línea.</span><span class="sxs-lookup"><span data-stu-id="5b302-111">In the **File Breakpoint** dialog box, edit **File** to specify a new file, **Line** to specify a new line, or **Character** to specify a new location within the line.</span></span> <span data-ttu-id="5b302-112">Si el nuevo archivo que especifica ya está abierto en una ventana del editor de consultas, el punto de interrupción se mueve a esa ventana del editor.</span><span class="sxs-lookup"><span data-stu-id="5b302-112">If the new file you specify is already open in a query editor window, the breakpoint is moved to that editor window.</span></span> <span data-ttu-id="5b302-113">Si el archivo no se abre, se abre una nueva ventana del editor, el archivo se carga y el punto de interrupción se mueve a la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="5b302-113">If the file is not opened, a new editor window is opened, the file is loaded in, and the breakpoint moved to the new location.</span></span>  
  
     <span data-ttu-id="5b302-114">La opción para **Permitir que el código fuente sea diferente al de la versión original** no tiene ningún efecto al depurar [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b302-114">The **Allow the source code to be different from the original version** option has no effect when debugging [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b302-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b302-115">See Also</span></span>  
 <span data-ttu-id="5b302-116">[Especificar un número de llamadas](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="5b302-116">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 <span data-ttu-id="5b302-117">[Especificar una acción de punto de interrupción](specify-a-breakpoint-action.md) </span><span class="sxs-lookup"><span data-stu-id="5b302-117">[Specify a Breakpoint Action](specify-a-breakpoint-action.md) </span></span>  
 <span data-ttu-id="5b302-118">[Especificar una condición de punto de interrupción](specify-a-breakpoint-condition.md) </span><span class="sxs-lookup"><span data-stu-id="5b302-118">[Specify a Breakpoint Condition](specify-a-breakpoint-condition.md) </span></span>  
 [<span data-ttu-id="5b302-119">Especificar un filtro del punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="5b302-119">Specify a Breakpoint Filter</span></span>](specify-a-breakpoint-filter.md)  
