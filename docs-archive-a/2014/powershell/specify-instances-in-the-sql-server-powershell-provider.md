---
title: Especificar instancias del proveedor de PowerShell de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 9373de68-fd43-45f2-b9a6-149c96610aeb
author: stevestein
ms.author: sstein
ms.openlocfilehash: cc04bacc1ff36b0b5ce526a377fcdb750ad134a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672137"
---
# <a name="specify-instances-in-the-sql-server-powershell-provider"></a><span data-ttu-id="95a5a-102">Especificar instancias del proveedor de PowerShell de SQL Server</span><span class="sxs-lookup"><span data-stu-id="95a5a-102">Specify Instances in the SQL Server PowerShell Provider</span></span>
  <span data-ttu-id="95a5a-103">Las rutas de acceso especificadas para el proveedor de PowerShell de SQL Server deben identificar la instancia de [!INCLUDE[ssDE](../includes/ssde-md.md)] y el equipo en que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="95a5a-103">The paths specified for the SQL Server PowerShell provider must identify the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] and the computer it is running on.</span></span> <span data-ttu-id="95a5a-104">La sintaxis para especificar el equipo y la instancia debe cumplir las reglas de los identificadores de SQL Server y las rutas de acceso de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95a5a-104">The syntax for specifying the computer and the instance must comply with both the rules for SQL Server identifiers and Windows PowerShell paths.</span></span>  
  
1.  <span data-ttu-id="95a5a-105">**Antes de empezar:**  [Limitaciones y restricciones](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="95a5a-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="95a5a-106">**Para especificar una instancia:**  [Ejemplos](#Examples)</span><span class="sxs-lookup"><span data-stu-id="95a5a-106">**To specify an instance:**  [Examples](#Examples)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="95a5a-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="95a5a-107">Before You Begin</span></span>  
 <span data-ttu-id="95a5a-108">El primer nodo situado a continuación de SQLSERVER:\SQL en una ruta de acceso de proveedor de SQL Server es el nombre del equipo en el que se ejecuta la instancia de [!INCLUDE[ssDE](../includes/ssde-md.md)], por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="95a5a-108">The first node following the SQLSERVER:\SQL in a SQL Server provider path is the name of the computer that is running the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)]; for example:</span></span>  
  
```  
SQLSERVER:\SQL\MyComputer  
```  
  
 <span data-ttu-id="95a5a-109">Si está ejecutando Windows PowerShell en el mismo equipo que la instancia de [!INCLUDE[ssDE](../includes/ssde-md.md)], puede usar localhost o (local) en lugar del nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="95a5a-109">If you are running Windows PowerShell on the same computer as the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], you can use either localhost or (local) instead of the name of the computer.</span></span> <span data-ttu-id="95a5a-110">Los scripts que usan localhost o (local) se pueden ejecutar en cualquier equipo sin tener que cambiar para reflejar los distintos nombres de los equipos.</span><span class="sxs-lookup"><span data-stu-id="95a5a-110">Scripts that use localhost or (local) can be run on any computer without having to be changed to reflect the different computer names.</span></span>  
  
 <span data-ttu-id="95a5a-111">Puede ejecutar varias instancias del programa ejecutable de [!INCLUDE[ssDE](../includes/ssde-md.md)] en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="95a5a-111">You can run multiple instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] executable program on the same computer.</span></span> <span data-ttu-id="95a5a-112">El nodo situado a continuación del nombre del equipo en una ruta de acceso del proveedor de SQL Server identifica la instancia; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="95a5a-112">The node following the computer name in a SQL Server provider path identifies the instance; for example:</span></span>  
  
```  
SQLSERVER:\SQL\MyComputer\MyInstance  
```  
  
 <span data-ttu-id="95a5a-113">Cada equipo puede tener una instancia predeterminada de [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95a5a-113">Each computer can have one default instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="95a5a-114">No especifique un nombre para la instancia predeterminada al instalarla.</span><span class="sxs-lookup"><span data-stu-id="95a5a-114">You do not specify a name for the default instance when you install it.</span></span> <span data-ttu-id="95a5a-115">Si especifica solamente un nombre de equipo en una cadena de conexión, se conectará a la instancia predeterminada en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="95a5a-115">If you specify only a computer name in a connection string, you are connected to the default instance on that computer.</span></span> <span data-ttu-id="95a5a-116">Todas las demás instancias en el equipo deben ser instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="95a5a-116">All other instances on the computer must be named instances.</span></span> <span data-ttu-id="95a5a-117">Durante la instalación se especifica el nombre de instancia y las cadenas de conexión deben especificar tanto el nombre de equipo como el nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="95a5a-117">You specify the instance name during setup, and connection strings must specify both the computer name and the instance name.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="95a5a-118">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="95a5a-118">Limitations and Restrictions</span></span>  
 <span data-ttu-id="95a5a-119">No puede usar un punto (.) para especificar el equipo local en los scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95a5a-119">You cannot use a period (.) to specify the local computer in PowerShell scripts.</span></span> <span data-ttu-id="95a5a-120">No se admite el punto porque PowerShell lo interpreta como comando.</span><span class="sxs-lookup"><span data-stu-id="95a5a-120">The period is not supported because the period is interpreted as a command by PowerShell.</span></span>  
  
 <span data-ttu-id="95a5a-121">Windows PowerShell suele tratar como comandos los caracteres que van entre paréntesis de (local).</span><span class="sxs-lookup"><span data-stu-id="95a5a-121">The parenthesis characters in (local) are normally treated as commands by Windows PowerShell.</span></span> <span data-ttu-id="95a5a-122">Debe codificarlos o convertirlos para poderlos usar en una ruta de acceso, o agregar la ruta de acceso entre comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="95a5a-122">You must either encode them or escape them for use in a path, or enclose the path in double-quotation marks.</span></span> <span data-ttu-id="95a5a-123">Para obtener más información, vea Codificar y descodificar identificadores de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95a5a-123">For more information, see Encode and Decode SQL Server Identifiers.</span></span>  
  
 <span data-ttu-id="95a5a-124">El proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requiere que siempre se especifique un nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="95a5a-124">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider requires that you always specify an instance name.</span></span> <span data-ttu-id="95a5a-125">Para las instancias predeterminadas, debe especificar el nombre de instancia DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="95a5a-125">For default instances, you must specify an instance name of DEFAULT.</span></span>  
  
##  <a name="examples-computer-and-instance-names"></a><a name="Examples"></a><span data-ttu-id="95a5a-126">Example Nombres de equipo y de instancia</span><span class="sxs-lookup"><span data-stu-id="95a5a-126">Examples; Computer and Instance Names</span></span>  
 <span data-ttu-id="95a5a-127">En este ejemplo se usan el host local y DEFAULT para especificar la instancia predeterminada en el equipo local:</span><span class="sxs-lookup"><span data-stu-id="95a5a-127">This example uses localhost and DEFAULT to specify the default instance on the local computer:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT
```  
  
 <span data-ttu-id="95a5a-128">Windows PowerShell suele tratar como comandos los caracteres que van entre paréntesis de (local).</span><span class="sxs-lookup"><span data-stu-id="95a5a-128">The parenthesis characters in (local) are normally treated as commands by Windows PowerShell.</span></span> <span data-ttu-id="95a5a-129">Debe:</span><span class="sxs-lookup"><span data-stu-id="95a5a-129">You must either:</span></span>  
  
-   <span data-ttu-id="95a5a-130">Poner las cadenas de ruta de acceso entre comillas:</span><span class="sxs-lookup"><span data-stu-id="95a5a-130">Enclose the path string in quotes:</span></span>  
  
    ```powershell
    Set-Location "SQLSERVER:\SQL\(local)\DEFAULT"  
    ```  
  
-   <span data-ttu-id="95a5a-131">Eludir el paréntesis mediante el carácter de acento invertido (\`).</span><span class="sxs-lookup"><span data-stu-id="95a5a-131">Escape the parenthesis using the back tick character (\`):</span></span>  
  
    ```powershell
    Set-Location SQLSERVER:\SQL\`(local`)\DEFAULT  
    ```  
  
-   <span data-ttu-id="95a5a-132">Codificar el paréntesis mediante su representación hexadecimal:</span><span class="sxs-lookup"><span data-stu-id="95a5a-132">Encode the parenthesis using their hexadecimal representation:</span></span>  
  
    ```powershell
    Set-Location SQLSERVER:\SQL\%28local%29\DEFAULT  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="95a5a-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95a5a-133">See Also</span></span>  
 <span data-ttu-id="95a5a-134">[SQL Server identificadores en PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="95a5a-134">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="95a5a-135">[Proveedor de SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="95a5a-135">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="95a5a-136">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="95a5a-136">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
