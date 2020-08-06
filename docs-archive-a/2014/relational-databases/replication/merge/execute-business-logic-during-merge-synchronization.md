---
title: Ejecutar lógica de negocios durante la sincronización de mezcla | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- custom error resolution [SQL Server replication]
- custom change handling [SQL Server replication]
- errors [SQL Server replication], business logic handlers
- merge replication business logic handlers [SQL Server replication]
- conflict resolution [SQL Server replication], merge replication
- business logic handlers [SQL Server replication]
ms.assetid: 9d4da2ef-c17f-4a31-a1f6-5c3b7ca85f71
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1e082cbbb46ceae712cd39925c28fe89988a3793
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661970"
---
# <a name="execute-business-logic-during-merge-synchronization"></a><span data-ttu-id="ab34a-102">Ejecutar lógica de negocios durante la sincronización de mezcla</span><span class="sxs-lookup"><span data-stu-id="ab34a-102">Execute Business Logic During Merge Synchronization</span></span>
  <span data-ttu-id="ab34a-103">El marco de trabajo de controladores de lógica de negocios permite escribir un ensamblado de código administrado al que se llama durante el proceso de sincronización de mezcla.</span><span class="sxs-lookup"><span data-stu-id="ab34a-103">The business logic handler framework allows you to write a managed code assembly that is called during the merge synchronization process.</span></span> <span data-ttu-id="ab34a-104">El ensamblado incluye lógica de negocios que puede responder a varias condiciones durante la sincronización: cambios de datos, conflictos y errores.</span><span class="sxs-lookup"><span data-stu-id="ab34a-104">The assembly includes business logic that can respond to a number of conditions during synchronization: data changes, conflicts, and errors.</span></span> <span data-ttu-id="ab34a-105">El marco de trabajo de controladores de lógica de negocios proporciona un modelo de programación simple y los datos que el proceso de mezcla suministra al ensamblado tienen el formato de un conjunto de datos ADO.NET, lo que permite aprovechar el conocimiento de ADO.NET en lugar de aprender el uso de una interfaz privada.</span><span class="sxs-lookup"><span data-stu-id="ab34a-105">The business logic handler framework provides a simple programming model, and the data that the merge process provides to your assembly is in the form of an ADO.NET data set, so you can leverage knowledge of ADO.NET rather than learning a proprietary interface.</span></span> <span data-ttu-id="ab34a-106">Para obtener más información acerca de los controladores de lógica de negocios de programación, vea:</span><span class="sxs-lookup"><span data-stu-id="ab34a-106">For more information on programming business logic handlers, see:</span></span>  
  
-   <span data-ttu-id="ab34a-107">Referencia de la interfaz de programación de aplicaciones (API): <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport></span><span class="sxs-lookup"><span data-stu-id="ab34a-107">The application programming interface (API) reference: <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport></span></span>  
  
-   <span data-ttu-id="ab34a-108">Instrucciones sobre cómo implementar un controlador de lógica de negocios: [Implement a Business Logic Handler for a Merge Article](../implement-a-business-logic-handler-for-a-merge-article.md) (Implementar un controlador de lógica de negocios para un artículo de mezcla)</span><span class="sxs-lookup"><span data-stu-id="ab34a-108">Instructions on how to implement a business logic handler: [Implement a Business Logic Handler for a Merge Article](../implement-a-business-logic-handler-for-a-merge-article.md)</span></span>  
  
## <a name="uses-for-business-logic-handlers"></a><span data-ttu-id="ab34a-109">Usos de los controladores de lógica de negocios</span><span class="sxs-lookup"><span data-stu-id="ab34a-109">Uses for Business Logic Handlers</span></span>  
 <span data-ttu-id="ab34a-110">El proceso de sincronización de mezcla puede invocar controladores de lógica de negocios para que lleven a cabo las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ab34a-110">The merge synchronization process can invoke business logic handlers to perform:</span></span>  
  
-   <span data-ttu-id="ab34a-111">Control personalizado de cambios</span><span class="sxs-lookup"><span data-stu-id="ab34a-111">Custom change handling</span></span>  
  
-   <span data-ttu-id="ab34a-112">Resolución personalizada de conflictos</span><span class="sxs-lookup"><span data-stu-id="ab34a-112">Custom conflict resolution</span></span>  
  
-   <span data-ttu-id="ab34a-113">Resolución personalizada de errores</span><span class="sxs-lookup"><span data-stu-id="ab34a-113">Custom error resolution</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ab34a-114">El controlador de lógica de negocios especificado se ejecuta para cada fila que se sincroniza.</span><span class="sxs-lookup"><span data-stu-id="ab34a-114">The business logic handler you specify is executed for every row that is synchronized.</span></span> <span data-ttu-id="ab34a-115">La lógica compleja y las llamadas a otras aplicaciones o servicios de red pueden afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ab34a-115">Complex logic and calls to other applications or network services can impact performance.</span></span>  
  
### <a name="custom-change-handling"></a><span data-ttu-id="ab34a-116">Control personalizado de cambios</span><span class="sxs-lookup"><span data-stu-id="ab34a-116">Custom Change Handling</span></span>  
 <span data-ttu-id="ab34a-117">Se puede invocar el controlador de lógica de negocios durante el procesamiento de cambios de datos que no produzcan conflictos y realizar una de estas tres acciones:</span><span class="sxs-lookup"><span data-stu-id="ab34a-117">The business logic handler can be invoked during the processing of non-conflicting data changes and can perform one of three actions:</span></span>  
  
-   <span data-ttu-id="ab34a-118">Rechazar los datos</span><span class="sxs-lookup"><span data-stu-id="ab34a-118">Reject the data</span></span>  
  
     <span data-ttu-id="ab34a-119">Esto resulta útil para aplicaciones que no desean propagar los datos a un suscriptor o de un suscriptor determinado.</span><span class="sxs-lookup"><span data-stu-id="ab34a-119">This is useful for applications that do not want changes propagated to or from a given Subscriber.</span></span> <span data-ttu-id="ab34a-120">Por ejemplo, un administrador puede filtrar las inserciones que no pertenezcan a la partición del suscriptor, o bien rechazar las eliminaciones realizadas en un suscriptor.</span><span class="sxs-lookup"><span data-stu-id="ab34a-120">For example, an administrator could filter out inserts that do not belong in the Subscriber's partition, or possibly reject deletes performed at a Subscriber.</span></span> <span data-ttu-id="ab34a-121">O bien, una aplicación podría rechazar un pedido realizado en un suscriptor debido a que el inventario ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="ab34a-121">As another example, an application could reject an order entered at a Subscriber because the inventory is no longer available.</span></span>  
  
-   <span data-ttu-id="ab34a-122">Aceptar los datos</span><span class="sxs-lookup"><span data-stu-id="ab34a-122">Accept the data</span></span>  
  
     <span data-ttu-id="ab34a-123">Esto es útil para aplicaciones en las que es necesario revisar los cambios de datos realizados en el publicador o en el suscriptor antes de permitir que se propaguen.</span><span class="sxs-lookup"><span data-stu-id="ab34a-123">This is useful for applications in which it is necessary to review data changes made at either the Publisher or Subscriber before allowing them to be propagated.</span></span> <span data-ttu-id="ab34a-124">Por ejemplo, una aplicación de nivel intermedio podría examinar los pedidos de campo nuevos e integrarlos con un proceso de flujo de trabajo de compras en dicho nivel.</span><span class="sxs-lookup"><span data-stu-id="ab34a-124">For example, a mid-tier application could examine new orders coming in from the field and integrate with a procurement workflow process in the mid-tier.</span></span>  
  
-   <span data-ttu-id="ab34a-125">Aplicar datos personalizados</span><span class="sxs-lookup"><span data-stu-id="ab34a-125">Apply custom data</span></span>  
  
     <span data-ttu-id="ab34a-126">Esto es útil para aplicaciones que deben suplantar operaciones o valores de datos específicos.</span><span class="sxs-lookup"><span data-stu-id="ab34a-126">This is useful for applications that need to override specific data values or operations.</span></span> <span data-ttu-id="ab34a-127">Por ejemplo, una aplicación podría transformar la eliminación de una fila en una actualización especial que establezca la columna **estado** de la fila en el valor "eliminado" y después realice un seguimiento de la identidad del cliente que lleva a cabo la eliminación.</span><span class="sxs-lookup"><span data-stu-id="ab34a-127">For example, an application could transform a row delete into a special update that sets a **status** column in the row to a value of "deleted" and then tracks the identity of the client performing the delete.</span></span> <span data-ttu-id="ab34a-128">Esto podría ser útil con fines de auditoría o flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ab34a-128">This might be useful for auditing or workflow purposes.</span></span>  
  
### <a name="custom-conflict-resolution"></a><span data-ttu-id="ab34a-129">Resolución personalizada de conflictos</span><span class="sxs-lookup"><span data-stu-id="ab34a-129">Custom Conflict Resolution</span></span>  
 <span data-ttu-id="ab34a-130">La replicación de mezcla permite la detección y resolución de conflictos, y permite al usuario aceptar una estrategia de resolución predeterminada o elegir la resolución personalizada de los conflictos.</span><span class="sxs-lookup"><span data-stu-id="ab34a-130">Merge replication provides conflict detection and resolution, allowing you to accept a default resolution strategy or choose custom resolution for conflicts.</span></span> <span data-ttu-id="ab34a-131">Para más información, consulte [Replicación de mezcla avanzada: detección y resolución de conflictos](advanced-merge-replication-conflict-detection-and-resolution.md).</span><span class="sxs-lookup"><span data-stu-id="ab34a-131">For more information, see [Advanced Merge Replication Conflict Detection and Resolution](advanced-merge-replication-conflict-detection-and-resolution.md).</span></span> <span data-ttu-id="ab34a-132">Se puede invocar el controlador de lógica de negocios durante el procesamiento de cambios de datos que produzcan conflictos y realizar una de estas dos acciones:</span><span class="sxs-lookup"><span data-stu-id="ab34a-132">The business logic handler can be invoked during the processing of conflicting data changes and can perform one of two actions:</span></span>  
  
-   <span data-ttu-id="ab34a-133">Aceptar la resolución predeterminada</span><span class="sxs-lookup"><span data-stu-id="ab34a-133">Accept default resolution</span></span>  
  
     <span data-ttu-id="ab34a-134">Esto es útil para aplicaciones que pueden necesitar revisar el conflicto, realizar otras acciones y, posiblemente, registrar un mensaje de conflicto personalizado.</span><span class="sxs-lookup"><span data-stu-id="ab34a-134">This is useful for applications that might need to review the conflict, perform additional actions, and possibly log a custom conflict log message.</span></span>  
  
-   <span data-ttu-id="ab34a-135">Realizar una resolución personalizada</span><span class="sxs-lookup"><span data-stu-id="ab34a-135">Perform custom resolution</span></span>  
  
     <span data-ttu-id="ab34a-136">Esto es útil para aplicaciones que pueden necesitar seleccionar valores de datos específicos para su lógica de negocios y suministrar este conjunto de datos personalizado al proceso de sincronización.</span><span class="sxs-lookup"><span data-stu-id="ab34a-136">This is useful for applications that might need to select data values that are specific to their business logic and supply the synchronization process with this custom dataset.</span></span> <span data-ttu-id="ab34a-137">Por ejemplo, una aplicación podría proporcionar una nueva versión de la fila ganadora combinando valores de los conjuntos de datos del publicador y el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="ab34a-137">For example, an application could provide a new version of the winning row by combining values from the Publisher and Subscriber data sets.</span></span>  
  
### <a name="custom-error-resolution"></a><span data-ttu-id="ab34a-138">Resolución personalizada de errores</span><span class="sxs-lookup"><span data-stu-id="ab34a-138">Custom Error Resolution</span></span>  
 <span data-ttu-id="ab34a-139">Se puede invocar la lógica personalizada durante la propagación de cambios que dan como resultado errores.</span><span class="sxs-lookup"><span data-stu-id="ab34a-139">Custom logic can be invoked during the propagation of changes that result in errors.</span></span> <span data-ttu-id="ab34a-140">La lógica puede realizar una de las dos acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ab34a-140">The logic can perform one of two actions:</span></span>  
  
-   <span data-ttu-id="ab34a-141">Aceptar la resolución predeterminada del error</span><span class="sxs-lookup"><span data-stu-id="ab34a-141">Accept default error resolution</span></span>  
  
     <span data-ttu-id="ab34a-142">Esto es útil para aplicaciones que pueden necesitar revisar el error, realizar otras acciones y, posiblemente, registrar un mensaje de error personalizado.</span><span class="sxs-lookup"><span data-stu-id="ab34a-142">This is useful for applications that might need to review the error and perform additional action and possibly log a custom error log message.</span></span>  
  
-   <span data-ttu-id="ab34a-143">Aceptar la resolución personalizada del error</span><span class="sxs-lookup"><span data-stu-id="ab34a-143">Accept custom error resolution</span></span>  
  
     <span data-ttu-id="ab34a-144">Esto es útil para aplicaciones que pueden necesitar seleccionar valores de datos específicos para su lógica de negocios y suministrar este conjunto de datos personalizado al proceso de sincronización.</span><span class="sxs-lookup"><span data-stu-id="ab34a-144">This is useful for applications that might need to select data values that are specific to their business logic and supply the synchronization process with this custom dataset.</span></span> <span data-ttu-id="ab34a-145">Por ejemplo, si el proceso de replicación detecta una infracción de clave duplicada, el controlador de lógica de negocios podría proporcionar una nueva versión del cambio de datos en la que la clave ya no entre en conflicto.</span><span class="sxs-lookup"><span data-stu-id="ab34a-145">For example, if the replication process encounters a duplicate key violation, the business logic handler could provide a new version of the data change in which the key will no longer conflict.</span></span> <span data-ttu-id="ab34a-146">Después, los cambios realizados en el publicador y el suscriptor pueden persistir en la base de datos y el proceso de replicación no tiene que compensar el error de inserción con una eliminación.</span><span class="sxs-lookup"><span data-stu-id="ab34a-146">Changes made at the Publisher and Subscriber can then persist in the database, and the replication process doesn't have to compensate for the failed insert with a delete.</span></span>  
  
## <a name="deployment-scenarios-for-business-logic-handlers"></a><span data-ttu-id="ab34a-147">Escenarios de implementación de controladores de lógica de negocios</span><span class="sxs-lookup"><span data-stu-id="ab34a-147">Deployment Scenarios for Business Logic Handlers</span></span>  
 <span data-ttu-id="ab34a-148">Los controladores de lógica de negocios se pueden implementar en:</span><span class="sxs-lookup"><span data-stu-id="ab34a-148">Business logic handlers can be deployed at:</span></span>  
  
-   <span data-ttu-id="ab34a-149">El distribuidor.</span><span class="sxs-lookup"><span data-stu-id="ab34a-149">The Distributor.</span></span> <span data-ttu-id="ab34a-150">Utilice una suscripción de inserción para que la lógica de negocios se ejecute en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="ab34a-150">Use a push subscription so that business logic is executed at the Distributor.</span></span>  
  
-   <span data-ttu-id="ab34a-151">El suscriptor.</span><span class="sxs-lookup"><span data-stu-id="ab34a-151">The Subscriber.</span></span> <span data-ttu-id="ab34a-152">Utilice una suscripción de extracción para que la lógica de negocios se ejecute en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="ab34a-152">Use a pull subscription so that business logic is executed at the Subscriber.</span></span>  
  
-   <span data-ttu-id="ab34a-153">Un servidor con Internet Information Services (IIS), si se utiliza la sincronización web.</span><span class="sxs-lookup"><span data-stu-id="ab34a-153">An Internet Information Services (IIS) server if Web synchronization is used.</span></span> <span data-ttu-id="ab34a-154">Utilice una suscripción de extracción sincronizada con la sincronización web y el controlador de lógica de negocios se ejecutará en el servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="ab34a-154">Use a pull subscription synchronized with Web synchronization, and the business logic handler will execute at the IIS Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab34a-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab34a-155">See Also</span></span>  
 <span data-ttu-id="ab34a-156">[Replicación de mezcla](merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="ab34a-156">[Merge Replication](merge-replication.md) </span></span>  
 <span data-ttu-id="ab34a-157">[Subscribe to Publications](../subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="ab34a-157">[Subscribe to Publications](../subscribe-to-publications.md) </span></span>  
 <span data-ttu-id="ab34a-158">[Sincronizar datos](../synchronize-data.md) </span><span class="sxs-lookup"><span data-stu-id="ab34a-158">[Synchronize Data](../synchronize-data.md) </span></span>  
 [<span data-ttu-id="ab34a-159">Sincronización web para la replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="ab34a-159">Web Synchronization for Merge Replication</span></span>](../web-synchronization-for-merge-replication.md)  
  
  
