---
title: Creación, modificación y eliminación de FileTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], altering
- FileTables [SQL Server], dropping
- FileTables [SQL Server], creating
ms.assetid: 47d69e37-8778-4630-809b-2261b5c41c2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3a10e6333f6dd38a850a832b82a7cb7a0e0bf698
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663534"
---
# <a name="create-alter-and-drop-filetables"></a><span data-ttu-id="1e7ae-102">Crear, modificar y quitar FileTables</span><span class="sxs-lookup"><span data-stu-id="1e7ae-102">Create, Alter, and Drop FileTables</span></span>
  <span data-ttu-id="1e7ae-103">Describe cómo crear una nueva FileTable. O bien, modificar o quitar una FileTable existente.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-103">Describes how to create a new FileTable, or alter or drop an existing FileTable.</span></span>  
  
##  <a name="creating-a-filetable"></a><a name="BasicsCreate"></a> <span data-ttu-id="1e7ae-104">Crear una FileTable</span><span class="sxs-lookup"><span data-stu-id="1e7ae-104">Creating a FileTable</span></span>  
 <span data-ttu-id="1e7ae-105">Una FileTable es una tabla de usuario especializada que tiene un esquema predefinido y fijo.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-105">A FileTable is a specialized user table that has a pre-defined and fixed schema.</span></span> <span data-ttu-id="1e7ae-106">Este esquema almacena los datos FILESTREAM, la información de directorios y archivos, así como los atributos de archivos.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-106">This schema stores FILESTREAM data, file and directory information, and file attributes.</span></span> <span data-ttu-id="1e7ae-107">Para obtener información acerca del esquema de FileTable, vea [FileTable Schema](filetable-schema.md).</span><span class="sxs-lookup"><span data-stu-id="1e7ae-107">For information about the FileTable schema, see [FileTable Schema](filetable-schema.md).</span></span>  
  
 <span data-ttu-id="1e7ae-108">Puede crear una nueva FileTable con Transact-SQL o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e7ae-108">You can create a new FileTable by using Transact-SQL or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="1e7ae-109">Puesto que una FileTable tiene un esquema fijo, no tiene que especificar ninguna lista de columnas.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-109">Since a FileTable has a fixed schema, you do not have to specify a list of columns.</span></span> <span data-ttu-id="1e7ae-110">La sintaxis simple para crear una FileTable permite especificar:</span><span class="sxs-lookup"><span data-stu-id="1e7ae-110">The simple syntax for creating a FileTable lets you specify:</span></span>  
  
-   <span data-ttu-id="1e7ae-111">Un nombre de directorio.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-111">A directory name.</span></span> <span data-ttu-id="1e7ae-112">En la jerarquía de carpetas de FileTable, este directorio de nivel de tabla se convierte en el elemento secundario del directorio de la base de datos especificado en el nivel de base de datos y en el elemento primario de los archivos o directorios almacenados en la tabla.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-112">In the FileTable folder hierarchy, this table-level directory becomes the child of the database directory specified at the database level, and the parent of the files or directories stored in the table.</span></span>  
  
-   <span data-ttu-id="1e7ae-113">El nombre de la intercalación que se va usar para los nombres de archivo en la columna **Name** de la FileTable.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-113">The name of the collation to be used for file names in the **Name** column of the FileTable.</span></span>  
  
-   <span data-ttu-id="1e7ae-114">Los nombres que se van a utilizar para la clave principal 3 y las restricciones únicas que se crean automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-114">The names to be used for the 3 primary key and unique constraints that are automatically created.</span></span>  
  
###  <a name="how-to-create-a-filetable"></a><a name="HowToCreate"></a> <span data-ttu-id="1e7ae-115">Procedimientos para: crear una FileTable</span><span class="sxs-lookup"><span data-stu-id="1e7ae-115">How To: Create a FileTable</span></span>  
 <span data-ttu-id="1e7ae-116">**Crear una FileTable con Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-116">**Create a FileTable by Using Transact-SQL**</span></span>  
 <span data-ttu-id="1e7ae-117">Cree una FileTable llamando a la instrucción [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) con la opción **AS FileTable**.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-117">Create a FileTable by calling the [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) statement with the **AS FileTable** option.</span></span> <span data-ttu-id="1e7ae-118">Puesto que una FileTable tiene un esquema fijo, no tiene que especificar ninguna lista de columnas.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-118">Since a FileTable has a fixed schema, you do not have to specify a list of columns.</span></span> <span data-ttu-id="1e7ae-119">Puede especificar los siguientes valores para la nueva FileTable:</span><span class="sxs-lookup"><span data-stu-id="1e7ae-119">You can specify the following settings for the new FileTable:</span></span>  
  
1.  <span data-ttu-id="1e7ae-120">**FILETABLE_DIRECTORY**.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-120">**FILETABLE_DIRECTORY**.</span></span> <span data-ttu-id="1e7ae-121">Especifica el directorio que actúa como directorio raíz de todos los archivos y directorios almacenados en la FileTable.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-121">Specifies the directory that serves as the root directory for all the files and directories stored in the FileTable.</span></span> <span data-ttu-id="1e7ae-122">Este nombre debe ser único entre todos los nombres de directorio de FileTable en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-122">This name should be unique among all the FileTable directory names in the database.</span></span> <span data-ttu-id="1e7ae-123">La comparación de unicidad no distingue mayúsculas de minúsculas, independientemente de la configuración de intercalación actual.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-123">Comparison for uniqueness is case-insensitive, regardless of the current collation settings.</span></span>  
  
    -   <span data-ttu-id="1e7ae-124">Este valor tiene un tipo de datos de **nvarchar(255)** y usa una intercalación fija de **Latin1_General_CI_AS_KS_WS**.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-124">This value has a data type of **nvarchar(255)** and uses a fixed collation of **Latin1_General_CI_AS_KS_WS**.</span></span>  
  
    -   <span data-ttu-id="1e7ae-125">El nombre de directorio que proporcione debe cumplir los requisitos del sistema de archivos de un nombre de directorio válido.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-125">The directory name that you provide must comply with the requirements of the file system for a valid directory name.</span></span>  
  
    -   <span data-ttu-id="1e7ae-126">Este nombre debe ser único entre todos los nombres de directorio de FileTable en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-126">This name should be unique among all the FileTable directory names in the database.</span></span> <span data-ttu-id="1e7ae-127">La comparación de unicidad no distingue mayúsculas de minúsculas, independientemente de la configuración de intercalación actual.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-127">Comparison for uniqueness is case-insensitive, regardless of the current collation settings.</span></span>  
  
    -   <span data-ttu-id="1e7ae-128">Si no proporciona un nombre de directorio al crear la FileTable, su nombre se usa como el del directorio.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-128">If you do not provide a directory name when you create the FileTable, then the name of the FileTable itself is used as the directory name.</span></span>  
  
2.  <span data-ttu-id="1e7ae-129">**FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-129">**FILETABLE_COLLATE_FILENAME**.</span></span> <span data-ttu-id="1e7ae-130">Especifica el nombre de la intercalación que se va a aplicar a la columna **Name** en la FileTable.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-130">Specifies the name of the collation to be applied to the **Name** column in the FileTable.</span></span>  
  
    1.  <span data-ttu-id="1e7ae-131">La intercalación especificada **no debe distinguir mayúsculas de minúsculas** para cumplir la semántica de nomenclatura de archivo de Windows.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-131">The specified collation must be **case-insensitive** to comply with Windows file naming semantics.</span></span>  
  
    2.  <span data-ttu-id="1e7ae-132">Si no proporciona un valor para **FILETABLE_COLLATE_FILENAME**o especifica **database_default**, la columna hereda la intercalación de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-132">If you do not provide a value for **FILETABLE_COLLATE_FILENAME**, or you specify **database_default**, the column inherits the collation of the current database.</span></span> <span data-ttu-id="1e7ae-133">Si la intercalación de la base de datos actual distingue mayúsculas de minúsculas, se produce un error en la operación **CREATE TABLE** .</span><span class="sxs-lookup"><span data-stu-id="1e7ae-133">If the current database collation is case-sensitive, an error is raised and the **CREATE TABLE** operation fails.</span></span>  
  
3.  <span data-ttu-id="1e7ae-134">También puede especificar los nombres que se van a utilizar para la clave principal 3 y las restricciones únicas que se crean automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-134">You can also specify the names to be used for the 3 primary key and unique constraints that are automatically created.</span></span> <span data-ttu-id="1e7ae-135">Si no proporciona nombres, el sistema generará los nombres cómo se describe más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-135">If you do not provide names, then the system generates names as described later in this topic.</span></span>  
  
    -   <span data-ttu-id="1e7ae-136">**FILETABLE_PRIMARY_KEY_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-136">**FILETABLE_PRIMARY_KEY_CONSTRAINT_NAME**</span></span>  
  
    -   <span data-ttu-id="1e7ae-137">**FILETABLE_STREAMID_UNIQUE_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-137">**FILETABLE_STREAMID_UNIQUE_CONSTRAINT_NAME**</span></span>  
  
    -   <span data-ttu-id="1e7ae-138">**FILETABLE_FULLPATH_UNIQUE_CONSTRAINT_NAME**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-138">**FILETABLE_FULLPATH_UNIQUE_CONSTRAINT_NAME**</span></span>  
  
 <span data-ttu-id="1e7ae-139">**Ejemplos**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-139">**Examples**</span></span>  
  
 <span data-ttu-id="1e7ae-140">En el ejemplo siguiente se crea una nueva FileTable y se especifican valores definidos por el usuario para **FILETABLE_DIRECTORY** y **FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-140">The following example creates a new FileTable and specifies user-defined values for both **FILETABLE_DIRECTORY** and **FILETABLE_COLLATE_FILENAME**.</span></span>  
  
```sql  
CREATE TABLE DocumentStore AS FileTable  
    WITH (   
          FileTable_Directory = 'DocumentTable',  
          FileTable_Collate_Filename = database_default  
         );  
GO  
```  
  
 <span data-ttu-id="1e7ae-141">El siguiente ejemplo también crea una nueva FileTable.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-141">The following example also creates a new FileTable.</span></span> <span data-ttu-id="1e7ae-142">Puesto que no se especifican valores definidos por el usuario, el valor de **FILETABLE_DIRECTORY** se convierte en el nombre de la FileTable, el valor de **FILETABLE_COLLATE_FILENAME** se convierte en database_default y la clave principal y las restricciones únicas reciben nombres generados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-142">Since user-defined values are not specified, the value of **FILETABLE_DIRECTORY** becomes the name of the FileTable, the value of **FILETABLE_COLLATE_FILENAME** becomes database_default, and the primary key and unique contraints receive system-generated names.</span></span>  
  
```sql  
CREATE TABLE DocumentStore AS FileTable;  
GO  
```  
  
 <span data-ttu-id="1e7ae-143">**Crear una FileTable con SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-143">**Create a FileTable by Using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="1e7ae-144">En el Explorador de objetos, expanda los objetos situados debajo de la base de datos seleccionada, haga clic con el botón derecho en la carpeta **Tablas** y, luego, seleccione **Nueva FileTable**.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-144">In Object Explorer, expand the objects under the selected database, then right-click on the **Tables** folder, and then select **New FileTable**.</span></span>  
  
 <span data-ttu-id="1e7ae-145">Esta opción abre una nueva ventana de script que contiene una plantilla de script Transact-SQL que puede personalizar y ejecutar para crear una FileTable.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-145">This option opens a new script window which contains a Transact-SQL script template that you can customize and run to create a FileTable.</span></span> <span data-ttu-id="1e7ae-146">Use la opción **Especificar valores para parámetros de plantilla** en el menú **Consulta** para personalizar el script fácilmente.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-146">Use the **Specify Values for Template Parameters** option on the **Query** menu to customize the script easily.</span></span>  
  
###  <a name="requirements-and-restrictions-for-creating-a-filetable"></a><a name="ReqCreate"></a> <span data-ttu-id="1e7ae-147">Requisitos y restricciones para crear una FileTable</span><span class="sxs-lookup"><span data-stu-id="1e7ae-147">Requirements and Restrictions for Creating a FileTable</span></span>  
  
-   <span data-ttu-id="1e7ae-148">No puede modificar una tabla existente para convertirla en una FileTable.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-148">You cannot alter an existing table to convert it into a FileTable.</span></span>  
  
-   <span data-ttu-id="1e7ae-149">El directorio primario especificado anteriormente en el nivel de base de datos debe tener un valor distinto de NULL.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-149">The parent directory previously specified at the database level must have a non-null value.</span></span> <span data-ttu-id="1e7ae-150">Para obtener información sobre cómo especificar el directorio de nivel de base de datos, vea [Habilitar los requisitos previos de FileTables](enable-the-prerequisites-for-filetable.md).</span><span class="sxs-lookup"><span data-stu-id="1e7ae-150">For information about specifying the database-level directory, see [Enable the Prerequisites for FileTable](enable-the-prerequisites-for-filetable.md).</span></span>  
  
-   <span data-ttu-id="1e7ae-151">Una FileTable requiere un grupo de archivos FILESTREAM válido, ya que una FileTable contiene una columna FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-151">A FileTable requires a valid FILESTREAM filegroup, since a FileTable contains a FILESTREAM column.</span></span> <span data-ttu-id="1e7ae-152">Opcionalmente, puede especificar un grupo de archivos FILESTREAM válido como parte del comando **CREATE TABLE** para crear una FileTable.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-152">You can optionally specify a valid FILESTREAM filegroup as part of the **CREATE TABLE** command for creating a FileTable.</span></span> <span data-ttu-id="1e7ae-153">Si no especifica ningún grupo de archivos, la FileTable usa el grupo de archivos FILESTREAM predeterminado para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-153">If you do not specify a filegroup, then the FileTable uses the default FILESTREAM filegroup for the database.</span></span> <span data-ttu-id="1e7ae-154">Si la base de datos no tiene ningún grupo de archivos FILESTREAM, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-154">If the database does not have a FILESTREAM filegroup, then an error is raised.</span></span>  
  
-   <span data-ttu-id="1e7ae-155">No puede crear ninguna restricción de tabla como parte de una instrucción **CREATE TABLE...AS FILETABLE**.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-155">You cannot create a table constraint as part of a **CREATE TABLE...AS FILETABLE** statement.</span></span> <span data-ttu-id="1e7ae-156">No obstante, puede agregar la restricción más tarde con una instrucción **ALTER TABLE** .</span><span class="sxs-lookup"><span data-stu-id="1e7ae-156">However you can add the constraint later by using an **ALTER TABLE** statement.</span></span>  
  
-   <span data-ttu-id="1e7ae-157">No puede crear ninguna FileTable en la base de datos **tempdb** ni en ninguna de la demás bases de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-157">You cannot create a FileTable in the **tempdb** database or in any of the other system databases.</span></span>  
  
-   <span data-ttu-id="1e7ae-158">No puede crear ninguna FileTable como tabla temporal.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-158">You cannot create a FileTable as a temporary table.</span></span>  
  
##  <a name="altering-a-filetable"></a><a name="BasicsAlter"></a> <span data-ttu-id="1e7ae-159">Modificar una FileTable</span><span class="sxs-lookup"><span data-stu-id="1e7ae-159">Altering a FileTable</span></span>  
 <span data-ttu-id="1e7ae-160">Puesto que una FileTable tiene un esquema predefinido y fijo, no puede agregar ni cambiar sus columnas.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-160">Since a FileTable has a pre-defined and fixed schema, you cannot add or change its columns.</span></span> <span data-ttu-id="1e7ae-161">No obstante, puede agregar índices personalizados, desencadenadores, restricciones y opciones adicionales a una FileTable.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-161">However, you can add custom indexes, triggers, constraints, and other options to a FileTable.</span></span>  
  
 <span data-ttu-id="1e7ae-162">Para obtener información sobre el uso de la instrucción ALTER TABLE para habilitar o deshabilitar el espacio de nombres de FileTable, incluidas las restricciones definidas por el sistema, vea [Administrar FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="1e7ae-162">For information about using the ALTER TABLE statement to enable or disable the FileTable namespace, including the system-defined constraints, see [Manage FileTables](manage-filetables.md).</span></span>  
  
###  <a name="how-to-change-the-directory-for-a-filetable"></a><a name="HowToChange"></a> <span data-ttu-id="1e7ae-163">Procedimientos para: cambiar el directorio de un objeto FileTable</span><span class="sxs-lookup"><span data-stu-id="1e7ae-163">How To: Change the Directory for a FileTable</span></span>  
 <span data-ttu-id="1e7ae-164">**Cambiar el directorio de un objeto FileTable mediante Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-164">**Change the Directory for a FileTable by Using Transact-SQL**</span></span>  
 <span data-ttu-id="1e7ae-165">Llame a la instrucción ALTER TABLE y proporcione un nuevo valor válido para la opción **FILETABLE_DIRECTORY** SET.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-165">Call the ALTER TABLE statement and provide a valid new value for the **FILETABLE_DIRECTORY** SET option.</span></span>  
  
 <span data-ttu-id="1e7ae-166">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-166">**Example**</span></span>  
  
```sql  
ALTER TABLE filetable_name  
    SET ( FILETABLE_DIRECTORY = N'directory_name' );  
GO  
```  
  
 <span data-ttu-id="1e7ae-167">**Cambiar el directorio de un objeto FileTable mediante SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-167">**Change the Directory for a FileTable by Using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="1e7ae-168">En el Explorador de objetos, haga clic con el botón derecho en el objeto FileTable y seleccione **Propiedades** para abrir el cuadro de diálogo **Propiedades de la tabla** .</span><span class="sxs-lookup"><span data-stu-id="1e7ae-168">In Object Explorer, right-click on the FileTable and select **Properties** to open the **Table Properties** dialog box.</span></span> <span data-ttu-id="1e7ae-169">En la página **FileTable** , escriba un nuevo valor para **Nombre del directorio de FileTable**.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-169">On the **FileTable** page, enter a new value for **FileTable directory name**.</span></span>  
  
###  <a name="requirements-and-restrictions-for-altering-a-filetable"></a><a name="ReqAlter"></a> <span data-ttu-id="1e7ae-170">Requisitos y restricciones para modificar una FileTable</span><span class="sxs-lookup"><span data-stu-id="1e7ae-170">Requirements and Restrictions for Altering a FileTable</span></span>  
  
-   <span data-ttu-id="1e7ae-171">No puede modificar el valor de **FILETABLE_COLLATE_FILENAME**.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-171">You cannot alter the value of **FILETABLE_COLLATE_FILENAME**.</span></span>  
  
-   <span data-ttu-id="1e7ae-172">No puede cambiar, quitar ni deshabilitar las columnas definidas por el sistema de una FileTable.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-172">You cannot change, drop, or disable the system-defined columns of a FileTable.</span></span>  
  
-   <span data-ttu-id="1e7ae-173">No puede agregar nueva columnas de usuario, columnas calculadas ni columnas calculadas persistentes a una FileTable.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-173">You cannot add new user columns, computed columns, or persisted computed columns to a FileTable.</span></span>  
  
##  <a name="dropping-a-filetable"></a><a name="BasicsDrop"></a> <span data-ttu-id="1e7ae-174">Quitar una FileTable</span><span class="sxs-lookup"><span data-stu-id="1e7ae-174">Dropping a FileTable</span></span>  
 <span data-ttu-id="1e7ae-175">Puede quitar una FileTable mediante la sintaxis normal de la instrucción [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1e7ae-175">You can drop a FileTable by using the ordinary syntax for the [DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="1e7ae-176">Cuando se quita una FileTable, también se quitan los objetos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1e7ae-176">When you drop a FileTable, the following objects are also dropped:</span></span>  
  
-   <span data-ttu-id="1e7ae-177">También se quitan todas las columnas de la FileTable y todos los objetos asociados con la tabla, por ejemplo, índices, restricciones y desencadenadores.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-177">All the columns of the FileTable and all the objects associated with the table, such as indexes, constraints, and triggers, are also dropped.</span></span>  
  
-   <span data-ttu-id="1e7ae-178">El directorio y los subdirectorios de la FileTable que contiene desaparecen de la jerarquía de archivos y directorios de FILESTREAM de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-178">The FileTable directory and the sub-directories that it contained disappear from the FILESTREAM file and directory hierarchy of the database.</span></span>  
  
 <span data-ttu-id="1e7ae-179">Se produce un error en el comando DROP TABLE si hay identificadores de archivo abiertos en el espacio de nombres de archivo de FileTable.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-179">The DROP TABLE command fails if there are open file handles in the FileTable's file namespace.</span></span> <span data-ttu-id="1e7ae-180">Para obtener información sobre cómo cerrar identificadores abiertos, vea [Administrar FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="1e7ae-180">For information about closing open handles, see [Manage FileTables](manage-filetables.md).</span></span>  
  
##  <a name="other-database-objects-are-created-when-you-create-a-filetable"></a><a name="BasicsOtherObjects"></a> <span data-ttu-id="1e7ae-181">Se crean otros objetos de base de datos cuando se crea una FileTable</span><span class="sxs-lookup"><span data-stu-id="1e7ae-181">Other Database Objects Are Created When You Create a FileTable</span></span>  
 <span data-ttu-id="1e7ae-182">Cuando cree una nueva FileTable, también se crean algunas restricciones y algunos índices definidos por el sistema.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-182">When you create a new FileTable, some system-defined indexes and constraints are also created.</span></span> <span data-ttu-id="1e7ae-183">No puede modificar ni quitar estos objetos; desaparecen solo cuando se quita el propio objeto FileTable.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-183">You cannot alter or drop these objects; they disappear only when the FileTable itself is dropped.</span></span> <span data-ttu-id="1e7ae-184">Para ver la lista de estos objetos, consulte la vista de catálogo [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1e7ae-184">To see the list of these objects, query the catalog view [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span></span>  
  
```sql  
--View all objects for all filetables, unsorted  
SELECT * FROM sys.filetable_system_defined_objects;  
GO  
  
--View sorted list with friendly names  
SELECT OBJECT_NAME(parent_object_id) AS 'FileTable', OBJECT_NAME(object_id) AS 'System-defined Object'  
    FROM sys.filetable_system_defined_objects  
    ORDER BY FileTable, 'System-defined Object';  
GO  
```  
  
 <span data-ttu-id="1e7ae-185">**Índices creados cuando cree una nueva FileTable**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-185">**Indexes that are created when you create a new FileTable**</span></span>  
 <span data-ttu-id="1e7ae-186">Cuando cree una nueva FileTable, también se crean los siguiente índices definidos por el sistema:</span><span class="sxs-lookup"><span data-stu-id="1e7ae-186">When you create a new FileTable, the following system-defined indexes are also created:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1e7ae-187">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-187">**Columns**</span></span>|<span data-ttu-id="1e7ae-188">**Tipo de índice**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-188">**Index type**</span></span>|  
|<span data-ttu-id="1e7ae-189">[path_locator] ASC</span><span class="sxs-lookup"><span data-stu-id="1e7ae-189">[path_locator] ASC</span></span>|<span data-ttu-id="1e7ae-190">Clave principal, no agrupada</span><span class="sxs-lookup"><span data-stu-id="1e7ae-190">Primary Key, nonclustered</span></span>|  
|<span data-ttu-id="1e7ae-191">[parent_path_locator] ASC,</span><span class="sxs-lookup"><span data-stu-id="1e7ae-191">[parent_path_locator] ASC,</span></span><br /><br /> <span data-ttu-id="1e7ae-192">[name] ASC</span><span class="sxs-lookup"><span data-stu-id="1e7ae-192">[name] ASC</span></span>|<span data-ttu-id="1e7ae-193">Única, no agrupada</span><span class="sxs-lookup"><span data-stu-id="1e7ae-193">Unique, nonclustered</span></span>|  
|<span data-ttu-id="1e7ae-194">[stream_id] ASC</span><span class="sxs-lookup"><span data-stu-id="1e7ae-194">[stream_id] ASC</span></span>|<span data-ttu-id="1e7ae-195">Única, no agrupada</span><span class="sxs-lookup"><span data-stu-id="1e7ae-195">Unique, nonclustered</span></span>|  
  
 <span data-ttu-id="1e7ae-196">**Restricciones creadas cuando cree una nueva FileTable**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-196">**Constraints that are created when you create a new FileTable**</span></span>  
 <span data-ttu-id="1e7ae-197">Cuando cree una nueva FileTable, también se crean las siguiente restricciones definidas por el sistema:</span><span class="sxs-lookup"><span data-stu-id="1e7ae-197">When you create a new FileTable, the following system-defined constraints are also created:</span></span>  
  
|<span data-ttu-id="1e7ae-198">Restricciones</span><span class="sxs-lookup"><span data-stu-id="1e7ae-198">Constraints</span></span>|<span data-ttu-id="1e7ae-199">Aplica</span><span class="sxs-lookup"><span data-stu-id="1e7ae-199">Enforces</span></span>|  
|-----------------|--------------|  
|<span data-ttu-id="1e7ae-200">Restricciones predeterminadas en las siguiente columnas:</span><span class="sxs-lookup"><span data-stu-id="1e7ae-200">Default constraints on the following columns:</span></span><br /><br /> <span data-ttu-id="1e7ae-201">**creation_time**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-201">**creation_time**</span></span> <br /> <span data-ttu-id="1e7ae-202">**is_archive**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-202">**is_archive**</span></span> <br /> <span data-ttu-id="1e7ae-203">**is_directory**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-203">**is_directory**</span></span> <br /> <span data-ttu-id="1e7ae-204">**is_hidden**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-204">**is_hidden**</span></span> <br /> <span data-ttu-id="1e7ae-205">**is_offline**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-205">**is_offline**</span></span> <br /> <span data-ttu-id="1e7ae-206">**is_readonly**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-206">**is_readonly**</span></span> <br /> <span data-ttu-id="1e7ae-207">**is_system**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-207">**is_system**</span></span> <br /> <span data-ttu-id="1e7ae-208">**is_temporary**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-208">**is_temporary**</span></span> <br /> <span data-ttu-id="1e7ae-209">**last_access_time**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-209">**last_access_time**</span></span> <br /> <span data-ttu-id="1e7ae-210">**last_write_time**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-210">**last_write_time**</span></span> <br /> <span data-ttu-id="1e7ae-211">**path_locator**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-211">**path_locator**</span></span> <br /> <span data-ttu-id="1e7ae-212">**stream_id**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-212">**stream_id**</span></span>|<span data-ttu-id="1e7ae-213">Las restricciones predeterminadas definidas por el sistema aplican valores predeterminados a las columnas especificadas.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-213">The system-defined default constraints enforce default values for the specified columns.</span></span>|  
|<span data-ttu-id="1e7ae-214">Restricciones CHECK</span><span class="sxs-lookup"><span data-stu-id="1e7ae-214">Check constraints</span></span>|<span data-ttu-id="1e7ae-215">Las restricciones CHECK definidas por el sistema se aplican a los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="1e7ae-215">The system-defined check constraints enforce the following requirements:</span></span><br /><br /> <span data-ttu-id="1e7ae-216">Nombres de archivo válidos.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-216">Valid filenames.</span></span><br /><br /> <span data-ttu-id="1e7ae-217">Atributos de archivo válidos.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-217">Valid file attributes.</span></span><br /><br /> <span data-ttu-id="1e7ae-218">El objeto primario debe ser un directorio.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-218">Parent object must be a directory.</span></span><br /><br /> <span data-ttu-id="1e7ae-219">La jerarquía del espacio de nombres se bloquea durante la manipulación de archivos.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-219">Namespace hierarchy is locked during file manipulation.</span></span>|  
  
 <span data-ttu-id="1e7ae-220">**Convención de nomenclatura para las restricciones definidas por el sistema**</span><span class="sxs-lookup"><span data-stu-id="1e7ae-220">**Naming convention for the system-defined constraints**</span></span>  
 <span data-ttu-id="1e7ae-221">A las restricciones definidas por el sistema descritas anteriormente se les asigna un nombre con el formato **\<constraintType>_\<tablename>[\_\<columnname>]\_\<uniquifier>** , donde:</span><span class="sxs-lookup"><span data-stu-id="1e7ae-221">The system-defined constraints described above are named in the format **\<constraintType>_\<tablename>[\_\<columnname>]\_\<uniquifier>** where:</span></span>  
  
-   <span data-ttu-id="1e7ae-222">*<constraint_type>* es CK (restricción CHECK), DF (restricción DEFAULT), FK (clave externa), PK (clave principal) o UQ (restricción UNIQUE).</span><span class="sxs-lookup"><span data-stu-id="1e7ae-222">*<constraint_type>* is CK (check constraint), DF (default constraint), FK (foreign key), PK (primary key), or UQ (unique constraint).</span></span>  
  
-   <span data-ttu-id="1e7ae-223">*\<uniquifier>* es una cadena generada por el sistema para que el nombre sea único.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-223">*\<uniquifier>* is a system-generated string to make the name unique.</span></span> <span data-ttu-id="1e7ae-224">Esta cadena puede contener el nombre de la FileTable y un identificador único.</span><span class="sxs-lookup"><span data-stu-id="1e7ae-224">This string may contain the FileTable name and a unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e7ae-225">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e7ae-225">See Also</span></span>  
 [<span data-ttu-id="1e7ae-226">Administrar FileTables</span><span class="sxs-lookup"><span data-stu-id="1e7ae-226">Manage FileTables</span></span>](manage-filetables.md)  
  
  
