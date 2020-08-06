---
title: Navegación por las rutas acceso de SQL Server PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: d68aca48-d161-45ed-9f4f-14122ed30218
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0a605479991c3e907cd9dcae254cc1bc04a49392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749997"
---
# <a name="navigate-sql-server-powershell-paths"></a><span data-ttu-id="e61ad-102">Navegar por las rutas de acceso de SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="e61ad-102">Navigate SQL Server PowerShell Paths</span></span>
  <span data-ttu-id="e61ad-103">El proveedor de PowerShell de [!INCLUDE[ssDE](../includes/ssde-md.md)] expone el conjunto de objetos de una instancia de SQL Server en una estructura similar a una ruta de acceso del archivo.</span><span class="sxs-lookup"><span data-stu-id="e61ad-103">The [!INCLUDE[ssDE](../includes/ssde-md.md)] PowerShell provider exposes the set of objects in an instance of SQL Server in a structure similar to a file path.</span></span> <span data-ttu-id="e61ad-104">Puede usar los cmdlets de Windows PowerShell para navegar por la ruta de acceso del proveedor y crear las unidades personalizadas para acortar la ruta de acceso que tiene que escribir.</span><span class="sxs-lookup"><span data-stu-id="e61ad-104">You can use Windows PowerShell cmdlets to navigate the provider path, and create custom drives to shorten the path you have to type.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="e61ad-105">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="e61ad-105">Before You Begin</span></span>  
 <span data-ttu-id="e61ad-106">Windows PowerShell implementa cmdlets para navegar por la estructura de ruta de acceso que representa la jerarquía de objetos compatible con un proveedor de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e61ad-106">Windows PowerShell implements cmdlets to navigate the path structure that represent the hierarchy of objects supported by a PowerShell provider.</span></span> <span data-ttu-id="e61ad-107">Cuando ha navegado a un nodo de la ruta de acceso, puede usar otros cmdlets para realizar operaciones básicas en el objeto actual.</span><span class="sxs-lookup"><span data-stu-id="e61ad-107">When you have navigated to a node in the path, you can use other cmdlets to perform basic operations on the current object.</span></span> <span data-ttu-id="e61ad-108">Dado que los cmdlets se usan con frecuencia, tienen alias canónicos cortos.</span><span class="sxs-lookup"><span data-stu-id="e61ad-108">Because the cmdlets are used frequently, they have short, canonical aliases.</span></span> <span data-ttu-id="e61ad-109">También hay un conjunto de alias que asigna los cmdlets a comandos del símbolo del sistema similares, y otro conjunto para los comandos shell de UNIX.</span><span class="sxs-lookup"><span data-stu-id="e61ad-109">There is also one set of aliases that maps the cmdlets to similar command prompt commands, and another set for UNIX shell commands.</span></span>  
  
 <span data-ttu-id="e61ad-110">El proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] implementa un subconjunto de los cmdlets de proveedor, que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e61ad-110">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider implements a subset of the provider cmdlets, shown in the following table.</span></span>  
  
|<span data-ttu-id="e61ad-111">cmdlet</span><span class="sxs-lookup"><span data-stu-id="e61ad-111">cmdlet</span></span>|<span data-ttu-id="e61ad-112">Alias canónico</span><span class="sxs-lookup"><span data-stu-id="e61ad-112">Canonical alias</span></span>|<span data-ttu-id="e61ad-113">Alias de cmd</span><span class="sxs-lookup"><span data-stu-id="e61ad-113">cmd alias</span></span>|<span data-ttu-id="e61ad-114">Alias de shell de UNIX</span><span class="sxs-lookup"><span data-stu-id="e61ad-114">UNIX shell alias</span></span>|<span data-ttu-id="e61ad-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e61ad-115">Description</span></span>|  
|------------|---------------------|---------------|----------------------|-----------------|  
|<span data-ttu-id="e61ad-116">**Get-Location**</span><span class="sxs-lookup"><span data-stu-id="e61ad-116">**Get-Location**</span></span>|<span data-ttu-id="e61ad-117">**gl**</span><span class="sxs-lookup"><span data-stu-id="e61ad-117">**gl**</span></span>|<span data-ttu-id="e61ad-118">**pwd**</span><span class="sxs-lookup"><span data-stu-id="e61ad-118">**pwd**</span></span>|<span data-ttu-id="e61ad-119">**pwd**</span><span class="sxs-lookup"><span data-stu-id="e61ad-119">**pwd**</span></span>|<span data-ttu-id="e61ad-120">Obtiene el nodo actual.</span><span class="sxs-lookup"><span data-stu-id="e61ad-120">Gets the current node.</span></span>|  
|`Set-Location`|<span data-ttu-id="e61ad-121">**SL**</span><span class="sxs-lookup"><span data-stu-id="e61ad-121">**sl**</span></span>|<span data-ttu-id="e61ad-122">**cd, chdir**</span><span class="sxs-lookup"><span data-stu-id="e61ad-122">**cd, chdir**</span></span>|<span data-ttu-id="e61ad-123">**cd, chdir**</span><span class="sxs-lookup"><span data-stu-id="e61ad-123">**cd, chdir**</span></span>|<span data-ttu-id="e61ad-124">Cambia el nodo actual.</span><span class="sxs-lookup"><span data-stu-id="e61ad-124">Changes the current node.</span></span>|  
|<span data-ttu-id="e61ad-125">**Get-ChildItem**</span><span class="sxs-lookup"><span data-stu-id="e61ad-125">**Get-ChildItem**</span></span>|<span data-ttu-id="e61ad-126">**gci**</span><span class="sxs-lookup"><span data-stu-id="e61ad-126">**gci**</span></span>|<span data-ttu-id="e61ad-127">**dir**</span><span class="sxs-lookup"><span data-stu-id="e61ad-127">**dir**</span></span>|<span data-ttu-id="e61ad-128">**LS**</span><span class="sxs-lookup"><span data-stu-id="e61ad-128">**ls**</span></span>|<span data-ttu-id="e61ad-129">Enumera los objetos almacenados en el nodo actual.</span><span class="sxs-lookup"><span data-stu-id="e61ad-129">Lists the objects stored at the current node.</span></span>|  
|<span data-ttu-id="e61ad-130">**Get-Item**</span><span class="sxs-lookup"><span data-stu-id="e61ad-130">**Get-Item**</span></span>|<span data-ttu-id="e61ad-131">**gi**</span><span class="sxs-lookup"><span data-stu-id="e61ad-131">**gi**</span></span>|||<span data-ttu-id="e61ad-132">Devuelve las propiedades del elemento actual.</span><span class="sxs-lookup"><span data-stu-id="e61ad-132">Returns the properties of the current item.</span></span>|  
|<span data-ttu-id="e61ad-133">**Rename-Item**</span><span class="sxs-lookup"><span data-stu-id="e61ad-133">**Rename-Item**</span></span>|<span data-ttu-id="e61ad-134">**rni**</span><span class="sxs-lookup"><span data-stu-id="e61ad-134">**rni**</span></span>|<span data-ttu-id="e61ad-135">**RN**</span><span class="sxs-lookup"><span data-stu-id="e61ad-135">**rn**</span></span>|<span data-ttu-id="e61ad-136">**ren**</span><span class="sxs-lookup"><span data-stu-id="e61ad-136">**ren**</span></span>|<span data-ttu-id="e61ad-137">Cambia el nombre de un objeto.</span><span class="sxs-lookup"><span data-stu-id="e61ad-137">Renames an object.</span></span>|  
|<span data-ttu-id="e61ad-138">**Remove-Item**</span><span class="sxs-lookup"><span data-stu-id="e61ad-138">**Remove-Item**</span></span>|<span data-ttu-id="e61ad-139">**r**</span><span class="sxs-lookup"><span data-stu-id="e61ad-139">**ri**</span></span>|<span data-ttu-id="e61ad-140">**del, rd**</span><span class="sxs-lookup"><span data-stu-id="e61ad-140">**del, rd**</span></span>|<span data-ttu-id="e61ad-141">**rm, rmdir**</span><span class="sxs-lookup"><span data-stu-id="e61ad-141">**rm, rmdir**</span></span>|<span data-ttu-id="e61ad-142">Quita un objeto.</span><span class="sxs-lookup"><span data-stu-id="e61ad-142">Removes an object.</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e61ad-143">Algunos identificadores de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (nombres de objeto) contienen caracteres que Windows PowerShell no admite en los nombres de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="e61ad-143">Some [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers (object names) contain characters that Windows PowerShell does not support in path names.</span></span> <span data-ttu-id="e61ad-144">Para obtener más información sobre cómo usar nombres que contengan estos caracteres, vea [SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e61ad-144">For more information about how to use names that contain these characters, see [SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md).</span></span>  
  
### <a name="sql-server-information-returned-by-get-childitem"></a><span data-ttu-id="e61ad-145">Información de SQL Server devuelta por Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="e61ad-145">SQL Server Information Returned by Get-ChildItem</span></span>  
 <span data-ttu-id="e61ad-146">La información devuelta por **Get-ChildItem** (o sus alias **dir** e **ls** ) depende de la ubicación en una ruta de acceso de SQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="e61ad-146">The information returned by **Get-ChildItem** (or its **dir** and **ls** aliases) depends on your location in a SQLSERVER: path.</span></span>  
  
|<span data-ttu-id="e61ad-147">Ubicación de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="e61ad-147">Path location</span></span>|<span data-ttu-id="e61ad-148">Resultados de Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="e61ad-148">Get-ChildItem results</span></span>|  
|-------------------|----------------------------|  
|<span data-ttu-id="e61ad-149">SQLSERVER:\SQL</span><span class="sxs-lookup"><span data-stu-id="e61ad-149">SQLSERVER:\SQL</span></span>|<span data-ttu-id="e61ad-150">Devuelve el nombre del equipo local.</span><span class="sxs-lookup"><span data-stu-id="e61ad-150">Returns the name of the local computer.</span></span> <span data-ttu-id="e61ad-151">Si ha usado SMO o WMI para conectarse a las instancias de [!INCLUDE[ssDE](../includes/ssde-md.md)] en otros equipos, esos equipos también se enumeran.</span><span class="sxs-lookup"><span data-stu-id="e61ad-151">If you have used the SMO or WMI to connect to instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] on other computers, those computers are also listed.</span></span>|  
|<span data-ttu-id="e61ad-152">SQLSERVER: \ SQL \\ *NombreDeEquipo*</span><span class="sxs-lookup"><span data-stu-id="e61ad-152">SQLSERVER:\SQL\\*ComputerName*</span></span>|<span data-ttu-id="e61ad-153">Lista de instancias del [!INCLUDE[ssDE](../includes/ssde-md.md)] en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e61ad-153">The list of instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] on the computer.</span></span>|  
|<span data-ttu-id="e61ad-154">SQLServer: \ SQL \\ *NombreDeEquipo* \\ *nombreDeInstancia*</span><span class="sxs-lookup"><span data-stu-id="e61ad-154">SQLSERVER:\SQL\\*ComputerName*\\*InstanceName*</span></span>|<span data-ttu-id="e61ad-155">Lista de tipos de objeto de nivel superior en la instancia, como Extremos, Certificados y Bases de datos.</span><span class="sxs-lookup"><span data-stu-id="e61ad-155">The list of top-level object types in the instance, such as Endpoints, Certificates, and Databases.</span></span>|  
|<span data-ttu-id="e61ad-156">Nodo de clase de objeto, como Databases</span><span class="sxs-lookup"><span data-stu-id="e61ad-156">Object class node, such as Databases</span></span>|<span data-ttu-id="e61ad-157">Lista de objetos de ese tipo, como la lista de bases de datos: master, model, AdventureWorks2008R2.</span><span class="sxs-lookup"><span data-stu-id="e61ad-157">The list of objects of that type, such as the list of databases: master, model, AdventureWorks20008R2.</span></span>|  
|<span data-ttu-id="e61ad-158">Nodo de nombre de objeto, como AdventureWorks2012</span><span class="sxs-lookup"><span data-stu-id="e61ad-158">Object name node, such as AdventureWorks2012</span></span>|<span data-ttu-id="e61ad-159">Lista de los tipos de objeto contenidos en el objeto.</span><span class="sxs-lookup"><span data-stu-id="e61ad-159">The list of object types contained within the object.</span></span> <span data-ttu-id="e61ad-160">Por ejemplo, una base de datos mostraría tipos de objeto como tablas y vistas.</span><span class="sxs-lookup"><span data-stu-id="e61ad-160">For example, a database would list object types such as tables and views.</span></span>|  
  
 <span data-ttu-id="e61ad-161">De forma predeterminada, **Get-ChildItem** no muestra ningún objeto del sistema.</span><span class="sxs-lookup"><span data-stu-id="e61ad-161">By default, **Get-ChildItem** does not list any system objects.</span></span> <span data-ttu-id="e61ad-162">Use el parámetro *Force* para ver los objetos del sistema, como los objetos del esquema **sys** .</span><span class="sxs-lookup"><span data-stu-id="e61ad-162">Use the *Force* parameter to see system objects, such as the objects in the **sys** schema.</span></span>  
  
### <a name="custom-drives"></a><span data-ttu-id="e61ad-163">Unidades personalizadas</span><span class="sxs-lookup"><span data-stu-id="e61ad-163">Custom Drives</span></span>  
 <span data-ttu-id="e61ad-164">Windows PowerShell deja que los usuarios definan las unidades virtuales, a las que se hace referencia como unidades de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e61ad-164">Windows PowerShell lets users define virtual drives, which are referred to as PowerShell drives.</span></span> <span data-ttu-id="e61ad-165">Estas se asignan en los nodos de inicio de una instrucción de ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="e61ad-165">These map over the starting nodes of a path statement.</span></span> <span data-ttu-id="e61ad-166">Se suelen usar para acortar las rutas de acceso que se escriben con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="e61ad-166">They are typically used to shorten paths that are typed frequently.</span></span> <span data-ttu-id="e61ad-167">Las rutas de acceso de SQLSERVER: pueden requerir mucho tiempo y espacio en la ventana de Windows PowerShell, así como mucho esfuerzo para escribirlas.</span><span class="sxs-lookup"><span data-stu-id="e61ad-167">SQLSERVER: paths can get long, taking space in the Windows PowerShell window and requiring a lot of typing.</span></span> <span data-ttu-id="e61ad-168">Si va a trabajar mucho en un nodo de ruta de acceso determinado, puede definir una unidad de Windows PowerShell personalizada que se asigne a ese nodo.</span><span class="sxs-lookup"><span data-stu-id="e61ad-168">If you are going to do a lot of work at a particular path node, you can define a custom Windows PowerShell drive that maps to that node.</span></span>  
  
## <a name="use-powershell-cmdlet-aliases"></a><span data-ttu-id="e61ad-169">Use Alias de Cmdlet de PowerShell</span><span class="sxs-lookup"><span data-stu-id="e61ad-169">Use PowerShell Cmdlet Aliases</span></span>  
 <span data-ttu-id="e61ad-170">**Use un alias de cmdlet**</span><span class="sxs-lookup"><span data-stu-id="e61ad-170">**Use a cmdlet alias**</span></span>  
  
-   <span data-ttu-id="e61ad-171">En lugar de escribir un nombre completo de cmdlet, escriba un alias más corto que se asigna a un comando de símbolo de sistema.</span><span class="sxs-lookup"><span data-stu-id="e61ad-171">Instead of typing a full cmdlet name, type a shorter alias, or one that maps to a familiar commend prompt command.</span></span>  
  
### <a name="alias-example-powershell"></a><span data-ttu-id="e61ad-172">Ejemplo de Alias (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="e61ad-172">Alias Example (PowerShell)</span></span>  
 <span data-ttu-id="e61ad-173">Por ejemplo, puede usar uno de los conjuntos de cmdlets o alias siguientes para recuperar una lista de las instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] disponibles para navegar a la carpeta SQLSERVER:\SQL y solicitar la lista de elementos secundarios de la misma:</span><span class="sxs-lookup"><span data-stu-id="e61ad-173">For example, you can use one of the following sets of cmdlets or aliases to retrieve a listing of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instances available to you by navigating to the SQLSERVER:\SQL folder and requesting the list of child items for the folder:</span></span>  
  
```powershell
## Shows using the full cmdet name.  
Set-Location SQLSERVER:\SQL  
Get-ChildItem  
  
## Shows using canonical aliases.  
sl SQLSERVER:\SQL  
gci  
  
## Shows using command prompt aliases.  
cd SQLSERVER:\SQL  
dir  
  
## Shows using Unix shell aliases.  
cd SQLSERVER:\SQL  
ls  
```  
  
## <a name="use-get-childitem"></a><span data-ttu-id="e61ad-174">Uso de Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="e61ad-174">Use Get-ChildItem</span></span>  

### <a name="return-information-by-using-get-childitem"></a><span data-ttu-id="e61ad-175">Devuelve información mediante Get-Childitem</span><span class="sxs-lookup"><span data-stu-id="e61ad-175">Return information by using Get-Childitem</span></span>
  
1.  <span data-ttu-id="e61ad-176">Navegue hasta el nodo para el que desea obtener una lista de childrem</span><span class="sxs-lookup"><span data-stu-id="e61ad-176">Navigate to the node for which you want a list of childrem</span></span>  
  
2.  <span data-ttu-id="e61ad-177">Ejecuta Get-Childitem para obtener la lista.</span><span class="sxs-lookup"><span data-stu-id="e61ad-177">Run Get-Childitem to get the list.</span></span>  
  
### <a name="get-childitem-example-powershell"></a><span data-ttu-id="e61ad-178">Ejemplo de Get-ChildItem (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="e61ad-178">Get-ChildItem Example (PowerShell)</span></span>  
 <span data-ttu-id="e61ad-179">Estos ejemplos muestran la información devuelta por Get-Childitem para varios nodos en una ruta de acceso del proveedor de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e61ad-179">These examples illustrate the information returned by Get-Childitem for different nodes in a SQL Server provider path.</span></span>  
  
```powershell
## Return the current computer and any computer  
## to which you have made a SQL or WMI connection.  
Set-Location SQLSERVER:\SQL  
Get-ChildItem  
  
## List the instances of the Database Engine on the local computer.  
Set-Location SQLSERVER:\SQL\localhost  
Get-ChildItem  
  
## Lists the categories of objects available in the  
## default instance on the local computer.  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT  
Get-ChildItem  
  
## Lists the databases from the local default instance.  
## The force parameter is used to include the system databases.  
Set-Location SQLSERVER:\SQL\localhost\DEFAULT\Databases  
Get-ChildItem -force  
```  
  
## <a name="create-a-custom-drive"></a><span data-ttu-id="e61ad-180">Crea una unidad personalizada</span><span class="sxs-lookup"><span data-stu-id="e61ad-180">Create a Custom Drive</span></span>  

### <a name="create-and-use-a-custom-drive"></a><span data-ttu-id="e61ad-181">Cree y use una unidad personalizada</span><span class="sxs-lookup"><span data-stu-id="e61ad-181">Create and use a custom drive</span></span>
  
1.  <span data-ttu-id="e61ad-182">Use `New-PSDrive` para definir una unidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="e61ad-182">Use `New-PSDrive` to define a custom drive.</span></span> <span data-ttu-id="e61ad-183">Use el parámetro de `Root` para especificar la ruta de acceso representada por el nombre de la unidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="e61ad-183">Use the `Root` parameter to specify the path that is represented by the custom drive name.</span></span>  
  
2.  <span data-ttu-id="e61ad-184">Haga referencia al nombre de la unidad personalizada en cmdlets de navegación de la ruta de acceso como `Set-Location`.</span><span class="sxs-lookup"><span data-stu-id="e61ad-184">Reference the custom drive name in path navigation cmdlets such as `Set-Location`.</span></span>  
  
### <a name="custom-drive-example-powershell"></a><span data-ttu-id="e61ad-185">Ejemplo de unidad personalizada (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="e61ad-185">Custom Drive Example (PowerShell)</span></span>  
 <span data-ttu-id="e61ad-186">Este ejemplo crea una unidad virtual denominada AWDB que asigna al nodo de una copia implementada de la base de datos de ejemplo de AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="e61ad-186">This example creates a virtual drive named AWDB that maps to the node for a deployed copy of the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="e61ad-187">La unidad virtual se usa para navegar a una tabla de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e61ad-187">The virtual drive is then used to navigate to a table in the database.</span></span>  
  
```powershell
## Create a new virtual drive.  
New-PSDrive -Name AWDB -Root SQLSERVER:\SQL\localhost\DEFAULT\Databases\AdventureWorks2012  
  
## Use AWDB: to navigate to a specific table.  
Set-Location AWDB:\Tables\Purchasing.Vendor  
```  
  
## <a name="see-also"></a><span data-ttu-id="e61ad-188">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e61ad-188">See Also</span></span>  
 <span data-ttu-id="e61ad-189">[Proveedor de SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="e61ad-189">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="e61ad-190">[Trabajar con rutas de acceso SQL Server PowerShell](work-with-sql-server-powershell-paths.md) </span><span class="sxs-lookup"><span data-stu-id="e61ad-190">[Work With SQL Server PowerShell Paths](work-with-sql-server-powershell-paths.md) </span></span>  
 <span data-ttu-id="e61ad-191">[Convertir urn en rutas de acceso del proveedor de SQL Server](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span><span class="sxs-lookup"><span data-stu-id="e61ad-191">[Convert URNs to SQL Server Provider Paths](../database-engine/convert-urns-to-sql-server-provider-paths.md) </span></span>  
 [<span data-ttu-id="e61ad-192">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="e61ad-192">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
