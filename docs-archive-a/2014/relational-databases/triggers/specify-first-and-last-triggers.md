---
title: Especificar el primer y el último desencadenador | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- first triggers [SQL Server]
- last triggers
- DML triggers, first or last triggers
- INSTEAD OF triggers
- AFTER triggers
ms.assetid: 9e6c7684-3dd3-46bb-b7be-523b33fae4d5
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ddb352b00dc759362c8f6ef1e861e55b6f184f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676909"
---
# <a name="specify-first-and-last-triggers"></a><span data-ttu-id="f0567-102">Especificar el primer y el último desencadenador</span><span class="sxs-lookup"><span data-stu-id="f0567-102">Specify First and Last Triggers</span></span>
  <span data-ttu-id="f0567-103">Puede especificar que uno de los desencadenadores AFTER asociados a una tabla sea el primero o el último que se ejecute para cada una de las acciones desencadenadoras INSERT, DELETE y UPDATE.</span><span class="sxs-lookup"><span data-stu-id="f0567-103">You can specify that one of the AFTER triggers associated with a table be either the first AFTER trigger or the last AFTER trigger that is fired for each INSERT, DELETE, and UPDATE triggering actions.</span></span> <span data-ttu-id="f0567-104">Los desencadenadores AFTER que se activan entre el primero y el último se ejecutan en un orden indefinido.</span><span class="sxs-lookup"><span data-stu-id="f0567-104">The AFTER triggers that are fired between the first and last triggers are executed in undefined order.</span></span>  
  
 <span data-ttu-id="f0567-105">Para especificar el orden de un desencadenador AFTER, use el procedimiento almacenado **sp_settriggerorder** .</span><span class="sxs-lookup"><span data-stu-id="f0567-105">To specify the order for an AFTER trigger, use the **sp_settriggerorder** stored procedure.</span></span> <span data-ttu-id="f0567-106">**sp_settriggerorder** tiene las opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="f0567-106">**sp_settriggerorder** has the following options.</span></span>  
  
|<span data-ttu-id="f0567-107">Opción</span><span class="sxs-lookup"><span data-stu-id="f0567-107">Option</span></span>|<span data-ttu-id="f0567-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0567-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f0567-109">**Primero**</span><span class="sxs-lookup"><span data-stu-id="f0567-109">**First**</span></span>|<span data-ttu-id="f0567-110">Especifica que el desencadenador DML es el primer desencadenador AFTER que se activa para una acción desencadenadora.</span><span class="sxs-lookup"><span data-stu-id="f0567-110">Specifies that the DML trigger is the first AFTER trigger fired for a triggering action.</span></span>|  
|<span data-ttu-id="f0567-111">**Último**</span><span class="sxs-lookup"><span data-stu-id="f0567-111">**Last**</span></span>|<span data-ttu-id="f0567-112">Especifica que el desencadenador DML es el último desencadenador AFTER que se activa para una acción desencadenadora.</span><span class="sxs-lookup"><span data-stu-id="f0567-112">Specifies that the DML trigger is the last AFTER trigger fired for a triggering action.</span></span>|  
|<span data-ttu-id="f0567-113">**None**</span><span class="sxs-lookup"><span data-stu-id="f0567-113">**None**</span></span>|<span data-ttu-id="f0567-114">Especifica que no hay ningún orden determinado para la activación del desencadenador DML.</span><span class="sxs-lookup"><span data-stu-id="f0567-114">Specifies that there is no specific order in which the DML trigger should be fired.</span></span> <span data-ttu-id="f0567-115">Se utiliza principalmente para restablecer un desencadenador que era el primero o el último.</span><span class="sxs-lookup"><span data-stu-id="f0567-115">Used mainly to reset a trigger from being either first or last.</span></span>|  
  
 <span data-ttu-id="f0567-116">En el siguiente ejemplo se muestra el uso de **sp_settriggerorder**:</span><span class="sxs-lookup"><span data-stu-id="f0567-116">The following example shows using **sp_settriggerorder**:</span></span>  
  
```  
sp_settriggerorder @triggername = 'MyTrigger', @order = 'first', @stmttype = 'UPDATE'  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f0567-117">Los desencadenadores primero y último deben ser dos desencadenadores DML diferentes.</span><span class="sxs-lookup"><span data-stu-id="f0567-117">The first and last triggers must be two different DML triggers.</span></span>  
  
 <span data-ttu-id="f0567-118">Una tabla puede tener los desencadenadores INSERT, UPDATE y DELETE definidos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f0567-118">A table can have INSERT, UPDATE, and DELETE triggers defined on it at the same time.</span></span> <span data-ttu-id="f0567-119">Cada tipo de instrucción puede tener sus propios desencadenadores primero y último, pero no pueden ser los mismos.</span><span class="sxs-lookup"><span data-stu-id="f0567-119">Each statement type can have its own first and last triggers, but they cannot be the same triggers.</span></span>  
  
 <span data-ttu-id="f0567-120">Si el primer o último desencadenador definido para una tabla no cubre una acción desencadenadora, como FOR UPDATE, FOR DELETE o FOR INSERT, no habrá desencadenadores primero ni último para las acciones que falten.</span><span class="sxs-lookup"><span data-stu-id="f0567-120">If the first or last trigger defined for a table does not cover a triggering action, such as not covering FOR UPDATE, FOR DELETE, or FOR INSERT, there is no first or last trigger for the missing actions.</span></span>  
  
 <span data-ttu-id="f0567-121">No se pueden especificar desencadenadores INSTEAD OF como primero ni último desencadenador.</span><span class="sxs-lookup"><span data-stu-id="f0567-121">INSTEAD OF triggers cannot be specified as first or last triggers.</span></span> <span data-ttu-id="f0567-122">Los desencadenadores INSTEAD OF se activan antes de actualizar las tablas subyacentes.</span><span class="sxs-lookup"><span data-stu-id="f0567-122">INSTEAD OF triggers are fired before updates are made to the underlying tables.</span></span> <span data-ttu-id="f0567-123">Si un desencadenador INSTEAD OF realiza actualizaciones en las tablas subyacentes, éstas se realizarán después de que se activen los desencadenadores AFTER definidos en la tabla.</span><span class="sxs-lookup"><span data-stu-id="f0567-123">If updates are made by an INSTEAD OF trigger to underlying tables, the updates occur before any AFTER triggers defined on the table are fired.</span></span> <span data-ttu-id="f0567-124">Por ejemplo, si un desencadenador INSTEAD OF INSERT de una vista inserta datos en una tabla base y ésta contiene un desencadenador INSTEAD OF INSERT y tres desencadenadores AFTER INSERT, se activará el desencadenador INSTEAD OF INSERT de la tabla base en lugar de la acción de inserción, y los desencadenadores AFTER de la tabla base se activarán después de cualquier acción de inserción de la tabla base.</span><span class="sxs-lookup"><span data-stu-id="f0567-124">For example, if an INSTEAD OF INSERT trigger on a view inserts data into a base table and the base table itself contains an INSTEAD OF INSERT trigger and three AFTER INSERT triggers, the INSTEAD OF INSERT trigger on the base table is fired instead of the inserting action, and the AFTER triggers on the base table are fired after any inserting action on the base table.</span></span> <span data-ttu-id="f0567-125">Para más información, consulte [DML Triggers](dml-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="f0567-125">For more information, see [DML Triggers](dml-triggers.md).</span></span>  
  
 <span data-ttu-id="f0567-126">Si una instrucción ALTER TRIGGER cambia un desencadenador primero o último, se quitará el atributo **First** o **Last** y el valor de orden se establecerá como **None**.</span><span class="sxs-lookup"><span data-stu-id="f0567-126">If an ALTER TRIGGER statement changes a first or last trigger, the **First** or **Last** attribute is dropped and the order value is set to **None**.</span></span> <span data-ttu-id="f0567-127">Para restablecer el orden, se debe usar **sp_settriggerorder**.</span><span class="sxs-lookup"><span data-stu-id="f0567-127">The order must be reset by using **sp_settriggerorder**.</span></span>  
  
 <span data-ttu-id="f0567-128">La función OBJECTPROPERTY informa acerca de si un desencadenador es primero o último mediante las propiedades **ExecIsFirstTrigger** y **ExecIsLastTrigger**.</span><span class="sxs-lookup"><span data-stu-id="f0567-128">The OBJECTPROPERTY function reports whether a trigger is a first or last trigger by using the properties **ExecIsFirstTrigger** and **ExecIsLastTrigger**.</span></span>  
  
 <span data-ttu-id="f0567-129">La replicación genera automáticamente un primer desencadenador para cualquier tabla incluida en una suscripción de actualización inmediata o en cola.</span><span class="sxs-lookup"><span data-stu-id="f0567-129">Replication automatically generates a first trigger for any table that is included in an immediate updating or queued updating subscription.</span></span> <span data-ttu-id="f0567-130">La replicación requiere que su desencadenador sea el primero.</span><span class="sxs-lookup"><span data-stu-id="f0567-130">Replication requires that its trigger be the first trigger.</span></span> <span data-ttu-id="f0567-131">Generará un error si se intenta incluir una tabla con un primer desencadenador en una suscripción de actualización inmediata o en cola.</span><span class="sxs-lookup"><span data-stu-id="f0567-131">Replication raises an error when you try to include a table with a first trigger in an immediate updating or queued updating subscription.</span></span> <span data-ttu-id="f0567-132">Si intenta convertir un desencadenador en el primero después de haber incluido una tabla en una suscripción, **sp_settriggerorder** devolverá un error.</span><span class="sxs-lookup"><span data-stu-id="f0567-132">If you try to make a trigger a first trigger after a table has been included in a subscription, **sp_settriggerorder** returns an error.</span></span> <span data-ttu-id="f0567-133">Tanto si usa ALTER en el desencadenador de replicación como si usa **sp_settriggerorder** para convertir el desencadenador de replicación en un desencadenador último o sin orden definido, la suscripción no funcionará correctamente.</span><span class="sxs-lookup"><span data-stu-id="f0567-133">If you use ALTER on the replication trigger or use **sp_settriggerorder** to change the replication trigger to a last or none trigger, the subscription will not function correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0567-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0567-134">See Also</span></span>  
 <span data-ttu-id="f0567-135">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f0567-135">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span></span>  
 [<span data-ttu-id="f0567-136">sp_settriggerorder &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f0567-136">sp_settriggerorder &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-settriggerorder-transact-sql)  
  
  
