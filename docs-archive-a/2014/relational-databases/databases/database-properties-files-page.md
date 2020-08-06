---
title: Propiedades de la base de datos (página Archivos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.files.f1
ms.assetid: 3c030e51-db82-4b43-b1e5-8547ddd3de87
author: stevestein
ms.author: sstein
ms.openlocfilehash: 955a17857ce0d847fb712473dddd581a072ab83d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744128"
---
# <a name="database-properties-files-page"></a><span data-ttu-id="23f3d-102">Propiedades de la base de datos (página Archivos)</span><span class="sxs-lookup"><span data-stu-id="23f3d-102">Database Properties (Files Page)</span></span>
  <span data-ttu-id="23f3d-103">Utilice esta página para crear una nueva base de datos o para ver o modificar las propiedades de la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="23f3d-103">Use this page to create a new database, or view or modify properties for the selected database.</span></span> <span data-ttu-id="23f3d-104">Este tema se aplica a **Propiedades de la base de datos (página Archivos)** de las bases de datos existentes y a **Nueva base de datos (página General)** .</span><span class="sxs-lookup"><span data-stu-id="23f3d-104">This topic applies to the **Database Properties (Files Page)** for existing databases, and to the **New Database (General Page)**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="23f3d-105">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="23f3d-105">UI element list</span></span>  
 <span data-ttu-id="23f3d-106">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="23f3d-106">**Database name**</span></span>  
 <span data-ttu-id="23f3d-107">Agregue o muestre el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="23f3d-107">Add or display the name of the database.</span></span>  
  
 <span data-ttu-id="23f3d-108">**Propietario**</span><span class="sxs-lookup"><span data-stu-id="23f3d-108">**Owner**</span></span>  
 <span data-ttu-id="23f3d-109">Especifique el propietario de la base de datos seleccionándolo en la lista.</span><span class="sxs-lookup"><span data-stu-id="23f3d-109">Specify the owner of the database by selecting from the list.</span></span>  
  
 <span data-ttu-id="23f3d-110">**Usar indización de texto completo**</span><span class="sxs-lookup"><span data-stu-id="23f3d-110">**Use full-text indexing**</span></span>  
 <span data-ttu-id="23f3d-111">Esta casilla está activada y deshabilitada debido a que la indización de texto completo siempre está habilitada en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23f3d-111">This check box is checked and disabled because full-text indexing is always enabled in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="23f3d-112">Para obtener más información, vea [Búsqueda de texto completo](../search/full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="23f3d-112">For more information, see [Full-Text Search](../search/full-text-search.md).</span></span>  
  
 <span data-ttu-id="23f3d-113">**Archivos de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="23f3d-113">**Database Files**</span></span>  
 <span data-ttu-id="23f3d-114">Agregue, vea, modifique o quite archivos de la base de datos asociada.</span><span class="sxs-lookup"><span data-stu-id="23f3d-114">Add, view, modify, or remove database files for the associated database.</span></span> <span data-ttu-id="23f3d-115">Los archivos de la base de datos tienen las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="23f3d-115">Database files have the following properties:</span></span>  
  
 <span data-ttu-id="23f3d-116">**Nombre lógico**</span><span class="sxs-lookup"><span data-stu-id="23f3d-116">**Logical Name**</span></span>  
 <span data-ttu-id="23f3d-117">Escriba o modifique el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="23f3d-117">Enter or modify the name of the file.</span></span>  
  
 <span data-ttu-id="23f3d-118">**Tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="23f3d-118">**File Type**</span></span>  
 <span data-ttu-id="23f3d-119">Seleccione el tipo de archivo en la lista.</span><span class="sxs-lookup"><span data-stu-id="23f3d-119">Select the file type from the list.</span></span> <span data-ttu-id="23f3d-120">El tipo de archivo puede ser **Datos**, **Registro**o **Datos de FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="23f3d-120">The file type can be **Data**, **Log**, or **Filestream Data**.</span></span> <span data-ttu-id="23f3d-121">No se puede modificar el tipo de archivo de un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="23f3d-121">You cannot modify the file type of an existing file.</span></span>  
  
 <span data-ttu-id="23f3d-122">Seleccione **Datos de FILESTREAM** si va a agregar archivos (contenedores) a un grupo de archivos optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="23f3d-122">Select **Filestream Data** if you are adding files (containers) to a memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="23f3d-123">Para agregar archivos (contenedores) a un grupo de archivos de datos FILESTREAM, debe haber habilitado FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="23f3d-123">To add files (containers) to a Filestream data filegroup, FILESTREAM must be enabled.</span></span> <span data-ttu-id="23f3d-124">Puede habilitar FILESTREAM mediante el cuadro de diálogo [Propiedades del servidor (página Opciones avanzadas)](../../database-engine/configure-windows/server-properties-advanced-page.md) .</span><span class="sxs-lookup"><span data-stu-id="23f3d-124">You can enable FILESTREAM by using the [Server Properties (Advanced Page)](../../database-engine/configure-windows/server-properties-advanced-page.md) dialog box.</span></span>  
  
 <span data-ttu-id="23f3d-125">**Grupo de archivos**</span><span class="sxs-lookup"><span data-stu-id="23f3d-125">**Filegroup**</span></span>  
 <span data-ttu-id="23f3d-126">Seleccione el grupo de archivos en la lista.</span><span class="sxs-lookup"><span data-stu-id="23f3d-126">Select the filegroup for the file from the list.</span></span> <span data-ttu-id="23f3d-127">El grupo de archivos es PRIMARY de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="23f3d-127">By default, the filegroup is PRIMARY.</span></span> <span data-ttu-id="23f3d-128">Puede crear un grupo de archivos si selecciona **\<new filegroup>** y escribe información sobre el grupo de archivos en el cuadro de diálogo **Grupo de archivos nuevo**.</span><span class="sxs-lookup"><span data-stu-id="23f3d-128">You can create a new filegroup by selecting **\<new filegroup>** and entering information about the filegroup in the **New Filegroup** dialog box.</span></span> <span data-ttu-id="23f3d-129">También se puede crear un nuevo grupo de archivos en la página **Grupo de archivos** .</span><span class="sxs-lookup"><span data-stu-id="23f3d-129">A new filegroup can also be created on the **Filegroup** page.</span></span> <span data-ttu-id="23f3d-130">No se puede modificar el grupo de archivos de un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="23f3d-130">You cannot modify the filegroup of an existing file.</span></span>  
  
 <span data-ttu-id="23f3d-131">Al agregar archivos (contenedores) a un grupo de archivos optimizados para memoria, el campo **Grupo de archivos** se rellenará con el nombre del grupo de archivos optimizados para memoria de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="23f3d-131">When adding files (containers) to a memory-optimized filegroup, the **Filegroup** field will be populated with the name of the database's memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="23f3d-132">**Tamaño inicial**</span><span class="sxs-lookup"><span data-stu-id="23f3d-132">**Initial Size**</span></span>  
 <span data-ttu-id="23f3d-133">Escriba o modifique el tamaño inicial del archivo en megabytes.</span><span class="sxs-lookup"><span data-stu-id="23f3d-133">Enter or modify the initial size for the file in megabytes.</span></span> <span data-ttu-id="23f3d-134">De forma predeterminada, será el valor de la base de datos **modelo** .</span><span class="sxs-lookup"><span data-stu-id="23f3d-134">By default, this is the value of the **model** database.</span></span>  
  
 <span data-ttu-id="23f3d-135">Este campo no es válido para los archivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="23f3d-135">This field is not valid for FILESTREAM files.</span></span>  
  
 <span data-ttu-id="23f3d-136">Para los archivos de los grupos de archivos optimizados para memoria, este campo no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="23f3d-136">For files in memory-optimized filegroups, this field cannot be modified.</span></span>  
  
 <span data-ttu-id="23f3d-137">**Crecimiento automático**</span><span class="sxs-lookup"><span data-stu-id="23f3d-137">**Autogrowth**</span></span>  
 <span data-ttu-id="23f3d-138">Seleccione o muestre las propiedades de crecimiento automático del archivo.</span><span class="sxs-lookup"><span data-stu-id="23f3d-138">Select or display the autogrowth properties for the file.</span></span> <span data-ttu-id="23f3d-139">Estas propiedades controlan cómo se expande el archivo cuando se alcanza su máximo tamaño de archivo.</span><span class="sxs-lookup"><span data-stu-id="23f3d-139">These properties control how the file expands when its maximum file size is reached.</span></span> <span data-ttu-id="23f3d-140">Para editar los valores de crecimiento automático, haga clic en el botón de edición situado junto a las propiedades de crecimiento automático del archivo deseado y modifique los valores del cuadro de diálogo **Cambiar crecimiento automático** .</span><span class="sxs-lookup"><span data-stu-id="23f3d-140">To edit autogrowth values, click the edit button next to the autogrowth properties for the file that you want, and change the values in the **Change Autogrowth** dialog box.</span></span> <span data-ttu-id="23f3d-141">De forma predeterminada, serán los valores de la base de datos **modelo** .</span><span class="sxs-lookup"><span data-stu-id="23f3d-141">By default, these are the values of the **model** database.</span></span>  
  
 <span data-ttu-id="23f3d-142">Este campo no es válido para los archivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="23f3d-142">This field is not valid for FILESTREAM files.</span></span>  
  
 <span data-ttu-id="23f3d-143">En el caso de los archivos de los grupos de archivos optimizados para memoria, este campo debe establecerse en **Ilimitado**.</span><span class="sxs-lookup"><span data-stu-id="23f3d-143">For files in memory-optimized filegroups, this field should be **Unlimited**.</span></span>  
  
 <span data-ttu-id="23f3d-144">**Path**</span><span class="sxs-lookup"><span data-stu-id="23f3d-144">**Path**</span></span>  
 <span data-ttu-id="23f3d-145">Muestra la ruta de acceso del archivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="23f3d-145">Displays the path of the selected file.</span></span> <span data-ttu-id="23f3d-146">Para especificar una ruta de acceso a un nuevo archivo, haga clic en el botón de edición situado junto a la ruta de acceso al archivo y navegue a la carpeta de destino.</span><span class="sxs-lookup"><span data-stu-id="23f3d-146">To specify a path for a new file, click the edit button next to the path for the file, and navigate to the destination folder.</span></span> <span data-ttu-id="23f3d-147">No se puede modificar la ruta de acceso de un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="23f3d-147">You cannot modify the path of an existing file.</span></span>  
  
 <span data-ttu-id="23f3d-148">Para los archivos FILESTREAM, la ruta de acceso es una carpeta.</span><span class="sxs-lookup"><span data-stu-id="23f3d-148">For FILESTREAM files, the path is a folder.</span></span> <span data-ttu-id="23f3d-149">El [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] creará los archivos subyacentes en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="23f3d-149">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] will create the underlying files in this folder.</span></span>  
  
 <span data-ttu-id="23f3d-150">**Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="23f3d-150">**File Name**</span></span>  
 <span data-ttu-id="23f3d-151">Muestra el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="23f3d-151">Displays the name of the file.</span></span>  
  
 <span data-ttu-id="23f3d-152">Este campo no es válido para los archivos FILESTREAM, lo cual incluye los archivos en grupos de archivos optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="23f3d-152">This field is not valid for FILESTREAM files, including files in memory-optimized filegroups.</span></span>  
  
 <span data-ttu-id="23f3d-153">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="23f3d-153">**Add**</span></span>  
 <span data-ttu-id="23f3d-154">Agrega un nuevo archivo a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="23f3d-154">Add a new file to the database.</span></span>  
  
 <span data-ttu-id="23f3d-155">**Remove**</span><span class="sxs-lookup"><span data-stu-id="23f3d-155">**Remove**</span></span>  
 <span data-ttu-id="23f3d-156">Elimina el archivo seleccionado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="23f3d-156">Delete the selected file from the database.</span></span> <span data-ttu-id="23f3d-157">No podrá eliminarse un archivo a menos que esté vacío.</span><span class="sxs-lookup"><span data-stu-id="23f3d-157">A file cannot be removed unless it is empty.</span></span> <span data-ttu-id="23f3d-158">El archivo de datos principal y el archivo de registro principal no se pueden quitar.</span><span class="sxs-lookup"><span data-stu-id="23f3d-158">The primary data file and log file cannot be removed.</span></span>  
  
 <span data-ttu-id="23f3d-159">Para obtener información acerca de los archivos, vea [Database Files and Filegroups](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="23f3d-159">For information about files, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f3d-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23f3d-160">See Also</span></span>  
 <span data-ttu-id="23f3d-161">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="23f3d-161">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="23f3d-162">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="23f3d-162">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
