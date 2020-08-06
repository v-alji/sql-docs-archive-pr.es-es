---
title: Agregar un procedimiento almacenado extendido a SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], adding
- adding extended stored procedures
- collations [SQL Server], extended stored procedures
ms.assetid: 10f1bb74-3b43-4efd-b7ab-7a85a8600a50
author: rothja
ms.author: jroth
ms.openlocfilehash: 03ac8c2a0fa9ce77db59d50b3a7b9da42415e013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675392"
---
# <a name="adding-an-extended-stored-procedure-to-sql-server"></a><span data-ttu-id="8f040-102">Agregar un procedimiento almacenado extendido a SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f040-102">Adding an Extended Stored Procedure to SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="8f040-103">En su lugar, utilice la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="8f040-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="8f040-104">Un archivo DLL que contiene funciones de procedimiento almacenado extendido actúa como extensión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f040-104">A DLL that contains extended stored procedure functions acts as an extension to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8f040-105">Para instalar el archivo DLL, cópielo en un directorio como, por ejemplo, el que contiene los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] archivos DLL estándar (c:\Archivos de programa\Microsoft SQL Server\MSSQL12.0.\* x\*\MSSQL\Binn de forma predeterminada).</span><span class="sxs-lookup"><span data-stu-id="8f040-105">To install the DLL, copy the file to a directory, such as the one that contains the standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DLL files (C:\Program Files\Microsoft SQL Server\MSSQL12.0.*x*\MSSQL\Binn by default).</span></span>  
  
 <span data-ttu-id="8f040-106">Una vez que haya copiado en el servidor el archivo DLL de procedimiento almacenado extendido, un administrador del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe registrar en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cada una de las funciones de procedimiento almacenado extendido del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="8f040-106">After the extended stored procedure DLL has been copied to the server, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator must register to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] each extended stored procedure function in the DLL.</span></span> <span data-ttu-id="8f040-107">Para ello, debe utilizarse el procedimiento almacenado del sistema sp_addextendedproc.</span><span class="sxs-lookup"><span data-stu-id="8f040-107">This is done using the sp_addextendedproc system stored procedure.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8f040-108">Antes de agregar el procedimiento almacenado extendido al servidor y otorgar permisos de ejecución a otros usuarios, el administrador del sistema debe revisarlo por completo para asegurarse de que no contenga código perjudicial o malintencionado.</span><span class="sxs-lookup"><span data-stu-id="8f040-108">The system administrator should thoroughly review an extended stored procedure to ensure that it does not contain harmful or malicious code before adding it to the server and granting execute permissions to other users.</span></span>  <span data-ttu-id="8f040-109">Valide todos los datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8f040-109">Validate all user input.</span></span> <span data-ttu-id="8f040-110">No concatene la entrada del usuario antes de validarla.</span><span class="sxs-lookup"><span data-stu-id="8f040-110">Do not concatenate user input before validating it.</span></span> <span data-ttu-id="8f040-111">No ejecute nunca un comando creado a partir de una entrada de usuario no validada.</span><span class="sxs-lookup"><span data-stu-id="8f040-111">Never execute a command constructed from unvalidated user input.</span></span>  
  
 <span data-ttu-id="8f040-112">El primer parámetro de sp_addextendedproc especifica el nombre de la función y el segundo parámetro especifica el nombre del archivo DLL donde reside dicha función.</span><span class="sxs-lookup"><span data-stu-id="8f040-112">The first parameter of sp_addextendedproc specifies the name of the function, and the second parameter specifies the name of the DLL in which that function resides.</span></span> <span data-ttu-id="8f040-113">Se recomienda especificar la ruta de acceso completa del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="8f040-113">It is recommended that you specify the complete path of the DLL.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8f040-114">Los archivos DLL existentes que no se hayan registrado con una ruta de acceso completa no funcionarán tras una actualización a SQL Server 2005 o posterior.</span><span class="sxs-lookup"><span data-stu-id="8f040-114">Existing DLLs that were not registered with a complete path will not work after upgrading to SQL Server 2005 or later.</span></span> <span data-ttu-id="8f040-115">Para corregir el problema, utilice sp_dropextendedproc con el fin de eliminar el archivo DLL del registro y, a continuación, vuelva a registrarlo con sp_addextendedproc, especificando la ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="8f040-115">To correct the problem, use sp_dropextendedproc to unregister the DLL, and then reregister it with sp_addextendedproc, specifying the complete path.</span></span>  
  
 <span data-ttu-id="8f040-116">El nombre de la función especificada en `sp_addextendedproc` debe ser exactamente el mismo que el nombre de la función del archivo DLL, incluidas las mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8f040-116">The name of the function specified in `sp_addextendedproc` must be exactly the same, including the case, as the function's name in the DLL.</span></span> <span data-ttu-id="8f040-117">Por ejemplo, este comando registra una función `xp_hello,` situada en un archivo dll denominado `xp_hello.dll`, como un procedimiento almacenado extendido de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8f040-117">For example, this command registers a function `xp_hello,` located in a dll named `xp_hello.dll`, as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extended stored procedure:</span></span>  
  
```  
sp_addextendedproc 'xp_hello', 'c:\Program Files\Microsoft SQL Server\MSSQL12.0.MSSQLSERVER\MSSQL\Binn\xp_hello.dll';  
```  
  
 <span data-ttu-id="8f040-118">Si el nombre de la función especificada en `sp_addextendedproc` no coincide exactamente con el nombre de función del archivo DLL, el nuevo nombre se registrará en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], pero no podrá utilizarse.</span><span class="sxs-lookup"><span data-stu-id="8f040-118">If the name of the function specified in `sp_addextendedproc` does not exactly match the function name in the DLL, the new name will be registered in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but the name will not be usable.</span></span> <span data-ttu-id="8f040-119">Por ejemplo, aunque `xp_Hello` se registre como un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] procedimiento almacenado extendido ubicado en `xp_hello.dll` , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no podrá encontrar la función en el archivo dll si usa `xp_Hello` para llamar a la función más adelante.</span><span class="sxs-lookup"><span data-stu-id="8f040-119">For example, although `xp_Hello` is registered as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extended stored procedure located in `xp_hello.dll`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not be able to find the function in the DLL if you use `xp_Hello` to call the function later.</span></span>  
  
```  
--Register the function (xp_hello) with an initial upper case  
sp_addextendedproc 'xp_Hello', 'c:\xp_hello.dll';  
  
--Use the newly registered name to call the function  
DECLARE @txt varchar(33);  
EXEC xp_Hello @txt OUTPUT;  
  
--This is the error message  
Server: Msg 17750, Level 16, State 1, Procedure xp_Hello, Line 1  
Could not load the DLL xp_hello.dll, or one of the DLLs it references. Reason: 127(The specified procedure could not be found.).  
```  
  
 <span data-ttu-id="8f040-120">Si el nombre de la función especificada en `sp_addextendedproc` coincide exactamente con el nombre de función del archivo DLL y la intercalación de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no distingue mayúsculas de minúsculas, el usuario puede llamar al procedimiento almacenado extendido utilizando cualquier combinación de letras mayúsculas y minúsculas en el nombre.</span><span class="sxs-lookup"><span data-stu-id="8f040-120">If the name of the function specified in `sp_addextendedproc` matches exactly the function name in the DLL, and the collation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is case-insensitive, the user can call the extended stored procedure using any combination of lower- and upper-case letters of the name.</span></span>  
  
```  
--Register the function (xp_hello)  
sp_addextendedproc 'xp_hello', 'c:\xp_hello.dll';  
  
--The following will succeed in calling xp_hello  
DECLARE @txt varchar(33);  
EXEC xp_Hello @txt OUTPUT;  
  
DECLARE @txt varchar(33);  
EXEC xp_HelLO @txt OUTPUT;  
  
DECLARE @txt varchar(33);  
EXEC xp_HELLO @txt OUTPUT;  
```  
  
 <span data-ttu-id="8f040-121">Cuando la intercalación de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] distinga mayúsculas de minúsculas, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no podrá llamar al procedimiento almacenado extendido (aunque se haya registrado exactamente con el mismo nombre e intercalación que la función del archivo DLL) si se llama al procedimiento con distintas letras mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8f040-121">When the collation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is case-sensitive, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not be able to call the extended stored procedure -- even if it was registered with exactly the same name and collation as the function in the DLL -- if the procedure is called with a different case.</span></span>  
  
```  
--Register the function (xp_hello)  
sp_addextendedproc 'xp_hello', 'c:\xp_hello.dll';  
  
--The following will result in an error  
DECLARE @txt varchar(33);  
EXEC xp_HELLO @txt OUTPUT;  
  
--This is the error  
Server: Msg 2812, Level 16, State 62, Line 1  
```  
  
 <span data-ttu-id="8f040-122">No es necesario detener y reiniciar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f040-122">It is not necessary to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f040-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f040-123">See Also</span></span>  
 <span data-ttu-id="8f040-124">[sp_addextendedproc &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8f040-124">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span></span>  
 [<span data-ttu-id="8f040-125">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8f040-125">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
