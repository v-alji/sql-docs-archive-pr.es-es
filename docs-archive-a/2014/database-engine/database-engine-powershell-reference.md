---
title: Referencia del motor de base de datos de PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3c379a43-c497-47dd-8e7d-2b015c068bb7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2d72f9fcedee02e475369c32a7c263578c9ff156
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673878"
---
# <a name="database-engine-powershell-reference"></a><span data-ttu-id="af753-102">Referencia del motor de base de datos de PowerShell</span><span class="sxs-lookup"><span data-stu-id="af753-102">Database Engine PowerShell Reference</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="af753-103">incluye un conjunto de cmdlets de Windows PowerShell 2.0 para realizar acciones comunes en [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af753-103">includes a set of Windows PowerShell 2.0 cmdlets for performing common actions in the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="af753-104">Además, las expresiones de consulta y los nombres de recursos uniformes (URN) pueden convertirse en rutas acceso de SQL Server PowerShell o usarse para especificar uno o más objetos en [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af753-104">In addition, Query Expressions and Uniform Resource Names (URN) can be converted to SQL Server PowerShell paths, or used to specify one or more objects in the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
## <a name="database-engine-cmdlets"></a><span data-ttu-id="af753-105">Cmdlets del motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="af753-105">Database Engine Cmdlets</span></span>  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] <span data-ttu-id="af753-106">incluye relativamente pocos cmdlets para [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af753-106">includes relatively few cmdlets for the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="af753-107">La mayoría de los scripts de PowerShell que funcionan con [!INCLUDE[ssDE](../includes/ssde-md.md)] usan el proveedor de SQL Server PowerShell y los modelos de objetos de administración.</span><span class="sxs-lookup"><span data-stu-id="af753-107">Most PowerShell scripts working with the [!INCLUDE[ssDE](../includes/ssde-md.md)] use the SQL Server PowerShell provider and the manageability object models.</span></span> <span data-ttu-id="af753-108">Para más información, consulte [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="af753-108">For more information, see [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span></span>  
  
 <span data-ttu-id="af753-109">Para obtener información sobre cómo obtener ayuda para los cmdlets de SQL Server en un entorno de Windows PowerShell, vea [Get Help SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="af753-109">To learn how to get help about the SQL Server cmdlets in a Windows PowerShell environment, see [Get Help SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="af753-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="af753-110">In This Section</span></span>  
 <span data-ttu-id="af753-111">Esta sección contiene información sobre los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="af753-111">This section contains information about these cmdlets.</span></span>  
  
|<span data-ttu-id="af753-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="af753-112">Description</span></span>|<span data-ttu-id="af753-113">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="af753-113">Cmdlet</span></span>|  
|-----------------|------------|  
|<span data-ttu-id="af753-114">Ejecuta scripts Transact-SQL y XQuery como, por ejemplo, los scripts que se pueden ejecutar con la utilidad `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="af753-114">Runs Transact-SQL and XQuery scripts, such as scripts that can be run using the `sqlcmd` utility.</span></span>|[<span data-ttu-id="af753-115">cmdlet Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="af753-115">Invoke-Sqlcmd cmdlet</span></span>](../../2014/database-engine/invoke-sqlcmd-cmdlet.md)|  
|<span data-ttu-id="af753-116">Evalúa si un objeto de motor de base de datos cumple una directiva de administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="af753-116">Evaluates whether a Database Engine object complies with a Policy-based Management policy.</span></span>|[<span data-ttu-id="af753-117">cmdlet Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="af753-117">Invoke-PolicyEvaluation cmdlet</span></span>](../../2014/database-engine/invoke-policyevaluation-cmdlet.md)|  
  
### <a name="information-about-other-cmdlets"></a><span data-ttu-id="af753-118">Información sobre otros cmdlets</span><span class="sxs-lookup"><span data-stu-id="af753-118">Information About Other Cmdlets</span></span>  
 <span data-ttu-id="af753-119">Los cmdlets `Encode-Sqlname` y `Decode-Sqlname` le ayudan a especificar los identificadores de SQL Server que contienen caracteres no admitidos en las rutas de acceso de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af753-119">The `Encode-Sqlname` and `Decode-Sqlname` cmdlets help you specify SQL Server identifiers that contain characters not supported in PowerShell paths.</span></span> <span data-ttu-id="af753-120">Para más información, consulte [SQL Server Identifiers in PowerShell](../powershell/sql-server-identifiers-in-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="af753-120">For more information, see [SQL Server Identifiers in PowerShell](../powershell/sql-server-identifiers-in-powershell.md).</span></span>  
  
 <span data-ttu-id="af753-121">Use el cmdlet `Convert-UrnToPath` para convertir un nombre de recurso único de un objeto de [!INCLUDE[ssDE](../includes/ssde-md.md)] en una ruta de acceso para el proveedor de SQL Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af753-121">Use the `Convert-UrnToPath` cmdlet to convert a Unique Resource Name for a [!INCLUDE[ssDE](../includes/ssde-md.md)] object to a path for the SQL Server PowerShell provider.</span></span> <span data-ttu-id="af753-122">Para más información, consulte [Convert URNs to SQL Server Provider Paths](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md).</span><span class="sxs-lookup"><span data-stu-id="af753-122">For more information, see [Convert URNs to SQL Server Provider Paths](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md).</span></span>  
  
## <a name="query-expressions-and-unique-resource-names"></a><span data-ttu-id="af753-123">Expresiones de consulta y nombres de recursos únicos</span><span class="sxs-lookup"><span data-stu-id="af753-123">Query Expressions and Unique Resource Names</span></span>  
 <span data-ttu-id="af753-124">Las expresiones de consulta son cadenas que usan una sintaxis similar a XPath para especificar un conjunto de criterios que enumeran uno o más objetos de una jerarquía del modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="af753-124">Query expressions are strings that use syntax similar to XPath to specify a set of criteria that enumerate one or more objects in an object model hierarchy.</span></span> <span data-ttu-id="af753-125">Un nombre de recurso único (URN) es un tipo específico de cadena de expresión de consulta que identifica exclusivamente un objeto único.</span><span class="sxs-lookup"><span data-stu-id="af753-125">A Unique Resource Name (URN) is a specific type of query expression string that uniquely identifies a single object.</span></span> <span data-ttu-id="af753-126">Para más información, consulte [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span><span class="sxs-lookup"><span data-stu-id="af753-126">For more information, see [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af753-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af753-127">See Also</span></span>  
 [<span data-ttu-id="af753-128">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="af753-128">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
  
  
