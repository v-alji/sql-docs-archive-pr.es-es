---
title: Agregar archivos de datos o de registro a una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], files
- adding data files
- adding files
- adding log files
- file additions [SQL Server], steps
- files [SQL Server], adding
- data additions [SQL Server]
ms.assetid: 8ead516a-1334-4f40-84b2-509d0a8ffa45
author: stevestein
ms.author: sstein
ms.openlocfilehash: f72e00f9dab422652237b4b85579c544d0cda9fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751137"
---
# <a name="add-data-or-log-files-to-a-database"></a><span data-ttu-id="da489-102">Agregar archivos de datos o de registro a una base de datos</span><span class="sxs-lookup"><span data-stu-id="da489-102">Add Data or Log Files to a Database</span></span>
  <span data-ttu-id="da489-103">En este tema se describe cómo agregar archivos de datos o de registro a una base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da489-103">This topic describes how to add data or log files to a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="da489-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="da489-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="da489-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="da489-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="da489-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="da489-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="da489-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="da489-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="da489-108">**Para agregar archivos de datos o de registro a una base de datos, use:**</span><span class="sxs-lookup"><span data-stu-id="da489-108">**To add data or log files to a database, using:**</span></span>  
  
     [<span data-ttu-id="da489-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="da489-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="da489-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="da489-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="da489-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="da489-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="da489-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="da489-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="da489-113">No se puede agregar o quitar un archivo mientras se está ejecutando una instrucción BACKUP.</span><span class="sxs-lookup"><span data-stu-id="da489-113">You cannot add or remove a file while a BACKUP statement is running.</span></span>  
  
-   <span data-ttu-id="da489-114">Para cada base de datos pueden especificarse hasta 32.767 archivos y 32.767 grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="da489-114">A maximum of 32,767 files and 32,767 filegroups can be specified for each database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="da489-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="da489-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="da489-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="da489-116">Permissions</span></span>  
 <span data-ttu-id="da489-117">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="da489-117">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="da489-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="da489-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-data-or-log-files-to-a-database"></a><span data-ttu-id="da489-119">Para agregar archivos de datos o de registro a una base de datos</span><span class="sxs-lookup"><span data-stu-id="da489-119">To add data or log files to a database</span></span>  
  
1.  <span data-ttu-id="da489-120">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="da489-120">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="da489-121">Expanda **Bases de datos**, haga clic con el botón derecho en la base de datos de la que quiera agregar los archivos y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="da489-121">Expand **Databases**, right-click the database from which to add the files, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="da489-122">En el cuadro de diálogo **Propiedades de la base de datos** , seleccione la página **Archivos** .</span><span class="sxs-lookup"><span data-stu-id="da489-122">In the **Database Properties** dialog box, select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="da489-123">Para agregar un archivo de datos o de registro de transacciones, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="da489-123">To add a data or transaction log file, click **Add**.</span></span>  
  
5.  <span data-ttu-id="da489-124">En la cuadrícula **Archivos de la base de datos** , escriba un nombre lógico para el archivo.</span><span class="sxs-lookup"><span data-stu-id="da489-124">In the **Database files** grid, enter a logical name for the file.</span></span> <span data-ttu-id="da489-125">El nombre debe ser único en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="da489-125">The file name must be unique within the database.</span></span>  
  
6.  <span data-ttu-id="da489-126">Seleccione el tipo de archivo: de datos o de registro.</span><span class="sxs-lookup"><span data-stu-id="da489-126">Select the file type, data or log.</span></span>  
  
7.  <span data-ttu-id="da489-127">En el caso de un archivo de datos, seleccione el grupo de archivos en el que se debe incluir el archivo de la lista, o bien seleccione **\<new filegroup>** para crear un nuevo grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="da489-127">For a data file, select the filegroup in which the file should be included from the list, or select **\<new filegroup>** to create a new filegroup.</span></span> <span data-ttu-id="da489-128">Los archivos de registro de transacciones no pueden formar parte de un grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="da489-128">Transaction logs cannot be put in filegroups.</span></span>  
  
8.  <span data-ttu-id="da489-129">Especifique el tamaño inicial del archivo.</span><span class="sxs-lookup"><span data-stu-id="da489-129">Specify the initial size of the file.</span></span> <span data-ttu-id="da489-130">Defina el mayor tamaño posible para los archivos de datos, según la cantidad de datos máxima prevista para la base datos.</span><span class="sxs-lookup"><span data-stu-id="da489-130">Make the data file as large as possible, based on the maximum amount of data you expect in the database.</span></span>  
  
9. <span data-ttu-id="da489-131">Para especificar cómo debe crecer el archivo, haga clic en ( **...** ) en la columna **Crecimiento automático**.</span><span class="sxs-lookup"><span data-stu-id="da489-131">To specify how the file should grow, click (**...**) in the **Autogrowth** column.</span></span> <span data-ttu-id="da489-132">Seleccione entre las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="da489-132">Select from the following options:</span></span>  
  
    1.  <span data-ttu-id="da489-133">Para permitir que el archivo actualmente seleccionado crezca cuando se necesite más espacio para los datos, active la casilla **Habilitar crecimiento automático** y, a continuación, elija una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="da489-133">To allow for the currently selected file to grow as more data space is required, select the **Enable Autogrowth** check box and then select from the following options:</span></span>  
  
    2.  <span data-ttu-id="da489-134">Para especificar que el archivo debe crecer en incrementos fijos, seleccione **En megabytes** y especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="da489-134">To specify that the file should grow by fixed increments, select **In Megabytes** and specify a value.</span></span>  
  
    3.  <span data-ttu-id="da489-135">Para especificar que el archivo debe crecer en un porcentaje de su tamaño actual, seleccione **En porcentaje** y especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="da489-135">To specify that the file should grow by a percentage of the current file size, select **In Percent** and specify a value.</span></span>  
  
10. <span data-ttu-id="da489-136">Para especificar el límite de tamaño máximo del archivo, seleccione una de estas opciones:</span><span class="sxs-lookup"><span data-stu-id="da489-136">To specify the maximum file size limit, select from the following options:</span></span>  
  
    1.  <span data-ttu-id="da489-137">Para especificar el tamaño máximo que se debe permitir que alcance el archivo, seleccione **Limitar el crecimiento de los archivos (MB)** y especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="da489-137">To specify the maximum size the file should be able to grow to, select **Restricted File Growth (MB)** and specify a value.</span></span>  
  
    2.  <span data-ttu-id="da489-138">Para que el archivo crezca tanto como sea necesario, seleccione **No limitar el crecimiento de los archivos**.</span><span class="sxs-lookup"><span data-stu-id="da489-138">To allow for the file to grow as much as needed, select **Unrestricted File Growth**.</span></span>  
  
    3.  <span data-ttu-id="da489-139">Para evitar que el archivo crezca, desactive la casilla **Habilitar crecimiento automático** .</span><span class="sxs-lookup"><span data-stu-id="da489-139">To prevent the file from growing, clear the **Enable Autogrowth** check box.</span></span> <span data-ttu-id="da489-140">El tamaño del archivo no superará el límite especificado en la columna **Tamaño inicial (MB)** .</span><span class="sxs-lookup"><span data-stu-id="da489-140">The size of the file will not grow beyond the value specified in the **Initial Size (MB)** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="da489-141">El tamaño máximo de una base de datos está determinado por la cantidad de espacio en disco disponible y los límites de licencia establecidos para la versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="da489-141">The maximum database size is determined by the amount of disk space available and the licensing limits determined by the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you are using.</span></span>  
  
11. <span data-ttu-id="da489-142">Especifique la ruta de acceso a la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="da489-142">Specify the path for the file location.</span></span> <span data-ttu-id="da489-143">La ruta debe existir antes de agregar el archivo.</span><span class="sxs-lookup"><span data-stu-id="da489-143">The specified path must exist before adding the file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="da489-144">De forma predeterminada, los datos y los registros de transacciones se colocan en la misma unidad y ruta de acceso para adecuarse a sistemas de un solo disco, pero puede que esto no resulte óptimo para los entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="da489-144">By default, the data and transaction logs are put on the same drive and path to accommodate single-disk systems, but may not be optimal for production environments.</span></span> <span data-ttu-id="da489-145">Para más información, consulte [Database Files and Filegroups](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="da489-145">For more information, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span>  
  
12. <span data-ttu-id="da489-146">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="da489-146">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="da489-147">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="da489-147">Using Transact-SQL</span></span>  
  
#### <a name="to-add-data-or-log-files-to-a-database"></a><span data-ttu-id="da489-148">Para agregar archivos de datos o de registro a una base de datos</span><span class="sxs-lookup"><span data-stu-id="da489-148">To add data or log files to a database</span></span>  
  
1.  <span data-ttu-id="da489-149">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da489-149">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="da489-150">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="da489-150">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="da489-151">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="da489-151">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="da489-152">El ejemplo agrega un grupo de archivos con dos archivos a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="da489-152">The example adds a filegroup with two files to a database.</span></span> <span data-ttu-id="da489-153">En el siguiente ejemplo se crea el grupo de archivos `Test1FG1` en la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] y se agregan dos archivos de 5 MB al grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="da489-153">The example creates the filegroup `Test1FG1` in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database and adds two 5-MB files to the filegroup.</span></span>  
  
 [!code-sql[DatabaseDDL#AlterDatabase2](../../snippets/tsql/SQL14/tsql/databaseddl/transact-sql/alterdatabase.sql#alterdatabase2)]  
  
 <span data-ttu-id="da489-154">Para obtener más ejemplos, vea [Opciones File y Filegroup de ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span><span class="sxs-lookup"><span data-stu-id="da489-154">For more examples, see [ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da489-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da489-155">See Also</span></span>  
 <span data-ttu-id="da489-156">[Database Files and Filegroups](database-files-and-filegroups.md) </span><span class="sxs-lookup"><span data-stu-id="da489-156">[Database Files and Filegroups](database-files-and-filegroups.md) </span></span>  
 <span data-ttu-id="da489-157">[Eliminar archivos de datos o de registro de una base de datos](delete-data-or-log-files-from-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="da489-157">[Delete Data or Log Files from a Database](delete-data-or-log-files-from-a-database.md) </span></span>  
 [<span data-ttu-id="da489-158">Aumentar el tamaño de una base de datos</span><span class="sxs-lookup"><span data-stu-id="da489-158">Increase the Size of a Database</span></span>](increase-the-size-of-a-database.md)  
  
  
