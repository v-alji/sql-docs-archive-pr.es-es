---
title: Usar los cmdlets del motor de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Cmdlets [SQL Server], Encode-Sqlname
- Encode-Sqlname cmdlet
- PowerShell [SQL Server], Encode-Sqlname
- Convert-UrnToPath cmdlet
- PowerShell [SQL Server], cmdlets
- Cmdlets [SQL Server]
- PowerShell [SQL Server], Convert-UrnToPath
- Cmdlets [SQL Server], Convert-UrnToPath
- Decode-Sqlname cmdlet
- PowerShell [SQL Server], Decode-Sqlname
- Cmdlets [SQL Server], Decode-Sqlname
ms.assetid: 720aa982-09ae-41a3-b603-a91004cfbe3e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 015500c7c985f9f1a1d190954406844f3b184932
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663059"
---
# <a name="use-the-database-engine-cmdlets"></a><span data-ttu-id="b1618-102">Utilizar los cmdlets del motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="b1618-102">Use the Database Engine cmdlets</span></span>
  <span data-ttu-id="b1618-103">Los cmdlets de Windows PowerShell son comandos de una sola función que suelen seguir la convención de nomenclatura verbo-nombre, como **Get-Help** o **Set-MachineName**.</span><span class="sxs-lookup"><span data-stu-id="b1618-103">Windows PowerShell cmdlets are single-function commands that typically have a verb-noun naming convention, such as **Get-Help** or **Set-MachineName**.</span></span> <span data-ttu-id="b1618-104">El proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para Windows PowerShell proporciona cmdlets específicos a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1618-104">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider for Windows PowerShell supplies cmdlets specific to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="database-engine-cmdlets"></a><span data-ttu-id="b1618-105">Cmdlets del motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="b1618-105">Database Engine cmdlets</span></span>  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="b1618-106">implementa una pequeña parte de los cmdlets de [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1618-106">implements a small number of cmdlets for the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="b1618-107">Estos cmdlets se usan principalmente para ejecutar scripts Transact-SQL existentes de los nuevos scripts de PowerShell, evaluar las directivas de administración basadas en directivas y ayuda a especificar los identificadores de SQL Server en rutas de acceso del proveedor de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1618-107">These cmdlets are primarily used to run existing Transact-SQL scripts from new PowerShell scripts, evaluate policy-based management policies, and aid in specifying SQL Server identifiers in SQL Server Provider paths.</span></span>  
  
 <span data-ttu-id="b1618-108">La mayoría de los scripts de Windows PowerShell funciona con [!INCLUDE[ssDE](../includes/ssde-md.md)] mediante el proveedor de SQL Server PowerShell y los modelos de objetos de administración de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1618-108">Most Windows PowerShell scripts work with the [!INCLUDE[ssDE](../includes/ssde-md.md)] by using the SQL Server PowerShell provider and the SQL Server manageability object models.</span></span> <span data-ttu-id="b1618-109">Para más información, consulte el artículo sobre [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b1618-109">For more information, see [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="get-cmdlet-help"></a><span data-ttu-id="b1618-110">Obtener Ayuda de los cmdlets</span><span class="sxs-lookup"><span data-stu-id="b1618-110">Get Cmdlet Help</span></span>  
 <span data-ttu-id="b1618-111">En el entorno de Windows PowerShell, el cmdlet **Get-Help** proporciona información de ayuda para cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1618-111">In the Windows PowerShell environment, the **Get-Help** cmdlet provides help information for each cmdlet.</span></span> <span data-ttu-id="b1618-112">**Get-Help** devuelve información como la sintaxis, las definiciones de parámetro, los tipos de entrada y salida y una descripción de la acción realizada por el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1618-112">**Get-Help** returns information such as the syntax, parameter definitions, input and output types, and a description of the action performed by the cmdlet.</span></span> <span data-ttu-id="b1618-113">Para más información, consulte [Get Help SQL Server PowerShell](../../2014/database-engine/get-help-sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b1618-113">For more information, see [Get Help SQL Server PowerShell](../../2014/database-engine/get-help-sql-server-powershell.md).</span></span>  
  
### <a name="partial-parameter-names"></a><span data-ttu-id="b1618-114">Nombres de parámetros parciales</span><span class="sxs-lookup"><span data-stu-id="b1618-114">Partial Parameter Names</span></span>  
 <span data-ttu-id="b1618-115">No tiene que especificar el nombre completo de un parámetro de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1618-115">You do not have to specify the entire name of a cmdlet parameter.</span></span> <span data-ttu-id="b1618-116">Solo tiene que especificar una parte del nombre que sea suficiente para separarlo de forma exclusiva de los otros parámetros admitidos por el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b1618-116">You only have to specify enough of the name to uniquely separate it from the other parameters that are supported by the cmdlet.</span></span> <span data-ttu-id="b1618-117">Por ejemplo, en estos ejemplos se muestran tres formas de especificar el parámetro **Invoke-Sqlcmd -QueryTimeout** :</span><span class="sxs-lookup"><span data-stu-id="b1618-117">For example, these examples show three ways of specifying the **Invoke-Sqlcmd -QueryTimeout** parameter:</span></span>  
  
```powershell
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryTimeout 3  
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryTime 3  
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryT 3  
```  
  
## <a name="database-engine-cmdlet-tasks"></a><span data-ttu-id="b1618-118">Tareas de cmdlets del motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="b1618-118">Database Engine cmdlet Tasks</span></span>  
  
|<span data-ttu-id="b1618-119">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="b1618-119">Task Description</span></span>|<span data-ttu-id="b1618-120">Tema</span><span class="sxs-lookup"><span data-stu-id="b1618-120">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="b1618-121">Describe el uso de **Invoke-Sqlcmd** para ejecutar scripts de **sqlcmd** o comandos que contienen instrucciones [!INCLUDE[tsql](../includes/tsql-md.md)] o XQuery.</span><span class="sxs-lookup"><span data-stu-id="b1618-121">Describes using **Invoke-Sqlcmd** to run **sqlcmd** scripts or commands that contain [!INCLUDE[tsql](../includes/tsql-md.md)] or XQuery statements.</span></span> <span data-ttu-id="b1618-122">Puede aceptar la entrada de **sqlcmd** como parámetro de entrada de la cadena de caracteres o como nombre de un archivo de script que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="b1618-122">It can accept the **sqlcmd** input as either a character string input parameter, or as the name of a script file to open.</span></span>|[<span data-ttu-id="b1618-123">cmdlet Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="b1618-123">Invoke-Sqlcmd cmdlet</span></span>](../../2014/database-engine/invoke-sqlcmd-cmdlet.md)|  
|<span data-ttu-id="b1618-124">Describe el uso de **Invoke-PolicyEvaluation** para informar de si un conjunto de objetos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] de destino cumple las condiciones definidas en las directivas de administración basadas en directivas.</span><span class="sxs-lookup"><span data-stu-id="b1618-124">Describes using **Invoke-PolicyEvaluation** to report whether a target set of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects comply with the conditions that are defined in policy-based management policies.</span></span> <span data-ttu-id="b1618-125">Opcionalmente, el cmdlet se puede usar para volver a configurar cualquier opción que se pueda establecer en los objetos de destino que no cumplan las condiciones de la directiva.</span><span class="sxs-lookup"><span data-stu-id="b1618-125">Optionally, the cmdlet can be used to reconfigure any settable options in the target objects that do not comply with the policy conditions.</span></span>|[<span data-ttu-id="b1618-126">cmdlet Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="b1618-126">Invoke-PolicyEvaluation cmdlet</span></span>](../../2014/database-engine/invoke-policyevaluation-cmdlet.md)|  
|<span data-ttu-id="b1618-127">Describe el uso de `Encode-Sqlname` y `Decode-Sqlname` para administrar los identificadores de SQL Server que contienen caracteres no admitidos en las rutas de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1618-127">Describes using `Encode-Sqlname` and `Decode-Sqlname` to handle SQL Server identifiers that contain characters not supported in Windows PowerShell paths.</span></span>|[<span data-ttu-id="b1618-128">Codificar y descodificar identificadores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="b1618-128">Encode and Decode SQL Server Identifiers</span></span>](../powershell/encode-and-decode-sql-server-identifiers.md)|  
|<span data-ttu-id="b1618-129">Describe el uso de `Convert-UrnToPath` para convertir un nombre de recursos uniforme (URN) del objeto de administración de SQL Server a la ruta de acceso equivalente en el proveedor de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b1618-129">Describes using `Convert-UrnToPath` to convert a SQL Server Manageability Object Uniform Resource Name (URN) to the equivalent SQL Server Provider path.</span></span>|[<span data-ttu-id="b1618-130">Convertir URN en rutas de acceso del proveedor de SQL Server</span><span class="sxs-lookup"><span data-stu-id="b1618-130">Convert URNs to SQL Server Provider Paths</span></span>](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md)|  
  
## <a name="see-also"></a><span data-ttu-id="b1618-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1618-131">See Also</span></span>  
 <span data-ttu-id="b1618-132">[Proveedor de SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="b1618-132">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="b1618-133">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="b1618-133">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span></span>  
 [<span data-ttu-id="b1618-134">Información general de los cmdlets de PowerShell para Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b1618-134">Overview of PowerShell Cmdlets for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](availability-groups/windows/overview-of-powershell-cmdlets-for-always-on-availability-groups-sql-server.md)  
  
  
