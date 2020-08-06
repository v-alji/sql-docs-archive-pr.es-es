---
title: Replicación de tablas e índices con particiones | Microsoft Docs
ms.custom: ''
ms.date: 09/10/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- partitioned indexes [SQL Server], replicating
- partitioned tables [SQL Server], replicating
- replication [SQL Server], partitioned tables
- publishing [SQL Server replication], partitioned tables
- transactional replication, partitioned tables
ms.assetid: c9fa81b1-6c81-4c11-927b-fab16301a8f5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 616707bfb11b48b170fc8f0e8872076d2cd09d1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669593"
---
# <a name="replicate-partitioned-tables-and-indexes"></a><span data-ttu-id="1c372-102">Replicar tablas e índices con particiones</span><span class="sxs-lookup"><span data-stu-id="1c372-102">Replicate Partitioned Tables and Indexes</span></span>
  <span data-ttu-id="1c372-103">La creación de particiones facilita el uso de tablas o índices grandes, ya que permite administrar y tener acceso a subconjuntos de datos de forma rápida y eficaz, y mantener la integridad de una recopilación de datos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="1c372-103">Partitioning makes large tables or indexes more manageable because partitioning enables you to manage and access subsets of data quickly and efficiently, and maintain the integrity of a data collection at the same time.</span></span> <span data-ttu-id="1c372-104">Para obtener más información, vea [Partitioned Tables and Indexes](../../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="1c372-104">For more information, see [Partitioned Tables and Indexes](../../partitions/partitioned-tables-and-indexes.md).</span></span> <span data-ttu-id="1c372-105">La replicación es compatible con la creación de particiones al proporcionar un conjunto de propiedades que especifican cómo se deben tratar las tablas y los índices con particiones.</span><span class="sxs-lookup"><span data-stu-id="1c372-105">Replication supports partitioning by providing a set of properties that specify how partitioned tables and indexes should be treated.</span></span>  
  
## <a name="article-properties-for-transactional-and-merge-replication"></a><span data-ttu-id="1c372-106">Propiedades de artículos para replicación transaccional y de mezcla</span><span class="sxs-lookup"><span data-stu-id="1c372-106">Article Properties for Transactional and Merge Replication</span></span>  
 <span data-ttu-id="1c372-107">En la tabla siguiente se enumeran los objetos que se utilizan para la partición de datos.</span><span class="sxs-lookup"><span data-stu-id="1c372-107">The following table lists the objects that are used to partition data.</span></span>  
  
|<span data-ttu-id="1c372-108">Object</span><span class="sxs-lookup"><span data-stu-id="1c372-108">Object</span></span>|<span data-ttu-id="1c372-109">Se crea utilizando</span><span class="sxs-lookup"><span data-stu-id="1c372-109">Created by using</span></span>|  
|------------|----------------------|  
|<span data-ttu-id="1c372-110">Tabla o índice con particiones</span><span class="sxs-lookup"><span data-stu-id="1c372-110">Partitioned table or index</span></span>|<span data-ttu-id="1c372-111">CREATE TABLE o CREATE INDEX</span><span class="sxs-lookup"><span data-stu-id="1c372-111">CREATE TABLE or CREATE INDEX</span></span>|  
|<span data-ttu-id="1c372-112">Función de partición</span><span class="sxs-lookup"><span data-stu-id="1c372-112">Partition function</span></span>|<span data-ttu-id="1c372-113">CREATE PARTITION FUNCTION</span><span class="sxs-lookup"><span data-stu-id="1c372-113">CREATE PARTITION FUNCTION</span></span>|  
|<span data-ttu-id="1c372-114">Esquema de partición</span><span class="sxs-lookup"><span data-stu-id="1c372-114">Partition scheme</span></span>|<span data-ttu-id="1c372-115">CREATE PARTITION SCHEME</span><span class="sxs-lookup"><span data-stu-id="1c372-115">CREATE PARTITION SCHEME</span></span>|  
  
 <span data-ttu-id="1c372-116">El primer conjunto de propiedades relacionadas con la creación de particiones son las opciones de esquema de artículo que determinan si las particiones de los objetos se deben copiar en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="1c372-116">The first set of properties related to partitioning are the article schema options that determine whether partitioning objects should be copied to the Subscriber.</span></span> <span data-ttu-id="1c372-117">Estas opciones de esquema se pueden establecer de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="1c372-117">These schema options can be set in the following ways:</span></span>  
  
-   <span data-ttu-id="1c372-118">En la página **Propiedades del artículo** del Asistente para nueva publicación o en el cuadro de diálogo Propiedades de la publicación.</span><span class="sxs-lookup"><span data-stu-id="1c372-118">In the **Article Properties** page of the New Publication Wizard or the Publication Properties dialog box.</span></span> <span data-ttu-id="1c372-119">Para copiar los objetos enumerados en la tabla anterior, especifique un valor de `true` para las propiedades **copiar esquemas de particionamiento de tabla** y **copiar esquemas de particionamiento de índice**.</span><span class="sxs-lookup"><span data-stu-id="1c372-119">To copy the objects listed in the previous table, specify a value of `true` for the properties **Copy table partitioning schemes** and **Copy index partitioning schemes**.</span></span> <span data-ttu-id="1c372-120">Para obtener más información sobre cómo acceder a la página **Propiedades del artículo**, vea [Ver y modificar propiedades de publicación](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1c372-120">For information about how to access the **Article Properties** page, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
-   <span data-ttu-id="1c372-121">Utilizando el parámetro *schema_option* de uno de los procedimientos almacenados siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c372-121">By using the *schema_option* parameter of one of the following stored procedures:</span></span>  
  
    -   <span data-ttu-id="1c372-122">[sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) o [sp_changearticle](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql) para la replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="1c372-122">[sp_addarticle](/sql/relational-databases/system-stored-procedures/sp-addarticle-transact-sql) or [sp_changearticle](/sql/relational-databases/system-stored-procedures/sp-changearticle-transact-sql) for transactional replication</span></span>  
  
    -   <span data-ttu-id="1c372-123">[sp_addmergearticle](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql) o [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql) para la replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="1c372-123">[sp_addmergearticle](/sql/relational-databases/system-stored-procedures/sp-addmergearticle-transact-sql) or [sp_changemergearticle](/sql/relational-databases/system-stored-procedures/sp-changemergearticle-transact-sql) for merge replication</span></span>  
  
     <span data-ttu-id="1c372-124">Para copiar los objetos enumerados en la tabla anterior, especifique los valores de opciones de esquema adecuados.</span><span class="sxs-lookup"><span data-stu-id="1c372-124">To copy the objects listed in the previous table, specify the appropriate schema option values.</span></span> <span data-ttu-id="1c372-125">Para obtener información sobre cómo especificar opciones de esquema, vea [Specify Schema Options](specify-schema-options.md).</span><span class="sxs-lookup"><span data-stu-id="1c372-125">For information about how to specify schema options, see [Specify Schema Options](specify-schema-options.md).</span></span>  
  
 <span data-ttu-id="1c372-126">La replicación copia los objetos en el suscriptor durante la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="1c372-126">Replication copies objects to the Subscriber during the initial synchronization.</span></span> <span data-ttu-id="1c372-127">Si el esquema de partición utiliza grupos de archivos distintos del archivo de grupos PRIMARY, esos grupos de archivos deben existir en el suscriptor antes de la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="1c372-127">If the partition scheme uses filegroups other than the PRIMARY filegroup, those filegroups must exist on the Subscriber before the initial synchronization.</span></span>  
  
 <span data-ttu-id="1c372-128">Una vez inicializado el suscriptor, los cambios de los datos se propagan al suscriptor y se aplican a las particiones adecuadas.</span><span class="sxs-lookup"><span data-stu-id="1c372-128">After the Subscriber is initialized, data changes are propagated to the Subscriber and applied to the appropriate partitions.</span></span> <span data-ttu-id="1c372-129">Sin embargo, no se admiten cambios en el esquema de partición.</span><span class="sxs-lookup"><span data-stu-id="1c372-129">However, changes to the partition scheme are not supported.</span></span> <span data-ttu-id="1c372-130">Las replicaciones transaccional y de mezcla no admiten la replicación de los comandos siguientes: ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME, ni la instrucción REBUILD WITH PARTITION de ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="1c372-130">Transactional and merge replication do not support replicating the following commands: ALTER PARTITION FUNCTION, ALTER PARTITION SCHEME, or the REBUILD WITH PARTITION statement of ALTER INDEX.</span></span>  <span data-ttu-id="1c372-131">Los cambios asociados a ellos no se replicarán automáticamente al suscriptor.</span><span class="sxs-lookup"><span data-stu-id="1c372-131">The changes associated with them will not be automatically replicated to the Subscriber.</span></span> <span data-ttu-id="1c372-132">Es responsabilidad del usuario realizar modificaciones similares en el suscriptor de forma manual.</span><span class="sxs-lookup"><span data-stu-id="1c372-132">It is the responsibility of the user to make similar changes manually at the Subscriber.</span></span>  
  
## <a name="replication-support-for-partition-switching"></a><span data-ttu-id="1c372-133">Compatibilidad de la replicación con la modificación de particiones</span><span class="sxs-lookup"><span data-stu-id="1c372-133">Replication Support for Partition Switching</span></span>  
 <span data-ttu-id="1c372-134">Una de las ventajas principales de crear particiones en una tabla es la posibilidad de mover rápida y eficazmente subconjuntos de datos entre particiones.</span><span class="sxs-lookup"><span data-stu-id="1c372-134">One of the key benefits of table partitioning is the ability to quickly and efficiently move subsets of data between partitions.</span></span> <span data-ttu-id="1c372-135">Los datos se mueven utilizando el comando SWITCH PARTITION.</span><span class="sxs-lookup"><span data-stu-id="1c372-135">Data is moved by using the SWITCH PARTITION command.</span></span> <span data-ttu-id="1c372-136">De forma predeterminada, cuando en una tabla se habilita la replicación, las operaciones SWITCH PARTITION se bloquean por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c372-136">By default, when a table is enabled for replication, SWITCH PARTITION operations are blocked for the following reasons:</span></span>  
  
-   <span data-ttu-id="1c372-137">Si los datos se mueven a una tabla o fuera de una tabla que existe en el publicador pero que no existe en el suscriptor, ambos pueden llegar a ser incoherentes entre sí.</span><span class="sxs-lookup"><span data-stu-id="1c372-137">If data is moved into or out of a table that exists at the Publisher but does not exist at the Subscriber, the Publisher and Subscriber could become inconsistent with one another.</span></span> <span data-ttu-id="1c372-138">Este problema se produce normalmente cuando los datos se mueven a o fuera de una tabla de ensayo.</span><span class="sxs-lookup"><span data-stu-id="1c372-138">This problem typically occurs when data is moved into or out of a staging table.</span></span>  
  
-   <span data-ttu-id="1c372-139">Si el suscriptor tiene para la tabla con particiones una definición diferente de la del publicador, se producirá un error en el Agente de distribución cuando intente aplicar los cambios en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="1c372-139">If the Subscriber has a different definition for the partitioned table than the Publisher, the Distribution Agent will fail when it tries to apply changes at the Subscriber.</span></span>  
  
 <span data-ttu-id="1c372-140">A pesar de estos posibles problemas, la modificación de particiones puede habilitarse en la replicación transaccional.</span><span class="sxs-lookup"><span data-stu-id="1c372-140">Despite these potential issues, partition switching can be enabled for transactional replication.</span></span> <span data-ttu-id="1c372-141">Antes de habilitar la modificación de particiones, asegúrese de que todas las tablas implicadas en ella existen en el publicador y en el suscriptor, y de que la tabla y las definiciones de partición son las mismas.</span><span class="sxs-lookup"><span data-stu-id="1c372-141">Before you enable partition switching, make sure that all tables that are involved in partition switching exist at the Publisher and Subscriber, and make sure that the table and partition definitions are the same.</span></span>  
  
 <span data-ttu-id="1c372-142">Cuando las particiones tienen exactamente el mismo esquema de partición en los publicadores y en los suscriptores puede activar *allow_partition_switch* junto con *replication_partition_switch* , con lo que solo se replicará la instrucción de cambio de partición en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="1c372-142">When partitions have the exact same partition scheme at the publishers and subscribers you can turn on *allow_partition_switch* along with *replication_partition_switch* which will only replicate the partition switch statement to the subscriber.</span></span> <span data-ttu-id="1c372-143">También puede activar *allow_partition_switch* sin replicación de DDL.</span><span class="sxs-lookup"><span data-stu-id="1c372-143">You can also turn on *allow_partition_switch* without replicating the DDL.</span></span> <span data-ttu-id="1c372-144">Esto resulta útil en el caso en que desee distribuir los meses anteriores de la partición pero mantener la partición replicada para otro año a efectos de copia de seguridad en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="1c372-144">This is useful in the case where you want to roll old months out of the partition but keep the replicated partition in place for another year for backup purposes at the subscriber.</span></span>  
  
 <span data-ttu-id="1c372-145">Si habilita la conmutación de particiones en SQL Server 2008 R2 a través de la versión actual, puede que también necesite las operaciones de división y combinación más adelante.</span><span class="sxs-lookup"><span data-stu-id="1c372-145">If you enable partition switching on SQL Server 2008 R2 through the current version, you might also need split and merge operations in near future.</span></span> <span data-ttu-id="1c372-146">Antes de ejecutar una operación de división o combinación en una tabla replicada, asegúrese de que la partición en cuestión no tenga ningún comando replicado pendiente.</span><span class="sxs-lookup"><span data-stu-id="1c372-146">Before executing a split or merge operation on a replicated table ensure that the partition in question does not have any pending replicated commands.</span></span> <span data-ttu-id="1c372-147">También debe asegurarse de que no se ejecuten operaciones DML en la partición durante las operaciones de división y combinación.</span><span class="sxs-lookup"><span data-stu-id="1c372-147">You should also ensure that no DML operations are executed on the partition during the split and merge operations.</span></span> <span data-ttu-id="1c372-148">Si hay transacciones que no ha procesado el lector del registro o si se realizan operaciones de DML en una partición de una tabla replicada mientras se ejecuta una operación de división o combinación (que implica la misma partición), se podría producir un error de procesamiento con el agente de registro del LOG.</span><span class="sxs-lookup"><span data-stu-id="1c372-148">If there are transactions which the log reader has not processed, or if DML operations are performed on a partition of a replicated table while a split or merge operation is executed (involving the same partition), it could lead to a processing error with log reader agent.</span></span> <span data-ttu-id="1c372-149">Para corregir el error, puede solicitar que se vuelva a inicializar la suscripción.</span><span class="sxs-lookup"><span data-stu-id="1c372-149">In order to correct the error, it might require a re-initialization of the subscription.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="1c372-150">No debe habilitar la modificación de particiones para las publicaciones punto a punto, debido a la columna oculta que se usa para detectar y solucionar conflictos.</span><span class="sxs-lookup"><span data-stu-id="1c372-150">You should not enable partition switching for Peer-to-Peer publications, due to the hidden column which is used to detect and resolve conflict.</span></span>  
  
### <a name="enabling-partition-switching"></a><span data-ttu-id="1c372-151">Habilitar la modificación de particiones</span><span class="sxs-lookup"><span data-stu-id="1c372-151">Enabling Partition Switching</span></span>  
 <span data-ttu-id="1c372-152">Las propiedades siguientes de las publicaciones transaccionales permiten a los usuarios controlar el comportamiento de la modificación de particiones en un entorno replicado:</span><span class="sxs-lookup"><span data-stu-id="1c372-152">The following properties for transactional publications enable users to control the behavior of partition switching in a replicated environment:</span></span>  
  
-   <span data-ttu-id="1c372-153">\*\* \@ allow_partition_switch\*\*, cuando se establece en `true` , se puede ejecutar switch Partition en la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="1c372-153">**\@allow_partition_switch**, when set to `true`, SWITCH PARTITION can be executed against the publication database.</span></span>  
  
-   <span data-ttu-id="1c372-154">\*\* \@ replicate_partition_switch\*\* determina si la instrucción switch Partition de DDL se debe replicar en los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="1c372-154">**\@replicate_partition_switch** determines whether the SWITCH PARTITION DDL statement should be replicated to Subscribers.</span></span> <span data-ttu-id="1c372-155">Esta opción solo es válida cuando \*\* \@ allow_partition_switch\*\* está establecida en `true` .</span><span class="sxs-lookup"><span data-stu-id="1c372-155">This option is valid only when **\@allow_partition_switch** is set to `true`.</span></span>  
  
 <span data-ttu-id="1c372-156">Puede establecer estas propiedades utilizando [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) cuando se crea la publicación, o usando [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) después de crearla.</span><span class="sxs-lookup"><span data-stu-id="1c372-156">You can set these properties by using [sp_addpublication](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) when the publication is created, or by using [sp_changepublication](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) after the publication is created.</span></span> <span data-ttu-id="1c372-157">Según se indicaba anteriormente, la replicación de mezcla no admite la modificación de particiones.</span><span class="sxs-lookup"><span data-stu-id="1c372-157">As noted earlier, merge replication does not support partition switching.</span></span> <span data-ttu-id="1c372-158">Para ejecutar SWITCH PARTITION en una tabla en la que está habilitada la replicación de mezcla, quite la tabla de la publicación.</span><span class="sxs-lookup"><span data-stu-id="1c372-158">To execute SWITCH PARTITION on a table that is enabled for merge replication, remove the table from the publication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c372-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c372-159">See Also</span></span>  
 [<span data-ttu-id="1c372-160">Publicar datos y objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="1c372-160">Publish Data and Database Objects</span></span>](publish-data-and-database-objects.md)  
  
  