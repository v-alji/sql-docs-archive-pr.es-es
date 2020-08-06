---
title: Habilitar y configurar FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], enabling
ms.assetid: 78737e19-c65b-48d9-8fa9-aa6f1e1bce73
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f6c0e505bd32636d045519b36e439bc21c7079d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662113"
---
# <a name="enable-and-configure-filestream"></a><span data-ttu-id="bef93-102">Habilitar y configurar FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="bef93-102">Enable and Configure FILESTREAM</span></span>
  <span data-ttu-id="bef93-103">Para empezar a utilizar FILESTREAM, debe habilitarlo en la instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bef93-103">Before you can start to use FILESTREAM, you must enable FILESTREAM on the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="bef93-104">En este tema se describe cómo habilitar FILESTREAM con el Administrador de configuración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bef93-104">This topic describes how to enable FILESTREAM by using SQL Server Configuration Manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bef93-105">No puede habilitar FILESTREAM en una versión de 32 bits de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ejecute en un sistema operativo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="bef93-105">You cannot enable FILESTREAM on a 32-bit version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on a 64-bit operating system.</span></span>  
  
##  <a name="enabling-filestream"></a><a name="enabling"></a> <span data-ttu-id="bef93-106">Habilitar FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="bef93-106">Enabling FILESTREAM</span></span>  
  
#### <a name="to-enable-and-change-filestream-settings"></a><span data-ttu-id="bef93-107">Para habilitar y cambiar la configuración de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="bef93-107">To enable and change FILESTREAM settings</span></span>  
  
1.  <span data-ttu-id="bef93-108">En el menú **Inicio** , elija **Todos los programas**, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], **Herramientas de configuración**y, por último, **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bef93-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="bef93-109">En la lista de servicios, haga clic con el botón derecho en **Servicios de SQL Server**y, después, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="bef93-109">In the list of services, right-click **SQL Server Services**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="bef93-110">En el complemento **Administrador de configuración de SQL Server** , busque la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la que quiera habilitar FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="bef93-110">In the **SQL Server Configuration Manager** snap-in, locate the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which you want to enable FILESTREAM.</span></span>  
  
4.  <span data-ttu-id="bef93-111">Haga clic con el botón derecho en la instancia y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bef93-111">Right-click the instance, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="bef93-112">En el cuadro de diálogo **Propiedades de SQL Server** , haga clic en la pestaña **FILESTREAM** .</span><span class="sxs-lookup"><span data-stu-id="bef93-112">In the **SQL Server Properties** dialog box, click the **FILESTREAM** tab.</span></span>  
  
6.  <span data-ttu-id="bef93-113">Seleccione la casilla **Habilitar FILESTREAM para acceso Transact-SQL** .</span><span class="sxs-lookup"><span data-stu-id="bef93-113">Select the **Enable FILESTREAM for Transact-SQL access** check box.</span></span>  
  
7.  <span data-ttu-id="bef93-114">Si quiere leer y escribir datos FILESTREAM de Windows, haga clic en **Habilitar FILESTREAM para el acceso de transmisión por secuencias de E/S de archivos**.</span><span class="sxs-lookup"><span data-stu-id="bef93-114">If you want to read and write FILESTREAM data from Windows, click **Enable FILESTREAM for file I/O streaming access**.</span></span> <span data-ttu-id="bef93-115">Escriba el nombre del recurso compartido de Windows en el cuadro **Nombre de recurso compartido de Windows** .</span><span class="sxs-lookup"><span data-stu-id="bef93-115">Enter the name of the Windows share in the **Windows Share Name** box.</span></span>  
  
8.  <span data-ttu-id="bef93-116">Si los clientes remotos deben tener acceso a los datos FILESTREAM que están almacenados en este recurso compartido, seleccione **Permitir que los clientes remotos tengan acceso de transmisión por secuencias a los datos FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="bef93-116">If remote clients must access the FILESTREAM data that is stored on this share, select **Allow remote clients to have streaming access to FILESTREAM data**.</span></span>  
  
9. <span data-ttu-id="bef93-117">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="bef93-117">Click **Apply**.</span></span>  
  
10. <span data-ttu-id="bef93-118">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], haga clic en **Nueva consulta** para mostrar el Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="bef93-118">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to display the Query Editor.</span></span>  
  
11. <span data-ttu-id="bef93-119">En el Editor de consultas, escriba el siguiente código de [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="bef93-119">In Query Editor, enter the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
    ```sql  
    EXEC sp_configure filestream_access_level, 2  
    RECONFIGURE  
    ```  
  
12. <span data-ttu-id="bef93-120">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bef93-120">Click **Execute**.</span></span>  
  
13. <span data-ttu-id="bef93-121">Reinicie el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bef93-121">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  

  
##  <a name="best-practices"></a><a name="best"></a> <span data-ttu-id="bef93-122">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="bef93-122">Best Practices</span></span>  
  
###  <a name="physical-configuration-and-maintenance"></a><a name="config"></a><span data-ttu-id="bef93-123">Configuración física y mantenimiento</span><span class="sxs-lookup"><span data-stu-id="bef93-123">Physical Configuration and Maintenance</span></span>  
 <span data-ttu-id="bef93-124">Cuando configure volúmenes de almacenamiento FILESTREAM, tenga en cuenta las directrices siguientes:</span><span class="sxs-lookup"><span data-stu-id="bef93-124">When you set up FILESTREAM storage volumes, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="bef93-125">Desactive la opción de nombres cortos de archivo en equipos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="bef93-125">Turn off short file names on FILESTREAM computer systems.</span></span> <span data-ttu-id="bef93-126">Los nombres cortos de archivo requieren mucho más tiempo para su creación.</span><span class="sxs-lookup"><span data-stu-id="bef93-126">Short file names take significantly longer to create.</span></span> <span data-ttu-id="bef93-127">Para deshabilitar la opción de nombres cortos de archivo, emplee la utilidad **fsutil** de Windows.</span><span class="sxs-lookup"><span data-stu-id="bef93-127">To disable short file names, use the Windows **fsutil** utility.</span></span>  
  
-   <span data-ttu-id="bef93-128">Desfragmente periódicamente los equipos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="bef93-128">Regularly defragment FILESTREAM computer systems.</span></span>  
  
-   <span data-ttu-id="bef93-129">Use clústeres NTFS de 64 kB.</span><span class="sxs-lookup"><span data-stu-id="bef93-129">Use 64-KB NTFS clusters.</span></span> <span data-ttu-id="bef93-130">Los volúmenes comprimidos deben establecerse en clústeres NTFS de 4 kB.</span><span class="sxs-lookup"><span data-stu-id="bef93-130">Compressed volumes must be set to 4-KB NTFS clusters.</span></span>  
  
-   <span data-ttu-id="bef93-131">Deshabilite la indexación en volúmenes FILESTREAM y establezca **disablelastaccess** . Para establecer **disablelastaccess**, use la utilidad **fsutil** de Windows.</span><span class="sxs-lookup"><span data-stu-id="bef93-131">Disable indexing on FILESTREAM volumes and set **disablelastaccess** To set **disablelastaccess**, use the Windows **fsutil** utility.</span></span>  
  
-   <span data-ttu-id="bef93-132">Deshabilite el examen del antivirus de volúmenes FILESTREAM cuando no sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bef93-132">Disable antivirus scanning of FILESTREAM volumes when it is not unnecessary.</span></span> <span data-ttu-id="bef93-133">Cuando el análisis del antivirus sea necesario, evite el establecimiento de directivas que eliminen automáticamente los archivos causantes del problema.</span><span class="sxs-lookup"><span data-stu-id="bef93-133">If antivirus scanning is necessary, avoid setting policies that will automatically delete offending files.</span></span>  
  
-   <span data-ttu-id="bef93-134">Configure y ajuste el nivel RAID que proporcione la tolerancia a errores y el rendimiento requeridos por una aplicación.</span><span class="sxs-lookup"><span data-stu-id="bef93-134">Set up and tune the RAID level for fault tolerance and the performance that is required by an application.</span></span>  
  
||||||  
|-|-|-|-|-|  
|<span data-ttu-id="bef93-135">Nivel RAID</span><span class="sxs-lookup"><span data-stu-id="bef93-135">RAID level</span></span>|<span data-ttu-id="bef93-136">Rendimiento de escritura</span><span class="sxs-lookup"><span data-stu-id="bef93-136">Write performance</span></span>|<span data-ttu-id="bef93-137">Rendimiento de lectura</span><span class="sxs-lookup"><span data-stu-id="bef93-137">Read performance</span></span>|<span data-ttu-id="bef93-138">Tolerancia a errores</span><span class="sxs-lookup"><span data-stu-id="bef93-138">Fault tolerance</span></span>|<span data-ttu-id="bef93-139">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bef93-139">Remarks</span></span>|  
|<span data-ttu-id="bef93-140">RAID 5</span><span class="sxs-lookup"><span data-stu-id="bef93-140">RAID 5</span></span>|<span data-ttu-id="bef93-141">Normal</span><span class="sxs-lookup"><span data-stu-id="bef93-141">Normal</span></span>|<span data-ttu-id="bef93-142">Normal</span><span class="sxs-lookup"><span data-stu-id="bef93-142">Normal</span></span>|<span data-ttu-id="bef93-143">Excelente</span><span class="sxs-lookup"><span data-stu-id="bef93-143">Excellent</span></span>|<span data-ttu-id="bef93-144">El rendimiento es mejor que en el caso de un disco o JBOD y menor que RAID 0 o RAID 5 con creación de bandas.</span><span class="sxs-lookup"><span data-stu-id="bef93-144">Performance is better than one disk or JBOD; and less than RAID 0 or RAID 5 with striping.</span></span>|  
|<span data-ttu-id="bef93-145">RAID 0</span><span class="sxs-lookup"><span data-stu-id="bef93-145">RAID 0</span></span>|<span data-ttu-id="bef93-146">Excelente</span><span class="sxs-lookup"><span data-stu-id="bef93-146">Excellent</span></span>|<span data-ttu-id="bef93-147">Excelente</span><span class="sxs-lookup"><span data-stu-id="bef93-147">Excellent</span></span>|<span data-ttu-id="bef93-148">None</span><span class="sxs-lookup"><span data-stu-id="bef93-148">None</span></span>||  
|<span data-ttu-id="bef93-149">RAID 5 con creación de bandas</span><span class="sxs-lookup"><span data-stu-id="bef93-149">RAID 5 + stripping</span></span>|<span data-ttu-id="bef93-150">Excelente</span><span class="sxs-lookup"><span data-stu-id="bef93-150">Excellent</span></span>|<span data-ttu-id="bef93-151">Excelente</span><span class="sxs-lookup"><span data-stu-id="bef93-151">Excellent</span></span>|<span data-ttu-id="bef93-152">Excelente</span><span class="sxs-lookup"><span data-stu-id="bef93-152">Excellent</span></span>|<span data-ttu-id="bef93-153">Opción más cara.</span><span class="sxs-lookup"><span data-stu-id="bef93-153">Most expensive option.</span></span>|  
  

  
###  <a name="physical-database-design"></a><a name="database"></a><span data-ttu-id="bef93-154">Diseño físico de la base de datos</span><span class="sxs-lookup"><span data-stu-id="bef93-154">Physical Database Design</span></span>  
 <span data-ttu-id="bef93-155">Cuando diseñe una base de datos de FILESTREAM, tenga en cuenta las directrices siguientes:</span><span class="sxs-lookup"><span data-stu-id="bef93-155">When you design a FILESTREAM database, consider the following guidelines:</span></span>  
  
-   <span data-ttu-id="bef93-156">Las columnas FILESTREAM deben ir acompañadas de una `uniqueidentifier` columna ROWGUID correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bef93-156">FILESTREAM columns must be accompanied by a corresponding `uniqueidentifier`ROWGUID column.</span></span> <span data-ttu-id="bef93-157">Estos tipos de tablas también deben ir acompañados de un índice único.</span><span class="sxs-lookup"><span data-stu-id="bef93-157">These kinds of tables must also be accompanied by a unique index.</span></span> <span data-ttu-id="bef93-158">Normalmente, este índice no es un índice clúster.</span><span class="sxs-lookup"><span data-stu-id="bef93-158">Typically this index is not a clustered index.</span></span> <span data-ttu-id="bef93-159">Si la lógica de negocios de bases de datos requiere un índice clúster, debe asegurarse de que los valores almacenados en el índice no sean aleatorios.</span><span class="sxs-lookup"><span data-stu-id="bef93-159">If the databases business logic requires a clustered index, you have to make sure that the values stored in the index are not random.</span></span> <span data-ttu-id="bef93-160">Los valores aleatorios harán que el índice se vuelva a ordenar cada vez que se agregue o se quite una fila en la tabla.</span><span class="sxs-lookup"><span data-stu-id="bef93-160">Random values will cause the index to be reordered every time that a row is added or removed from the table.</span></span>  
  
-   <span data-ttu-id="bef93-161">Por razones de rendimiento, los contenedores y grupos de archivos FILESTREAM deben residir en volúmenes distintos del sistema operativo, base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , registro de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , tempdb o archivo de paginación.</span><span class="sxs-lookup"><span data-stu-id="bef93-161">For performance reasons, FILESTREAM filegroups and containers should reside on volumes other than the operating system, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log, tempdb, or paging file.</span></span>  
  
-   <span data-ttu-id="bef93-162">FILESTREAM no admite directamente la aplicación de directivas ni la administración del espacio.</span><span class="sxs-lookup"><span data-stu-id="bef93-162">Space management and policies are not directly supported by FILESTREAM.</span></span> <span data-ttu-id="bef93-163">Sin embargo, es posible administrar el espacio y aplicar directivas indirectamente mediante la asignación de cada grupo de archivos FILESTREAM a un volumen independiente y usando las características de administración del volumen.</span><span class="sxs-lookup"><span data-stu-id="bef93-163">However, you can manage space and apply policies indirectly by assigning each FILESTREAM filegroup to a separate volume and using the volume's management features.</span></span>  
  
  
