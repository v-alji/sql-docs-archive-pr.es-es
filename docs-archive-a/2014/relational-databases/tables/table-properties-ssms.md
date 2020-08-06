---
title: Propiedades de la tabla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.tableproperties.storage.f1
- sql12.SWB.SELECTCOLUMNS.F1
- sql12.swb.tableproperties.filetable.f1
- sql12.swb.tableproperties.general.f1
- sql12.swb.tableproperties.changetracking.f1
ms.assetid: ad8a2fd4-f092-4c0f-be85-54ce8b9d725a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 037e56649d3473e3fe09b9533bcc96b4729870d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673562"
---
# <a name="table-properties"></a><span data-ttu-id="2ee0e-102">Propiedades de tabla</span><span class="sxs-lookup"><span data-stu-id="2ee0e-102">Table Properties</span></span>
  <span data-ttu-id="2ee0e-103">En este tema se describen las propiedades de la tabla que se muestran en el cuadro de diálogo Propiedades de tabla en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ee0e-103">This topic describes the table properties that are displayed in the Table Properties dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2ee0e-104">Para obtener más información sobre cómo mostrar estas propiedades, vea [Ver la definición de tabla](view-the-table-definition.md).</span><span class="sxs-lookup"><span data-stu-id="2ee0e-104">For more information about how to display these properties, see [View the Table Definition](view-the-table-definition.md).</span></span>  
  
 <span data-ttu-id="2ee0e-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-105">**In This Topic**</span></span>  
  
1.  [<span data-ttu-id="2ee0e-106">Página General</span><span class="sxs-lookup"><span data-stu-id="2ee0e-106">General Page</span></span>](#GeneralPage)  
  
2.  [<span data-ttu-id="2ee0e-107">Página Seguimiento de cambios</span><span class="sxs-lookup"><span data-stu-id="2ee0e-107">Change Tracking Page</span></span>](#ChangeTracking)  
  
3.  [<span data-ttu-id="2ee0e-108">Página FileTable</span><span class="sxs-lookup"><span data-stu-id="2ee0e-108">File Table Page</span></span>](#FileTable)  
  
4.  [<span data-ttu-id="2ee0e-109">Página Almacenamiento</span><span class="sxs-lookup"><span data-stu-id="2ee0e-109">Storage Page</span></span>](#Storage)  
  
##  <a name="general-page"></a><a name="GeneralPage"></a> <span data-ttu-id="2ee0e-110">Página General</span><span class="sxs-lookup"><span data-stu-id="2ee0e-110">General Page</span></span>  
 <span data-ttu-id="2ee0e-111">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-111">**Database**</span></span>  
 <span data-ttu-id="2ee0e-112">Nombre de la base de datos que contiene esta tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-112">The name of the database containing this table.</span></span>  
  
 <span data-ttu-id="2ee0e-113">**Server**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-113">**Server**</span></span>  
 <span data-ttu-id="2ee0e-114">Nombre de la instancia de servidor actual.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-114">The name of the current server instance.</span></span>  
  
 <span data-ttu-id="2ee0e-115">**User**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-115">**User**</span></span>  
 <span data-ttu-id="2ee0e-116">Nombre del usuario de esta conexión.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-116">The name of the user of this connection.</span></span>  
  
 <span data-ttu-id="2ee0e-117">**Fecha de creación**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-117">**Created Date**</span></span>  
 <span data-ttu-id="2ee0e-118">Fecha y hora de creación de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-118">The date and time that the table was created.</span></span>  
  
 <span data-ttu-id="2ee0e-119">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-119">**Name**</span></span>  
 <span data-ttu-id="2ee0e-120">Nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-120">The name of the table.</span></span>  
  
 <span data-ttu-id="2ee0e-121">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-121">**Schema**</span></span>  
 <span data-ttu-id="2ee0e-122">Esquema al que pertenece la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-122">The schema that owns the table.</span></span>  
  
 <span data-ttu-id="2ee0e-123">**Objeto de sistema**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-123">**System object**</span></span>  
 <span data-ttu-id="2ee0e-124">Indica que esta tabla es una tabla de sistema, utilizada por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para incluir información interna.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-124">Indicates this table is a system table, used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to contain internal information.</span></span> <span data-ttu-id="2ee0e-125">Los usuarios no deben cambiar ni hacer referencia directamente a las tablas de sistema.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-125">Users should not directly change or reference system tables.</span></span>  
  
 <span data-ttu-id="2ee0e-126">**Valores NULL ANSI**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-126">**ANSI NULLs**</span></span>  
 <span data-ttu-id="2ee0e-127">Indica si el objeto se ha creado con la opción ANSI NULL establecida en ON.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-127">Indicates if the object was created with the ANSI NULLs option set to ON.</span></span> <span data-ttu-id="2ee0e-128">Para obtener más información, vea [SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ee0e-128">For more information, see [SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql)</span></span>  
  
 <span data-ttu-id="2ee0e-129">**Identificador entre comillas**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-129">**Quoted identifier**</span></span>  
 <span data-ttu-id="2ee0e-130">Indica si el objeto se ha creado con la opción de identificador entre comillas establecida en ON.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-130">Indicates if the object was created with the quoted identifier option set to ON.</span></span> <span data-ttu-id="2ee0e-131">Para obtener más información, vea [SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ee0e-131">For more information, see [SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql)</span></span>  
  
 <span data-ttu-id="2ee0e-132">**Extensión de bloqueo**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-132">**Lock Escalation**</span></span>  
 <span data-ttu-id="2ee0e-133">Indica la granularidad de la extensión de bloqueo de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-133">Indicates the lock escalation granularity of the table.</span></span> <span data-ttu-id="2ee0e-134">Para obtener más información acerca del bloqueo del motor de base de datos, vea [Guía de las versiones de fila y el bloqueo de transacciones de SQL Server](https://msdn.microsoft.com/library/jj856598.aspx).</span><span class="sxs-lookup"><span data-stu-id="2ee0e-134">For more information about locking in the Database Engine, see [SQL Server Transaction Locking and Row Versioning Guide](https://msdn.microsoft.com/library/jj856598.aspx).</span></span> <span data-ttu-id="2ee0e-135">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="2ee0e-135">Possible values are:</span></span>  
  
 <span data-ttu-id="2ee0e-136">AUTO</span><span class="sxs-lookup"><span data-stu-id="2ee0e-136">AUTO</span></span>  
 <span data-ttu-id="2ee0e-137">Esta opción permite al [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] seleccionar la granularidad de la escala de bloqueo que sea adecuada para el esquema de tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-137">This option allows the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] to select the lock escalation granularity that is appropriate for the table schema.</span></span>  
  
-   <span data-ttu-id="2ee0e-138">Si la tabla tiene particiones, se permitirá la extensión de bloqueo en la granularidad de árbol b (HoBT) o montón.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-138">If the table is partitioned, lock escalation will be allowed to the heap or B-tree (HoBT) granularity.</span></span> <span data-ttu-id="2ee0e-139">Una vez realizada la extensión del bloqueo hasta el nivel de HoBT, el bloqueo no se extenderá a la granularidad de TABLE más adelante.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-139">After the lock is escalated to the HoBT level, the lock will not be escalated later to TABLE granularity.</span></span>  
  
-   <span data-ttu-id="2ee0e-140">Si la tabla no tiene particiones, la extensión del bloqueo se aplicará a la granularidad de TABLE.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-140">If the table is not partitioned, the lock escalation will be done to the TABLE granularity.</span></span>  
  
 <span data-ttu-id="2ee0e-141">TABLE</span><span class="sxs-lookup"><span data-stu-id="2ee0e-141">TABLE</span></span>  
 <span data-ttu-id="2ee0e-142">La extensión de bloqueo se aplicará a la granularidad de nivel de tabla, independientemente de que la tabla tenga o no particiones.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-142">Lock escalation will be done at table-level granularity regardless of whether the table is partitioned or not partitioned.</span></span> <span data-ttu-id="2ee0e-143">TABLE es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-143">TABLE is the default value.</span></span>  
  
 <span data-ttu-id="2ee0e-144">DISABLE</span><span class="sxs-lookup"><span data-stu-id="2ee0e-144">DISABLE</span></span>  
 <span data-ttu-id="2ee0e-145">Evita la extensión de bloqueo en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-145">Prevents lock escalation in most cases.</span></span> <span data-ttu-id="2ee0e-146">No siempre se evitan los bloqueos de nivel de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-146">Table-level locks are not completely disallowed.</span></span> <span data-ttu-id="2ee0e-147">Por ejemplo, si está examinando una tabla que no tiene ningún índice clúster en el nivel de aislamiento serializable, [!INCLUDE[ssDE](../../includes/ssde-md.md)] debe realizar un bloqueo de la tabla para proteger la integridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-147">For example, when you are scanning a table that has no clustered index under the serializable isolation level, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] must take a table lock to protect data integrity.</span></span>  
  
 <span data-ttu-id="2ee0e-148">**Tabla replicada**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-148">**Table is replicated**</span></span>  
 <span data-ttu-id="2ee0e-149">Indica si se ha replicado la tabla en otra base de datos mediante la replicación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2ee0e-149">Indicates when the table is replicated to another database using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication.</span></span> <span data-ttu-id="2ee0e-150">Los valores posibles son `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-150">Possible values are `True` or `False`.</span></span>  
  
##  <a name="change-tracking-page"></a><a name="ChangeTracking"></a><span data-ttu-id="2ee0e-151">Change Tracking página</span><span class="sxs-lookup"><span data-stu-id="2ee0e-151">Change Tracking Page</span></span>  
 <span data-ttu-id="2ee0e-152">**Seguimiento de cambios**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-152">**Change Tracking**</span></span>  
 <span data-ttu-id="2ee0e-153">Indica si el seguimiento de cambios está habilitado para la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-153">Indicates whether change tracking is enabled for the table.</span></span> <span data-ttu-id="2ee0e-154">El valor predeterminado es `False`.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-154">The default value is `False`.</span></span>  
  
 <span data-ttu-id="2ee0e-155">Esta opción solo está disponible cuando el seguimiento de cambios está habilitado para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-155">This option is available only when change tracking is enabled for the database.</span></span>  
  
 <span data-ttu-id="2ee0e-156">Para habilitar el seguimiento de cambios, deberá contar con permisos para modificar la tabla y ésta deberá tener una clave principal.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-156">To enable change tracking, the table must have a primary key, and you must have permission to modify the table.</span></span> <span data-ttu-id="2ee0e-157">Puede configurar el seguimiento de cambios mediante [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ee0e-157">You can configure change tracking by using [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
 <span data-ttu-id="2ee0e-158">**Seguimiento de columnas actualizadas**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-158">**Track Columns Updated**</span></span>  
 <span data-ttu-id="2ee0e-159">Indica si el [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] hace un seguimiento de qué columnas se actualizaron.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-159">Indicates whether the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] tracks which columns were updated.</span></span>  
  
 <span data-ttu-id="2ee0e-160">Para obtener más información sobre el seguimiento de cambios, vea [Acerca del seguimiento de cambios &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2ee0e-160">For more information about Change Tracking, see [About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md).</span></span>  
  
##  <a name="filetable-page"></a><a name="FileTable"></a><span data-ttu-id="2ee0e-161">Página de FileTable</span><span class="sxs-lookup"><span data-stu-id="2ee0e-161">FileTable Page</span></span>  
 <span data-ttu-id="2ee0e-162">Muestra las propiedades de la tabla relacionada con las tablas FileTable.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-162">Displays properties of the table related to FileTables.</span></span> <span data-ttu-id="2ee0e-163">Para obtener más información, vea [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2ee0e-163">For more information, see [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span></span>  
  
 <span data-ttu-id="2ee0e-164">**Intercalación de la columna Nombre de una tabla FileTable**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-164">**FileTable name column collation**</span></span>  
 <span data-ttu-id="2ee0e-165">La intercalación que se aplica a la columna **Nombre** de FileTable.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-165">The collation that is applied to the **Name** column in a FileTable.</span></span> <span data-ttu-id="2ee0e-166">La columna **Nombre** contiene nombres de archivo y de directorio.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-166">The **Name** column contains file and directory names.</span></span>  
  
 <span data-ttu-id="2ee0e-167">**Nombre del directorio de FileTable**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-167">**FileTable directory name**</span></span>  
 <span data-ttu-id="2ee0e-168">La carpeta raíz para la tabla FileTable.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-168">The root folder for the FileTable.</span></span>  
  
 <span data-ttu-id="2ee0e-169">**Espacio de nombres de FileTable habilitado**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-169">**FileTable namespace enabled**</span></span>  
 <span data-ttu-id="2ee0e-170">Si es `True`, este valor indica que la tabla es una tabla FileTable.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-170">When `True`, this value indicates that the table is a FileTable.</span></span> <span data-ttu-id="2ee0e-171">Si cambia este valor a `False`, cambiará la tabla FileTable a una tabla de usuario ordinaria.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-171">If you change this value to `False`, you are changing the FileTable to an ordinary user table.</span></span> <span data-ttu-id="2ee0e-172">Si posteriormente desea cambiar la tabla a una tabla FileTable, la tabla tiene que pasar una comprobación de coherencia de FileTable antes de que la conversión se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-172">If you later want to change the table back to a FileTable, the table will have to pass a FileTable consistency check before the conversion succeeds.</span></span>  
  
##  <a name="storage-page"></a><a name="Storage"></a><span data-ttu-id="2ee0e-173">Página almacenamiento</span><span class="sxs-lookup"><span data-stu-id="2ee0e-173">Storage Page</span></span>  
 <span data-ttu-id="2ee0e-174">Muestra las propiedades relacionadas con el almacenamiento de la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-174">Displays the storage related properties of the selected table.</span></span>  
  
### <a name="compression"></a><span data-ttu-id="2ee0e-175">Compresión</span><span class="sxs-lookup"><span data-stu-id="2ee0e-175">Compression</span></span>  
 <span data-ttu-id="2ee0e-176">**Tipo de compresión**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-176">**Compression type**</span></span>  
 <span data-ttu-id="2ee0e-177">El tipo de compresión de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-177">The compression type of the table.</span></span> <span data-ttu-id="2ee0e-178">Esta propiedad solo está disponible para tablas que no tienen particiones.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-178">This property is only available for tables that are not partitioned.</span></span> <span data-ttu-id="2ee0e-179">Para obtener más información, consulte [Data Compression](../data-compression/data-compression.md).</span><span class="sxs-lookup"><span data-stu-id="2ee0e-179">For more information, see [Data Compression](../data-compression/data-compression.md).</span></span>  
  
 <span data-ttu-id="2ee0e-180">**Particiones que utilizan la compresión de página**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-180">**Partitions using page compression**</span></span>  
 <span data-ttu-id="2ee0e-181">El número de particiones que están utilizando la compresión de página.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-181">The partition numbers that are using page compression.</span></span> <span data-ttu-id="2ee0e-182">Esta propiedad solo está disponible para tablas con particiones.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-182">This property is only available for partitioned tables.</span></span>  
  
 <span data-ttu-id="2ee0e-183">**Particiones no comprimidas**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-183">**Partitions not compressed**</span></span>  
 <span data-ttu-id="2ee0e-184">El número de particiones que no se comprimen.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-184">The partition numbers that are not compressed.</span></span> <span data-ttu-id="2ee0e-185">Esta propiedad solo está disponible para tablas con particiones.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-185">This property is only available for partitioned tables.</span></span>  
  
 <span data-ttu-id="2ee0e-186">**Particiones que utilizan la compresión de fila**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-186">**Partitions using row compression**</span></span>  
 <span data-ttu-id="2ee0e-187">El número de particiones que están utilizando la compresión de fila.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-187">The partition numbers that are using row compression.</span></span> <span data-ttu-id="2ee0e-188">Esta propiedad solo está disponible para tablas con particiones.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-188">This property is only available for partitioned tables.</span></span>  
  
### <a name="filegroup"></a><span data-ttu-id="2ee0e-189">Grupo de archivos</span><span class="sxs-lookup"><span data-stu-id="2ee0e-189">Filegroup</span></span>  
 <span data-ttu-id="2ee0e-190">**Grupo de archivos de texto**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-190">**Text filegroup**</span></span>  
 <span data-ttu-id="2ee0e-191">Nombre del grupo de archivos que contiene los datos de texto de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-191">The name of the filegroup that contains the text data for the table.</span></span>  
  
 <span data-ttu-id="2ee0e-192">**Grupo de archivos**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-192">**Filegroup**</span></span>  
 <span data-ttu-id="2ee0e-193">El nombre del grupo de archivos que contiene la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-193">The name of the filegroup that contains the table.</span></span>  
  
 <span data-ttu-id="2ee0e-194">**La tabla tiene particiones**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-194">**Table is partitioned**</span></span>  
 <span data-ttu-id="2ee0e-195">Los valores posibles son `True` y `False`.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-195">Possible values are `True` and `False`.</span></span>  
  
 <span data-ttu-id="2ee0e-196">**Grupo de archivos de flujo de archivos**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-196">**Filestream filegroup**</span></span>  
 <span data-ttu-id="2ee0e-197">Especifique el nombre del grupo de archivos de datos FILESTREAM si la tabla tiene una columna `varbinary(max)` con el atributo FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-197">Specify the name of the FILESTREAM data filegroup if the table has a `varbinary(max)` column that has the FILESTREAM attribute.</span></span> <span data-ttu-id="2ee0e-198">El valor predeterminado es el grupo de archivos de datos de FILESTREAM predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-198">The default value is the default FILESTREAM data filegroup.</span></span>  
  
 <span data-ttu-id="2ee0e-199">Si la tabla no contiene datos de FILESTREAM, el campo estará en blanco.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-199">If the table does not contain FILESTREAM data, the field is blank.</span></span>  
  
### <a name="general"></a><span data-ttu-id="2ee0e-200">General</span><span class="sxs-lookup"><span data-stu-id="2ee0e-200">General</span></span>  
 <span data-ttu-id="2ee0e-201">**El formato de almacenamiento Vardecimal está habilitado**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-201">**Vardecimal storage format is enabled**</span></span>  
 <span data-ttu-id="2ee0e-202">Cuando `True` es, este valor de solo lectura indica `decimal` que `numeric` los tipos de datos y se almacenan con el formato de almacenamiento vardecimal.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-202">When `True`, this read-only value indicates that `decimal` and `numeric` data types are stored by using the vardecimal storage format.</span></span> <span data-ttu-id="2ee0e-203">Para cambiar esta opción, utilice la `vardecimal storage format` opción de [sp_tableoption](/sql/relational-databases/system-stored-procedures/sp-tableoption-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ee0e-203">To change this option, use the `vardecimal storage format` option of [sp_tableoption](/sql/relational-databases/system-stored-procedures/sp-tableoption-transact-sql).</span></span> <span data-ttu-id="2ee0e-204">El formato de almacenamiento Vardecimal está en desuso.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-204">Vardecimal storage format is deprecated.</span></span> <span data-ttu-id="2ee0e-205">En su lugar, use la compresión de fila.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-205">Use ROW compression instead.</span></span>  
  
 <span data-ttu-id="2ee0e-206">**Espacio de índice**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-206">**Index space**</span></span>  
 <span data-ttu-id="2ee0e-207">La cantidad de espacio en megabytes que ocupan los índices en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-207">The amount of space in megabytes that the indexes occupy in the table.</span></span> <span data-ttu-id="2ee0e-208">Este valor no incluye el uso del espacio del índice XML en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-208">This value does not include XML index space usage for the table.</span></span> <span data-ttu-id="2ee0e-209">Si los índices XML pertenecen a la tabla, use [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-209">If XML indexes belong to the table, use [sp_spaceused](/sql/relational-databases/system-stored-procedures/sp-spaceused-transact-sql) instead.</span></span>  
  
 <span data-ttu-id="2ee0e-210">**Recuento de filas**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-210">**Row count**</span></span>  
 <span data-ttu-id="2ee0e-211">Número de filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-211">The number of rows in the table.</span></span>  
  
 <span data-ttu-id="2ee0e-212">**Espacio de datos**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-212">**Data space**</span></span>  
 <span data-ttu-id="2ee0e-213">La cantidad de espacio en megabytes que ocupan los datos en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-213">The amount of space in megabytes that the data occupies in the table.</span></span>  
  
### <a name="partitioning"></a><span data-ttu-id="2ee0e-214">Creación de particiones</span><span class="sxs-lookup"><span data-stu-id="2ee0e-214">Partitioning</span></span>  
 <span data-ttu-id="2ee0e-215">Esta sección solo está disponible si la tabla tiene particiones.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-215">This section is only available if the table is partitioned.</span></span> <span data-ttu-id="2ee0e-216">Para obtener más información, vea [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="2ee0e-216">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="2ee0e-217">**Columna de partición**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-217">**Partition column**</span></span>  
 <span data-ttu-id="2ee0e-218">El nombre de la columna en la que la tabla tiene una partición.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-218">The name of the column on which the table is partitioned.</span></span>  
  
 <span data-ttu-id="2ee0e-219">**Esquema de partición**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-219">**Partition scheme**</span></span>  
 <span data-ttu-id="2ee0e-220">Nombre del esquema de partición si la tabla tiene particiones.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-220">Name of the partition scheme if the table is partitioned.</span></span> <span data-ttu-id="2ee0e-221">Si no tiene particiones, el campo está en blanco.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-221">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="2ee0e-222">**Número de particiones**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-222">**Number of partitions**</span></span>  
 <span data-ttu-id="2ee0e-223">El número de particiones de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-223">The number of partitions in the table.</span></span>  
  
 <span data-ttu-id="2ee0e-224">**Esquema de partición de FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="2ee0e-224">**FILESTREAM partition scheme**</span></span>  
 <span data-ttu-id="2ee0e-225">Nombre del esquema de partición de FILESTREAM si la tabla tiene particiones.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-225">The name of the FILESTREAM partition scheme if the table is partitioned.</span></span> <span data-ttu-id="2ee0e-226">Si no tiene particiones, el campo está en blanco.</span><span class="sxs-lookup"><span data-stu-id="2ee0e-226">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="2ee0e-227">El esquema de partición FILESTREAM debe ser simétrico al esquema especificado en la opción **Esquema de partición** .</span><span class="sxs-lookup"><span data-stu-id="2ee0e-227">The FILESTREAM partition scheme must be symmetric to the scheme that is specified in the **Partition scheme** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ee0e-228">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ee0e-228">See Also</span></span>  
 <span data-ttu-id="2ee0e-229">[Ver la definición de tabla](view-the-table-definition.md) </span><span class="sxs-lookup"><span data-stu-id="2ee0e-229">[View the Table Definition](view-the-table-definition.md) </span></span>  
 [<span data-ttu-id="2ee0e-230">Modificar columnas &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2ee0e-230">Modify Columns &#40;Database Engine&#41;</span></span>](../tables/modify-columns-database-engine.md)  
  
  
