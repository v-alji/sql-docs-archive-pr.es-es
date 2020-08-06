---
title: Reconciliar los cambios realizados por varios usuarios (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- table modifications [SQL Server], multiple users
- reconciling changes made by multiple users
- modifications made by multiple users
ms.assetid: fc7ed4f2-ad3d-47fc-a3ef-51e5bb069ef0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 337d505fce474a33301c18313fe6137f6bc0ec1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744944"
---
# <a name="reconcile-changes-made-by-multiple-users-visual-database-tools"></a><span data-ttu-id="d1df3-102">Reconciliar los cambios realizados por varios usuarios (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d1df3-102">Reconcile Changes Made by Multiple Users (Visual Database Tools)</span></span>
  <span data-ttu-id="d1df3-103">En un entorno multiusuario, varios usuarios pueden realizar cambios en el mismo objeto al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d1df3-103">In a multiuser environment, changes can be made on the same object by multiple users at once.</span></span> <span data-ttu-id="d1df3-104">Esto puede ocurrir cuando se trabaja en la estructura del objeto en los diseñadores de diagramas de base de datos o tablas, o con los valores de los resultados que devuelve el panel Resultados del Diseñador de consultas y vistas.</span><span class="sxs-lookup"><span data-stu-id="d1df3-104">This can happen when you're working on the structure of the object in the Table or Database Diagram designers or it can happen to values in the results returned in the Query and View designer's Results pane.</span></span> <span data-ttu-id="d1df3-105">Esto puede ocasionar conflictos que es necesario solucionar.</span><span class="sxs-lookup"><span data-stu-id="d1df3-105">This can cause conflicts that you'll want to resolve.</span></span>  
  
## <a name="conflicts-in-the-table-or-database-diagram-designers"></a><span data-ttu-id="d1df3-106">Conflictos en los diseñadores de diagramas de base de datos o tablas</span><span class="sxs-lookup"><span data-stu-id="d1df3-106">Conflicts in the Table or Database Diagram Designers</span></span>  
 <span data-ttu-id="d1df3-107">Por ejemplo, otro usuario podría eliminar o cambiar el nombre de una tabla mientras está trabajando con esa tabla o con una tabla relacionada en el Diseñador de tablas.</span><span class="sxs-lookup"><span data-stu-id="d1df3-107">For example, another user might delete or rename a table while you are working with the same or a related table in Table Designer.</span></span> <span data-ttu-id="d1df3-108">Al intentar guardar la tabla, el [Cuadro de diálogo Se han detectado cambios en la base de datos &#40;Visual Database Tools&#41;](visual-database-tools.md) le informará que la base de datos se actualizó desde que se abrió la tabla.</span><span class="sxs-lookup"><span data-stu-id="d1df3-108">When you attempt to save your table, the [Database Changes Detected Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) notifies you that the database has been updated since you opened the table.</span></span>  
  
 <span data-ttu-id="d1df3-109">Este cuadro de diálogo también muestra una lista de objetos de base de datos que se verán afectados como resultado de guardar la tabla.</span><span class="sxs-lookup"><span data-stu-id="d1df3-109">This dialog box also displays a list of database objects that will be affected as a result of saving your table.</span></span> <span data-ttu-id="d1df3-110">En este momento, puede realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="d1df3-110">At this point, you can take one of these actions:</span></span>  
  
-   <span data-ttu-id="d1df3-111">Elija **Sí** para guardar la tabla y actualizar la base de datos con todos los cambios de la lista.</span><span class="sxs-lookup"><span data-stu-id="d1df3-111">Choose **Yes** to save your table and update the database with all the changes in the list.</span></span>  
  
     <span data-ttu-id="d1df3-112">Esta acción puede afectar a las tablas que comparten los mismos objetos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1df3-112">This action could affect tables that share the same database objects.</span></span> <span data-ttu-id="d1df3-113">Por ejemplo, supongamos que edita la columna `au`_`id` de la tabla `titleauthors` mientras otro usuario trabaja con la tabla `authors` , que está relacionada con la tabla `titleauthors` mediante la columna `au`\_`id` .</span><span class="sxs-lookup"><span data-stu-id="d1df3-113">For example, suppose you edit the `au`_`id` column in the `titleauthors` table while another user is working on the `authors` table which is related to the `titleauthors` table by the `au`\_`id` column.</span></span> <span data-ttu-id="d1df3-114">Si guarda la tabla, se verá afectada la tabla del otro usuario.</span><span class="sxs-lookup"><span data-stu-id="d1df3-114">Saving your table will affect the other user's table.</span></span> <span data-ttu-id="d1df3-115">De igual manera, supongamos que otro usuario ha definido una restricción CHECK para la columna `qty` de la tabla `sales` .</span><span class="sxs-lookup"><span data-stu-id="d1df3-115">Similarly, suppose that another user defined a check constraint for the `qty` column in the `sales` table.</span></span> <span data-ttu-id="d1df3-116">Si elimina la columna `qty` y guarda la tabla `sales` , la restricción CHECK del otro usuario se verá afectada.</span><span class="sxs-lookup"><span data-stu-id="d1df3-116">If you delete the `qty` column and save the `sales` table, the other user's check constraint will be affected.</span></span>  
  
-   <span data-ttu-id="d1df3-117">Elija **No** para cancelar la acción de guardar.</span><span class="sxs-lookup"><span data-stu-id="d1df3-117">Choose **No** to cancel the save action.</span></span>  
  
     <span data-ttu-id="d1df3-118">A continuación, puede cerrar la tabla sin guardarla.</span><span class="sxs-lookup"><span data-stu-id="d1df3-118">You can then close the table without saving it.</span></span> <span data-ttu-id="d1df3-119">Cuando vuelva a abrir la tabla, coincidirá con el contenido de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1df3-119">When you reopen the table it will match what is in the database.</span></span>  
  
-   <span data-ttu-id="d1df3-120">Elija **Guardar archivo de texto** para guardar una lista de los cambios.</span><span class="sxs-lookup"><span data-stu-id="d1df3-120">Choose **Save Text File** to save a list of the changes.</span></span>  
  
     <span data-ttu-id="d1df3-121">Puede guardar la lista de los cambios de la base de datos que se muestran en el cuadro de diálogo **Se han detectado cambios en la base de datos** en un archivo de texto para poder investigar la causa de los cambios de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="d1df3-121">You can save the list of database changes shown in the **Database Changes Detected** dialog box to a text file so that you can investigate the cause of other users' changes.</span></span> <span data-ttu-id="d1df3-122">Por ejemplo, si otro usuario ha editado una tabla que usted marcó para eliminar, es posible que desee comprobar si debe eliminarse la tabla antes de actualizar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1df3-122">For example, if another user edited a table that you marked for deletion, you may want to research whether the table should be deleted before updating the database.</span></span>  
  
## <a name="conflicts-in-the-query-and-view-designer"></a><span data-ttu-id="d1df3-123">Conflictos en el Diseñador de consultas y vistas</span><span class="sxs-lookup"><span data-stu-id="d1df3-123">Conflicts in the Query and View Designer</span></span>  
 <span data-ttu-id="d1df3-124">Si ejecuta una consulta o devuelve los resultados de una vista, los datos se muestran en el [panel Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d1df3-124">If you run a query or return the results of a view, the data is shown in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="d1df3-125">Varios usuarios pueden trabajar en el mismo conjunto de datos al mismo tiempo, lo cual puede ocasionar conflictos.</span><span class="sxs-lookup"><span data-stu-id="d1df3-125">Multiple users can work on the same set of data at the same time, which can cause conflicts.</span></span>  
  
 <span data-ttu-id="d1df3-126">Por ejemplo, supongamos que usted y un colega ejecutan una consulta cada uno para mostrar todos los datos de la tabla `titleauthors` .</span><span class="sxs-lookup"><span data-stu-id="d1df3-126">For example, lets say you and a colleague each run a query to show all the data in the `titleauthors` table.</span></span> <span data-ttu-id="d1df3-127">Su colega cambia el nombre del primer registro devuelto de Barb a Barbara.</span><span class="sxs-lookup"><span data-stu-id="d1df3-127">Your colleague changes the first name in the first record returned from Barb to Barbara.</span></span> <span data-ttu-id="d1df3-128">En ese momento el valor que hay en ese campo de la base de datos es Barbara, aunque en su conjunto de resultados siga apareciendo Barb.</span><span class="sxs-lookup"><span data-stu-id="d1df3-128">At this point the database has Barbara in that field, while your result set still shows Barb.</span></span> <span data-ttu-id="d1df3-129">A continuación, escribe Bárbara y hace clic fuera de de la fila.</span><span class="sxs-lookup"><span data-stu-id="d1df3-129">Now you type in Barbara and click off of the row.</span></span> <span data-ttu-id="d1df3-130">Recibirá un mensaje que le preguntará cómo desea solucionar el conflicto.</span><span class="sxs-lookup"><span data-stu-id="d1df3-130">You will receive a message asking you how you want to resolve the conflict.</span></span>  
  
-   <span data-ttu-id="d1df3-131">Haga clic en **Sí** para actualizar la base de datos con los cambios.</span><span class="sxs-lookup"><span data-stu-id="d1df3-131">Click **Yes** to update the database with your changes.</span></span>  
  
     <span data-ttu-id="d1df3-132">Con ello, se reemplazarán los cambios de su colega.</span><span class="sxs-lookup"><span data-stu-id="d1df3-132">This will override your colleague's changes.</span></span>  
  
-   <span data-ttu-id="d1df3-133">Haga clic en **No** para actualizar el conjunto de resultados de modo que coincida con lo que hay actualmente en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1df3-133">Click **No** to have your result set updated to what's currently in the database.</span></span>  
  
     <span data-ttu-id="d1df3-134">Con ello, se reemplazarán sus cambios por los de su colega.</span><span class="sxs-lookup"><span data-stu-id="d1df3-134">This will override your changes with those of your colleague's.</span></span>  
  
-   <span data-ttu-id="d1df3-135">Haga clic en **Cancelar** para continuar la edición sin solucionar el conflicto.</span><span class="sxs-lookup"><span data-stu-id="d1df3-135">Click **Cancel** to continue to edit without resolving the conflict.</span></span>  
  
     <span data-ttu-id="d1df3-136">En este caso, no podrá confirmar sus cambios en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d1df3-136">In this case you will not be able to commit your changes to the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1df3-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1df3-137">See Also</span></span>  
 [<span data-ttu-id="d1df3-138">Cuadro de diálogo Se han detectado cambios en la base de datos &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="d1df3-138">Database Changes Detected Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
