---
title: Movimiento de una base de datos protegida por TDE a otra instancia de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, moving
- TDE, moving a database
ms.assetid: fb420903-df54-4016-bab6-49e6dfbdedc7
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 3b03b4d9ecf31e9953fd3e22cec5c51bbacc0c25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752066"
---
# <a name="move-a-tde-protected-database-to-another-sql-server"></a><span data-ttu-id="918de-102">Mover una base de datos protegida por TDE a otra instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="918de-102">Move a TDE Protected Database to Another SQL Server</span></span>
  <span data-ttu-id="918de-103">En este tema se describe cómo proteger una base de datos mediante el uso del cifrado de datos transparente (TDE) y, a continuación, mover la base de datos a otra instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="918de-103">This topic describes how to protect a database by using transparent data encryption (TDE), and then move the database to another instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="918de-104">TDE realiza el cifrado y descifrado de E/S en tiempo real de los archivos de datos y de registro.</span><span class="sxs-lookup"><span data-stu-id="918de-104">TDE performs real-time I/O encryption and decryption of the data and log files.</span></span> <span data-ttu-id="918de-105">El cifrado usa una clave de cifrado de base de datos (DEK), que se almacena en el registro de arranque de la base de datos de disponibilidad durante la recuperación.</span><span class="sxs-lookup"><span data-stu-id="918de-105">The encryption uses a database encryption key (DEK), which is stored in the database boot record for availability during recovery.</span></span> <span data-ttu-id="918de-106">DEK es una clave simétrica protegida mediante un certificado almacenado en la base de datos maestra (`master`) del servidor o una clave asimétrica protegida por un módulo EKM.</span><span class="sxs-lookup"><span data-stu-id="918de-106">The DEK is a symmetric key secured by using a certificate stored in the `master` database of the server or an asymmetric key protected by an EKM module.</span></span>  
  
 <span data-ttu-id="918de-107">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="918de-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="918de-108">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="918de-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="918de-109">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="918de-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="918de-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="918de-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="918de-111">**Para crear una base de datos protegida por el cifrado de datos transparente, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="918de-111">**To create a database protected by transparent data encryption, using:**</span></span>  
  
     [<span data-ttu-id="918de-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="918de-112">SQL Server Management Studio</span></span>](#SSMSCreate)  
  
     [<span data-ttu-id="918de-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="918de-113">Transact-SQL</span></span>](#TsqlCreate)  
  
-   <span data-ttu-id="918de-114">**Para mover una base de datos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="918de-114">**To move a database, using:**</span></span>  
  
     [<span data-ttu-id="918de-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="918de-115">SQL Server Management Studio</span></span>](#SSMSMove)  
  
     [<span data-ttu-id="918de-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="918de-116">Transact-SQL</span></span>](#TsqlMove)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="918de-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="918de-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="918de-118">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="918de-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="918de-119">Cuando se mueve una base de datos protegida por TDE, también debe mover el certificado o la clave asimétrica que se usan para abrir DEK.</span><span class="sxs-lookup"><span data-stu-id="918de-119">When moving a TDE protected database, you must also move the certificate or asymmetric key that is used to open the DEK.</span></span> <span data-ttu-id="918de-120">El certificado o la clave asimétrica se deben instalar en la `master` base de datos del servidor de destino para que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pueda tener acceso a los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="918de-120">The certificate or asymmetric key must be installed in the `master` database of the destination server, so that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can access the database files.</span></span> <span data-ttu-id="918de-121">Para obtener más información, vea [Cifrado de datos transparente &#40;TDE&#41;](transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="918de-121">For more information, see [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span></span>  
  
-   <span data-ttu-id="918de-122">Debe conservar copias tanto del archivo de certificado como del archivo de clave privada para recuperar el certificado.</span><span class="sxs-lookup"><span data-stu-id="918de-122">You must retain copies of both the certificate file and the private key file in order to recover the certificate.</span></span> <span data-ttu-id="918de-123">No es necesario que la contraseña de la clave privada sea la misma que la contraseña de la clave maestra de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="918de-123">The password for the private key does not have to be the same as the database master key password.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="918de-124">almacena los archivos creados aquí en **c:\Archivos de programa\Microsoft SQL Server\MSSQL12. MSSQLSERVER\MSSQL\DATA** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="918de-124">stores the files created here in **C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA** by default.</span></span> <span data-ttu-id="918de-125">Los nombres de los archivos y las ubicaciones pueden ser distintos.</span><span class="sxs-lookup"><span data-stu-id="918de-125">Your file names and locations might be different.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="918de-126">Seguridad</span><span class="sxs-lookup"><span data-stu-id="918de-126">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="918de-127">Permisos</span><span class="sxs-lookup"><span data-stu-id="918de-127">Permissions</span></span>  
  
-   <span data-ttu-id="918de-128">Requiere `CONTROL DATABASE` el permiso en la `master` base de datos para crear la clave maestra de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="918de-128">Requires `CONTROL DATABASE` permission on the `master` database to create the database master key.</span></span>  
  
-   <span data-ttu-id="918de-129">Requiere el `CREATE CERTIFICATE` permiso en la `master` base de datos para crear el certificado que protege DEK.</span><span class="sxs-lookup"><span data-stu-id="918de-129">Requires `CREATE CERTIFICATE` permission on the `master` database to create the certificate that protects the DEK.</span></span>  
  
-   <span data-ttu-id="918de-130">Requiere el permiso `CONTROL DATABASE` para la base de datos cifrada y el permiso `VIEW DEFINITION` para el certificado o la clave asimétrica usados para cifrar la clave de cifrado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="918de-130">Requires `CONTROL DATABASE` permission on the encrypted database and `VIEW DEFINITION` permission on the certificate or asymmetric key that is used to encrypt the database encryption key.</span></span>  
  
##  <a name="to-create-a-database-protected-by-transparent-data-encryption"></a><a name="SSMSProcedure"></a> <span data-ttu-id="918de-131">Para crear una base de datos protegida por el cifrado de datos transparente</span><span class="sxs-lookup"><span data-stu-id="918de-131">To create a database protected by transparent data encryption</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSCreate"></a> <span data-ttu-id="918de-132">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="918de-132">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="918de-133">Cree una clave maestra de base de datos y un certificado en la `master` base de datos.</span><span class="sxs-lookup"><span data-stu-id="918de-133">Create a database master key and certificate in the `master` database.</span></span> <span data-ttu-id="918de-134">Para obtener más información, vea **Usar Transact-SQL** más adelante.</span><span class="sxs-lookup"><span data-stu-id="918de-134">For more information, see **Using Transact-SQL** below.</span></span>  
  
2.  <span data-ttu-id="918de-135">Cree una copia de seguridad del certificado de servidor en la `master` base de datos.</span><span class="sxs-lookup"><span data-stu-id="918de-135">Create a backup of the server certificate in the `master` database.</span></span> <span data-ttu-id="918de-136">Para obtener más información, vea **Usar Transact-SQL** más adelante.</span><span class="sxs-lookup"><span data-stu-id="918de-136">For more information, see **Using Transact-SQL** below.</span></span>  
  
3.  <span data-ttu-id="918de-137">En el Explorador de objetos, haga clic con el botón derecho en la carpeta **Bases de datos** y seleccione **Nueva base de datos**.</span><span class="sxs-lookup"><span data-stu-id="918de-137">In Object Explorer, right-click the **Databases** folder and select **New Database**.</span></span>  
  
4.  <span data-ttu-id="918de-138">En el cuadro de diálogo **Nueva base de datos** , en el cuadro **Nombre de la base de datos** , escriba el nombre de la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="918de-138">In the **New Database** dialog box, in the **Database name** box, enter the name of the new database.</span></span>  
  
5.  <span data-ttu-id="918de-139">En el cuadro **Propietario** , escriba el nombre del propietario de la nueva base de datos.</span><span class="sxs-lookup"><span data-stu-id="918de-139">In the **Owner** box, enter the name of the new database's owner.</span></span> <span data-ttu-id="918de-140">Como alternativa, haga clic en los puntos suspensivos **(...)** para abrir el cuadro de diálogo **Seleccionar propietario de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="918de-140">Alternately, click the ellipsis **(...)** to open the **Select Database Owner** dialog box.</span></span> <span data-ttu-id="918de-141">Para obtener más información sobre la creación de una nueva base de datos, vea [Create a Database](../../databases/create-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="918de-141">For more information on creating a new database, see [Create a Database](../../databases/create-a-database.md).</span></span>  
  
6.  <span data-ttu-id="918de-142">En el Explorador de objetos, haga clic en el signo más para expandir la carpeta **Bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="918de-142">In Object Explorer, click the plus sign to expand the **Databases** folder.</span></span>  
  
7.  <span data-ttu-id="918de-143">Haga clic con el botón derecho en la base de datos que creó, seleccione **Tareas**y **Administrar cifrado de base de datos**.</span><span class="sxs-lookup"><span data-stu-id="918de-143">Right-click the database you created, point to **Tasks**, and select **Manage Database Encryption**.</span></span>  
  
     <span data-ttu-id="918de-144">En el cuadro de diálogo **Administrar cifrado de base de datos** están disponibles las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="918de-144">The following options are available on the **Manage Database Encryption** dialog box.</span></span>  
  
     <span data-ttu-id="918de-145">**Algoritmo de cifrado**</span><span class="sxs-lookup"><span data-stu-id="918de-145">**Encryption Algorithm**</span></span>  
     <span data-ttu-id="918de-146">Muestra o establece el algoritmo que se debe utilizar para el cifrado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="918de-146">Displays or sets the algorithm to use for database encryption.</span></span> <span data-ttu-id="918de-147">`AES128` es el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="918de-147">`AES128` is the default algorithm.</span></span> <span data-ttu-id="918de-148">Este campo no puede estar vacío.</span><span class="sxs-lookup"><span data-stu-id="918de-148">This field cannot be blank.</span></span> <span data-ttu-id="918de-149">Para obtener más información sobre algoritmos de cifrado, vea [Choose an Encryption Algorithm](choose-an-encryption-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="918de-149">For more information on encryption algorithms, see [Choose an Encryption Algorithm](choose-an-encryption-algorithm.md).</span></span>  
  
     <span data-ttu-id="918de-150">**Usar certificado de servidor**</span><span class="sxs-lookup"><span data-stu-id="918de-150">**Use server certificate**</span></span>  
     <span data-ttu-id="918de-151">Establece que el cifrado se proteja mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="918de-151">Sets the encryption to be secured by a certificate.</span></span> <span data-ttu-id="918de-152">Seleccione uno de la lista.</span><span class="sxs-lookup"><span data-stu-id="918de-152">Select one from the list.</span></span> <span data-ttu-id="918de-153">Si no tiene el permiso `VIEW DEFINITION` para los certificados de servidor, esta lista estará vacía.</span><span class="sxs-lookup"><span data-stu-id="918de-153">If you do not have the `VIEW DEFINITION` permission on server certificates, this list will be empty.</span></span> <span data-ttu-id="918de-154">Si se selecciona un método de cifrado de certificado, este valor no puede estar vacío.</span><span class="sxs-lookup"><span data-stu-id="918de-154">If a certificate method of encryption is selected, this value cannot be empty.</span></span> <span data-ttu-id="918de-155">Para obtener más información acerca de los certificados, vea [SQL Server Certificates and Asymmetric Keys](../sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="918de-155">For more information about certificates, see [SQL Server Certificates and Asymmetric Keys](../sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
     <span data-ttu-id="918de-156">**Usar clave asimétrica de servidor**</span><span class="sxs-lookup"><span data-stu-id="918de-156">**Use server asymmetric key**</span></span>  
     <span data-ttu-id="918de-157">Establece que el cifrado se proteja mediante una clave asimétrica.</span><span class="sxs-lookup"><span data-stu-id="918de-157">Sets the encryption to be secured by an asymmetric key.</span></span> <span data-ttu-id="918de-158">Solo se muestran las claves asimétricas disponibles.</span><span class="sxs-lookup"><span data-stu-id="918de-158">Only available asymmetric keys are displayed.</span></span> <span data-ttu-id="918de-159">Solo una clave asimétrica protegida por un módulo EKM puede cifrar una base de datos mediante TDE.</span><span class="sxs-lookup"><span data-stu-id="918de-159">Only an asymmetric key protected by an EKM module can encrypt a database using TDE.</span></span>  
  
     <span data-ttu-id="918de-160">**Activar cifrado de base de datos**</span><span class="sxs-lookup"><span data-stu-id="918de-160">**Set Database Encryption On**</span></span>  
     <span data-ttu-id="918de-161">Modifica la base de datos para habilitar (activada) o deshabilitar (sin activar) TDE.</span><span class="sxs-lookup"><span data-stu-id="918de-161">Alters the database to turn on (checked) or turn off (unchecked) TDE.</span></span>  
  
8.  <span data-ttu-id="918de-162">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="918de-162">When finished, click **OK**.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlCreate"></a> <span data-ttu-id="918de-163">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="918de-163">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="918de-164">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="918de-164">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="918de-165">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="918de-165">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="918de-166">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="918de-166">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Create a database master key and a certificate in the master database.  
    USE master ;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1';  
    GO  
    CREATE CERTIFICATE TestSQLServerCert   
    WITH SUBJECT = 'Certificate to protect TDE key'  
    GO  
    -- Create a backup of the server certificate in the master database.  
    -- The following code stores the backup of the certificate and the private key file in the default data location for this instance of SQL Server   
    -- (C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA).  
  
    BACKUP CERTIFICATE TestSQLServerCert   
    TO FILE = 'TestSQLServerCert'  
    WITH PRIVATE KEY   
    (  
        FILE = 'SQLPrivateKeyFile',  
        ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1'  
    );  
    GO  
    -- Create a database to be protected by TDE.  
    CREATE DATABASE CustRecords ;  
    GO  
    -- Switch to the new database.  
    -- Create a database encryption key, that is protected by the server certificate in the master database.   
    -- Alter the new database to encrypt the database using TDE.  
    USE CustRecords;  
    GO  
    CREATE DATABASE ENCRYPTION KEY  
    WITH ALGORITHM = AES_128  
    ENCRYPTION BY SERVER CERTIFICATE TestSQLServerCert;  
    GO  
    ALTER DATABASE CustRecords  
    SET ENCRYPTION ON;  
    GO  
    ```  
  
 <span data-ttu-id="918de-167">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="918de-167">For more information, see:</span></span>  
  
-   [<span data-ttu-id="918de-168">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="918de-168">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="918de-169">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="918de-169">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="918de-170">BACKUP CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="918de-170">BACKUP CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-certificate-transact-sql)  
  
-   [<span data-ttu-id="918de-171">CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="918de-171">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
-   [<span data-ttu-id="918de-172">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="918de-172">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)  
  
-   [<span data-ttu-id="918de-173">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="918de-173">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
##  <a name="to-move-a-database"></a><a name="TsqlProcedure"></a><span data-ttu-id="918de-174">Para quitar una base de datos</span><span class="sxs-lookup"><span data-stu-id="918de-174">To move a database</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSMove"></a> <span data-ttu-id="918de-175">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="918de-175">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="918de-176">En el Explorador de objetos, haga clic con el botón derecho en la base de datos que cifró anteriormente, seleccione **Tareas** y **Separar...** .</span><span class="sxs-lookup"><span data-stu-id="918de-176">In Object Explorer, right-click the database you encrypted above, point to **Tasks** and select **Detach...**.</span></span>  
  
     <span data-ttu-id="918de-177">En el cuadro de diálogo **Separar base de datos** están disponibles las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="918de-177">The following options are available in the **Detach Database** dialog box.</span></span>  
  
     <span data-ttu-id="918de-178">**Bases de datos que se van a separar**</span><span class="sxs-lookup"><span data-stu-id="918de-178">**Databases to detach**</span></span>  
     <span data-ttu-id="918de-179">Enumera las bases de datos que se van a separar.</span><span class="sxs-lookup"><span data-stu-id="918de-179">Lists the databases to detach.</span></span>  
  
     <span data-ttu-id="918de-180">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="918de-180">**Database Name**</span></span>  
     <span data-ttu-id="918de-181">Muestra el nombre de la base de datos que se va a separar.</span><span class="sxs-lookup"><span data-stu-id="918de-181">Displays the name of the database to be detached.</span></span>  
  
     <span data-ttu-id="918de-182">**Quitar conexiones**</span><span class="sxs-lookup"><span data-stu-id="918de-182">**Drop Connections**</span></span>  
     <span data-ttu-id="918de-183">Desconecta las conexiones a la base de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="918de-183">Disconnect connections to the specified database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="918de-184">No puede separar una base de datos con conexiones activas.</span><span class="sxs-lookup"><span data-stu-id="918de-184">You cannot detach a database with active connections.</span></span>  
  
     <span data-ttu-id="918de-185">**Actualizar estadísticas**</span><span class="sxs-lookup"><span data-stu-id="918de-185">**Update Statistics**</span></span>  
     <span data-ttu-id="918de-186">De forma predeterminada, la operación de separación conserva las estadísticas de optimización obsoletas al separar la base de datos; para actualizar las estadísticas de optimización existentes, haga clic en esta casilla.</span><span class="sxs-lookup"><span data-stu-id="918de-186">By default, the detach operation retains any out-of-date optimization statistics when detaching the database; to update the existing optimization statistics, click this check box.</span></span>  
  
     <span data-ttu-id="918de-187">**Mantener catálogos de texto completo**</span><span class="sxs-lookup"><span data-stu-id="918de-187">**Keep Full-Text Catalogs**</span></span>  
     <span data-ttu-id="918de-188">De forma predeterminada, la operación de separación conserva los catálogos de texto completo asociados a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="918de-188">By default, the detach operation keeps any full-text catalogs that are associated with the database.</span></span> <span data-ttu-id="918de-189">Para quitarlos, desactive la casilla **Mantener catálogos de texto completo** .</span><span class="sxs-lookup"><span data-stu-id="918de-189">To remove them, clear the **Keep Full-Text Catalogs** check box.</span></span> <span data-ttu-id="918de-190">Esta opción solo aparece cuando se está actualizando una base de datos desde [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="918de-190">This option appears only when you are upgrading a database from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="918de-191">**Estado**</span><span class="sxs-lookup"><span data-stu-id="918de-191">**Status**</span></span>  
     <span data-ttu-id="918de-192">Muestra uno de los siguientes estados: **Listo** o **No está listo**.</span><span class="sxs-lookup"><span data-stu-id="918de-192">Displays one of the following states: **Ready** or **Not ready**.</span></span>  
  
     <span data-ttu-id="918de-193">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="918de-193">**Message**</span></span>  
     <span data-ttu-id="918de-194">En la columna **Mensaje** puede aparecer información sobre la base de datos, tal y como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="918de-194">The **Message** column may display information about the database, as follows:</span></span>  
  
    -   <span data-ttu-id="918de-195">Cuando una base de datos está implicada en una replicación, el **Estado** es **No está listo** y la columna **Mensaje** muestra **Base de datos replicada**.</span><span class="sxs-lookup"><span data-stu-id="918de-195">When a database is involved with replication, the **Status** is **Not ready** and the **Message** column displays **Database replicated**.</span></span>  
  
    -   <span data-ttu-id="918de-196">Cuando una base de datos tiene una o varias conexiones activas, el valor de **Estado** es **No está listo** y en la columna **Mensaje** se muestra _<número_de_conexiones_activas>_ **Conexiones activas** (por ejemplo: **1 conexión activa**).</span><span class="sxs-lookup"><span data-stu-id="918de-196">When a database has one or more active connections, the **Status** is **Not ready** and the **Message** column displays _<number_of_active_connections>_**Active connection(s)** - for example: **1 Active connection(s)**.</span></span> <span data-ttu-id="918de-197">Antes de separar la base de datos, debe desconectar todas las conexiones activas seleccionando **Quitar conexiones**.</span><span class="sxs-lookup"><span data-stu-id="918de-197">Before you can detach the database, you need to disconnect any active connections by selecting **Drop Connections**.</span></span>  
  
     <span data-ttu-id="918de-198">Para obtener más información acerca de un mensaje, haga clic en el texto con hipervínculo para abrir el Monitor de actividad.</span><span class="sxs-lookup"><span data-stu-id="918de-198">To obtain more information about a message, click the hyperlinked text to open Activity Monitor.</span></span>  
  
2.  <span data-ttu-id="918de-199">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="918de-199">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="918de-200">Con el Explorador de Windows, mueva o copie los archivos de la base de datos desde el servidor de origen a la misma ubicación en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="918de-200">Using Windows Explorer, move or copy the database files from the source server to the same location on the destination server.</span></span>  
  
4.  <span data-ttu-id="918de-201">Con el Explorador de Windows, mueva o copie la copia de seguridad del certificado del servidor y el archivo de clave privada desde el servidor de origen a la misma ubicación del servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="918de-201">Using Windows Explorer, move or copy the backup of the server certificate and the private key file from the source server to the same location on the destination server.</span></span>  
  
5.  <span data-ttu-id="918de-202">Cree una clave maestra de la base de datos en la instancia de destino de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="918de-202">Create a database master key on the destination instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="918de-203">Para obtener más información, vea **Usar Transact-SQL** más adelante.</span><span class="sxs-lookup"><span data-stu-id="918de-203">For more information, see **Using Transact-SQL** below.</span></span>  
  
6.  <span data-ttu-id="918de-204">Vuelva a crear el certificado del servidor mediante el archivo de copia de seguridad del certificado del servidor original.</span><span class="sxs-lookup"><span data-stu-id="918de-204">Recreate the server certificate by using the original server certificate backup file.</span></span> <span data-ttu-id="918de-205">Para obtener más información, vea **Usar Transact-SQL** más adelante.</span><span class="sxs-lookup"><span data-stu-id="918de-205">For more information, see **Using Transact-SQL** below.</span></span>  
  
7.  <span data-ttu-id="918de-206">En el Explorador de objetos, en [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], haga clic con el botón derecho en la carpeta **Bases de datos** y, después, seleccione **Adjuntar...** .</span><span class="sxs-lookup"><span data-stu-id="918de-206">In Object Explorer in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], right-click the **Databases** folder and select **Attach...**.</span></span>  
  
8.  <span data-ttu-id="918de-207">En el cuadro de diálogo **Adjuntar bases de datos** , en **Bases de datos que se van a adjuntar**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="918de-207">In the **Attach Databases** dialog box, under **Databases to attach**, click **Add**.</span></span>  
  
9. <span data-ttu-id="918de-208">En el cuadro de diálogo **buscar archivos de base de datos-**_SERVER_NAME_ , seleccione el archivo de base de datos que desea adjuntar al nuevo servidor y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="918de-208">In the **Locate Database Files -**_server_name_ dialog box, select the database file to attach to the new server and click **OK**.</span></span>  
  
     <span data-ttu-id="918de-209">En el cuadro de diálogo **Adjuntar bases de datos** están disponibles las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="918de-209">The following options are available in the **Attach Databases** dialog box.</span></span>  
  
     <span data-ttu-id="918de-210">**Bases de datos que se van a adjuntar**</span><span class="sxs-lookup"><span data-stu-id="918de-210">**Databases to attach**</span></span>  
     <span data-ttu-id="918de-211">Muestra información sobre las bases de datos seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="918de-211">Displays information about the selected databases.</span></span>  
  
     \<no column header>  
     <span data-ttu-id="918de-212">Muestra un icono que indica el estado de la operación de adjuntar.</span><span class="sxs-lookup"><span data-stu-id="918de-212">Displays an icon indicating the status of the attach operation.</span></span> <span data-ttu-id="918de-213">Los iconos posibles se indican en la descripción de **Estado** , que encontrará más adelante.</span><span class="sxs-lookup"><span data-stu-id="918de-213">The possible icons are described in the **Status** description, below).</span></span>  
  
     <span data-ttu-id="918de-214">**Ubicación del archivo MDF**</span><span class="sxs-lookup"><span data-stu-id="918de-214">**MDF File Location**</span></span>  
     <span data-ttu-id="918de-215">Muestra la ruta de acceso y el nombre del archivo MDF seleccionado.</span><span class="sxs-lookup"><span data-stu-id="918de-215">Displays the path and file name of the selected MDF file.</span></span>  
  
     <span data-ttu-id="918de-216">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="918de-216">**Database Name**</span></span>  
     <span data-ttu-id="918de-217">Muestra el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="918de-217">Displays the name of the database.</span></span>  
  
     <span data-ttu-id="918de-218">**Adjuntar como**</span><span class="sxs-lookup"><span data-stu-id="918de-218">**Attach As**</span></span>  
     <span data-ttu-id="918de-219">Opcionalmente, especifica un nombre distinto con el que se debe adjuntar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="918de-219">Optionally, specifies a different name for the database to attach as.</span></span>  
  
     <span data-ttu-id="918de-220">**Propietario**</span><span class="sxs-lookup"><span data-stu-id="918de-220">**Owner**</span></span>  
     <span data-ttu-id="918de-221">Ofrece una lista desplegable de los posibles propietarios de base de datos desde los que opcionalmente puede seleccionarse otro propietario.</span><span class="sxs-lookup"><span data-stu-id="918de-221">Provides a drop-down list of possible database owners from which you can optionally select a different owner.</span></span>  
  
     <span data-ttu-id="918de-222">**Estado**</span><span class="sxs-lookup"><span data-stu-id="918de-222">**Status**</span></span>  
     <span data-ttu-id="918de-223">Muestra el estado de la base de datos de acuerdo con la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="918de-223">Displays the status of the database according to the following table.</span></span>  
  
    |<span data-ttu-id="918de-224">Icono</span><span class="sxs-lookup"><span data-stu-id="918de-224">Icon</span></span>|<span data-ttu-id="918de-225">Texto de estado</span><span class="sxs-lookup"><span data-stu-id="918de-225">Status text</span></span>|<span data-ttu-id="918de-226">Descripción</span><span class="sxs-lookup"><span data-stu-id="918de-226">Description</span></span>|  
    |----------|-----------------|-----------------|  
    |<span data-ttu-id="918de-227">(Sin icono)</span><span class="sxs-lookup"><span data-stu-id="918de-227">(No icon)</span></span>|<span data-ttu-id="918de-228">(Sin texto)</span><span class="sxs-lookup"><span data-stu-id="918de-228">(No text)</span></span>|<span data-ttu-id="918de-229">La operación de adjuntar no se ha iniciado o puede estar pendiente para este objeto.</span><span class="sxs-lookup"><span data-stu-id="918de-229">Attach operation has not been started or may be pending for this object.</span></span> <span data-ttu-id="918de-230">Es la opción predeterminada al abrir el diálogo.</span><span class="sxs-lookup"><span data-stu-id="918de-230">This is the default when the dialog is opened.</span></span>|  
    |<span data-ttu-id="918de-231">Triángulo verde hacia la derecha</span><span class="sxs-lookup"><span data-stu-id="918de-231">Green, right-pointing triangle</span></span>|<span data-ttu-id="918de-232">En curso</span><span class="sxs-lookup"><span data-stu-id="918de-232">In progress</span></span>|<span data-ttu-id="918de-233">La operación de adjuntar se ha iniciado, pero no ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="918de-233">Attach operation has been started but it is not complete.</span></span>|  
    |<span data-ttu-id="918de-234">Marca de verificación verde</span><span class="sxs-lookup"><span data-stu-id="918de-234">Green check mark</span></span>|<span data-ttu-id="918de-235">Correcto</span><span class="sxs-lookup"><span data-stu-id="918de-235">Success</span></span>|<span data-ttu-id="918de-236">El objeto se ha adjuntado correctamente.</span><span class="sxs-lookup"><span data-stu-id="918de-236">The object has been attached successfully.</span></span>|  
    |<span data-ttu-id="918de-237">Círculo rojo con una cruz blanca</span><span class="sxs-lookup"><span data-stu-id="918de-237">Red circle containing a white cross</span></span>|<span data-ttu-id="918de-238">Error</span><span class="sxs-lookup"><span data-stu-id="918de-238">Error</span></span>|<span data-ttu-id="918de-239">La operación de adjuntar ha detectado un error y no ha finalizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="918de-239">Attach operation encountered an error and did not complete successfully.</span></span>|  
    |<span data-ttu-id="918de-240">Círculo con dos cuadrantes negros (a la izquierda y la derecha) y dos cuadrantes blancos (en la parte superior e inferior)</span><span class="sxs-lookup"><span data-stu-id="918de-240">Circle containing two black quadrants (on left and right) and two white quadrants (on top and bottom)</span></span>|<span data-ttu-id="918de-241">Detenido</span><span class="sxs-lookup"><span data-stu-id="918de-241">Stopped</span></span>|<span data-ttu-id="918de-242">La operación de adjuntar no ha finalizado correctamente porque el usuario la ha detenido.</span><span class="sxs-lookup"><span data-stu-id="918de-242">Attach operation was not completed successfully because the user stopped the operation.</span></span>|  
    |<span data-ttu-id="918de-243">Círculo con una flecha curvada que apunta hacia la izquierda</span><span class="sxs-lookup"><span data-stu-id="918de-243">Circle containing a curved arrow pointing counter-clockwise</span></span>|<span data-ttu-id="918de-244">Revertido</span><span class="sxs-lookup"><span data-stu-id="918de-244">Rolled Back</span></span>|<span data-ttu-id="918de-245">La operación de adjuntar se ha ejecutado correctamente, pero se ha revertido debido a un error al adjuntar otro objeto.</span><span class="sxs-lookup"><span data-stu-id="918de-245">Attach operation was successful but it has been rolled back due to an error during attachment of another object.</span></span>|  
  
     <span data-ttu-id="918de-246">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="918de-246">**Message**</span></span>  
     <span data-ttu-id="918de-247">Muestra un mensaje en blanco o un hipervínculo que indica "Archivo no encontrado".</span><span class="sxs-lookup"><span data-stu-id="918de-247">Displays either a blank message or a "File not found" hyperlink.</span></span>  
  
     <span data-ttu-id="918de-248">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="918de-248">**Add**</span></span>  
     <span data-ttu-id="918de-249">Busca los archivos de base de datos principales necesarios.</span><span class="sxs-lookup"><span data-stu-id="918de-249">Find the necessary main database files.</span></span> <span data-ttu-id="918de-250">Si el usuario selecciona un archivo .mdf, la información pertinente se llena automáticamente en los respectivos campos de la cuadrícula **Bases de datos que se van a adjuntar** .</span><span class="sxs-lookup"><span data-stu-id="918de-250">When the user selects an .mdf file, applicable information is automatically filled in the respective fields of the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="918de-251">**Remove**</span><span class="sxs-lookup"><span data-stu-id="918de-251">**Remove**</span></span>  
     <span data-ttu-id="918de-252">Quita el archivo seleccionado de la cuadrícula **Bases de datos que se van a adjuntar** .</span><span class="sxs-lookup"><span data-stu-id="918de-252">Removes the selected file from the **Databases to attach** grid.</span></span>  
  
     <span data-ttu-id="918de-253">**"** _<database_name>_ **" detalles de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="918de-253">**"** _<database_name>_ **" database details**</span></span>  
     <span data-ttu-id="918de-254">Muestra los nombres de los archivos que se van a adjuntar.</span><span class="sxs-lookup"><span data-stu-id="918de-254">Displays the names of the files to be attached.</span></span> <span data-ttu-id="918de-255">Para comprobar o cambiar el nombre de la ruta de acceso de un archivo, haga clic en el botón **Examinar** ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="918de-255">To verify or change the pathname of a file, click the **Browse** button (**...**).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="918de-256">Si un archivo no existe, la columna **Mensaje** muestra "No se encontró".</span><span class="sxs-lookup"><span data-stu-id="918de-256">If a file does not exist, the **Message** column displays "Not found."</span></span> <span data-ttu-id="918de-257">Si un archivo de registro no se encuentra, indica que se halla en otro directorio o que se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="918de-257">If a log file is not found, it exists in another directory or has been deleted.</span></span> <span data-ttu-id="918de-258">En tal caso, debe actualizar la ruta de acceso del archivo en la cuadrícula **Detalles de la base de datos** para que señale la ubicación correcta o eliminar el archivo de registro de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="918de-258">You need to either update the file path in the **database details** grid to point to the correct location or remove the log file from the grid.</span></span> <span data-ttu-id="918de-259">Si un archivo de datos .ndf no se encuentra, debe actualizar su ruta de acceso en la cuadrícula para que señale la ubicación correcta.</span><span class="sxs-lookup"><span data-stu-id="918de-259">If an .ndf data file is not found, you need to update its path in the grid to point to the correct location.</span></span>  
  
     <span data-ttu-id="918de-260">**Nombre del archivo original**</span><span class="sxs-lookup"><span data-stu-id="918de-260">**Original File Name**</span></span>  
     <span data-ttu-id="918de-261">Muestra el nombre del archivo adjunto que pertenece a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="918de-261">Displays the name of the attached file belonging to the database.</span></span>  
  
     <span data-ttu-id="918de-262">**Tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="918de-262">**File Type**</span></span>  
     <span data-ttu-id="918de-263">Indica el tipo de archivo, que puede ser de **datos** o de **registro**.</span><span class="sxs-lookup"><span data-stu-id="918de-263">Indicates the type of file, **Data** or **Log**.</span></span>  
  
     <span data-ttu-id="918de-264">**Ruta de acceso del archivo actual**</span><span class="sxs-lookup"><span data-stu-id="918de-264">**Current File Path**</span></span>  
     <span data-ttu-id="918de-265">Muestra la ruta de acceso del archivo de base de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="918de-265">Displays the path to the selected database file.</span></span> <span data-ttu-id="918de-266">La ruta de acceso puede modificarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="918de-266">The path can be edited manually.</span></span>  
  
     <span data-ttu-id="918de-267">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="918de-267">**Message**</span></span>  
     <span data-ttu-id="918de-268">Muestra un mensaje en blanco o un hipervínculo que indica "**Archivo no encontrado**".</span><span class="sxs-lookup"><span data-stu-id="918de-268">Displays either a blank message or a "**File not found**" hyperlink.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlMove"></a> <span data-ttu-id="918de-269">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="918de-269">Using Transact-SQL</span></span>  
  
1.  <span data-ttu-id="918de-270">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="918de-270">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="918de-271">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="918de-271">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="918de-272">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="918de-272">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Detach the TDE protected database from the source server.   
    USE master ;  
    GO  
    EXEC master.dbo.sp_detach_db @dbname = N'CustRecords';  
    GO  
    -- Move or copy the database files from the source server to the same location on the destination server.   
    -- Move or copy the backup of the server certificate and the private key file from the source server to the same location on the destination server.   
    -- Create a database master key on the destination instance of SQL Server.   
    USE master;  
    GO  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '*rt@40(FL&dasl1';  
    GO  
    -- Recreate the server certificate by using the original server certificate backup file.   
    -- The password must be the same as the password that was used when the backup was created.  
  
    CREATE CERTIFICATE TestSQLServerCert   
    FROM FILE = 'TestSQLServerCert'  
    WITH PRIVATE KEY   
    (  
        FILE = 'SQLPrivateKeyFile',  
        DECRYPTION BY PASSWORD = '*rt@40(FL&dasl1'  
    );  
    GO  
    -- Attach the database that is being moved.   
    -- The path of the database files must be the location where you have stored the database files.  
    CREATE DATABASE [CustRecords] ON   
    ( FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\CustRecords.mdf' ),  
    ( FILENAME = N'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA\CustRecords_log.LDF' )  
    FOR ATTACH ;  
    GO  
    ```  
  
 <span data-ttu-id="918de-273">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="918de-273">For more information, see:</span></span>  
  
-   [<span data-ttu-id="918de-274">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="918de-274">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
-   [<span data-ttu-id="918de-275">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="918de-275">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="918de-276">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="918de-276">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="918de-277">CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="918de-277">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="918de-278">Consulte también</span><span class="sxs-lookup"><span data-stu-id="918de-278">See Also</span></span>  
 [<span data-ttu-id="918de-279">Adjuntar y separar bases de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="918de-279">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../../databases/database-detach-and-attach-sql-server.md)  
  
  
