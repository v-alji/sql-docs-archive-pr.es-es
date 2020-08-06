---
title: Crear procedimientos almacenados extendidos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- warnings [SQL Server]
- extended stored procedures [SQL Server], debugging
- extended stored procedures [SQL Server], creating
- messages [SQL Server], extended stored procedures
ms.assetid: 9f7c0cdb-6d88-44c0-b049-29953ae75717
author: rothja
ms.author: jroth
ms.openlocfilehash: d243b27b8542ec5fe10d795de1729d6c1fe484c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675390"
---
# <a name="creating-extended-stored-procedures"></a><span data-ttu-id="399c0-102">Crear procedimientos almacenados extendidos</span><span class="sxs-lookup"><span data-stu-id="399c0-102">Creating Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="399c0-103">En su lugar, utilice la integración con CLR.</span><span class="sxs-lookup"><span data-stu-id="399c0-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="399c0-104">Un procedimiento almacenado extendido es una función con un prototipo:</span><span class="sxs-lookup"><span data-stu-id="399c0-104">An extended stored procedure is a function with a prototype:</span></span>  
  
 <span data-ttu-id="399c0-105">*Xp_extendedProcName* SRVRETCODE **(** SRVPROC \*\* \* );\*\*</span><span class="sxs-lookup"><span data-stu-id="399c0-105">SRVRETCODE *xp_extendedProcName* **(** SRVPROC **\*);**</span></span>  
  
 <span data-ttu-id="399c0-106">El uso del prefijo xp_ es opcional.</span><span class="sxs-lookup"><span data-stu-id="399c0-106">Using the prefix xp_ is optional.</span></span> <span data-ttu-id="399c0-107">Los nombres de procedimiento almacenado extendido distinguen mayúsculas de minúsculas cuando se hace referencia a ellos en instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)], independientemente de la página de códigos o criterio de ordenación que se haya instalado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="399c0-107">Extended stored procedure names are case sensitive when referenced in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, regardless of code page/sort order installed on the server.</span></span> <span data-ttu-id="399c0-108">Cuando genere un archivo DLL:</span><span class="sxs-lookup"><span data-stu-id="399c0-108">When you build a DLL:</span></span>  
  
-   <span data-ttu-id="399c0-109">Si se necesita un punto de entrada, escriba una función DllMain.</span><span class="sxs-lookup"><span data-stu-id="399c0-109">If an entry point is necessary, write a DllMain function.</span></span>  
  
     <span data-ttu-id="399c0-110">Esta función es opcional; si no se proporciona en código fuente, el compilador vincula su propia versión, que solo devuelve TRUE.</span><span class="sxs-lookup"><span data-stu-id="399c0-110">This function is optional; if you do not provide it in source code, the compiler links its own version, which does nothing but return TRUE.</span></span> <span data-ttu-id="399c0-111">Si se proporciona una función DllMain, el sistema operativo llama a esta función cuando se adjunta o se separa un proceso o subproceso en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="399c0-111">If you provide a DllMain function, the operating system calls this function when a thread or process attaches to or detaches from the DLL.</span></span>  
  
-   <span data-ttu-id="399c0-112">Deben exportarse todas las funciones a las que se llama desde el exterior del archivo DLL (todas las funciones Efunction de procedimiento almacenado extendido).</span><span class="sxs-lookup"><span data-stu-id="399c0-112">All functions called from outside the DLL (all extended stored procedure Efunctions) must be exported.</span></span>  
  
     <span data-ttu-id="399c0-113">Puede exportar una función enumerando su nombre en la sección Exports de un archivo. def o puede anteponer el nombre de función en el código fuente con __declspec (dllexport), una extensión de compilador de Microsoft (tenga en cuenta que \_ _declspec () comienza con dos guiones bajos).</span><span class="sxs-lookup"><span data-stu-id="399c0-113">You can export a function by listing its name in the EXPORTS section of a .def file, or you can prefix the function name in the source code with __declspec(dllexport), a Microsoft compiler extension (Note that \__declspec() begins with two underscores).</span></span>  
  
 <span data-ttu-id="399c0-114">Estos archivos son necesarios para crear un archivo DLL de procedimientos almacenados extendidos.</span><span class="sxs-lookup"><span data-stu-id="399c0-114">These files are required for creating an extended stored procedure DLL.</span></span>  
  
|<span data-ttu-id="399c0-115">Archivo</span><span class="sxs-lookup"><span data-stu-id="399c0-115">File</span></span>|<span data-ttu-id="399c0-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="399c0-116">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="399c0-117">Srv.h</span><span class="sxs-lookup"><span data-stu-id="399c0-117">Srv.h</span></span>|<span data-ttu-id="399c0-118">Archivo de encabezado de la API Procedimiento almacenado extendido</span><span class="sxs-lookup"><span data-stu-id="399c0-118">Extended Stored Procedure API header file</span></span>|  
|<span data-ttu-id="399c0-119">Opends60.lib</span><span class="sxs-lookup"><span data-stu-id="399c0-119">Opends60.lib</span></span>|<span data-ttu-id="399c0-120">Biblioteca de importación de Opends60.dll</span><span class="sxs-lookup"><span data-stu-id="399c0-120">Import library for Opends60.dll</span></span>|  
  
 <span data-ttu-id="399c0-121">Para crear un archivo DLL de procedimientos almacenados extendidos, cree un proyecto de tipo biblioteca de vínculos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="399c0-121">To create an extended stored procedure DLL, create a project of type Dynamic Link Library.</span></span> <span data-ttu-id="399c0-122">Para obtener más información sobre la forma de crear un archivo DLL, vea la documentación del entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="399c0-122">For more information about creating a DLL, see the development environment documentation.</span></span>  
  
 <span data-ttu-id="399c0-123">Se recomienda encarecidamente que todos los archivos DLL de procedimientos almacenados extendidos implementen y exporten la siguiente función:</span><span class="sxs-lookup"><span data-stu-id="399c0-123">It is highly recommended that all extended stored procedure DLLs implement and export the following function:</span></span>  
  
```  
__declspec(dllexport) ULONG __GetXpVersion()  
{  
   return ODS_VERSION;  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="399c0-124">__declspec(dllexport) es una extensión de compilador específica de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="399c0-124">__declspec(dllexport) is a Microsoft-specific compiler extension.</span></span> <span data-ttu-id="399c0-125">Si el compilador no admite esta directiva, debe exportar esta función en el archivo DEF, bajo la sección EXPORTS.</span><span class="sxs-lookup"><span data-stu-id="399c0-125">If your compiler does not support this directive, you should export this function in your DEF file under the EXPORTS section.</span></span>  
  
 <span data-ttu-id="399c0-126">Cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se inicia con la marca de seguimiento-T260 o si un usuario con privilegios de administrador del sistema ejecuta DBCC TRACEON (260), y si la dll de procedimiento almacenado extendido no admite __GetXpVersion (), un mensaje de advertencia (Error 8131: el archivo dll de procedimientos almacenados extendidos '% ' no exporta \_ _GetXpVersion ().) se imprime en el registro de errores.</span><span class="sxs-lookup"><span data-stu-id="399c0-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started with the trace flag -T260 or if a user with system administrator privileges runs DBCC TRACEON (260), and if the extended stored procedure DLL does not support __GetXpVersion(), a warning message (Error 8131: Extended stored procedure DLL '%' does not export \__GetXpVersion().) is printed to the error log.</span></span> <span data-ttu-id="399c0-127">(Tenga en cuenta que \_ _GetXpVersion () comienza con dos guiones bajos).</span><span class="sxs-lookup"><span data-stu-id="399c0-127">(Note that \__GetXpVersion() begins with two underscores.)</span></span>  
  
 <span data-ttu-id="399c0-128">Si el archivo DLL de procedimientos almacenados extendidos exporta __GetXpVersion() pero la versión devuelta por la función es menor que la que requiere el servidor, en el registro de errores se imprime un mensaje de advertencia que indica la versión devuelta por la función y la versión esperada por el servidor.</span><span class="sxs-lookup"><span data-stu-id="399c0-128">If the extended stored procedure DLL exports __GetXpVersion(), but the version returned by the function is less than that required by the server, a warning message stating the version returned by the function and the version expected by the server is printed to the error log.</span></span> <span data-ttu-id="399c0-129">Si recibe este mensaje, devuelve un valor incorrecto de \_ _GetXpVersion () o está compilando con una versión anterior de SRV. h.</span><span class="sxs-lookup"><span data-stu-id="399c0-129">If you get this message, you are returning an incorrect value from \__GetXpVersion(), or you are compiling with an older version of srv.h.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="399c0-130">No debe llamarse a SetErrorMode, una función Win32 de [!INCLUDE[msCoName](../../includes/msconame-md.md)], en procedimientos almacenados extendidos.</span><span class="sxs-lookup"><span data-stu-id="399c0-130">SetErrorMode, a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 function, should not be called in extended stored procedures.</span></span>  
  
 <span data-ttu-id="399c0-131">Se recomienda que un procedimiento almacenado extendido de ejecución prolongada llame periódicamente a srv_got_attention para que el procedimiento pueda finalizarse si se elimina la conexión o se anula el lote.</span><span class="sxs-lookup"><span data-stu-id="399c0-131">It is recommended that a long-running extended stored procedure should call srv_got_attention periodically so that the procedure can terminate itself if the connection is killed or the batch is aborted.</span></span>  
  
 <span data-ttu-id="399c0-132">Para depurar un archivo DLL de procedimientos almacenados extendidos, cópielo en el directorio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\Binn.</span><span class="sxs-lookup"><span data-stu-id="399c0-132">To debug an extended stored procedure DLL, copy it to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\Binn directory.</span></span> <span data-ttu-id="399c0-133">Para especificar el archivo ejecutable para la sesión de depuración, escriba la ruta de acceso y el nombre del archivo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ejecutable (por ejemplo, C:\Archivos de programa\microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Sqlservr.exe).</span><span class="sxs-lookup"><span data-stu-id="399c0-133">To specify the executable for the debugging session, enter the path and file name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executable file (for example, C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Sqlservr.exe).</span></span> <span data-ttu-id="399c0-134">Para obtener información acerca de los argumentos de sqlservr, vea [sqlservr Application](../../tools/sqlservr-application.md).</span><span class="sxs-lookup"><span data-stu-id="399c0-134">For information about sqlservr arguments, see [sqlservr Application](../../tools/sqlservr-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="399c0-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="399c0-135">See Also</span></span>  
 [<span data-ttu-id="399c0-136">srv_got_attention API de procedimiento almacenado extendido &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="399c0-136">srv_got_attention &#40;Extended Stored Procedure API&#41;</span></span>](../extended-stored-procedures-reference/srv-got-attention-extended-stored-procedure-api.md)  
  
  
