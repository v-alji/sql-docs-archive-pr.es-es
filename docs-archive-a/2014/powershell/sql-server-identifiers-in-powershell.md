---
title: Identificadores de SQL Server en PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
helpviewer_keywords:
- Cmdlets [SQL Server], Encode-Sqlname
- PowerShell [SQL Server], identifiers
- Encode-Sqlname cmdlet
- PowerShell [SQL Server], Encode-Sqlname
- Decode-Sqlname cmdlet
- PowerShell [SQL Server], Decode-Sqlname
- identifiers [SQL Server], PowerShell
- Cmdlets [SQL Server], Decode-Sqlname
ms.assetid: 651099b0-33b4-453a-a864-b067f21eb8b9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5c54fb352fb17c099bda78c80f00f91dbba428f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745341"
---
# <a name="sql-server-identifiers-in-powershell"></a><span data-ttu-id="81ed4-102">Identificadores de SQL Server en PowerShell</span><span class="sxs-lookup"><span data-stu-id="81ed4-102">SQL Server Identifiers in PowerShell</span></span>
  <span data-ttu-id="81ed4-103">El proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para Windows PowerShell usa identificadores [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] en las rutas de acceso de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81ed4-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider for Windows PowerShell uses [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers in Windows PowerShell paths.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="81ed4-104">pueden contener caracteres que Windows PowerShell no admite en las rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="81ed4-104">identifiers can contain characters that Windows PowerShell does not support in paths.</span></span> <span data-ttu-id="81ed4-105">Debe definir estos caracteres como caracteres de escape o usar una codificación especial para ellos al usar los identificadores en las rutas de acceso de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81ed4-105">You must escape these characters or use special encoding for them when using the identifiers in Windows PowerShell paths.</span></span>  
  
## <a name="sql-server-identifiers-in-windows-powershell-paths"></a><span data-ttu-id="81ed4-106">Identificadores de SQL Server en rutas de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="81ed4-106">SQL Server Identifiers in Windows PowerShell Paths</span></span>  
 <span data-ttu-id="81ed4-107">Los proveedores de Windows PowerShell exponen las jerarquías de datos mediante una estructura de ruta similar a la que se usa para el sistema de archivos de Windows.</span><span class="sxs-lookup"><span data-stu-id="81ed4-107">Windows PowerShell providers expose data hierarchies using a path structure similar to that used for the Windows file system.</span></span> <span data-ttu-id="81ed4-108">El proveedor de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] implementa rutas a los objetos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81ed4-108">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider implements paths to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span> <span data-ttu-id="81ed4-109">En el [!INCLUDE[ssDE](../includes/ssde-md.md)], la unidad se establece en SQLSERVER:, la primera carpeta se establece en \SQL y se hace referencia a los objetos de la base de datos como contenedores y elementos.</span><span class="sxs-lookup"><span data-stu-id="81ed4-109">For the [!INCLUDE[ssDE](../includes/ssde-md.md)], the drive is set to SQLSERVER:, the first folder is set to \SQL, and the database objects are referenced as containers and items.</span></span> <span data-ttu-id="81ed4-110">Esta es la ruta de acceso a la tabla Vendor en el esquema Purchasing de la base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] en una instancia predeterminada de [!INCLUDE[ssDE](../includes/ssde-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="81ed4-110">This is the path to the Vendor table in the Purchasing schema of the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database in a default instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)]:</span></span>  
  
```  
SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Purchasing.Vendor  
```  
  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="81ed4-111">son los nombres de los objetos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , tales como nombres de tabla o de columna.</span><span class="sxs-lookup"><span data-stu-id="81ed4-111">identifiers are the names of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects, such as table or column names.</span></span> <span data-ttu-id="81ed4-112">Hay dos tipos de identificadores de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="81ed4-112">There are two types of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers:</span></span>  
  
-   <span data-ttu-id="81ed4-113">Los identificadores normales se limitan a un juego de caracteres que también se admite en las rutas de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81ed4-113">Regular identifiers are limited to a set of characters that are also supported in Windows PowerShell paths.</span></span> <span data-ttu-id="81ed4-114">Estos nombres se pueden utilizar en las rutas de Windows PowerShell sin cambiarse.</span><span class="sxs-lookup"><span data-stu-id="81ed4-114">These names can be used in Windows PowerShell paths without being changed.</span></span>  
  
-   <span data-ttu-id="81ed4-115">Los identificadores delimitados pueden utilizar caracteres no admitidos en los nombres de ruta de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81ed4-115">Delimited identifiers can use characters not supported in Windows PowerShell path names.</span></span> <span data-ttu-id="81ed4-116">Los identificadores delimitados se denominan identificadores entre corchetes si se escriben entre corchetes ([nombreDeIdentificador]) e identificadores entrecomillados si se escriben entre comillas dobles ("nombreDeIdentificador").</span><span class="sxs-lookup"><span data-stu-id="81ed4-116">Delimited identifiers are called bracketed identifiers if they are enclosed in brackets ([IdentifierName]) and quoted identifiers if they are enclosed in double quotes ("IdentifierName").</span></span> <span data-ttu-id="81ed4-117">Si un identificador delimitado utiliza caracteres no admitidos en las rutas de Windows PowerShell, estos se deben codificar o hacer que se eludan antes de utilizar el identificador como contenedor o nombre de elemento.</span><span class="sxs-lookup"><span data-stu-id="81ed4-117">If a delimited identifier uses characters not supported in Windows PowerShell paths, the characters must either be encoded or escaped before using the identifier as a container or item name.</span></span> <span data-ttu-id="81ed4-118">La codificación funciona con todos los caracteres.</span><span class="sxs-lookup"><span data-stu-id="81ed4-118">Encoding works for all characters.</span></span> <span data-ttu-id="81ed4-119">En el caso de ciertos caracteres, como el carácter de dos puntos (:), no se puede hacer que se eludan.</span><span class="sxs-lookup"><span data-stu-id="81ed4-119">Some characters, such as the colon character (:), cannot be escaped.</span></span>  
  
## <a name="sql-server-identifiers-in-cmdlets"></a><span data-ttu-id="81ed4-120">Identificadores de SQL Server en cmdlets</span><span class="sxs-lookup"><span data-stu-id="81ed4-120">SQL Server Identifiers in cmdlets</span></span>  
 <span data-ttu-id="81ed4-121">Algunos cmdlets de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tienen un parámetro que toma un identificador como entrada.</span><span class="sxs-lookup"><span data-stu-id="81ed4-121">Some [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets have a parameter that takes an identifier as input.</span></span> <span data-ttu-id="81ed4-122">Los valores de los parámetros se suelen proporcionar como constantes de cadena entrecomilladas o en variables de cadena.</span><span class="sxs-lookup"><span data-stu-id="81ed4-122">The parameter values are typically supplied as quoted string constants or in string variables.</span></span> <span data-ttu-id="81ed4-123">Cuando los identificadores se proporcionan como constantes de cadena o en variables, no hay ningún conflicto con el juego de caracteres admitidos por Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81ed4-123">When identifiers are supplied as string constants or in variables, there is no conflict with the set of characters that are supported by Windows PowerShell.</span></span>  
  
## <a name="sql-server-identifier-tasks"></a><span data-ttu-id="81ed4-124">Tareas de identificador de SQL Server</span><span class="sxs-lookup"><span data-stu-id="81ed4-124">SQL Server Identifier Tasks</span></span>  
  
|<span data-ttu-id="81ed4-125">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="81ed4-125">Task Description</span></span>|<span data-ttu-id="81ed4-126">Tema</span><span class="sxs-lookup"><span data-stu-id="81ed4-126">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="81ed4-127">Describe cómo especificar un nombre de instancia, incluido el nombre del equipo en el que se ejecuta la instancia.</span><span class="sxs-lookup"><span data-stu-id="81ed4-127">Describes how to specify an instance name, including the name of the computer the instance is running on.</span></span>|[<span data-ttu-id="81ed4-128">Especificar instancias del proveedor de PowerShell de SQL Server</span><span class="sxs-lookup"><span data-stu-id="81ed4-128">Specify Instances in the SQL Server PowerShell Provider</span></span>](sql-server-powershell-provider.md)|  
|<span data-ttu-id="81ed4-129">Describe cómo especificar la codificación hexadecimal para los caracteres en identificadores delimitados que no se admiten en las rutas de acceso de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81ed4-129">Describes how to specify the hexadecimal encoding for characters in delimited identifiers that are not supported in Windows PowerShell paths.</span></span> <span data-ttu-id="81ed4-130">También describe cómo descodificar los caracteres hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="81ed4-130">Also describes how to decode the hexadecimal characters.</span></span>|[<span data-ttu-id="81ed4-131">Codificar y descodificar identificadores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="81ed4-131">Encode and Decode SQL Server Identifiers</span></span>](encode-and-decode-sql-server-identifiers.md)|  
|<span data-ttu-id="81ed4-132">Describe cómo usar el carácter de escape de Windows PowerShell para los caracteres no admitidos en las rutas de acceso de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81ed4-132">Describes how to use the Windows PowerShell escape character for characters not supported in PowerShell paths.</span></span>|[<span data-ttu-id="81ed4-133">Identificadores de SQL Server de escape</span><span class="sxs-lookup"><span data-stu-id="81ed4-133">Escape SQL Server Identifiers</span></span>](escape-sql-server-identifiers.md)|  
  
## <a name="see-also"></a><span data-ttu-id="81ed4-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="81ed4-134">See Also</span></span>  
 <span data-ttu-id="81ed4-135">[Proveedor de SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="81ed4-135">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="81ed4-136">[SQL Server PowerShell](sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="81ed4-136">[SQL Server PowerShell](sql-server-powershell.md) </span></span>  
 [<span data-ttu-id="81ed4-137">Identificadores de base de datos</span><span class="sxs-lookup"><span data-stu-id="81ed4-137">Database Identifiers</span></span>](../relational-databases/databases/database-identifiers.md)  
  
  