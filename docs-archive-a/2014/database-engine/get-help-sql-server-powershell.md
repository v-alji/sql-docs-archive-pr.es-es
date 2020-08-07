---
title: Obtener ayuda de SQL Server PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Help [PowerShell]
- Help [SQL Server], PowerShell
- PowerShell [SQL Server], help
ms.assetid: 968c316d-db83-4c24-8ea6-9f18736842f7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f1d97a3b694eebb924f9e1ff228d4d38da4f45ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746423"
---
# <a name="get-help-sql-server-powershell"></a><span data-ttu-id="82626-102">Get Help SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="82626-102">Get Help SQL Server PowerShell</span></span>
  <span data-ttu-id="82626-103">Hay varios orígenes de información sobre cómo utilizar los cmdlets y el proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82626-103">There are several sources of information about using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider for Windows PowerShell and cmdlets.</span></span> <span data-ttu-id="82626-104">Esto incluye la ayuda que está disponible en el entorno de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82626-104">This includes the help that is available in the Windows PowerShell environment.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="82626-105">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="82626-105">Before You Begin</span></span>  
 <span data-ttu-id="82626-106">Para obtener información sobre Windows PowerShell, vea el [Guía de Introducción de Windows PowerShell](https://technet.microsoft.com/library/hh857337.aspx).</span><span class="sxs-lookup"><span data-stu-id="82626-106">To learn about Windows PowerShell, see [Windows PowerShell Getting Started Guide](https://technet.microsoft.com/library/hh857337.aspx).</span></span>  
  
 <span data-ttu-id="82626-107">Para ver una introducción a los cmdlets y el proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vea [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="82626-107">For an overview of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets and provider, see [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="help-in-the-windows-powershell-environment"></a><span data-ttu-id="82626-108">Ayuda en el entorno de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="82626-108">Help in the Windows PowerShell Environment</span></span>  
 <span data-ttu-id="82626-109">Use el cmdlet **Get-Help** para obtener ayuda en el entorno de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82626-109">Use the **Get-Help** cmdlet to get help in the Windows PowerShell environment.</span></span> <span data-ttu-id="82626-110">**Get-Help** proporciona ayuda básica para el lenguaje de Windows PowerShell y los diversos cmdlets y proveedores disponibles en Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82626-110">**Get-Help** provides basic help for the Windows PowerShell language and the various cmdlets and providers available in Windows PowerShell.</span></span>  
  
 <span data-ttu-id="82626-111">Para obtener más información sobre las formas en que puede usar **Get-Help**, vea [Obtener Ayuda: Get-Help](https://go.microsoft.com/fwlink/?LinkId=102136).</span><span class="sxs-lookup"><span data-stu-id="82626-111">For more information on the ways you can use **Get-Help**, see [Get-Help: Getting Help](https://go.microsoft.com/fwlink/?LinkId=102136).</span></span>  
  
### <a name="sql-server-powershell-provider-help"></a><span data-ttu-id="82626-112">Ayuda del proveedor de SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="82626-112">SQL Server PowerShell Provider Help</span></span>  
 <span data-ttu-id="82626-113">El proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell implementa varias carpetas en una unidad virtual de SQLSERVER, como el SQLSERVER: \ SQL y SQLSERVER: \ Carpetas de DAC.</span><span class="sxs-lookup"><span data-stu-id="82626-113">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider implements several folders on a SQLSERVER virtual drive, such as the SQLSERVER:\SQL and SQLSERVER:\DAC folders.</span></span> <span data-ttu-id="82626-114">Cada carpeta está asociada con uno de los modelos de objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="82626-114">Each folder is associated with one of the SQL Server manageability object models.</span></span> <span data-ttu-id="82626-115">Aunque puede mostrar los métodos y propiedades asociados con cada nodo en una ruta de acceso de SQL Server, no puede obtener ayuda para ellos en el entorno de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82626-115">While you can list the methods and properties associated with each node in a SQL Server path, you cannot get help for them in the PowerShell environment.</span></span> <span data-ttu-id="82626-116">Para una tabla de carpetas con vínculos a referencia de programación asociada, vea [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="82626-116">For a table of the folders with links to the associated programming reference, see [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span></span>  
  
### <a name="invoke-sqlcmd-help"></a><span data-ttu-id="82626-117">Ayuda de Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="82626-117">Invoke-Sqlcmd Help</span></span>  
 <span data-ttu-id="82626-118">El cmdlet **Invoke-Sqlcmd** toma como entrada cualquier archivo de script o consulta que la utilidad **sqlcmd** pueda ejecutar.</span><span class="sxs-lookup"><span data-stu-id="82626-118">The **Invoke-Sqlcmd** cmdlet takes as input any query or script file that can be run by the **sqlcmd** utility.</span></span> <span data-ttu-id="82626-119">Puede usar **Get-Help** para obtener información sobre **Invoke-Sqlcmd** y sus parámetros, pero no hay ninguna cobertura de **Get-Help** para las consultas **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="82626-119">You can use **Get-Help** to get information about **Invoke-Sqlcmd** and its parameters, but there is no **Get-Help** coverage for the **sqlcmd** queries.</span></span>  
  
 <span data-ttu-id="82626-120">La entrada *-Query* o *-QueryFromFile* puede contener:</span><span class="sxs-lookup"><span data-stu-id="82626-120">The *-Query* or *-QueryFromFile* input can contain:</span></span>  
  
-   <span data-ttu-id="82626-121">Variables y comandos de**sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="82626-121">**sqlcmd** variables and commands.</span></span> <span data-ttu-id="82626-122">Para obtener información sobre estas variables y comandos, consulte la sección Comentarios de [sqlcmd Utility](../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="82626-122">For information about these variables and commands, see the Remarks section of [sqlcmd Utility](../tools/sqlcmd-utility.md).</span></span>  
  
-   <span data-ttu-id="82626-123">Instrucciones[!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82626-123">[!INCLUDE[tsql](../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="82626-124">Para obtener más información sobre el idioma [!INCLUDE[tsql](../includes/tsql-md.md)], vea [Referencia de Transact-SQL &#40;motor de base de datos&#41;](/sql/t-sql/language-reference).</span><span class="sxs-lookup"><span data-stu-id="82626-124">For more information about the [!INCLUDE[tsql](../includes/tsql-md.md)] language, see [Transact-SQL Reference &#40;Database Engine&#41;](/sql/t-sql/language-reference).</span></span>  
  
-   <span data-ttu-id="82626-125">Instrucciones XQuery.</span><span class="sxs-lookup"><span data-stu-id="82626-125">XQuery statements.</span></span> <span data-ttu-id="82626-126">Para obtener más información sobre lenguaje XQuery admitido por [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vea [Referencia del lenguaje XQuery &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server).</span><span class="sxs-lookup"><span data-stu-id="82626-126">For more information about the XQuery language supported by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [XQuery Language Reference &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server).</span></span>  
  
## <a name="get-help-for-a-sql-server-cmdlet"></a><span data-ttu-id="82626-127">Obtener ayuda para un cmdlet de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="82626-127">Get Help for a SQL Server cmdlet</span></span>  
 <span data-ttu-id="82626-128">**Obtención de ayuda sobre un cmdlet**</span><span class="sxs-lookup"><span data-stu-id="82626-128">**To get help for a cmdlet**</span></span>  
  
-   <span data-ttu-id="82626-129">Ejecute Get-Help especificando el nombre del cmdlet y el nivel de ayuda que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="82626-129">Run Get-Help specifying the name of the cmdlet and the level of help to be returned.</span></span>  
  
### <a name="example-cmdlet-get-help"></a><span data-ttu-id="82626-130">Ejemplo: Get-Help de cmdlet</span><span class="sxs-lookup"><span data-stu-id="82626-130">Example: cmdlet Get-Help</span></span>  
 <span data-ttu-id="82626-131">Los siguientes ejemplos devuelven diferentes niveles de ayuda para **Invoke-Sqlcmd**:</span><span class="sxs-lookup"><span data-stu-id="82626-131">The following examples return various levels of help for **Invoke-Sqlcmd**:</span></span>  
  
```powershell
## Get the basic help.  
Get-Help Invoke-Sqlcmd  
  
## Get the full help.  
Get-Help Invoke-Sqlcmd -Full  
  
## Get the parameter descriptions.  
Get-Help Invoke-Sqlcmd -Parameter *  
  
## Get the code examples.  
Get-Help Invoke-Sqlcmd -Examples  
  
## Get the syntax diagram.  
Get-Help Invoke-Sqlcmd -Syntax  
```  
  
## <a name="get-a-list-of-providers"></a><span data-ttu-id="82626-132">Obtener una lista de proveedores</span><span class="sxs-lookup"><span data-stu-id="82626-132">Get a List of Providers</span></span>  

### <a name="to-get-a-list-of-active-providers"></a><span data-ttu-id="82626-133">Para obtener una lista de proveedores activo</span><span class="sxs-lookup"><span data-stu-id="82626-133">To get a list of active providers</span></span>
  
1.  <span data-ttu-id="82626-134">Ejecute Get-Help ejecutando la categoría del proveedor.</span><span class="sxs-lookup"><span data-stu-id="82626-134">Run Get-Help specifying the provider category.</span></span>  
  
 <span data-ttu-id="82626-135">Para obtener más información sobre cómo obtener ayuda del proveedor en Windows PowerShell, vea [Unidades y proveedores](https://go.microsoft.com/fwlink/?LinkId=102137).</span><span class="sxs-lookup"><span data-stu-id="82626-135">For more information about getting provider help in Windows PowerShell, see [Drives and Providers](https://go.microsoft.com/fwlink/?LinkId=102137).</span></span>  
  
### <a name="example-get-a-list-of-providers"></a><span data-ttu-id="82626-136">Ejemplo: Obtener una lista de proveedores</span><span class="sxs-lookup"><span data-stu-id="82626-136">Example: Get a List of Providers</span></span>  
 <span data-ttu-id="82626-137">Este código devuelve una lista de los proveedores habilitados actualmente en la sesión de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="82626-137">This code returns a list of the providers currently enabled in your Windows PowerShell session:</span></span>  
  
```powershell
Get-Help -Category provider  
```  
  
## <a name="get-help-about-the-sql-server-provider"></a><span data-ttu-id="82626-138">Obtener ayuda acerca del proveedor de SQL Server</span><span class="sxs-lookup"><span data-stu-id="82626-138">Get Help About the SQL Server Provider</span></span>  
 <span data-ttu-id="82626-139">**Para obtener ayuda acerca del proveedor**</span><span class="sxs-lookup"><span data-stu-id="82626-139">**To get help about the provider**</span></span>  
  
1.  <span data-ttu-id="82626-140">Ejecute Get-Help especificando el nombre SQLServer</span><span class="sxs-lookup"><span data-stu-id="82626-140">Run Get-Help specifying the name SQLServer</span></span>  
  
### <a name="example-get-sql-server-provider-help"></a><span data-ttu-id="82626-141">Ejemplo: Obtener Ayuda del proveedor de SQL Server</span><span class="sxs-lookup"><span data-stu-id="82626-141">Example: Get SQL Server Provider Help</span></span>  
 <span data-ttu-id="82626-142">Este ejemplo devuelve información básica sobre el proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="82626-142">This example returns basic information about the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider:</span></span>  
  
```powershell
Get-Help SQLServer  
```  
  
## <a name="list-methods-and-properties"></a><span data-ttu-id="82626-143">Enumerar métodos y propiedades</span><span class="sxs-lookup"><span data-stu-id="82626-143">List Methods and Properties</span></span>  
 <span data-ttu-id="82626-144">**Para mostrar los métodos y propiedades para un nodo en una ruta de acceso del proveedor de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="82626-144">**To list the methods and properties for a node in a SQL Server provider path**</span></span>  
  
1.  <span data-ttu-id="82626-145">Un CD de un nodo de la ruta de acceso de SQL Server, o crear una variable establecida en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="82626-145">Either CD to a node in the SQL Server path, or create a variable set to that location.</span></span>  
  
2.  <span data-ttu-id="82626-146">Ejecute el cmdlet **Get-Member** con el parámetro-type establecido en métodos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="82626-146">Run the **Get-Member** cmdlet with the -Type parameter set to either Methods or Properties</span></span>  
  
### <a name="examples-listing-methods-and-properties"></a><span data-ttu-id="82626-147">Ejemplos: Enumerar métodos y propiedades</span><span class="sxs-lookup"><span data-stu-id="82626-147">Examples: Listing Methods and Properties</span></span>  
 <span data-ttu-id="82626-148">En este ejemplo se enumeran los métodos admitidos para el nodo de bases de datos:</span><span class="sxs-lookup"><span data-stu-id="82626-148">This example lists the methods supported for the Databases node:</span></span>  
  
```powershell
Set-Location SQL:\MyComputer\DEFAULT\Databases  
Get-Item . | Get-Member -Type Methods  
```  
  
 <span data-ttu-id="82626-149">Este ejemplo enumera las propiedades de una variable que se ha establecido en un objeto SMO Table:</span><span class="sxs-lookup"><span data-stu-id="82626-149">This example lists the properties for a variable that has been set to an SMO Table object:</span></span>  
  
```powershell
$MyVar = New-Object Microsoft.SqlServer.Management.SMO.Table  
$MyVar | Get-Member -Type Properties  
```  
  
## <a name="see-also"></a><span data-ttu-id="82626-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82626-150">See Also</span></span>  
 <span data-ttu-id="82626-151">[Proveedor de SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="82626-151">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="82626-152">Utilizar los cmdlets del motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="82626-152">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
