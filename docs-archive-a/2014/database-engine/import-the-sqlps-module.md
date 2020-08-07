---
title: Importar el módulo SQLPS | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a972c56e-b2af-4fe6-abbd-817406e2c93a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 37e66db05615ce8a285a80e5ac26b0cae411abeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747180"
---
# <a name="import-the-sqlps-module"></a><span data-ttu-id="d6120-102">Importar el módulo SQLPS</span><span class="sxs-lookup"><span data-stu-id="d6120-102">Import the SQLPS Module</span></span>
  <span data-ttu-id="d6120-103">El método recomendado para administrar [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] desde PowerShell consiste en importar el módulo `sqlps` en un entorno de Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="d6120-103">The recommended way to manage [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] from PowerShell is to import the `sqlps` module into a Windows PowerShell 2.0 environment.</span></span> <span data-ttu-id="d6120-104">El módulo carga y registra los complementos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y los ensamblados de administración.</span><span class="sxs-lookup"><span data-stu-id="d6120-104">The module loads and registers the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins and manageability assemblies.</span></span>  
  
1.  <span data-ttu-id="d6120-105">**Antes de empezar:**  [seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="d6120-105">**Before You Begin:**  [Security](#Security)</span></span>  
  
2.  <span data-ttu-id="d6120-106">**Para cargar el módulo:**  [Cargar el módulo sqlps](#LoadSqlps)</span><span class="sxs-lookup"><span data-stu-id="d6120-106">**To load the module:**  [Load the sqlps Module](#LoadSqlps)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="d6120-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="d6120-107">Before You Begin</span></span>  
 <span data-ttu-id="d6120-108">Después de importar el módulo de `sqlps` en Windows PowerShell, a continuación puede:</span><span class="sxs-lookup"><span data-stu-id="d6120-108">After importing the `sqlps` module into Windows PowerShell, you can then:</span></span>  
  
-   <span data-ttu-id="d6120-109">Ejecutar interactivamente comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6120-109">Interactively run Windows PowerShell commands.</span></span>  
  
-   <span data-ttu-id="d6120-110">Ejecutar archivos de script de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6120-110">Run Windows PowerShell script files.</span></span>  
  
-   <span data-ttu-id="d6120-111">Ejecutar cmdlets de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6120-111">Run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets.</span></span>  
  
-   <span data-ttu-id="d6120-112">Usar las rutas de acceso del proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para navegar por la jerarquía de objetos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6120-112">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider paths to navigate through the hierarchy of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
-   <span data-ttu-id="d6120-113">Usar los modelos de objetos de administración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (como Microsoft.SqlServer.Management.Smo) para administrar los objetos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6120-113">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] manageability object models (such as Microsoft.SqlServer.Management.Smo) to manage [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6120-114">Los verbos usados en los nombres de dos cmdlets de SQL Server (`Encode-Sqlname` y `Decode-Sqlname`) no coinciden con los verbos aprobados para Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="d6120-114">The verbs used in the names of two SQL Server cmdlets (`Encode-Sqlname` and `Decode-Sqlname`) do not match the approved verbs for Windows PowerShell 2.0.</span></span> <span data-ttu-id="d6120-115">Esto no afecta a la operación, pero mejoras de Windows PowerShell genera una advertencia cuando el módulo de `sqlps` se importa a una sesión.</span><span class="sxs-lookup"><span data-stu-id="d6120-115">This has no effect on their operation, but Windows PowerShell raises a warning when the `sqlps` module is imported to a session.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d6120-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d6120-116">Security</span></span>  
 <span data-ttu-id="d6120-117">De forma predeterminada, Windows PowerShell se ejecuta con la directiva de ejecución de scripting establecida en **Restricted**, lo que evita la ejecución de cualquier script de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6120-117">By default, Windows PowerShell runs with the scripting execution policy set to **Restricted**, which prevents running any Windows PowerShell scripts.</span></span> <span data-ttu-id="d6120-118">Para cargar el módulo `sqlps`, puede usar el cmdlet `Set-ExecutionPolicy` para habilitar la ejecución de scripts firmados o de cualquier script.</span><span class="sxs-lookup"><span data-stu-id="d6120-118">To load the `sqlps` module, you can use the `Set-ExecutionPolicy` cmdlet to enable running signed scripts, or any scripts.</span></span> <span data-ttu-id="d6120-119">Ejecute solo scripts de orígenes de confianza y proteja todos los archivos de entrada y salida usando los permisos NTFS adecuados.</span><span class="sxs-lookup"><span data-stu-id="d6120-119">Only run scripts from trusted sources, and secure all input and output files using the appropriate NTFS permissions.</span></span> <span data-ttu-id="d6120-120">Para obtener más información sobre cómo habilitar scripts de Windows PowerShell, vea cómo [ejecutar scripts de Windows PowerShell](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell?view=powershell-6#how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows).</span><span class="sxs-lookup"><span data-stu-id="d6120-120">For more information about enabling Windows PowerShell scripts, see [Running Windows PowerShell Scripts](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell?view=powershell-6#how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows).</span></span>  
  
##  <a name="load-the-sqlps-module"></a><a name="LoadSqlps"></a> <span data-ttu-id="d6120-121">Cargar el módulo sqlps</span><span class="sxs-lookup"><span data-stu-id="d6120-121">Load the sqlps Module</span></span>  

### <a name="to-load-the-sqlps-module-in-windows-powershell"></a><span data-ttu-id="d6120-122">Para cargar el módulo sqlps en Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6120-122">To load the sqlps module in Windows PowerShell</span></span>
  
1.  <span data-ttu-id="d6120-123">Use el cmdlet `Set-ExecutionPolicy` para establecer la directiva de ejecución de script apropiada.</span><span class="sxs-lookup"><span data-stu-id="d6120-123">Use the `Set-ExecutionPolicy` cmdlet to set the appropriate script execution policy.</span></span>  
  
2.  <span data-ttu-id="d6120-124">Use el cmdlet `Import-Module` para importar el módulo sqlps.</span><span class="sxs-lookup"><span data-stu-id="d6120-124">Use the `Import-Module` cmdlet to import the sqlps module.</span></span> <span data-ttu-id="d6120-125">Especifique el parámetro de `DisableNameChecking` si desea suprimir la advertencia acerca de `Encode-Sqlname` y `Decode-Sqlname`.</span><span class="sxs-lookup"><span data-stu-id="d6120-125">Specify the `DisableNameChecking` parameter if you want to suppress the warning about `Encode-Sqlname` and `Decode-Sqlname`.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="d6120-126">Ejemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="d6120-126">Example (PowerShell)</span></span>  
 <span data-ttu-id="d6120-127">En este ejemplo se carga el módulo de `sqlps` con la comprobación de nombre desactivada.</span><span class="sxs-lookup"><span data-stu-id="d6120-127">This example loads the `sqlps` module with name checking turned off.</span></span>  
  
```powershell
## Import the SQL Server Module.  
  
Import-Module "sqlps" -DisableNameChecking  
```  

## <a name="see-also"></a><span data-ttu-id="d6120-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6120-128">See Also</span></span>  
 <span data-ttu-id="d6120-129">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="d6120-129">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span></span>  
 <span data-ttu-id="d6120-130">[Proveedor de SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="d6120-130">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="d6120-131">Utilizar los cmdlets del motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="d6120-131">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
