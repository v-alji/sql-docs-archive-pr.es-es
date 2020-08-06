---
title: Propiedades de la base de datos (página Grupos de archivos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.filegroups.f1
ms.assetid: 8d06e859-73dd-4019-b6e8-99c5c5297697
author: stevestein
ms.author: sstein
ms.openlocfilehash: d0546a17491ed5d3b36890a605c5faa922c24fe6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672095"
---
# <a name="database-properties-filegroups-page"></a><span data-ttu-id="967ea-102">Propiedades de la base de datos (página Grupos de archivos)</span><span class="sxs-lookup"><span data-stu-id="967ea-102">Database Properties (Filegroups Page)</span></span>
  <span data-ttu-id="967ea-103">Utilice esta página para ver los grupos de archivos o para agregar un nuevo grupo de archivos a la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="967ea-103">Use this page to view the filegroups or add a new filegroup to the selected database.</span></span> <span data-ttu-id="967ea-104">Los tipos de grupo de archivos se separan en grupos de archivos de *filas* , datos FILESTREAM y grupos de archivos optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="967ea-104">Filegroup types are separated into *row* filegroups, FILESTREAM data, and memory-optimized filegroups.</span></span>  
  
 <span data-ttu-id="967ea-105">Los grupos de archivos de filas contienen archivos de registro y de datos normales.</span><span class="sxs-lookup"><span data-stu-id="967ea-105">Row filegroups contain regular data and log files.</span></span> <span data-ttu-id="967ea-106">Los grupos de archivos de datos de FILESTREAM contienen archivos de datos de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="967ea-106">FILESTREAM data filegroups contain FILESTREAM data files.</span></span> <span data-ttu-id="967ea-107">Estos archivos de datos almacenan información sobre cómo se almacenan los datos de objetos binarios grandes (BLOB) en el sistema de archivos, cuando se utiliza el almacenamiento de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="967ea-107">These data files store information about how binary large object (BLOB) data is stored on the file system when you are using FILESTREAM storage.</span></span> <span data-ttu-id="967ea-108">Las opciones son las mismas para ambos tipos de grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="967ea-108">The options are the same for both types of filegroups.</span></span>  
  
 <span data-ttu-id="967ea-109">Si FILESTREAM no está habilitado, la sección **FILESTREAM** no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="967ea-109">If FILESTREAM is not enabled, the **Filestream** section will not be available.</span></span> <span data-ttu-id="967ea-110">Puede habilitar el almacenamiento de FILESTREAM mediante el cuadro de diálogo [Propiedades del servidor (página Avanzadas)](../../database-engine/configure-windows/server-properties-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="967ea-110">You can enable FILESTREAM storage by using [Server Properties (Advanced Page)](../../database-engine/configure-windows/server-properties-advanced-page.md).</span></span>  
  
 <span data-ttu-id="967ea-111">Para obtener más información sobre cómo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa los grupos de archivos de filas, vea [Archivos y grupos de archivos de base de datos](database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="967ea-111">For information about how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses row filegroups, see [Database Files and Filegroups](database-files-and-filegroups.md).</span></span> <span data-ttu-id="967ea-112">Para obtener más información sobre los grupos de archivos y datos de FILESTREAM, vea [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="967ea-112">For more information about FILESTREAM data and filegroups, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="967ea-113">Los grupos de archivos optimizados para memoria son necesarios para que una base de datos pueda contener una o más tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="967ea-113">Memory-optimized file groups are required for a database to contain one or more memory-optimized tables.</span></span>  
  
## <a name="row-and-filestream-data-filegroup-options"></a><span data-ttu-id="967ea-114">Opciones de grupo de archivos de filas y de datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="967ea-114">Row and FILESTREAM Data Filegroup Options</span></span>  
 <span data-ttu-id="967ea-115">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="967ea-115">**Name**</span></span>  
 <span data-ttu-id="967ea-116">Escriba el nombre del grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="967ea-116">Enter the name of the filegroup.</span></span>  
  
 <span data-ttu-id="967ea-117">**Archivos**</span><span class="sxs-lookup"><span data-stu-id="967ea-117">**Files**</span></span>  
 <span data-ttu-id="967ea-118">Muestra el recuento de archivos incluidos en el grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="967ea-118">Displays the count of files in the filegroup.</span></span>  
  
 <span data-ttu-id="967ea-119">**Solo lectura**</span><span class="sxs-lookup"><span data-stu-id="967ea-119">**Read-only**</span></span>  
 <span data-ttu-id="967ea-120">Seleccione esta opción para establecer el grupo de archivos en un estado de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="967ea-120">Select to set the filegroup to a read-only status.</span></span>  
  
 <span data-ttu-id="967ea-121">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="967ea-121">**Default**</span></span>  
 <span data-ttu-id="967ea-122">Seleccione esta opción para establecer este grupo de archivos como el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="967ea-122">Select to make this filegroup the default filegroup.</span></span> <span data-ttu-id="967ea-123">Puede tener un grupo de archivos predeterminado para las filas y un grupo de archivos predeterminado para los datos de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="967ea-123">You can have one default filegroup for rows and one default filegroup for FILESTREAM data.</span></span>  
  
 <span data-ttu-id="967ea-124">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="967ea-124">**Add**</span></span>  
 <span data-ttu-id="967ea-125">Agrega una nueva fila en blanco a la lista de grupos de archivo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="967ea-125">Adds a new blank row to the grid listing filegroups for the database.</span></span>  
  
 <span data-ttu-id="967ea-126">**Remove**</span><span class="sxs-lookup"><span data-stu-id="967ea-126">**Remove**</span></span>  
 <span data-ttu-id="967ea-127">Quita la fila del grupo de archivos seleccionado de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="967ea-127">Removes the selected filegroup row from the grid.</span></span>  
  
## <a name="memory-optimized-data-filegroup-options"></a><span data-ttu-id="967ea-128">Opciones de grupo de archivos de datos con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="967ea-128">Memory-Optimized Data Filegroup Options</span></span>  
 <span data-ttu-id="967ea-129">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="967ea-129">**Name**</span></span>  
 <span data-ttu-id="967ea-130">Escriba el nombre del grupo de archivos optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="967ea-130">Enter the name of the memory-optimized filegroup.</span></span>  
  
 <span data-ttu-id="967ea-131">**Archivos FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="967ea-131">**Filestream Files**</span></span>  
 <span data-ttu-id="967ea-132">Muestra el número de archivos (contenedores) en el grupo de archivos de datos optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="967ea-132">Displays the number of files (containers) in the memory-optimized data filegroup.</span></span> <span data-ttu-id="967ea-133">Puede agregar contenedores en la página **Archivos** .</span><span class="sxs-lookup"><span data-stu-id="967ea-133">You can add containers in the **Files** page.</span></span>  
  
 <span data-ttu-id="967ea-134">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="967ea-134">**Add**</span></span>  
 <span data-ttu-id="967ea-135">Agrega una nueva fila en blanco a la lista de grupos de archivo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="967ea-135">Adds a new blank row to the grid listing filegroups for the database.</span></span>  
  
 <span data-ttu-id="967ea-136">**Remove**</span><span class="sxs-lookup"><span data-stu-id="967ea-136">**Remove**</span></span>  
 <span data-ttu-id="967ea-137">Quita la fila del grupo de archivos seleccionado de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="967ea-137">Removes the selected filegroup row from the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="967ea-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="967ea-138">See Also</span></span>  
 <span data-ttu-id="967ea-139">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="967ea-139">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="967ea-140">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="967ea-140">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
