---
title: Importación en bloque de datos mediante las instrucciones BULK INSERT u OPENROWSET(BULK...) (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- BULK INSERT statement, importing data from a remote data file
- bulk importing [SQL Server], methods
- bulk exporting [SQL Server], methods
- OPENROWSET function, BULK INSERT
- bulk importing [SQL Server], security
- bulk rowset providers [SQL Server]
- bulk exporting [SQL Server], BULK INSERT statement
- remote data access [SQL Server], bulk importing
- bulk importing [SQL Server], BULK INSERT statement
- Transact-SQL bulk export/import operations
ms.assetid: 18a64236-0285-46ea-8929-6ee9bcc020b9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: be36167020b96dba6d494685d958c38e0e6afbba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675372"
---
# <a name="import-bulk-data-by-using-bulk-insert-or-openrowsetbulk-sql-server"></a><span data-ttu-id="c3ca4-102">Importación en bloque de datos mediante las instrucciones BULK INSERT o OPENROWSET(BULK...) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c3ca4-102">Import Bulk Data by Using BULK INSERT or OPENROWSET(BULK...) (SQL Server)</span></span>
  <span data-ttu-id="c3ca4-103">En este tema se ofrece información general acerca de cómo usar las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] BULK INSERT e INSERT...SELECT \* FROM OPENROWSET(BULK...) para realizar una importación masiva de datos desde un archivo de datos a una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3ca4-103">This topic provides an overview of how to use the [!INCLUDE[tsql](../../includes/tsql-md.md)] BULK INSERT statement and the INSERT...SELECT \* FROM OPENROWSET(BULK...) statement to bulk import data from a data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="c3ca4-104">También se describen las consideraciones de seguridad del uso de BULK INSERT y OPENROWSET(BULK...), así como el uso de estos métodos para una importación masiva desde un origen de datos remoto.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-104">This topic also describes security considerations for using BULK INSERT and OPENROWSET(BULK...), and using these methods to bulk import from a remote data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3ca4-105">Cuando se usa BULK INSERT u OPENROWSET(BULK...), es importante comprender el modo en que la versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trata la suplantación.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-105">When you use BULK INSERT or OPENROWSET(BULK...), it is important to understand how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version handles impersonation.</span></span> <span data-ttu-id="c3ca4-106">Para obtener más información, vea la sección "Consideraciones relativas a la seguridad" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-106">For more information, see "Security Considerations," later in this topic.</span></span>  
  
## <a name="bulk-insert-statement"></a><span data-ttu-id="c3ca4-107">Instrucción BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="c3ca4-107">BULK INSERT Statement</span></span>  
 <span data-ttu-id="c3ca4-108">BULK INSERT carga datos de un archivo de datos a una tabla.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-108">BULK INSERT loads data from a data file into a table.</span></span> <span data-ttu-id="c3ca4-109">Esta funcionalidad es parecida a la que ofrece la opción **in** del comando **bcp** , aunque el que lee el archivo de datos es el proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3ca4-109">This functionality is similar to that provided by the **in** option of the **bcp** command; however, the data file is read by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span> <span data-ttu-id="c3ca4-110">Para obtener una descripción de la sintaxis de BULK INSERT, vea [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c3ca4-110">For a description of the BULK INSERT syntax, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="c3ca4-111">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c3ca4-111">Examples</span></span>  
 <span data-ttu-id="c3ca4-112">Para obtener ejemplos de BULK INSERT, vea:</span><span class="sxs-lookup"><span data-stu-id="c3ca4-112">For BULK INSERT examples, see:</span></span>  
  
-   [<span data-ttu-id="c3ca4-113">BULK INSERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-113">BULK INSERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/bulk-insert-transact-sql)  
  
-   [<span data-ttu-id="c3ca4-114">Ejemplos de importación y exportación en bloque de documentos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-114">Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;</span></span>](examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-115">Mantener valores de identidad al importar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-115">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-116">Mantener valores NULL o usar valores predeterminados durante la importación en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-116">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-117">Especificar terminadores de campo y de fila &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-117">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-118">Usar un archivo de formato para importar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-118">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-119">Usar el formato de caracteres para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-119">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-120">Usar el formato nativo para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-120">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-121">Usar el formato de caracteres Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-121">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-122">Usar el formato nativo Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-122">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-123">Usar un archivo de formato para omitir una columna de tabla &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-123">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-124">Usar un archivo de formato para asignar columnas de tabla a campos de un archivo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-124">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
## <a name="openrowsetbulk-function"></a><span data-ttu-id="c3ca4-125">OPENROWSET(BULK...) Función</span><span class="sxs-lookup"><span data-stu-id="c3ca4-125">OPENROWSET(BULK...) Function</span></span>  
 <span data-ttu-id="c3ca4-126">Se tiene acceso al proveedor de conjuntos de filas BULK de OPENROWSET al llamar a la función OPENROWSET y especificar la opción BULK.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-126">The OPENROWSET bulk rowset provider is accessed by calling the OPENROWSET function and specifying the BULK option.</span></span> <span data-ttu-id="c3ca4-127">La función OPENROWSET(BULK...) permite acceder a datos remotos mediante la conexión a un origen de datos remoto como, por ejemplo, un archivo de datos, a través de un proveedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-127">The OPENROWSET(BULK...) function allows you to access remote data by connecting to a remote data source, such as a data file, through an OLE DB provider.</span></span>  
  
 <span data-ttu-id="c3ca4-128">Para realizar una importación masiva de datos, llame a OPENROWSET(BULK...) desde una cláusula SELECT...FROM en una instrucción INSERT.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-128">To bulk import data, call OPENROWSET(BULK...) from a SELECT...FROM clause within an INSERT statement.</span></span> <span data-ttu-id="c3ca4-129">La sintaxis básica de una importación masiva de datos es:</span><span class="sxs-lookup"><span data-stu-id="c3ca4-129">The basic syntax for bulk importing data is:</span></span>  
  
 <span data-ttu-id="c3ca4-130">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="c3ca4-130">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
  
 <span data-ttu-id="c3ca4-131">Cuando se usa en una instrucción INSERT, OPENROWSET(BULK...) admite sugerencias de tabla.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-131">When used in an INSERT statement, OPENROWSET(BULK...) supports table hints.</span></span> <span data-ttu-id="c3ca4-132">Además de las sugerencias de tabla normales, como TABLOCK, la cláusula BULK puede aceptar las sugerencias de tablas especializadas siguientes: IGNORE_CONSTRAINTS (ignora solo las restricciones CHECK), IGNORE_TRIGGERS, KEEPDEFAULTS y KEEPIDENTITY.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-132">In addition to the regular table hints, such as TABLOCK, the BULK clause can accept the following specialized table hints: IGNORE_CONSTRAINTS (ignores only the CHECK constraints), IGNORE_TRIGGERS, KEEPDEFAULTS, and KEEPIDENTITY.</span></span> <span data-ttu-id="c3ca4-133">Para obtener más información, vea [Sugerencias de tabla &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table).</span><span class="sxs-lookup"><span data-stu-id="c3ca4-133">For more information, see [Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table).</span></span>  
  
 <span data-ttu-id="c3ca4-134">Para obtener información sobre los usos adicionales de la opción BULK, vea [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c3ca4-134">For information about additional uses of the BULK option, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="c3ca4-135">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c3ca4-135">Examples</span></span>  
 <span data-ttu-id="c3ca4-136">Para obtener ejemplos de instrucciones INSERT...SELECT \* FROM OPENROWSET(BULK...), vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c3ca4-136">For examples of INSERT...SELECT \* FROM OPENROWSET(BULK...) statements, see the following topics:</span></span>  
  
-   [<span data-ttu-id="c3ca4-137">Ejemplos de importación y exportación en bloque de documentos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-137">Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;</span></span>](examples-of-bulk-import-and-export-of-xml-documents-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-138">Mantener valores de identidad al importar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-138">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-139">Mantener valores NULL o usar valores predeterminados durante la importación en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-139">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-140">Usar un archivo de formato para importar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-140">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-141">Usar el formato de caracteres para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-141">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-142">Usar un archivo de formato para omitir una columna de tabla &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-142">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-143">Usar un archivo de formato para omitir un campo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-143">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="c3ca4-144">Usar un archivo de formato para asignar columnas de tabla a campos de un archivo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-144">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
## <a name="security-considerations"></a><span data-ttu-id="c3ca4-145">Consideraciones sobre la seguridad</span><span class="sxs-lookup"><span data-stu-id="c3ca4-145">Security Considerations</span></span>  
 <span data-ttu-id="c3ca4-146">Si un usuario utiliza un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , se utilizará el perfil de seguridad de la cuenta de proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3ca4-146">If a user uses a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login, the security profile of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process account is used.</span></span> <span data-ttu-id="c3ca4-147">Un inicio de sesión que use autenticación de SQL Server no se puede autenticar fuera del Motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-147">A login using SQL Server authentication cannot be authenticated outside of the Database Engine.</span></span> <span data-ttu-id="c3ca4-148">Por tanto, cuando un inicio de sesión que usa autenticación de SQL Server inicia un comando BULK INSERT, la conexión con los datos se realiza usando el contexto de seguridad de la cuenta de proceso de SQL Server (la cuenta usada por el servicio Motor de base de datos de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="c3ca4-148">Therefore, when a BULK INSERT command is initiated by a login using SQL Server authentication, the connection to the data is made using the security context of the SQL Server process account (the account used by the SQL Server Database Engine service).</span></span> <span data-ttu-id="c3ca4-149">Para leer correctamente los datos de origen, debe conceder acceso a los datos de origen a la cuenta usada por el Motor de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-149">To successfully read the source data you must grant the account used by the SQL Server Database Engine, access to the source data.</span></span> <span data-ttu-id="c3ca4-150">Por el contrario, si un usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha iniciado sesión mediante autenticación de Windows, el usuario solo puede leer los archivos a los que la cuenta de usuario tiene acceso, independientemente del perfil de seguridad del proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3ca4-150">In contrast, if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user logs on by using Windows Authentication, the user can read only those files that can be accessed by the user account, regardless of the security profile of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span>  
  
 <span data-ttu-id="c3ca4-151">Por ejemplo, imagine un usuario que ha iniciado sesión en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-151">For example, consider a user who logged in to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using Windows Authentication.</span></span> <span data-ttu-id="c3ca4-152">Para que el usuario pueda utilizar BULK INSERT u OPENROWSET para importar datos de un archivo de datos a una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , la cuenta de usuario necesita acceso de lectura para el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-152">For the user to be able to use BULK INSERT or OPENROWSET to import data from a data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table, the user account requires read access to the data file.</span></span> <span data-ttu-id="c3ca4-153">Como el usuario dispone de acceso al archivo de datos, podrá importar datos del archivo a la tabla, aunque el proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no tenga permiso de acceso al archivo.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-153">With access to the data file, the user can import data from the file into a table even if the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process does not have permission to access the file.</span></span> <span data-ttu-id="c3ca4-154">El usuario no tiene que conceder permiso de acceso a archivos al proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c3ca4-154">The user does not have to grant file-access permission to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c3ca4-155">y [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows para permitir que una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se conecte a otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante el reenvío de las credenciales de un usuario de Windows autenticado.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-155">and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows can be configured to enable an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to connect to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by forwarding the credentials of an authenticated Windows user.</span></span> <span data-ttu-id="c3ca4-156">Esto se conoce como *suplantación* o *delegación*.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-156">This arrangement is known as *impersonation* or *delegation*.</span></span> <span data-ttu-id="c3ca4-157">Es importante entender cómo la versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trata la seguridad en la suplantación de usuarios al utilizar BULK INSERT u OPENROWSET.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-157">Understanding how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version handle security for user impersonation is important when you use BULK INSERT or OPENROWSET.</span></span> <span data-ttu-id="c3ca4-158">La suplantación de usuarios permite que el archivo de datos resida en un equipo diferente al del proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o del usuario.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-158">User impersonation allows the data file to reside on a different computer than either the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process or the user.</span></span> <span data-ttu-id="c3ca4-159">Por ejemplo, si un usuario del **Equipo_A** tiene acceso a un archivo de datos del **Equipo_B**y la delegación de credenciales se ha establecido correctamente, el usuario puede conectarse a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se esté ejecutando en el **Equipo_C**, tener acceso al archivo de datos del **Equipo_B**y realizar una importación en bloque de datos desde ese archivo a una tabla en el **Equipo_C**.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-159">For example, if a user on **Computer_A** has access to a data file on **Computer_B**, and the delegation of credentials has been set appropriately, the user can connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on **Computer_C**, access the data file on **Computer_B**, and bulk import data from that file into a table on **Computer_C**.</span></span>  
  
## <a name="bulk-importing-from-a-remote-data-file"></a><span data-ttu-id="c3ca4-160">Importación masiva desde un archivo de datos remoto</span><span class="sxs-lookup"><span data-stu-id="c3ca4-160">Bulk Importing from a Remote Data File</span></span>  
 <span data-ttu-id="c3ca4-161">Para usar BULK INSERT o INSERT...SELECT \* FROM OPENROWSET(BULK...) para la importación en bloque de datos desde otro equipo, el archivo de datos debe estar compartido entre los dos equipos.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-161">To use BULK INSERT or INSERT...SELECT \* FROM OPENROWSET(BULK...) to bulk import data from another computer, the data file must be shared between the two computers.</span></span> <span data-ttu-id="c3ca4-162">Para especificar un archivo de datos compartido, use la convención de nomenclatura universal (UNC) para el nombre, que tiene la forma general de **\\\\** _nombreDeServidor_ **\\** _nombreDeRecursoCompartido_ **\\** _rutaDeAcceso_ **\\** _nombreDeArchivo_.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-162">To specify a shared data file, use its universal naming convention (UNC) name, which takes the general form, **\\\\**_Servername_**\\**_Sharename_**\\**_Path_**\\**_Filename_.</span></span> <span data-ttu-id="c3ca4-163">Además, la cuenta usada para obtener acceso al archivo de datos debe tener los permisos necesarios para leer el archivo en el disco remoto.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-163">Additionally, the account used to access the data file must have the permissions that are required for reading the file on the remote disk.</span></span>  
  
 <span data-ttu-id="c3ca4-164">Por ejemplo, la siguiente instrucción `BULK INSERT` realiza la importación masiva de datos en una tabla `SalesOrderDetail` de la base de datos `AdventureWorks` desde un archivo de datos denominado `newdata.txt`.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-164">For example, the following `BULK INSERT` statement bulk imports data into the `SalesOrderDetail` table of the `AdventureWorks` database from a data file that is named `newdata.txt`.</span></span> <span data-ttu-id="c3ca4-165">Este archivo de datos reside en una carpeta compartida llamada `\dailyorders` en un directorio compartido de red llamado `salesforce` de un sistema llamado `computer2`.</span><span class="sxs-lookup"><span data-stu-id="c3ca4-165">This data file resides in a shared folder named `\dailyorders` on a network share directory named `salesforce` on a system named `computer2`.</span></span>  
  
```  
BULK INSERT AdventureWorks2012.Sales.SalesOrderDetail  
   FROM '\\computer2\salesforce\dailyorders\neworders.txt';  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c3ca4-166">Esta restricción no se aplica a la utilidad **bcp** debido a que el cliente lee el archivo independientemente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3ca4-166">This restriction does not apply to the **bcp** utility because the client reads the file independently of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ca4-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3ca4-167">See Also</span></span>  
 <span data-ttu-id="c3ca4-168">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3ca4-168">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="c3ca4-169">[SELECT &#40;cláusula de Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3ca4-169">[SELECT Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql) </span></span>  
 <span data-ttu-id="c3ca4-170">[Importar y exportar datos en bloque &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c3ca4-170">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="c3ca4-171">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3ca4-171">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="c3ca4-172">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3ca4-172">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 <span data-ttu-id="c3ca4-173">[FROM &#40;Transact-SQL&#41;](/sql/t-sql/queries/from-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c3ca4-173">[FROM &#40;Transact-SQL&#41;](/sql/t-sql/queries/from-transact-sql) </span></span>  
 <span data-ttu-id="c3ca4-174">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="c3ca4-174">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 [<span data-ttu-id="c3ca4-175">BULK INSERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c3ca4-175">BULK INSERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/bulk-insert-transact-sql)  
  
  