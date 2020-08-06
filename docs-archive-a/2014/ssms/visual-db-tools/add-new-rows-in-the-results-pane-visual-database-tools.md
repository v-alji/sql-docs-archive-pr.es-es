---
title: Agregar nuevas filas en el panel Resultados (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- inserting rows
- Query Designer [SQL Server], Results pane
- Results pane
- adding rows
- row additions [SQL Server], Results pane
ms.assetid: 59891c84-3f54-4ab9-8b86-72c59627b480
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3137da106279e09305261c6c7cb7fd06d254b4fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670758"
---
# <a name="add-new-rows-in-the-results-pane-visual-database-tools"></a><span data-ttu-id="df0f0-102">Agregar nuevas filas en el panel Resultados (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="df0f0-102">Add New Rows in the Results Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="df0f0-103">Puede agregar datos nuevos escribiéndolos manualmente o pegándolos desde otro programa, como el Bloc de notas o Excel.</span><span class="sxs-lookup"><span data-stu-id="df0f0-103">You can add new data either by typing it in or by pasting it from another program such as Notepad or Excel.</span></span> <span data-ttu-id="df0f0-104">La fila que se vaya a pegar deberá tener exactamente el mismo número y tipos de columnas que la tabla en la que se pegue.</span><span class="sxs-lookup"><span data-stu-id="df0f0-104">A row to be pasted must have exactly the same number and types of columns as the table into which you are pasting.</span></span> <span data-ttu-id="df0f0-105">Puede pegar varias filas en el panel Resultados de una vez.</span><span class="sxs-lookup"><span data-stu-id="df0f0-105">You can paste multiple rows into the Results pane at once.</span></span>  
  
 <span data-ttu-id="df0f0-106">Para más información sobre cómo ingresar los datos, consulte [Reglas para actualizar resultados &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="df0f0-106">For information about how to enter data see [Rules for Updating Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
### <a name="to-add-a-new-data-row"></a><span data-ttu-id="df0f0-107">Para agregar una nueva fila de datos</span><span class="sxs-lookup"><span data-stu-id="df0f0-107">To add a new data row</span></span>  
  
1.  <span data-ttu-id="df0f0-108">Navegue a la parte inferior del panel Resultados, donde hay una fila en blanco disponible para agregar una nueva fila de datos.</span><span class="sxs-lookup"><span data-stu-id="df0f0-108">Navigate to the bottom of the Results pane, where a blank row is available for adding a new data row.</span></span>  
  
     <span data-ttu-id="df0f0-109">Los valores iniciales de todas las columnas serán *NULL*.</span><span class="sxs-lookup"><span data-stu-id="df0f0-109">The initial values for all columns will be *NULL*.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="df0f0-110">Para ir directamente a la primera fila vacía, utilice la barra de navegación situada en el parte inferior del panel Resultados.</span><span class="sxs-lookup"><span data-stu-id="df0f0-110">To go directly to the first empty row use the navigation bar at the bottom of the Results pane.</span></span>  
  
2.  <span data-ttu-id="df0f0-111">Si pega filas desde el Portapapeles, seleccione la nueva fila haciendo clic en el botón que está situado a la izquierda de la fila.</span><span class="sxs-lookup"><span data-stu-id="df0f0-111">If you are pasting rows from the Clipboard, select the new row by clicking the button to its left.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="df0f0-112">Si una o varias de las filas que va a pegar no se pueden confirmar en la base de datos, aparecerá un mensaje en el que se indicarán las filas que no se han podido confirmar.</span><span class="sxs-lookup"><span data-stu-id="df0f0-112">If one or more of the rows you're pasting can't be committed to the database you will receive a message telling you which row(s) couldn't be committed.</span></span>  
  
3.  <span data-ttu-id="df0f0-113">Escriba los datos de la nueva fila.</span><span class="sxs-lookup"><span data-stu-id="df0f0-113">Enter the data for the new row.</span></span> <span data-ttu-id="df0f0-114">Si va a pegar, elija **Pegar** en el menú **Editar** .</span><span class="sxs-lookup"><span data-stu-id="df0f0-114">If you are pasting, choose **Paste** from the **Edit** menu.</span></span>  
  
4.  <span data-ttu-id="df0f0-115">Deje esa fila para confirmarla en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="df0f0-115">Leave that row to commit it to the database.</span></span>  
  
 <span data-ttu-id="df0f0-116">Si al guardar la fila se produce un error, el Diseñador de consultas y vistas mostrará un mensaje y, a continuación, le devolverá a la fila que estaba editando.</span><span class="sxs-lookup"><span data-stu-id="df0f0-116">If an error occurs when you save the row the Query and View Designer displays a message and then returns you to the row you were editing.</span></span> <span data-ttu-id="df0f0-117">Seguidamente, puede:</span><span class="sxs-lookup"><span data-stu-id="df0f0-117">You can then:</span></span>  
  
-   <span data-ttu-id="df0f0-118">Resolver el error realizando modificaciones adicionales en la fila.</span><span class="sxs-lookup"><span data-stu-id="df0f0-118">Resolve the error by making further edits in the row.</span></span>  
  
-   <span data-ttu-id="df0f0-119">Cancelar la modificación presionando la tecla ESC.</span><span class="sxs-lookup"><span data-stu-id="df0f0-119">Cancel the edit by pressing ESC.</span></span> <span data-ttu-id="df0f0-120">Si presiona ESC cuando está en una celda que ha cambiado, se cancelan los cambios de esa celda.</span><span class="sxs-lookup"><span data-stu-id="df0f0-120">If you press ESC while in a cell that you changed, the changes for that cell are canceled.</span></span> <span data-ttu-id="df0f0-121">Si presiona ESC cuando está en una celda que no ha cambiado, se cancelan los cambios de toda la celda.</span><span class="sxs-lookup"><span data-stu-id="df0f0-121">If you press ESC while in a cell you have not changed, the changes for the entire row are canceled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df0f0-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df0f0-122">See Also</span></span>  
 <span data-ttu-id="df0f0-123">[Trabajar con datos en el panel resultados &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="df0f0-123">[Work with Data in the Results Pane &#40;Visual Database Tools&#41;](results-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="df0f0-124">Realizar operaciones básicas con consultas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="df0f0-124">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
