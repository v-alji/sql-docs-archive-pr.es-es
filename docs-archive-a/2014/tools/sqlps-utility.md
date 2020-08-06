---
title: sqlps, utilidad | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- sqlps utility
- PowerShell [SQL Server], sqlps utility
ms.assetid: 4b2515a6-12c3-44fb-b263-1c567681cd2b
author: stevestein
ms.author: sstein
ms.openlocfilehash: b445366b3fb99ad4beebdf7b203ada77afe90c8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743724"
---
# <a name="sqlps-utility"></a><span data-ttu-id="6e4d4-102">sqlps, utilidad</span><span class="sxs-lookup"><span data-stu-id="6e4d4-102">sqlps Utility</span></span>
  <span data-ttu-id="6e4d4-103">La utilidad `sqlps` inicia una sesión de Windows PowerShell 2.0 con el proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell y los cmdlets cargados y registrados.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-103">The `sqlps` utility starts a Windows PowerShell 2.0 session with the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and cmdlets loaded and registered.</span></span> <span data-ttu-id="6e4d4-104">Puede escribir scripts o comandos de PowerShell que usen los componentes de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell para trabajar con instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y sus objetos.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-104">You can enter PowerShell commands or scripts that use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell components to work with instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and their objects.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="6e4d4-105">En su lugar, use el módulo `sqlps` de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-105">Use the `sqlps` PowerShell module instead.</span></span> <span data-ttu-id="6e4d4-106">Para obtener más información sobre el `sqlps` módulo, consulte [importar el módulo SQLPS](../database-engine/import-the-sqlps-module.md).</span><span class="sxs-lookup"><span data-stu-id="6e4d4-106">For more information about the `sqlps` module, see [Import the SQLPS Module](../database-engine/import-the-sqlps-module.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e4d4-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e4d4-107">Syntax</span></span>  
  
```  
  
      sqlps   
[ [ [ -NoLogo ][ -NoExit ][ -NoProfile ]  
    [ -OutPutFormat { Text | XML } ] [ -InPutFormat { Text | XML } ]  
  ]  
  [ -Command { -  
             | script_block [ -argsargument_array ]  
             | string [ command_parameters ]  
             }  
  ]  
]  
[ -? | -Help ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6e4d4-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6e4d4-108">Arguments</span></span>  
 <span data-ttu-id="6e4d4-109">**-NoLogo**</span><span class="sxs-lookup"><span data-stu-id="6e4d4-109">**-NoLogo**</span></span>  
 <span data-ttu-id="6e4d4-110">Especifica que la utilidad `sqlps` debe ocultar el título de copyright cuando se inicia.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-110">Specifies that the `sqlps` utility hide the copyright banner when it starts.</span></span>  
  
 <span data-ttu-id="6e4d4-111">**-NoExit**</span><span class="sxs-lookup"><span data-stu-id="6e4d4-111">**-NoExit**</span></span>  
 <span data-ttu-id="6e4d4-112">Especifica que la utilidad `sqlps` debe seguir ejecutándose después de que los comandos de inicio se hayan completado.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-112">Specifies that the `sqlps` utility continue running after the startup commands have completed.</span></span>  
  
 <span data-ttu-id="6e4d4-113">**-NoProfile**</span><span class="sxs-lookup"><span data-stu-id="6e4d4-113">**-NoProfile**</span></span>  
 <span data-ttu-id="6e4d4-114">Especifica que la utilidad `sqlps` no debe cargar un perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-114">Specifies that the `sqlps` utility not load a user profile.</span></span> <span data-ttu-id="6e4d4-115">Los perfiles de usuario registran los alias, funciones y variables de uso frecuente para usarlos en las sesiones de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-115">User profiles record commonly used aliases, functions, and variables for use across PowerShell sessions.</span></span>  
  
 <span data-ttu-id="6e4d4-116">**-OutPutFormat** { **Text** | **XML** }</span><span class="sxs-lookup"><span data-stu-id="6e4d4-116">**-OutPutFormat** { **Text** | **XML** }</span></span>  
 <span data-ttu-id="6e4d4-117">Especifica que `sqlps` se dé formato a la salida de la utilidad como cadenas de texto (**Text**) o en un formato CLIXML serializado (**XML**).</span><span class="sxs-lookup"><span data-stu-id="6e4d4-117">Specifies that the `sqlps` utility output be formatted as either text strings (**Text**) or in a serialized CLIXML format (**XML**).</span></span>  
  
 <span data-ttu-id="6e4d4-118">**-InPutFormat** { **Text** | **XML** }</span><span class="sxs-lookup"><span data-stu-id="6e4d4-118">**-InPutFormat** { **Text** | **XML** }</span></span>  
 <span data-ttu-id="6e4d4-119">Especifica que se dé formato a la entrada de la `sqlps` utilidad como cadenas de texto (**Text**) o en un formato CLIXML serializado (**XML**).</span><span class="sxs-lookup"><span data-stu-id="6e4d4-119">Specifies that input to the `sqlps` utility is formatted as either text strings (**Text**) or in a serialized CLIXML format (**XML**).</span></span>  
  
 <span data-ttu-id="6e4d4-120">**-Command**</span><span class="sxs-lookup"><span data-stu-id="6e4d4-120">**-Command**</span></span>  
 <span data-ttu-id="6e4d4-121">Especifica el comando que debe ejecutar la utilidad `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-121">Specifies the command for the `sqlps` utility to run.</span></span> <span data-ttu-id="6e4d4-122">La `sqlps` utilidad ejecuta el comando y, a continuación, se cierra, a menos que también se especifique **-NoExit** .</span><span class="sxs-lookup"><span data-stu-id="6e4d4-122">The `sqlps` utility runs the command and then exits, unless **-NoExit** is also specified.</span></span> <span data-ttu-id="6e4d4-123">No especifique ningún otro modificador después de **-Command**; se leerían como parámetros del comando.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-123">Do not specify any other switches after **-Command**, they will be read as command parameters.</span></span>  
  
 **-**  
 <span data-ttu-id="6e4d4-124">**-Command:** especifica que la `sqlps` utilidad lee la entrada de la entrada estándar.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-124">**-Command-** specifies that the `sqlps` utility read the input from the standard input.</span></span>  
  
 <span data-ttu-id="6e4d4-125">*script_block* [ **-args**_argument_array_ ]</span><span class="sxs-lookup"><span data-stu-id="6e4d4-125">*script_block* [ **-args**_argument_array_ ]</span></span>  
 <span data-ttu-id="6e4d4-126">Especifica un bloque de comandos de PowerShell que se han de ejecutar; el bloque debe incluirse entre llaves: {}.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-126">Specifies a block of PowerShell commands to run, the block must be enclosed in braces: {}.</span></span> <span data-ttu-id="6e4d4-127">*Script_block* solo se puede especificar cuando `sqlps` se llama a la utilidad desde **PowerShell** o desde otra sesión de la `sqlps` utilidad.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-127">*Script_block* can only be specified when the `sqlps` utility is called from either **PowerShell** or another `sqlps` utility session.</span></span> <span data-ttu-id="6e4d4-128">*argument_array* es una matriz de variables de PowerShell que contiene los argumentos de los comandos de PowerShell en *script_block*.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-128">The *argument_array* is an array of PowerShell variables containing the arguments for the PowerShell commands in the *script_block*.</span></span>  
  
 <span data-ttu-id="6e4d4-129">*string* [ *command_parameters* ]</span><span class="sxs-lookup"><span data-stu-id="6e4d4-129">*string* [ *command_parameters* ]</span></span>  
 <span data-ttu-id="6e4d4-130">Especifica una cadena que contiene los comandos de PowerShell que se han de ejecutar.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-130">Specifies a string that contains the PowerShell commands to be run.</span></span> <span data-ttu-id="6e4d4-131">Use el formato **"& { *`command`* }"**.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-131">Use the format **"&{*`command`*}"**.</span></span> <span data-ttu-id="6e4d4-132">Las comillas indican una cadena y el operador de invocación (&) hace que la `sqlps` utilidad ejecute el comando.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-132">The quotation marks indicate a string, and the invoke operator (&) causes the `sqlps` utility to run the command.</span></span>  
  
 <span data-ttu-id="6e4d4-133">[ **-?**</span><span class="sxs-lookup"><span data-stu-id="6e4d4-133">[ **-?**</span></span><span data-ttu-id="6e4d4-134"> |  **-Help** ]</span><span class="sxs-lookup"><span data-stu-id="6e4d4-134"> | **-Help** ]</span></span>  
 <span data-ttu-id="6e4d4-135">Muestra el resumen de la sintaxis de las opciones de la utilidad `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-135">Shows the syntax summary of the `sqlps` utility options.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e4d4-136">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6e4d4-136">Remarks</span></span>  
 <span data-ttu-id="6e4d4-137">La `sqlps` utilidad inicia el entorno de PowerShell (PowerShell.exe) y carga el [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] módulo de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-137">The `sqlps` utility starts the PowerShell environment (PowerShell.exe) and loads the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell module.</span></span> <span data-ttu-id="6e4d4-138">El módulo, también denominado `sqlps` , carga y registra estos [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Complementos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6e4d4-138">The module, also named `sqlps`, loads and registers these [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins:</span></span>  
  
-   <span data-ttu-id="6e4d4-139">Microsoft.SqlServer.Management.PSProvider.dll</span><span class="sxs-lookup"><span data-stu-id="6e4d4-139">Microsoft.SqlServer.Management.PSProvider.dll</span></span>  
  
     <span data-ttu-id="6e4d4-140">Implementa el proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell y cmdlets asociados como **Encode-SqlName** y **Decode-SqlName**.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-140">Implements the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell provider and associated cmdlets such as **Encode-SqlName** and **Decode-SqlName**.</span></span>  
  
-   <span data-ttu-id="6e4d4-141">Microsoft.SqlServer.Management.PSSnapin.dll</span><span class="sxs-lookup"><span data-stu-id="6e4d4-141">Microsoft.SqlServer.Management.PSSnapin.dll</span></span>  
  
     <span data-ttu-id="6e4d4-142">Implementa los cmdlets **Invoke-Sqlcmd** e **Invoke-PolicyEvaluation** .</span><span class="sxs-lookup"><span data-stu-id="6e4d4-142">Implements the **Invoke-Sqlcmd** and **Invoke-PolicyEvaluation** cmdlets.</span></span>  
  
 <span data-ttu-id="6e4d4-143">Puede usar la utilidad `sqlps` para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="6e4d4-143">You can use the `sqlps` utility to do the following:</span></span>  
  
-   <span data-ttu-id="6e4d4-144">Ejecutar interactivamente comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-144">Interactively run PowerShell commands.</span></span>  
  
-   <span data-ttu-id="6e4d4-145">Ejecutar archivos de script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-145">Run PowerShell script files.</span></span>  
  
-   <span data-ttu-id="6e4d4-146">Ejecutar cmdlets de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e4d4-146">Run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets.</span></span>  
  
-   <span data-ttu-id="6e4d4-147">Usar las rutas de acceso del proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para navegar por la jerarquía de objetos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e4d4-147">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider paths to navigate through the hierarchy of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="6e4d4-148">De forma predeterminada, la `sqlps` utilidad se ejecuta con la Directiva de ejecución de scripting establecida en **Restricted**.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-148">By default, the `sqlps` utility runs with the scripting execution policy set to **Restricted**.</span></span> <span data-ttu-id="6e4d4-149">Esto evita la ejecución de cualquier script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-149">This prevents running any PowerShell scripts.</span></span> <span data-ttu-id="6e4d4-150">Puede usar el cmdlet **Set-ExecutionPolicy** para habilitar la ejecución de scripts firmados o de cualquier script.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-150">You can use the **Set-ExecutionPolicy** cmdlet to enable running signed scripts, or any scripts.</span></span> <span data-ttu-id="6e4d4-151">Ejecute solo scripts de orígenes de confianza y proteja todos los archivos de entrada y salida con los permisos NTFS adecuados.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-151">Only run scripts from trusted sources, and secure all input and output files by using the appropriate NTFS permissions.</span></span> <span data-ttu-id="6e4d4-152">Para obtener más información sobre cómo habilitar los scripts de PowerShell, vea [Running Windows PowerShell Scripts](https://www.tech-recipes.com/rx/2513/powershell_enable_script_support/).</span><span class="sxs-lookup"><span data-stu-id="6e4d4-152">For more information about enabling PowerShell scripts, see [Running Windows PowerShell Scripts](https://www.tech-recipes.com/rx/2513/powershell_enable_script_support/).</span></span>  
  
 <span data-ttu-id="6e4d4-153">La versión de la utilidad `sqlps` en [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] y en [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] se implementó como un shell mínimo de Windows PowerShell 1.0.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-153">The version of the `sqlps` utility in [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] and [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] was implemented as a Windows PowerShell 1.0 mini-shell.</span></span> <span data-ttu-id="6e4d4-154">Los shells mínimos tienen ciertas restricciones, como no permitir que los usuarios carguen complementos distintos de los que ha cargado el shell mínimo.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-154">Mini-shells have certain restrictions, such as not allowing users to load snap-ins other than those loaded by the mini-shell.</span></span> <span data-ttu-id="6e4d4-155">Estas restricciones no se aplican a la versión [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] y posteriores de la utilidad, que se han cambiado para usar el módulo `sqlps`.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-155">These restrictions do not apply to the [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] and higher versions of the utility, which have been changed to use the `sqlps` module.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6e4d4-156">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6e4d4-156">Examples</span></span>  

### <a name="a-run-the-sqlps-utility-in-default-interactive-mode-without-the-copyright-banner"></a><span data-ttu-id="6e4d4-157">A.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-157">A.</span></span> <span data-ttu-id="6e4d4-158">Ejecutar la utilidad sqlps en modo predeterminado e interactivo sin el título de copyright</span><span class="sxs-lookup"><span data-stu-id="6e4d4-158">Run the sqlps utility in default, interactive mode without the copyright banner</span></span>
  
```cmd
sqlps -NoLogo  
```  
  
### <a name="b-run-a-sql-server-powershell-script-from-the-command-prompt"></a><span data-ttu-id="6e4d4-159">B.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-159">B.</span></span> <span data-ttu-id="6e4d4-160">Ejecutar un script de SQL Server PowerShell desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="6e4d4-160">Run a SQL Server PowerShell script from the command prompt</span></span>
  
```cmd
sqlps -Command "&{.\MyFolder.MyScript.ps1}"  
```  
  
### <a name="c-run-a-sql-server-powershell-script-from-the-command-prompt-and-keep-running-after-the-script-completes"></a><span data-ttu-id="6e4d4-161">C.</span><span class="sxs-lookup"><span data-stu-id="6e4d4-161">C.</span></span> <span data-ttu-id="6e4d4-162">Ejecutar un script de SQL Server PowerShell desde el símbolo del sistema y continuar la ejecución una vez que el script se complete</span><span class="sxs-lookup"><span data-stu-id="6e4d4-162">Run a SQL Server PowerShell script from the command prompt, and keep running after the script completes</span></span>
  
```cmd
sqlps -NoExit -Command "&{.\MyFolder.MyScript.ps1}"  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e4d4-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e4d4-163">See Also</span></span>  
 <span data-ttu-id="6e4d4-164">[Habilitar o deshabilitar un protocolo de red de servidor](../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="6e4d4-164">[Enable or Disable a Server Network Protocol](../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md) </span></span>  
 [<span data-ttu-id="6e4d4-165">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e4d4-165">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
