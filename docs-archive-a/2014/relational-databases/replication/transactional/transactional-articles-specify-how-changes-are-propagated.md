---
title: Especificar cómo se propagan los cambios para los artículos transaccionales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, propagation methods
ms.assetid: a10c5001-22cc-4667-8f0b-3d0818dca2e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72d377ba89f1d393eab48bd9c918012b0f503f9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745708"
---
# <a name="specify-how-changes-are-propagated-for-transactional-articles"></a><span data-ttu-id="a6cae-102">Especificar cómo se propagan los cambios para los artículos transaccionales</span><span class="sxs-lookup"><span data-stu-id="a6cae-102">Specify How Changes Are Propagated for Transactional Articles</span></span>
  <span data-ttu-id="a6cae-103">La replicación transaccional permite especificar cómo se propagan los cambios de datos del publicador a los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="a6cae-103">Transactional replication allows you to specify how data changes are propagated from the Publisher to Subscribers.</span></span> <span data-ttu-id="a6cae-104">Para cada tabla publicada, puede especificar uno de los cuatro métodos siguientes para propagar cada operación (INSERT, UPDATE o DELETE) al suscriptor:</span><span class="sxs-lookup"><span data-stu-id="a6cae-104">For each published table, you can specify one of four ways that each operation (INSERT, UPDATE, or DELETE) should be propagated to the Subscriber:</span></span>  
  
-   <span data-ttu-id="a6cae-105">Especifique que la replicación transaccional debe crear un script para un procedimiento almacenado y posteriormente, llamarlo para propagar los cambios a los suscriptores (la opción predeterminada).</span><span class="sxs-lookup"><span data-stu-id="a6cae-105">Specify that transactional replication should script out and subsequently call a stored procedure to propagate changes to Subscribers (the default).</span></span>  
  
-   <span data-ttu-id="a6cae-106">Especifique que el cambio debe propagarse utilizando una instrucción INSERT, UPDATE o DELETE (la opción predeterminada para los suscriptores que no son de[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="a6cae-106">Specify that the change should be propagated using an INSERT, UPDATE, or DELETE statement (the default for non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers).</span></span>  
  
-   <span data-ttu-id="a6cae-107">Especifique que debe utilizarse un procedimiento almacenado personalizado.</span><span class="sxs-lookup"><span data-stu-id="a6cae-107">Specify that a custom stored procedure should be used.</span></span>  
  
-   <span data-ttu-id="a6cae-108">Especifique que esta acción no debe realizarse en ningún suscriptor.</span><span class="sxs-lookup"><span data-stu-id="a6cae-108">Specify that this action should not be performed at any Subscriber.</span></span> <span data-ttu-id="a6cae-109">Las transacciones de este tipo no se replican.</span><span class="sxs-lookup"><span data-stu-id="a6cae-109">Transactions of that type are not replicated.</span></span>  
  
 <span data-ttu-id="a6cae-110">De forma predeterminada, la replicación transaccional propaga los cambios a los suscriptores a través de una serie de procedimientos almacenados que se instalan en cada suscriptor.</span><span class="sxs-lookup"><span data-stu-id="a6cae-110">By default, transactional replication propagates changes to Subscribers through a set of stored procedures that are installed on each Subscriber.</span></span> <span data-ttu-id="a6cae-111">Cuando se produce una inserción, una actualización o una eliminación en una tabla del publicador, la operación se convierte en una llamada a un procedimiento almacenado en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="a6cae-111">When an insert, update or delete occurs on a table at the Publisher, the operation is translated into a call to a stored procedure at the Subscriber.</span></span> <span data-ttu-id="a6cae-112">El procedimiento almacenado acepta parámetros que se asignan a las columnas de la tabla y permiten cambiar estas columnas en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="a6cae-112">The stored procedure accepts parameters that map to the columns in the table, allowing those columns to be changed at the Subscriber.</span></span>  
  
 <span data-ttu-id="a6cae-113">Para establecer el método de propagación para el cambio de datos en artículos transaccionales, vea [Establecer el método de propagación para cambios de datos en artículos transaccionales](../publish/set-the-propagation-method-for-data-changes-to-transactional-articles.md).</span><span class="sxs-lookup"><span data-stu-id="a6cae-113">To set the propagation method for data changes to transactional articles, see [Set the Propagation Method for Data Changes to Transactional Articles](../publish/set-the-propagation-method-for-data-changes-to-transactional-articles.md).</span></span>  
  
## <a name="default-and-custom-stored-procedures"></a><span data-ttu-id="a6cae-114">Procedimientos almacenados predeterminados y personalizados</span><span class="sxs-lookup"><span data-stu-id="a6cae-114">Default and custom stored procedures</span></span>  
 <span data-ttu-id="a6cae-115">Los tres procedimientos que crea la replicación de forma predeterminada en cada artículo de la tabla son:</span><span class="sxs-lookup"><span data-stu-id="a6cae-115">The three procedures that replication creates by default for each table article are:</span></span>  
  
-   <span data-ttu-id="a6cae-116">**sp_MSins_\<** *tablename* **>** , que controla las inserciones.</span><span class="sxs-lookup"><span data-stu-id="a6cae-116">**sp_MSins_\<** *tablename* **>**, which handles inserts.</span></span>  
  
-   <span data-ttu-id="a6cae-117">**sp_MSupd_\<** *tablename* **>** , que controla las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a6cae-117">**sp_MSupd_\<** *tablename* **>**, which handles updates.</span></span>  
  
-   <span data-ttu-id="a6cae-118">**sp_MSdel_\<** *tablename* **>** , que controla las eliminaciones.</span><span class="sxs-lookup"><span data-stu-id="a6cae-118">**sp_MSdel_\<** *tablename* **>**, which handles deletes.</span></span>  
  
 <span data-ttu-id="a6cae-119">El elemento **\<***tablename***>** empleado en el procedimiento depende de cómo se haya agregado el artículo a la publicación y de si la base de datos de suscripciones contiene una tabla del mismo nombre con un propietario distinto.</span><span class="sxs-lookup"><span data-stu-id="a6cae-119">The **\<***tablename***>** used in the procedure depends on how the article was added to the publication and whether the subscription database contains a table of the same name with a different owner.</span></span>  
  
 <span data-ttu-id="a6cae-120">Cualquiera de estos procedimientos se puede sustituir por un procedimiento personalizado que se especifica al agregar un artículo a una publicación.</span><span class="sxs-lookup"><span data-stu-id="a6cae-120">Any of these procedures can be replaced with a custom procedure that you specify when adding an article to a publication.</span></span> <span data-ttu-id="a6cae-121">Los procedimientos personalizados se utilizan si una aplicación requiere lógica personalizada, por ejemplo al insertar datos en una tabla de auditoría cuando se actualiza una fila en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="a6cae-121">Custom procedures are used if an application requires custom logic, such as inserting data into an audit table when a row is updated at a Subscriber.</span></span> <span data-ttu-id="a6cae-122">Para obtener más información acerca de cómo especificar procedimientos almacenados personalizados, vea los temas de procedimientos indicados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a6cae-122">For more information about specifying custom stored procedures, see the how to topics listed above.</span></span>  
  
 <span data-ttu-id="a6cae-123">Si especifica los procedimientos de replicación predeterminados o procedimientos personalizados, también debe especificar la sintaxis de llamada para cada procedimiento (la replicación selecciona los valores predeterminados si utiliza los procedimientos predeterminados).</span><span class="sxs-lookup"><span data-stu-id="a6cae-123">If you specify the default replication procedures or custom procedures, you also specify call syntax for each procedure (replication selects defaults if you use the default procedures).</span></span> <span data-ttu-id="a6cae-124">La sintaxis de llamada determina la estructura de los parámetros proporcionados al procedimiento y la cantidad de información que se envía al suscriptor con cada cambio de datos.</span><span class="sxs-lookup"><span data-stu-id="a6cae-124">The call syntax determines the structure of the parameters provided to the procedure and how much information is sent to the Subscriber with each data change.</span></span> <span data-ttu-id="a6cae-125">Para obtener más información, vea la sección "Sintaxis de llamada para procedimientos almacenados" en este tema.</span><span class="sxs-lookup"><span data-stu-id="a6cae-125">For more information, see the section "Call Syntax for Stored Procedures" in this topic.</span></span>  
  
### <a name="considerations-for-using-custom-stored-procedures"></a><span data-ttu-id="a6cae-126">Consideraciones para utilizar procedimientos almacenados personalizados</span><span class="sxs-lookup"><span data-stu-id="a6cae-126">Considerations for Using Custom Stored Procedures</span></span>  
 <span data-ttu-id="a6cae-127">Tenga en cuenta los siguientes aspectos cuando utilice procedimientos almacenados personalizados:</span><span class="sxs-lookup"><span data-stu-id="a6cae-127">Keep the following considerations in mind when using custom stored procedures:</span></span>  
  
-   <span data-ttu-id="a6cae-128">Debe proporcionar soporte para la lógica personalizada en el procedimiento almacenado; [!INCLUDE[msCoName](../../../includes/msconame-md.md)] no proporciona soporte para la lógica personalizada.</span><span class="sxs-lookup"><span data-stu-id="a6cae-128">You must support the logic in the stored procedure; [!INCLUDE[msCoName](../../../includes/msconame-md.md)] does not provide support for custom logic.</span></span>  
  
-   <span data-ttu-id="a6cae-129">Para evitar conflictos con las transacciones utilizadas en la replicación, no se deben utilizar transacciones explícitas en los procedimientos personalizados.</span><span class="sxs-lookup"><span data-stu-id="a6cae-129">In order to avoid conflicts with the transactions used by replication, explicit transactions should not be used in custom procedures.</span></span>  
  
-   <span data-ttu-id="a6cae-130">Por lo general, el esquema del suscriptor es idéntico al del publicador, pero también puede ser un subconjunto del esquema del publicador, si se utiliza el filtrado de columnas.</span><span class="sxs-lookup"><span data-stu-id="a6cae-130">The schema at the Subscriber is typically identical to the schema at the Publisher, but can also be a subset of the Publisher schema if column filtering is used.</span></span> <span data-ttu-id="a6cae-131">No obstante, si necesita transformar el esquema al mover los datos para que el esquema del suscriptor no sea un subconjunto del esquema del publicador, la solución recomendada es [!INCLUDE[ssISCurrent](../../../includes/ssiscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6cae-131">However, if you need to transform the schema as the data is moved such that the schema on the Subscriber is not a subset of the schema on the Publisher, [!INCLUDE[ssISCurrent](../../../includes/ssiscurrent-md.md)] is the recommended solution.</span></span> <span data-ttu-id="a6cae-132">Para más información, vea [SQL Server Integration Services](../../../integration-services/sql-server-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="a6cae-132">For more information, see [SQL Server Integration Services](../../../integration-services/sql-server-integration-services.md).</span></span>  
  
-   <span data-ttu-id="a6cae-133">Si realiza cambios de esquema en una tabla publicada, deberá volver a generar los procedimientos personalizados.</span><span class="sxs-lookup"><span data-stu-id="a6cae-133">If you make schema changes to a published table, the custom procedures must be regenerated.</span></span> <span data-ttu-id="a6cae-134">Para más información, vea [Volver a generar procedimientos transaccionales personalizados para reflejar cambios de esquema](transactional-articles-regenerate-to-reflect-schema-changes.md).</span><span class="sxs-lookup"><span data-stu-id="a6cae-134">For more information, see [Regenerate Custom Transactional Procedures to Reflect Schema Changes](transactional-articles-regenerate-to-reflect-schema-changes.md).</span></span>  
  
-   <span data-ttu-id="a6cae-135">Si usa un valor mayor que 1 para el parámetro **-SubscriptionStreams** del Agente de distribución, debe asegurarse de que las actualizaciones de las columnas de clave principal se lleven a cabo correctamente.</span><span class="sxs-lookup"><span data-stu-id="a6cae-135">If you use a value greater than 1 for **-SubscriptionStreams** parameter of the Distribution Agent, you must ensure that updates to primary key columns are successful.</span></span> <span data-ttu-id="a6cae-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a6cae-136">For example:</span></span>  
  
    ```  
    update ... set pk = 2 where pk = 1 -- update 1  
    update ... set pk = 3 where pk = 2 -- update 2  
    ```  
  
     <span data-ttu-id="a6cae-137">Si el Agente de distribución utiliza más de una conexión, estas dos actualizaciones podrían replicarse a través de conexiones distintas.</span><span class="sxs-lookup"><span data-stu-id="a6cae-137">If the Distribution Agent uses more than one connection, these two updates might be replicated over different connections.</span></span> <span data-ttu-id="a6cae-138">Si se aplica primero la actualización 1, no hay problema, pero si se aplica primero la actualización 2, el resultado será '0 filas afectadas', ya que aún no ha tenido lugar la actualización 1.</span><span class="sxs-lookup"><span data-stu-id="a6cae-138">If update 1 is applied first, there is no problem; if update 2 is applied first it will return '0 rows affected' because update 1 has not yet occurred.</span></span> <span data-ttu-id="a6cae-139">Los procedimientos predeterminados controlan esta situación generando un error si no hay ninguna fila afectada en una actualización:</span><span class="sxs-lookup"><span data-stu-id="a6cae-139">This situation is handled in the default procedures by raising an error if no rows are affected on an update:</span></span>  
  
    ```  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sys.sp_MSreplraiserror 20598  
    ```  
  
     <span data-ttu-id="a6cae-140">La generación del error obliga al Agente de distribución a volver a intentar la actualización a través de una sola conexión, lo cual se llevará a cabo correctamente.</span><span class="sxs-lookup"><span data-stu-id="a6cae-140">Raising the error forces the Distribution Agent to retry the updates over a single connection, which will succeed.</span></span> <span data-ttu-id="a6cae-141">Los procedimientos almacenados personalizados deben incluir una lógica similar.</span><span class="sxs-lookup"><span data-stu-id="a6cae-141">Custom stored procedures must include similar logic.</span></span>  
  
### <a name="call-syntax-for-stored-procedures"></a><span data-ttu-id="a6cae-142">Sintaxis de llamada para procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="a6cae-142">Call syntax for stored procedures</span></span>  
 <span data-ttu-id="a6cae-143">Hay cinco opciones para la sintaxis que se utiliza para llamar a los procedimientos empleados en la replicación transaccional:</span><span class="sxs-lookup"><span data-stu-id="a6cae-143">There are five options for the syntax used to call the procedures used by transactional replication:</span></span>  
  
-   <span data-ttu-id="a6cae-144">Sintaxis CALL</span><span class="sxs-lookup"><span data-stu-id="a6cae-144">CALL syntax.</span></span> <span data-ttu-id="a6cae-145">Se puede utilizar para inserciones, actualizaciones y eliminaciones.</span><span class="sxs-lookup"><span data-stu-id="a6cae-145">Can be used for inserts, updates, and deletes.</span></span> <span data-ttu-id="a6cae-146">De forma predeterminada, la replicación utiliza esta sintaxis para las inserciones y las eliminaciones.</span><span class="sxs-lookup"><span data-stu-id="a6cae-146">By default, replication uses this syntax for inserts and deletes.</span></span>  
  
-   <span data-ttu-id="a6cae-147">Sintaxis SCALL.</span><span class="sxs-lookup"><span data-stu-id="a6cae-147">SCALL syntax.</span></span> <span data-ttu-id="a6cae-148">Solo se puede utilizar para las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a6cae-148">Can be used for updates only.</span></span> <span data-ttu-id="a6cae-149">De forma predeterminada, la replicación utiliza esta sintaxis para las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a6cae-149">By default, replication uses this syntax for updates.</span></span>  
  
-   <span data-ttu-id="a6cae-150">Sintaxis MCALL</span><span class="sxs-lookup"><span data-stu-id="a6cae-150">MCALL syntax.</span></span> <span data-ttu-id="a6cae-151">Solo se puede utilizar para las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a6cae-151">Can be used for updates only.</span></span>  
  
-   <span data-ttu-id="a6cae-152">Sintaxis XCALL</span><span class="sxs-lookup"><span data-stu-id="a6cae-152">XCALL syntax.</span></span> <span data-ttu-id="a6cae-153">Se puede utilizar para actualizaciones y eliminaciones.</span><span class="sxs-lookup"><span data-stu-id="a6cae-153">Can be used for updates and deletes.</span></span>  
  
-   <span data-ttu-id="a6cae-154">VCALL.</span><span class="sxs-lookup"><span data-stu-id="a6cae-154">VCALL.</span></span> <span data-ttu-id="a6cae-155">Se utiliza para las suscripciones actualizables.</span><span class="sxs-lookup"><span data-stu-id="a6cae-155">Used for updatable subscriptions.</span></span> <span data-ttu-id="a6cae-156">Exclusivamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="a6cae-156">Internal use only.</span></span>  
  
 <span data-ttu-id="a6cae-157">Cada método difiere en la cantidad de datos propagados al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="a6cae-157">Each method differs in the amount of data that is propagated to the Subscriber.</span></span> <span data-ttu-id="a6cae-158">Por ejemplo, SCALL solo pasa valores para las columnas que resultan afectadas por una actualización.</span><span class="sxs-lookup"><span data-stu-id="a6cae-158">For example, SCALL passes in values only for the columns that are actually affected by an update.</span></span> <span data-ttu-id="a6cae-159">En cambio, XCALL utiliza todas las columnas (hayan sido afectadas o no por la actualización) y todos los valores de datos antiguos para cada columna.</span><span class="sxs-lookup"><span data-stu-id="a6cae-159">XCALL, by contrast, requires all columns (whether affected by an update or not) and all the old data values for each column.</span></span> <span data-ttu-id="a6cae-160">En muchos casos, SCALL es apropiado para las actualizaciones, pero si su aplicación necesita todos los valores de datos durante una actualización, XCALL permite utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="a6cae-160">In many cases, SCALL is appropriate for updates, but if your application requires all the data values during an update, XCALL allows for this.</span></span>  
  
#### <a name="call-syntax"></a><span data-ttu-id="a6cae-161">Sintaxis CALL</span><span class="sxs-lookup"><span data-stu-id="a6cae-161">CALL Syntax</span></span>  
 <span data-ttu-id="a6cae-162">Procedimientos almacenados INSERT</span><span class="sxs-lookup"><span data-stu-id="a6cae-162">INSERT stored procedures</span></span>  
 <span data-ttu-id="a6cae-163">Los procedimientos almacenados que controlan instrucciones INSERT recibirán los valores insertados de todas las columnas:</span><span class="sxs-lookup"><span data-stu-id="a6cae-163">Stored procedures handling INSERT statements will be passed the inserted values for all columns:</span></span>  
  
```  
c1, c2, c3,... cn  
```  
  
 <span data-ttu-id="a6cae-164">Procedimientos almacenados UPDATE</span><span class="sxs-lookup"><span data-stu-id="a6cae-164">UPDATE stored procedures</span></span>  
 <span data-ttu-id="a6cae-165">Los procedimientos almacenados que controlan instrucciones UPDATE recibirán los valores actualizados de todas las columnas definidas en el artículo, seguidas de los valores originales de las columnas de clave principal (no se intenta determinar qué columnas se modificaron):</span><span class="sxs-lookup"><span data-stu-id="a6cae-165">Stored procedures handling UPDATE statements will be passed the updated values for all columns defined in the article, followed by the original values for the primary key columns (no attempt is made to determine which columns were changed.):</span></span>  
  
```  
c1, c2, c3,... cn, pkc1, pkc2, pkc3,... pkcn  
```  
  
 <span data-ttu-id="a6cae-166">Procedimientos almacenados DELETE</span><span class="sxs-lookup"><span data-stu-id="a6cae-166">DELETE stored procedures</span></span>  
 <span data-ttu-id="a6cae-167">Los procedimientos almacenados que controlan instrucciones DELETE recibirán valores de las columnas de clave principal:</span><span class="sxs-lookup"><span data-stu-id="a6cae-167">Stored procedures handling DELETE statements will be passed values for the primary key columns:</span></span>  
  
```  
pkc1, pkc2, pkc3,... pkcn  
```  
  
#### <a name="scall-syntax"></a><span data-ttu-id="a6cae-168">Sintaxis SCALL</span><span class="sxs-lookup"><span data-stu-id="a6cae-168">SCALL Syntax</span></span>  
 <span data-ttu-id="a6cae-169">Procedimientos almacenados UPDATE</span><span class="sxs-lookup"><span data-stu-id="a6cae-169">UPDATE stored procedures</span></span>  
 <span data-ttu-id="a6cae-170">Los procedimientos almacenados que controlan instrucciones UPDATE solo recibirán los valores actualizados de las columnas que hayan cambiado, seguidos de los valores originales de las columnas de clave principal y de un parámetro de máscara de bits (`binary(n)`) que indica las columnas que han cambiado:</span><span class="sxs-lookup"><span data-stu-id="a6cae-170">Stored procedures handling UPDATE statements will be passed the updated values only for those columns that have changed, followed by the original values for the primary key columns, followed by a bitmask (`binary(n)`) parameter that indicates the changed columns.</span></span> <span data-ttu-id="a6cae-171">En el siguiente ejemplo, la columna 2 (c2) no ha cambiado:</span><span class="sxs-lookup"><span data-stu-id="a6cae-171">In the following example, column 2 (c2) has not changed:</span></span>  
  
```  
c1, , c3,... cn, pkc1, pkc2, pkc3,... pkcn, bitmask  
```  
  
#### <a name="mcall-syntax"></a><span data-ttu-id="a6cae-172">Sintaxis MCALL</span><span class="sxs-lookup"><span data-stu-id="a6cae-172">MCALL Syntax</span></span>  
 <span data-ttu-id="a6cae-173">Procedimientos almacenados UPDATE</span><span class="sxs-lookup"><span data-stu-id="a6cae-173">UPDATE stored procedures</span></span>  
 <span data-ttu-id="a6cae-174">Los procedimientos almacenados que controlan instrucciones UPDATE recibirán los valores actualizados de todas las columnas definidas en el artículo, seguidos de los valores originales de las columnas de clave principal y de un parámetro de máscara de bits (`binary(n)`) que indica las columnas que han cambiado:</span><span class="sxs-lookup"><span data-stu-id="a6cae-174">Stored procedures handling UPDATE statements will be passed the updated values for all columns defined in the article, followed by the original values for the primary key columns, followed by a bitmask (`binary(n)`) parameter that indicates the changed columns:</span></span>  
  
```  
c1, c2, c3,... cn, pkc1, pkc2, pkc3,... pkcn, bitmask  
```  
  
#### <a name="xcall-syntax"></a><span data-ttu-id="a6cae-175">Sintaxis XCALL</span><span class="sxs-lookup"><span data-stu-id="a6cae-175">XCALL Syntax</span></span>  
 <span data-ttu-id="a6cae-176">Procedimientos almacenados UPDATE</span><span class="sxs-lookup"><span data-stu-id="a6cae-176">UPDATE stored procedures</span></span>  
 <span data-ttu-id="a6cae-177">Los procedimientos almacenados que controlan instrucciones UPDATE recibirán los valores originales (es decir, la imagen anterior) de todas las columnas definidas en el artículo, seguidos de los valores actualizados (la imagen posterior) de todas las columnas definidas en el artículo.</span><span class="sxs-lookup"><span data-stu-id="a6cae-177">Stored procedures handling UPDATE statements will be passed the original values (the before image) for all columns defined in the article, followed by the updated values (the after image) for all columns defined in the article:</span></span>  
  
```  
old-c1, old-c2, old-c3,... old-cn, c1, c2, c3,... cn,  
```  
  
 <span data-ttu-id="a6cae-178">Procedimientos almacenados DELETE</span><span class="sxs-lookup"><span data-stu-id="a6cae-178">DELETE stored procedures</span></span>  
 <span data-ttu-id="a6cae-179">Los procedimientos almacenados que controlan instrucciones UPDATE recibirán los valores originales (es decir, la imagen anterior) de todas las columnas definidas en el artículo.</span><span class="sxs-lookup"><span data-stu-id="a6cae-179">Stored procedures handling DELETE statements will be passed the original (the before image) values for all columns defined in the article:</span></span>  
  
```  
old-c1, old-c2, old-c3,... old-cn  
```  
  
> [!NOTE]  
>  <span data-ttu-id="a6cae-180">Al utilizar XCALL, se espera que los valores de imagen anterior de las columnas **text** e **image** sean NULL.</span><span class="sxs-lookup"><span data-stu-id="a6cae-180">When using XCALL, the before image values for **text** and **image** columns are expected to be NULL.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a6cae-181">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a6cae-181">Examples</span></span>  
 <span data-ttu-id="a6cae-182">A continuación se indican los procedimientos predeterminados creados por la `Vendor Table` en la base de datos de ejemplo de [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6cae-182">The following procedures are the default procedures created for the `Vendor Table` in the [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] sample database.</span></span>  
  
```  
--INSERT procedure using CALL syntax  
create procedure [sp_MSins_PurchasingVendor]   
  @c1 int,@c2 nvarchar(15),@c3 nvarchar(50),@c4 tinyint,@c5 bit,@c6 bit,@c7 nvarchar(1024),@c8 datetime  
as   
begin   
insert into [Purchasing].[Vendor]([VendorID]  
,[AccountNumber]  
,[Name]  
,[CreditRating]  
,[PreferredVendorStatus]  
,[ActiveFlag]  
,[PurchasingWebServiceURL]  
,[ModifiedDate])  
values (   
 @c1  
,@c2  
,@c3  
,@c4  
,@c5  
,@c6  
,@c7  
,@c8  
 )   
end  
go  
  
--UPDATE procedure using SCALL syntax  
create procedure [sp_MSupd_PurchasingVendor]   
 @c1 int = null,@c2 nvarchar(15) = null,@c3 nvarchar(50) = null,@c4 tinyint = null,@c5 bit = null,@c6 bit = null,@c7 nvarchar(1024) = null,@c8 datetime = null,@pkc1 int  
,@bitmap binary(2)  
as  
begin  
update [Purchasing].[Vendor] set   
 [AccountNumber] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [AccountNumber] end  
,[Name] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [Name] end  
,[CreditRating] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [CreditRating] end  
,[PreferredVendorStatus] = case substring(@bitmap,1,1) & 16 when 16 then @c5 else [PreferredVendorStatus] end  
,[ActiveFlag] = case substring(@bitmap,1,1) & 32 when 32 then @c6 else [ActiveFlag] end  
,[PurchasingWebServiceURL] = case substring(@bitmap,1,1) & 64 when 64 then @c7 else [PurchasingWebServiceURL] end  
,[ModifiedDate] = case substring(@bitmap,1,1) & 128 when 128 then @c8 else [ModifiedDate] end  
where [VendorID] = @pkc1  
if @@rowcount = 0  
    if @@microsoftversion>0x07320000  
        exec sp_MSreplraiserror 20598  
end  
go  
  
--DELETE procedure using CALL syntax  
create procedure [sp_MSdel_PurchasingVendor]   
  @pkc1 int  
as   
begin   
delete [Purchasing].[Vendor]  
where [VendorID] = @pkc1  
if @@rowcount = 0  
    if @@microsoftversion>0x07320000  
        exec sp_MSreplraiserror 20598  
end   
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6cae-183">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6cae-183">See Also</span></span>  
 [<span data-ttu-id="a6cae-184">Article Options for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="a6cae-184">Article Options for Transactional Replication</span></span>](article-options-for-transactional-replication.md)  
  
  
