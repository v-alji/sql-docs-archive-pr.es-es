---
title: Creacíón de una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server], creating
- database creation [SQL Server], SQL Server Management Studio
- creating databases
ms.assetid: 4c4beea2-6cbc-4352-9db6-49ea8130bb64
author: stevestein
ms.author: sstein
ms.openlocfilehash: fe42e394482e3abf4d87c00c6e79ee84db6ba278
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672112"
---
# <a name="create-a-database"></a><span data-ttu-id="b8756-102">Crear una base de datos</span><span class="sxs-lookup"><span data-stu-id="b8756-102">Create a Database</span></span>
  <span data-ttu-id="b8756-103">En este tema se describe cómo crear una base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8756-103">This topic describes how to create a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b8756-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="b8756-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b8756-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="b8756-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b8756-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="b8756-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b8756-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b8756-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="b8756-108">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="b8756-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="b8756-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b8756-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b8756-110">**Para crear una base de datos, use:**</span><span class="sxs-lookup"><span data-stu-id="b8756-110">**To create a database, using:**</span></span>  
  
     [<span data-ttu-id="b8756-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8756-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b8756-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b8756-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b8756-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="b8756-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b8756-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="b8756-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b8756-115">En una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]se pueden especificar 32.767 bases de datos como máximo.</span><span class="sxs-lookup"><span data-stu-id="b8756-115">A maximum of 32,767 databases can be specified on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b8756-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b8756-116">Prerequisites</span></span>  
  
-   <span data-ttu-id="b8756-117">La instrucción CREATE DATABASE debe ejecutarse en modo de confirmación automática (el modo predeterminado de administración de transacciones) y no se permite en una transacción explícita o implícita.</span><span class="sxs-lookup"><span data-stu-id="b8756-117">The CREATE DATABASE statement must run in autocommit mode (the default transaction management mode) and is not allowed in an explicit or implicit transaction.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b8756-118">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="b8756-118">Recommendations</span></span>  
  
-   <span data-ttu-id="b8756-119">Cada vez que se crea, modifica o quita una base de datos de usuario, se debe hacer una copia de seguridad de la base de datos [maestra](master-database.md) .</span><span class="sxs-lookup"><span data-stu-id="b8756-119">The [master](master-database.md) database should be backed up whenever a user database is created, modified, or dropped.</span></span>  
  
-   <span data-ttu-id="b8756-120">Cuando cree una base de datos, defina el mayor tamaño posible para los archivos de datos según la cantidad de datos máxima prevista para la base datos.</span><span class="sxs-lookup"><span data-stu-id="b8756-120">When you create a database, make the data files as large as possible based on the maximum amount of data you expect in the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b8756-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b8756-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b8756-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="b8756-122">Permissions</span></span>  
 <span data-ttu-id="b8756-123">Requiere el permiso CREATE DATABASE en la base de datos maestra, o los permisos CREATE ANY DATABASE o ALTER ANY DATABASE.</span><span class="sxs-lookup"><span data-stu-id="b8756-123">Requires CREATE DATABASE permission in the master database, or requires CREATE ANY DATABASE, or ALTER ANY DATABASE permission.</span></span>  
  
 <span data-ttu-id="b8756-124">Para mantener el control del uso del disco en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el permiso para crear bases de datos suele limitarse a un número reducido de cuentas de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="b8756-124">To maintain control over disk use on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], permission to create databases is typically limited to a few login accounts.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b8756-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b8756-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-database"></a><span data-ttu-id="b8756-126">Para crear una base de datos</span><span class="sxs-lookup"><span data-stu-id="b8756-126">To create a database</span></span>  
  
1.  <span data-ttu-id="b8756-127">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="b8756-127">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="b8756-128">Haga clic con el botón derecho en **Bases de datos**y, después, haga clic en **Nueva base de datos**.</span><span class="sxs-lookup"><span data-stu-id="b8756-128">Right-click **Databases**, and then click **New Database**.</span></span>  
  
3.  <span data-ttu-id="b8756-129">En **Nueva base de datos**, especifique un nombre de base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8756-129">In **New Database**, enter a database name.</span></span>  
  
4.  <span data-ttu-id="b8756-130">Si desea crear la base de datos aceptando todos los valores predeterminados, haga clic en **Aceptar**; de lo contrario, continúe con siguientes los pasos opcionales.</span><span class="sxs-lookup"><span data-stu-id="b8756-130">To create the database by accepting all default values, click **OK**; otherwise, continue with the following optional steps.</span></span>  
  
5.  <span data-ttu-id="b8756-131">Para cambiar el nombre del propietario, haga clic en ( **...** ) para seleccionar otro.</span><span class="sxs-lookup"><span data-stu-id="b8756-131">To change the owner name, click (**...**) to select another owner.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b8756-132">La opción **Usar indexación de texto completo** siempre está activada y atenuada porque, a partir de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], todas las bases de datos de usuario están habilitadas para texto completo.</span><span class="sxs-lookup"><span data-stu-id="b8756-132">The **Use full-text indexing** option is always checked and dimmed because, beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], all user databases are full-text enabled.</span></span>  
  
6.  <span data-ttu-id="b8756-133">Para cambiar los valores predeterminados de los archivos de datos y de registro de transacciones principales, en la cuadrícula **Archivos de la base de datos** , haga clic en la celda correspondiente y especifique el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="b8756-133">To change the default values of the primary data and transaction log files, in the **Database files** grid, click the appropriate cell and enter the new value.</span></span> <span data-ttu-id="b8756-134">Para obtener más información, consulte [Agregar archivos de datos o de registro a una base de datos](add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="b8756-134">For more information, see [Add Data or Log Files to a Database](add-data-or-log-files-to-a-database.md).</span></span>  
  
7.  <span data-ttu-id="b8756-135">Para cambiar la intercalación de la base de datos, seleccione la página **Opciones** y una intercalación de la lista.</span><span class="sxs-lookup"><span data-stu-id="b8756-135">To change the collation of the database, select the **Options** page, and then select a collation from the list.</span></span>  
  
8.  <span data-ttu-id="b8756-136">Para cambiar el modelo de recuperación, seleccione la página **Opciones** y un modelo de recuperación de la lista.</span><span class="sxs-lookup"><span data-stu-id="b8756-136">To change the recovery model, select the **Options** page and select a recovery model from the list.</span></span>  
  
9. <span data-ttu-id="b8756-137">Para cambiar opciones de base de datos, seleccione la página **Opciones** y modifique las opciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8756-137">To change database options, select the **Options** page, and then modify the database options.</span></span> <span data-ttu-id="b8756-138">Para obtener una descripción de cada opción, vea [Opciones de ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="b8756-138">For a description of each option, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
10. <span data-ttu-id="b8756-139">Para agregar un nuevo grupo de archivos, haga clic en la página **Grupos de archivos** .</span><span class="sxs-lookup"><span data-stu-id="b8756-139">To add a new filegroup, click the **Filegroups** page.</span></span> <span data-ttu-id="b8756-140">Haga clic en **Agregar** y especifique los valores para el grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="b8756-140">Click **Add** and then enter the values for the filegroup.</span></span>  
  
11. <span data-ttu-id="b8756-141">Para agregar una propiedad extendida a la base de datos, seleccione la página **Propiedades extendidas** .</span><span class="sxs-lookup"><span data-stu-id="b8756-141">To add an extended property to the database, select the **Extended Properties** page.</span></span>  
  
    1.  <span data-ttu-id="b8756-142">En la columna **Nombre** , escriba un nombre para la propiedad extendida.</span><span class="sxs-lookup"><span data-stu-id="b8756-142">In the **Name** column, enter a name for the extended property.</span></span>  
  
    2.  <span data-ttu-id="b8756-143">En la columna **Valor** , escriba el texto de la propiedad extendida.</span><span class="sxs-lookup"><span data-stu-id="b8756-143">In the **Value** column, enter the extended property text.</span></span> <span data-ttu-id="b8756-144">Por ejemplo, especifique una o varias instrucciones que describan la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8756-144">For example, enter one or more statements that describe the database.</span></span>  
  
12. <span data-ttu-id="b8756-145">Para crear la base de datos, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8756-145">To create the database, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b8756-146">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b8756-146">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database"></a><span data-ttu-id="b8756-147">Para crear una base de datos</span><span class="sxs-lookup"><span data-stu-id="b8756-147">To create a database</span></span>  
  
1.  <span data-ttu-id="b8756-148">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8756-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b8756-149">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="b8756-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b8756-150">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b8756-150">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b8756-151">Este ejemplo crea la base de datos `Sales`.</span><span class="sxs-lookup"><span data-stu-id="b8756-151">This example creates the database `Sales`.</span></span> <span data-ttu-id="b8756-152">Debido a que no se usa la palabra clave PRIMARY, el primer archivo (`Sales`_`dat`) se convierte en el archivo principal.</span><span class="sxs-lookup"><span data-stu-id="b8756-152">Because the keyword PRIMARY is not used, the first file (`Sales`_`dat`) becomes the primary file.</span></span> <span data-ttu-id="b8756-153">Como no se especifica MB ni KB en el parámetro SIZE del archivo `Sales`\_`dat` , se utiliza MB y el tamaño se asigna en megabytes.</span><span class="sxs-lookup"><span data-stu-id="b8756-153">Because neither MB nor KB is specified in the SIZE parameter for the `Sales`\_`dat` file, it uses MB and is allocated in megabytes.</span></span> <span data-ttu-id="b8756-154">Cada vez que se crea, modifica o quita una base de datos de usuario, se debe hacer una copia de seguridad de la base de datos `Sales`\_`log` se asigna en megabytes porque el sufijo `MB` se ha indicado explícitamente en el parámetro `SIZE` .</span><span class="sxs-lookup"><span data-stu-id="b8756-154">The `Sales`\_`log` file is allocated in megabytes because the `MB` suffix is explicitly stated in the `SIZE` parameter.</span></span>  
  
```sql  
USE master ;  
GO  
CREATE DATABASE Sales  
ON   
( NAME = Sales_dat,  
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\saledat.mdf',  
    SIZE = 10,  
    MAXSIZE = 50,  
    FILEGROWTH = 5 )  
LOG ON  
( NAME = Sales_log,  
    FILENAME = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\salelog.ldf',  
    SIZE = 5MB,  
    MAXSIZE = 25MB,  
    FILEGROWTH = 5MB ) ;  
GO  
```  
  
 <span data-ttu-id="b8756-155">Para obtener más ejemplos, vea [CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b8756-155">For more examples, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8756-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8756-156">See Also</span></span>  
 <span data-ttu-id="b8756-157">[Database Files and Filegroups](database-files-and-filegroups.md) </span><span class="sxs-lookup"><span data-stu-id="b8756-157">[Database Files and Filegroups](database-files-and-filegroups.md) </span></span>  
 <span data-ttu-id="b8756-158">[Adjuntar y separar bases de datos &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b8756-158">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="b8756-159">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b8756-159">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="b8756-160">Agregar archivos de datos o de registro a una base de datos</span><span class="sxs-lookup"><span data-stu-id="b8756-160">Add Data or Log Files to a Database</span></span>](add-data-or-log-files-to-a-database.md)  
  
  
