---
title: Modificar un ensamblado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], modifying
- permissions [CLR integration]
- altering assemblies
- ALTER ASSEMBLY statement
ms.assetid: 9e765fbd-f339-473c-8537-22f478e79696
author: rothja
ms.author: jroth
ms.openlocfilehash: c22ca979675d3b7f263e3bc6de0c41c134a1abcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747628"
---
# <a name="altering-an-assembly"></a><span data-ttu-id="84888-102">Modificar un ensamblado</span><span class="sxs-lookup"><span data-stu-id="84888-102">Altering an Assembly</span></span>
  <span data-ttu-id="84888-103">Los ensamblados registrados en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se pueden actualizar con una versión más reciente mediante la instrucción ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="84888-103">Assemblies that have been registered in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can be updated from a more recent version using the ALTER ASSEMBLY statement.</span></span> <span data-ttu-id="84888-104">Para actualizar un ensamblado, use la instrucción ALTER ASSEMBLY con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="84888-104">To update an assembly, use the ALTER ASSEMBLY statement with the following syntax:</span></span>  
  
```  
ALTER ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
```  
  
 <span data-ttu-id="84888-105">ALTER ASSEMBLY no interrumpe los procesos actualmente en ejecución que utilizan el ensamblado; los procesos se siguen ejecutando con el ensamblado sin modificar.</span><span class="sxs-lookup"><span data-stu-id="84888-105">ALTER ASSEMBLY does not disrupt currently running processes that are using the assembly; the processes continue executing with the unaltered assembly.</span></span> <span data-ttu-id="84888-106">ALTER ASSEMBLY no se puede utilizar para cambiar las firmas de funciones de Common Language Runtime (CLR), funciones de agregado, procedimientos almacenados ni desencadenadores.</span><span class="sxs-lookup"><span data-stu-id="84888-106">ALTER ASSEMBLY cannot be used to change the signatures of common language runtime (CLR) functions, aggregate functions, stored procedures, and triggers.</span></span> <span data-ttu-id="84888-107">En el ensamblado se pueden agregar nuevos métodos públicos, los métodos privados se pueden modificar de todas las maneras y los métodos públicos se pueden modificar en tanto no se cambien las firmas ni los atributos.</span><span class="sxs-lookup"><span data-stu-id="84888-107">New public methods can be added to the assembly, private methods can be modified in any way, and public methods can be modified as long as signatures or attributes are not changed.</span></span> <span data-ttu-id="84888-108">Los campos que forman parte de un tipo definido por el usuario de serialización nativa, incluidos los miembros de datos o clases base, no pueden cambiarse mediante ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="84888-108">Fields that are contained within a native-serialized user-defined type, including data members or base classes, cannot be changed by using ALTER ASSEMBLY.</span></span> <span data-ttu-id="84888-109">No se admiten otros cambios.</span><span class="sxs-lookup"><span data-stu-id="84888-109">All other changes are unsupported.</span></span> <span data-ttu-id="84888-110">Para obtener más información, vea [ALTER assembly &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="84888-110">For more information, see [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span></span>  
  
## <a name="changing-the-permission-set-of-an-assembly"></a><span data-ttu-id="84888-111">Cambiar el conjunto de permisos de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="84888-111">Changing the Permission Set of an Assembly</span></span>  
 <span data-ttu-id="84888-112">El conjunto de permisos de un ensamblado también se puede cambiar mediante la instrucción ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="84888-112">The permission set of an assembly can also be changed using the ALTER ASSEMBLY statement.</span></span> <span data-ttu-id="84888-113">La instrucción siguiente cambia el conjunto de permisos del ensamblado SQLCLRTest a `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="84888-113">The following statement changes the permission set of the SQLCLRTest assembly to `EXTERNAL_ACCESS`.</span></span>  
  
```  
ALTER ASSEMBLY SQLCLRTest  
WITH PERMISSION_SET = EXTERNAL_ACCESS   
```  
  
 <span data-ttu-id="84888-114">Si el conjunto de permisos de un ensamblado se cambia de `SAFE` a `EXTERNAL_ACCESS` o `UNSAFE`, se debe crear previamente una clave asimétrica y el inicio de sesión correspondiendo con permiso `EXTERNAL ACCESS ASSEMBLY` o `UNSAFE ASSEMBLY` para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="84888-114">If the permission set of an assembly is being changed from `SAFE` to `EXTERNAL_ACCESS` or `UNSAFE`, an asymmetric key and corresponding login with `EXTERNAL ACCESS ASSEMBLY` permission or `UNSAFE ASSEMBLY` permission for the assembly must first be created.</span></span> <span data-ttu-id="84888-115">Para más información, consulte [Creating an Assembly](creating-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="84888-115">For more information, see [Creating an Assembly](creating-an-assembly.md).</span></span>  
  
## <a name="adding-the-source-code-of-an-assembly"></a><span data-ttu-id="84888-116">Agregar el código fuente de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="84888-116">Adding the Source Code of an Assembly</span></span>  
 <span data-ttu-id="84888-117">La cláusula ADD FILE de la sintaxis ALTER ASSEMBLY no está presente en CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="84888-117">The ADD FILE clause in the ALTER ASSEMBLY syntax is not present in CREATE ASSEMBLY.</span></span> <span data-ttu-id="84888-118">Puede usarla para agregar código fuente o cualquier otro archivo asociado a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="84888-118">You can use it to add source code or any other files associated with an assembly.</span></span> <span data-ttu-id="84888-119">Los archivos se copian desde sus ubicaciones originales y se almacenan en tablas del sistema en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="84888-119">The files are copied from their original locations and stored in system tables in the database.</span></span> <span data-ttu-id="84888-120">De esta forma, se garantiza que el código fuente u otros archivos estén disponibles siempre que sea necesario volver a crear o documentar la versión actual del UDT.</span><span class="sxs-lookup"><span data-stu-id="84888-120">This ensures that you always have source code or other files on hand should you ever need to re-create or document the current version of the UDT.</span></span>  
  
 <span data-ttu-id="84888-121">La instrucción siguiente agrega el código fuente de clase Point.cs al UDT Point.</span><span class="sxs-lookup"><span data-stu-id="84888-121">The following statement adds the Point.cs class source code for the Point UDT.</span></span> <span data-ttu-id="84888-122">De esta forma, el texto incluido en el archivo Point.cs se copia y se almacena en la base de datos con el nombre "PointSource".</span><span class="sxs-lookup"><span data-stu-id="84888-122">This copies the text contained in the Point.cs file and stores it in the database under the name "PointSource".</span></span>  
  
 `ALTER ASSEMBLY Point`  
  
 `ADD FILE FROM 'C:\Projects\Point\Point.cs' AS PointSource`  
  
## <a name="see-also"></a><span data-ttu-id="84888-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84888-123">See Also</span></span>  
 <span data-ttu-id="84888-124">[Administrar ensamblados de integración CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="84888-124">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="84888-125">[Crear un ensamblado](creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="84888-125">[Creating an Assembly](creating-an-assembly.md) </span></span>  
 <span data-ttu-id="84888-126">[Quitar un ensamblado](dropping-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="84888-126">[Dropping an Assembly](dropping-an-assembly.md) </span></span>  
 [<span data-ttu-id="84888-127">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="84888-127">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
  
