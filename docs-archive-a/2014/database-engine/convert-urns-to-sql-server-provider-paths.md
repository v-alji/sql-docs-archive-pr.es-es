---
title: Conversión de URN en rutas de acceso del proveedor de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c9b1b8f1-b117-4e87-9704-2170f62c5c8b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 56c2fdb5f84e57fe3f34348108f14418785659a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673261"
---
# <a name="convert-urns-to-sql-server-provider-paths"></a><span data-ttu-id="e511a-102">Convertir URN en rutas de acceso del proveedor de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e511a-102">Convert URNs to SQL Server Provider Paths</span></span>
  <span data-ttu-id="e511a-103">El modelo de objetos de administración de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (SMO) compila nombres de recursos uniformes (URN) para sus objetos.</span><span class="sxs-lookup"><span data-stu-id="e511a-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object model (SMO) builds Uniform Resource Names (URN) for its objects.</span></span> <span data-ttu-id="e511a-104">Cada URN identifica un objeto SMO y se puede convertir en una ruta de acceso del proveedor de PowerShell de SQL Server mediante el cmdlet `Convert-UrnToPath`.</span><span class="sxs-lookup"><span data-stu-id="e511a-104">Each URN uniquely identifies a SMO object, and can be converted to a SQL Server PowerShell provider path by using the `Convert-UrnToPath` cmdlet.</span></span>  
  
## <a name="converting-urns-to-paths"></a><span data-ttu-id="e511a-105">Convertir los URN en rutas de acceso</span><span class="sxs-lookup"><span data-stu-id="e511a-105">Converting URNs to Paths</span></span>  
 <span data-ttu-id="e511a-106">Cada URN tiene la misma información que una ruta de acceso al objeto, pero en un formato diferente.</span><span class="sxs-lookup"><span data-stu-id="e511a-106">Each URN has the same information as a path to the object, but in a different form.</span></span> <span data-ttu-id="e511a-107">Por ejemplo, esta es la ruta de acceso a una tabla:</span><span class="sxs-lookup"><span data-stu-id="e511a-107">For example, this is the path to a table:</span></span>  
  
 <span data-ttu-id="e511a-108">SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Person.Address</span><span class="sxs-lookup"><span data-stu-id="e511a-108">SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Person.Address</span></span>  
  
 <span data-ttu-id="e511a-109">Y este es el URN para el mismo objeto:</span><span class="sxs-lookup"><span data-stu-id="e511a-109">And this is the URN to the same object:</span></span>  
  
 <span data-ttu-id="e511a-110">Server[@Name='MyComputer']\Database[@Name='AdventureWorks2012']\Table[@Name='Address' and @Schema='Person']</span><span class="sxs-lookup"><span data-stu-id="e511a-110">Server[@Name='MyComputer']\Database[@Name='AdventureWorks2012']\Table[@Name='Address' and @Schema='Person']</span></span>  
  
 <span data-ttu-id="e511a-111">Si ha creado un objeto SMO en un script de PowerShell, puede hacer referencia a la propiedad `Urn` para obtener el URN del objeto y a, continuación, usar el cmdlet `Convert-UrnToPath` para convertir la cadena URN de SMO en una ruta de acceso de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e511a-111">If you have created a SMO object in a PowerShell script, you can reference the `Urn` property to get the URN for the object, and then use the `Convert-UrnToPath` cmdlet to convert the SMO URN string to a Windows PowerShell path.</span></span> <span data-ttu-id="e511a-112">Puede usar el proveedor para navegar a ubicaciones diferentes de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="e511a-112">You can then use the provider to navigate to different locations on the path.</span></span>  
  
 <span data-ttu-id="e511a-113">Si los nombres de nodo contienen caracteres extendidos que no se admiten en los nombres de ruta de acceso de Windows PowerShell, `Convert-UrnToPath` los codifica en su representación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="e511a-113">If node names contain extended characters that are not supported in Windows PowerShell path names, `Convert-UrnToPath` encodes them in their hexadecimal representation.</span></span> <span data-ttu-id="e511a-114">Por ejemplo "My:Table" se devuelve como "My%3ATable".</span><span class="sxs-lookup"><span data-stu-id="e511a-114">For example "My:Table" is returned as "My%3ATable".</span></span>  
  
 <span data-ttu-id="e511a-115">Para obtener ejemplos del uso del cmdlet, en Windows PowerShell, ejecute:</span><span class="sxs-lookup"><span data-stu-id="e511a-115">For examples of using the cmdlet, in Windows PowerShell, run:</span></span>  
  
```powershell
Get-Help Convert-UrnToPath -Examples  
```  
  
## <a name="see-also"></a><span data-ttu-id="e511a-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e511a-116">See Also</span></span>  
 <span data-ttu-id="e511a-117">[Expresiones de consulta y nombres de recursos uniformes](../powershell/query-expressions-and-uniform-resource-names.md) </span><span class="sxs-lookup"><span data-stu-id="e511a-117">[Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md) </span></span>  
 <span data-ttu-id="e511a-118">[Proveedor de SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="e511a-118">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="e511a-119">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="e511a-119">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
