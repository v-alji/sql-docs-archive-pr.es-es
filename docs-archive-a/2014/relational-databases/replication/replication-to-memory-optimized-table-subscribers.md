---
title: Replicación en suscriptores de tablas con optimización para memoria | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
ms.assetid: 1a8e6bc7-433e-471d-b646-092dc80a2d1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: df61b83d2f6d07cbbd21773b8940dd4e5341f76b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662788"
---
# <a name="replication-to-memory-optimized-table-subscribers"></a><span data-ttu-id="23bb8-102">Replicación en suscriptores de tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="23bb8-102">Replication to Memory-Optimized Table Subscribers</span></span>
  <span data-ttu-id="23bb8-103">Las tablas que actúan como suscriptores de replicación transaccional, excluida la replicación transaccional punto a punto, pueden configurarse como tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="23bb8-103">Tables acting as transactional replication subscribers, excluding Peer-to-peer transactional replication, can be configured as memory-optimized tables.</span></span> <span data-ttu-id="23bb8-104">Otras configuraciones de replicación no son compatibles con las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="23bb8-104">Other replication configurations are not compatible with memory-optimized tables.</span></span>  
  
## <a name="configuring-a-memory-optimized-table-as-a-subscriber"></a><span data-ttu-id="23bb8-105">Configurar una tabla optimizada para memoria como suscriptor</span><span class="sxs-lookup"><span data-stu-id="23bb8-105">Configuring a memory-optimized table as a subscriber</span></span>  
 <span data-ttu-id="23bb8-106">Para configurar una tabla optimizada para memoria como suscriptor, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="23bb8-106">To configure a memory-optimized table as a subscriber, perform the following steps.</span></span>  
  
 <span data-ttu-id="23bb8-107">**Crear y habilitar una publicación**</span><span class="sxs-lookup"><span data-stu-id="23bb8-107">**Create and Enable Publication**</span></span>  
  
1.  <span data-ttu-id="23bb8-108">Crear una publicación.</span><span class="sxs-lookup"><span data-stu-id="23bb8-108">Create a publication.</span></span>  
  
2.  <span data-ttu-id="23bb8-109">Agregue artículos a la publicación.</span><span class="sxs-lookup"><span data-stu-id="23bb8-109">Add articles to the publication.</span></span> <span data-ttu-id="23bb8-110">Para el parámetro `@upd_cmd`, use la convención SCALL o SQL.</span><span class="sxs-lookup"><span data-stu-id="23bb8-110">For the `@upd_cmd` parameter, use the SCALL or SQL convention.</span></span>  
  
    ```  
    EXEC sp_addarticle  
        @publication = N'Publication1',  
        @article = N'Mem_Table',  
        @source_owner = N'dbo',  
        @source_object = N'Mem_Table',  
        @type = N'logbased',  
        @description = null,  
        @creation_script = null,  
        @pre_creation_cmd = N'none',  
        @schema_option = 0x00000000080050DF,  
        @identityrangemanagementoption = N'manual',  
        @destination_table = N'Mem_Table',  
        @destination_owner = N'dbo',  
        @vertical_partition = N'false',  
        @ins_cmd = N'CALL sp_MSins_Mem_Table',  
        @del_cmd = N'CALL sp_MSdel_Mem_Table',  
        @upd_cmd = N'SCALL sp_MSupd_Mem_Table';  
    GO  
    ```  
  
 <span data-ttu-id="23bb8-111">**Generar una instantánea y ajustar el esquema**</span><span class="sxs-lookup"><span data-stu-id="23bb8-111">**Generate a Snapshot and Adjust the Schema**</span></span>  
  
1.  <span data-ttu-id="23bb8-112">Cree un trabajo de instantánea y genere una instantánea.</span><span class="sxs-lookup"><span data-stu-id="23bb8-112">Create a snapshot job and generate a snapshot.</span></span>  
  
    ```  
    EXEC sp_addpublication_snapshot @publication = N'Publication1', @frequency_type = 1;  
    EXEC sp_startpublication_snapshot @publication = N'Publication1';  
    ```  
  
2.  <span data-ttu-id="23bb8-113">Navegue hasta la carpeta de la instantánea.</span><span class="sxs-lookup"><span data-stu-id="23bb8-113">Navigate to the snapshot folder.</span></span> <span data-ttu-id="23bb8-114">La ubicación predeterminada es "C:\Archivos de Programa\microsoft SQL Server\MSSQL12. \<INSTANCE> \MSSQL\repldata\unc\XXX\YYYYMMDDHHMMSS \\ ".</span><span class="sxs-lookup"><span data-stu-id="23bb8-114">The default location is "C:\Program Files\Microsoft SQL Server\MSSQL12.\<INSTANCE>\MSSQL\repldata\unc\XXX\YYYYMMDDHHMMSS\\".</span></span>  
  
3.  <span data-ttu-id="23bb8-115">Busque el **. SCH** en la tabla y ábralo en Management Studio.</span><span class="sxs-lookup"><span data-stu-id="23bb8-115">Locate the **.SCH** file for your table and open it in Management Studio.</span></span> <span data-ttu-id="23bb8-116">Cambie el esquema de tabla y actualice el procedimiento almacenado como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="23bb8-116">Change the table schema and update the stored procedure as described below.</span></span>  
  
     <span data-ttu-id="23bb8-117">Evalúe los índices definidos en el archivo IDX.</span><span class="sxs-lookup"><span data-stu-id="23bb8-117">Evaluate the indexes defined in the IDX file.</span></span> <span data-ttu-id="23bb8-118">Modifique `CREATE TABLE` para especificar los índices, las restricciones, la clave principal y la sintaxis optimizada para memoria necesarios.</span><span class="sxs-lookup"><span data-stu-id="23bb8-118">Modify `CREATE TABLE` to specify the required indexes, constraints, primary key, and memory-optimized syntax.</span></span> <span data-ttu-id="23bb8-119">Para las tablas optimizadas para memoria, las columnas de índice deben ser NOT NULL y las columnas de índice de tipos de caracteres deben ser Unicode y usar la intercalación BIN2.</span><span class="sxs-lookup"><span data-stu-id="23bb8-119">For memory-optimized tables, index columns should be NOT NULL and index columns of character types must be Unicode and use BIN2 collation.</span></span> <span data-ttu-id="23bb8-120">Vea el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23bb8-120">See example below:</span></span>  
  
    ```  
    SET ANSI_PADDING ON;  
    GO  
  
    SET ANSI_NULLS ON;  
    GO  
  
    SET QUOTED_IDENTIFIER ON;  
    GO  
  
    CREATE TABLE [dbo].[Mem_Table]([c1] [int] NOT NULL,  
        [c2] [float] NOT NULL,  
        [c3] [decimal](10, 2) NOT NULL,  
        [c4] [nvarchar](5) COLLATE SQL_Latin1_General_CP850_BIN2 NOT NULL,  
        INDEX [hash_index_sample_memoryoptimizedtable_c2] HASH (c2) WITH (BUCKET_COUNT = 1024),  
        INDEX [index_sample_memoryoptimizedtable_c3] NONCLUSTERED ([c3]),  
        INDEX [nvarchar_index_sample_memoryoptimizedtable_c4] ([c4]),  
        CONSTRAINT [PK_sample_memoryoptimizedtable] PRIMARY KEY NONCLUSTERED ([c1])) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA);  
    GO  
    ```  
  
4.  <span data-ttu-id="23bb8-121">Cuando use la convención SCALL para el parámetro `@upd_cmd`, vaya al archivo de esquema (.SCH) y cambie la instrucción de actualización de tabla en `create procedure [sp_MSupd_<SCHEMA><TABLE_NAME>]` para quitar las columnas de clave principal.</span><span class="sxs-lookup"><span data-stu-id="23bb8-121">When using SCALL convention for the `@upd_cmd` parameter, go to the schema (.SCH) file and change the table update statement in `create procedure [sp_MSupd_<SCHEMA><TABLE_NAME>]` to remove primary key columns.</span></span>  
  
     <span data-ttu-id="23bb8-122">Para admitir actualizaciones de la clave principal, use un procedimiento almacenado de actualización personalizado para reemplazar la instrucción de actualización de la clave principal de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="23bb8-122">To support primary key updates, use a custom update stored procedure to replace the primary key update statement, as follows:</span></span>  
  
    1.  <span data-ttu-id="23bb8-123">Seleccione los valores de columna ausentes (SCALL solo proporciona la columna implicada en la operación de actualización).</span><span class="sxs-lookup"><span data-stu-id="23bb8-123">Select missing column values (SCALL only provides the column involved into the update operation).</span></span>  
  
    2.  <span data-ttu-id="23bb8-124">Elimine el registro existente.</span><span class="sxs-lookup"><span data-stu-id="23bb8-124">Delete the existing record.</span></span>  
  
    3.  <span data-ttu-id="23bb8-125">Inserte un nuevo registro con los nuevos valores suministrados, incluida la nueva clave principal.</span><span class="sxs-lookup"><span data-stu-id="23bb8-125">Insert a new record with new values provided including the new primary key.</span></span>  
  
     <span data-ttu-id="23bb8-126">El procedimiento de actualización original es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="23bb8-126">The original update procedure looks like this:</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                   @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    update [dbo].[Mem_Table] set  
                   [c1] = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
     <span data-ttu-id="23bb8-127">Si la clave principal nunca se debe actualizar en un publicador.</span><span class="sxs-lookup"><span data-stu-id="23bb8-127">If the primary key should never be updated on a publisher.</span></span> <span data-ttu-id="23bb8-128">Marque con comentarios la actualización de esas columnas en el procedimiento de actualización de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="23bb8-128">Comment out the update to such columns in the update procedure as follows:</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                   @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    update [dbo].[Mem_Table] set  
    --             [c1] = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
     <span data-ttu-id="23bb8-129">Para permitir actualizaciones a la clave principal, modifique el procedimiento de actualización de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="23bb8-129">To allow the support of updates to the primary key, modify the update procedure to read as follows</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                    @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    select  
                   @c1 = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   @c2 = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   @c3 = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   @c4 = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    from [dbo].[Mem_Table] where [c1] = @pkc1  
    if @@rowcount <> 0 begin  
            delete [dbo].[Mem_Table] where [c1] = @pkc1  
            if @@rowcount <> 0  
                   insert into [dbo].[Mem_Table]([c1],  
                           [c2],  
                           [c3],  
                           [c4]) values (  
                           @c1,  
                           @c2,  
                           @c3,  
                           @c4  
                   )   
    end  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
5.  <span data-ttu-id="23bb8-130">Cree una base de datos de suscriptor con la opción de **aislamiento elevar a Snapshot** y establezca la intercalación predeterminada en Latin1_General_CS_AS_KS_WS en el caso de usar tipos de datos de caracteres no Unicode.</span><span class="sxs-lookup"><span data-stu-id="23bb8-130">Create subscriber database using the **elevate to snapshot isolation** option and set the default collation to Latin1_General_CS_AS_KS_WS in case of using non Unicode character data types.</span></span>  
  
    ```  
    CREATE DATABASE [Sub]   
    CONTAINMENT = NONE   
    ON PRIMARY ( NAME = [Sub], FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub.mdf]),   
    FILEGROUP [mem] CONTAINS MEMORY_OPTIMIZED_DATA ( NAME = [mem],   
    FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub])  
    LOG ON ( NAME = [Sub_log], FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub.ldf])  
    COLLATE Latin1_General_CS_AS_KS_WS;  
  
    ALTER DATABASE [Sub] SET MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT = ON;  
    GO  
    ```  
  
6.  <span data-ttu-id="23bb8-131">Aplique el esquema a la base de datos de un suscriptor y guarde el esquema para su uso futuro.</span><span class="sxs-lookup"><span data-stu-id="23bb8-131">Apply the schema to a subscriber's database and save the schema for future use.</span></span>  
  
7.  <span data-ttu-id="23bb8-132">Cargue los datos del publicador (origen) en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="23bb8-132">Load the publisher (source) data to the subscriber.</span></span> <span data-ttu-id="23bb8-133">Los datos no deben cambiarse en el publicador hasta que no agregue una suscripción.</span><span class="sxs-lookup"><span data-stu-id="23bb8-133">Data should not change at the publisher until you add a subscription.</span></span>  <span data-ttu-id="23bb8-134">Puede usar BCP como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="23bb8-134">You can use BCP as shown below:</span></span>  
  
    ```  
    bcp Pub.dbo.Mem_Table out Mem_Table.bcp -S. -T -C1252 -n  
    bcp Sub.dbo.Mem_Table in Mem_Table.bcp -S. -T -C1252 -n  
    ```  
  
8.  <span data-ttu-id="23bb8-135">Reconfigure el artículo para deshabilitar los cambios de esquema en el suscriptor:</span><span class="sxs-lookup"><span data-stu-id="23bb8-135">Reconfigure the article to disable schema changes on the subscriber:</span></span>  
  
    ```  
    EXEC sp_changearticle  
        @publication = N'Publication1',  
        @article = N'Mem_Table',  
        @property = N'schema_option',  
        @value = 0,  
        @force_invalidate_snapshot = 1,  
        @force_reinit_subscription = 1;  
    GO  
    ```  
  
 <span data-ttu-id="23bb8-136">**Agregar una suscripción nosync**</span><span class="sxs-lookup"><span data-stu-id="23bb8-136">**Add no sync Subscription**</span></span>  
  
 <span data-ttu-id="23bb8-137">Agregue una suscripción nosync.</span><span class="sxs-lookup"><span data-stu-id="23bb8-137">Add a nosync subscription.</span></span>  
  
```  
EXEC sp_addsubscription  
    @publication = N' Publication1',  
    @subscriber = @@ServerName,  
    @destination_db = N'Sub',  
    @subscription_type = N'Push',  
    @sync_type = N'replication support only',  
    @article = N'all',  
    @update_mode = N'read only',  
    @subscriber_type = 0;  
GO  
```  
  
 <span data-ttu-id="23bb8-138">Las tablas con optimización para memoria deben empezar ahora a recibir actualizaciones del publicador.</span><span class="sxs-lookup"><span data-stu-id="23bb8-138">Memory-optimized tables should now start receiving updates from the publisher.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="23bb8-139">Restricciones</span><span class="sxs-lookup"><span data-stu-id="23bb8-139">Restrictions</span></span>  
 <span data-ttu-id="23bb8-140">Solo se admite la replicación transaccional unidireccional.</span><span class="sxs-lookup"><span data-stu-id="23bb8-140">Only one-way transactional replication is supported.</span></span> <span data-ttu-id="23bb8-141">No se admite la replicación transaccional punto a punto.</span><span class="sxs-lookup"><span data-stu-id="23bb8-141">Peer-to-peer transactional replication is not supported.</span></span>  
  
 <span data-ttu-id="23bb8-142">Las tablas con optimización para memoria no se pueden publicar.</span><span class="sxs-lookup"><span data-stu-id="23bb8-142">Memory-optimized tables cannot be published.</span></span>  
  
 <span data-ttu-id="23bb8-143">Las tablas de replicación del distribuidor no se pueden configurar como tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="23bb8-143">Replication tables on the distributor cannot be configured as memory-optimized tables.</span></span>  
  
 <span data-ttu-id="23bb8-144">La replicación de mezcla no puede incluir tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="23bb8-144">Merge replication cannot include memory-optimized tables.</span></span>  
  
 <span data-ttu-id="23bb8-145">En el suscriptor, las tablas implicadas en la replicación transaccional se pueden configurar como tablas optimizadas para memoria, pero las tablas del suscriptor deben cumplir los requisitos de las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="23bb8-145">At the subscriber, tables involved in transactional replication can be configured as memory optimized tables, but the subscriber tables must meet the requirements of memory-optimized tables.</span></span> <span data-ttu-id="23bb8-146">Esto requiere las restricciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="23bb8-146">This requires the following restrictions.</span></span>  
  
-   <span data-ttu-id="23bb8-147">Para crear una tabla optimizada para memoria en un suscriptor de replicación transaccional, los archivos de esquema de instantáneas usados para crear las tablas optimizadas para memoria se deben modificar manualmente.</span><span class="sxs-lookup"><span data-stu-id="23bb8-147">To create a memory-optimized table on a transactional replication subscriber, the snapshot schema files used to create the memory-optimized tables must be manually modified.</span></span> <span data-ttu-id="23bb8-148">Para obtener más información, vea [modificar un archivo de esquema](#Schema).</span><span class="sxs-lookup"><span data-stu-id="23bb8-148">For more information, see [Modifying a schema file](#Schema).</span></span>  
  
-   <span data-ttu-id="23bb8-149">Las tablas replicadas en tablas optimizadas para memoria de un suscriptor tienen el límite de 8060 bytes por fila de las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="23bb8-149">Tables replicated to memory-optimized tables on a subscriber are limited to the 8060 bytes per row limit of memory-optimized tables.</span></span>  
  
-   <span data-ttu-id="23bb8-150">Las tablas replicadas en tablas optimizadas para memoria de un suscriptor están limitadas a los tipos de datos permitidos en las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="23bb8-150">Tables replicated to memory-optimized tables on a subscriber are limited to the data types permitted in memory-optimized tables.</span></span> <span data-ttu-id="23bb8-151">Para obtener más información, vea [tipos de datos admitidos](../in-memory-oltp/supported-data-types-for-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="23bb8-151">For more information, see [Supported Data Types](../in-memory-oltp/supported-data-types-for-in-memory-oltp.md).</span></span>  
  
-   <span data-ttu-id="23bb8-152">Hay ciertas restricciones para la actualización de la clave principal de tablas que se replican en una tabla optimizada para memoria en un suscriptor.</span><span class="sxs-lookup"><span data-stu-id="23bb8-152">There are restrictions on updating the primary key of tables being replicated to a memory-optimized table on a subscriber.</span></span> <span data-ttu-id="23bb8-153">Para obtener más información, vea [replicar cambios en una clave principal](#PrimaryKey).</span><span class="sxs-lookup"><span data-stu-id="23bb8-153">For more information, see [Replicating changes to a primary key](#PrimaryKey).</span></span>  
  
-   <span data-ttu-id="23bb8-154">En las tablas optimizadas para memoria no se admiten claves externas, restricciones UNIQUE, desencadenadores, modificaciones de esquema, ROWGUIDCOL, columnas calculadas, compresión de datos, tipos de datos de alias, control de versiones ni bloqueos.</span><span class="sxs-lookup"><span data-stu-id="23bb8-154">Foreign key, unique constraint, triggers, schema modifications, ROWGUIDCOL, computed columns, data compression, alias data types, versioning, and locks are not supported in memory-optimized tables.</span></span> <span data-ttu-id="23bb8-155">Vea [Transact-SQL Constructs Not Supported by In-Memory OLTP](../in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md) para obtener información.</span><span class="sxs-lookup"><span data-stu-id="23bb8-155">See [Transact-SQL Constructs Not Supported by In-Memory OLTP](../in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md) for information.</span></span>  
  
##  <a name="modifying-a-schema-file"></a><a name="Schema"></a><span data-ttu-id="23bb8-156">Modificar un archivo de esquema</span><span class="sxs-lookup"><span data-stu-id="23bb8-156">Modifying a schema file</span></span>  
  
-   <span data-ttu-id="23bb8-157">No se admiten índices clúster.</span><span class="sxs-lookup"><span data-stu-id="23bb8-157">Clustered indexes are not supported.</span></span> <span data-ttu-id="23bb8-158">Cambie los índices clúster a los índices no clúster.</span><span class="sxs-lookup"><span data-stu-id="23bb8-158">Change any clustered indexes to nonclustered indexes.</span></span>  
  
-   <span data-ttu-id="23bb8-159">Todas las columnas de la clave de un índice se deben especificar como `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="23bb8-159">All columns in the key of an index must be specified as `NOT NULL`.</span></span>  
  
-   <span data-ttu-id="23bb8-160">Si se usa la opción `DURABILITY = SCHEMA_AND_DATA` de tabla optimizada para memoria, la tabla debe tener un índice de clave principal no clúster.</span><span class="sxs-lookup"><span data-stu-id="23bb8-160">If using the memory-optimized table option `DURABILITY = SCHEMA_AND_DATA` the table must have a nonclustered primary key index.</span></span>  
  
-   <span data-ttu-id="23bb8-161">ANSI_PADDING debe ser ON.</span><span class="sxs-lookup"><span data-stu-id="23bb8-161">ANSI_PADDING must be ON.</span></span>  
  
##  <a name="replicating-changes-to-a-primary-key"></a><a name="PrimaryKey"></a><span data-ttu-id="23bb8-162">Replicación de cambios en una clave principal</span><span class="sxs-lookup"><span data-stu-id="23bb8-162">Replicating changes to a primary key</span></span>  
 <span data-ttu-id="23bb8-163">La clave principal de una tabla optimizada para memoria no se puede actualizar.</span><span class="sxs-lookup"><span data-stu-id="23bb8-163">The primary key of a memory-optimized table cannot be updated.</span></span> <span data-ttu-id="23bb8-164">Para replicar la actualización de una clave principal en un suscriptor, modifique el procedimiento almacenado de actualización para entregar la actualización como un par de eliminación e inserción.</span><span class="sxs-lookup"><span data-stu-id="23bb8-164">To replicate a primary key update on a subscriber, modify the update stored procedure to deliver the update as a delete and insert pair.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23bb8-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23bb8-165">See Also</span></span>  
 [<span data-ttu-id="23bb8-166">Replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="23bb8-166">SQL Server Replication</span></span>](sql-server-replication.md)  
  
  
