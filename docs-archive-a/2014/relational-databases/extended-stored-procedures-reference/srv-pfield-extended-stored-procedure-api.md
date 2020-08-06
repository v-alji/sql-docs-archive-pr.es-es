---
title: srv_pfield (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_pfield
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_pfield
ms.assetid: a61e4c1f-e65b-48ea-a7d1-3e1544af389d
author: rothja
ms.author: jroth
ms.openlocfilehash: 90680d59dbf36ad3f713fd7a09d07553890a8668
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751018"
---
# <a name="srv_pfield-extended-stored-procedure-api"></a><span data-ttu-id="da10c-102">srv_pfield (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="da10c-102">srv_pfield (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="da10c-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="da10c-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="da10c-104">Devuelve información acerca de una conexión de base de datos.</span><span class="sxs-lookup"><span data-stu-id="da10c-104">Returns information about a database connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da10c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da10c-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_pfield (  
SRV_PROC *  
srvproc  
,  
int   
field  
,  
int *  
len  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="da10c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="da10c-106">Arguments</span></span>  
 <span data-ttu-id="da10c-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="da10c-107">*srvproc*</span></span>  
 <span data-ttu-id="da10c-108">Puntero que identifica una conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="da10c-108">Pointer identifying a database connection.</span></span>  
  
 <span data-ttu-id="da10c-109">*campo*</span><span class="sxs-lookup"><span data-stu-id="da10c-109">*field*</span></span>  
 <span data-ttu-id="da10c-110">Especifica los datos que se van a devolver en la conexión.</span><span class="sxs-lookup"><span data-stu-id="da10c-110">Specifies data on the connection to return.</span></span>  
  
|<span data-ttu-id="da10c-111">Value</span><span class="sxs-lookup"><span data-stu-id="da10c-111">Value</span></span>|<span data-ttu-id="da10c-112">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="da10c-112">Returns</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="da10c-113">SRV_APPLNAME</span><span class="sxs-lookup"><span data-stu-id="da10c-113">SRV_APPLNAME</span></span>|<span data-ttu-id="da10c-114">El nombre de aplicación proporcionado por el cliente cuando estableció la conexión.</span><span class="sxs-lookup"><span data-stu-id="da10c-114">The application name provided by the client when it established the connection.</span></span>|  
|<span data-ttu-id="da10c-115">SRV_BCPFLAG</span><span class="sxs-lookup"><span data-stu-id="da10c-115">SRV_BCPFLAG</span></span>|<span data-ttu-id="da10c-116">Una marca que es TRUE si el cliente está preparando una operación de copia masiva; de lo contrario, FALSE.</span><span class="sxs-lookup"><span data-stu-id="da10c-116">A flag that is TRUE if the client is preparing for a bulk copy operation; otherwise, FALSE.</span></span>|  
|<span data-ttu-id="da10c-117">SRV_CLIB</span><span class="sxs-lookup"><span data-stu-id="da10c-117">SRV_CLIB</span></span>|<span data-ttu-id="da10c-118">El nombre de la biblioteca que permite al cliente hablar con un servidor.</span><span class="sxs-lookup"><span data-stu-id="da10c-118">The name of the library that enables the client to talk to a server.</span></span>|  
|<span data-ttu-id="da10c-119">SRV_CPID</span><span class="sxs-lookup"><span data-stu-id="da10c-119">SRV_CPID</span></span>|<span data-ttu-id="da10c-120">El identificador de proceso de cliente en el equipo de origen del cliente.</span><span class="sxs-lookup"><span data-stu-id="da10c-120">The client process ID on the client source computer.</span></span>|  
|<span data-ttu-id="da10c-121">SRV_HOST</span><span class="sxs-lookup"><span data-stu-id="da10c-121">SRV_HOST</span></span>|<span data-ttu-id="da10c-122">El nombre del equipo del cliente proporcionado por el cliente cuando estableció la conexión.</span><span class="sxs-lookup"><span data-stu-id="da10c-122">The name of the client's machine provided by the client when it established the connection.</span></span>|  
|<span data-ttu-id="da10c-123">SRV_LIBVERS</span><span class="sxs-lookup"><span data-stu-id="da10c-123">SRV_LIBVERS</span></span>|<span data-ttu-id="da10c-124">La versión de la biblioteca del cliente.</span><span class="sxs-lookup"><span data-stu-id="da10c-124">The version of the client library.</span></span>|  
|<span data-ttu-id="da10c-125">SRV_LSECURE</span><span class="sxs-lookup"><span data-stu-id="da10c-125">SRV_LSECURE</span></span>|<span data-ttu-id="da10c-126">Una marca.</span><span class="sxs-lookup"><span data-stu-id="da10c-126">A flag.</span></span> <span data-ttu-id="da10c-127">TRUE si la conexión utilizó seguridad integrada para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="da10c-127">TRUE if the connection used integrated security to login.</span></span>|  
|<span data-ttu-id="da10c-128">SRV_NETWORK_MODULE</span><span class="sxs-lookup"><span data-stu-id="da10c-128">SRV_NETWORK_MODULE</span></span>|<span data-ttu-id="da10c-129">El nombre de la DLL de Net-Library que utiliza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da10c-129">The name of the Net-Library DLL used by the connection.</span></span>|  
|<span data-ttu-id="da10c-130">SRV_NETWORK_VERSION</span><span class="sxs-lookup"><span data-stu-id="da10c-130">SRV_NETWORK_VERSION</span></span>|<span data-ttu-id="da10c-131">La versión de la DLL de Net-Library que utiliza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da10c-131">The version of the Net-Library DLL used by the connection.</span></span>|  
|<span data-ttu-id="da10c-132">SRV_NETWORK_CONNECTION</span><span class="sxs-lookup"><span data-stu-id="da10c-132">SRV_NETWORK_CONNECTION</span></span>|<span data-ttu-id="da10c-133">La cadena de conexión pasada a la DLL de la biblioteca de red usada para la conexión *srvproc* actual.</span><span class="sxs-lookup"><span data-stu-id="da10c-133">The connection string passed to the Net-Library DLL used for the current *srvproc* connection.</span></span>|  
|<span data-ttu-id="da10c-134">SRV_PIPEHANDLE</span><span class="sxs-lookup"><span data-stu-id="da10c-134">SRV_PIPEHANDLE</span></span>|<span data-ttu-id="da10c-135">Una cadena que contiene el identificador de canalización de un cliente conectado o NULL si el cliente está conectado en una red que no utiliza canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="da10c-135">A string containing the pipe handle of a connected client, or NULL if the client is connected on a network that does not use named pipes.</span></span> <span data-ttu-id="da10c-136">Para utilizar este identificador como un identificador de canalización válido con [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, convierta esta cadena en un entero.</span><span class="sxs-lookup"><span data-stu-id="da10c-136">To use this handle as a valid pipe handle with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, convert this string to an integer.</span></span>|  
|<span data-ttu-id="da10c-137">SRV_RMTSERVER</span><span class="sxs-lookup"><span data-stu-id="da10c-137">SRV_RMTSERVER</span></span>|<span data-ttu-id="da10c-138">El servidor desde el que inicia sesión el proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="da10c-138">The server from which the client process is logged in.</span></span> <span data-ttu-id="da10c-139">Si el inicio de sesión se realiza desde un cliente, este valor es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="da10c-139">If the login is from a client, this value is an empty string.</span></span>|  
|<span data-ttu-id="da10c-140">SRV_ROWSENT</span><span class="sxs-lookup"><span data-stu-id="da10c-140">SRV_ROWSENT</span></span>|<span data-ttu-id="da10c-141">El número de filas ya enviado por *srvproc* para el conjunto actual de resultados.</span><span class="sxs-lookup"><span data-stu-id="da10c-141">The number of rows already sent by *srvproc* for the current set of results.</span></span>|  
|<span data-ttu-id="da10c-142">SRV_SPID</span><span class="sxs-lookup"><span data-stu-id="da10c-142">SRV_SPID</span></span>|<span data-ttu-id="da10c-143">El identificador de subproceso de servidor de *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="da10c-143">The server thread ID of the *srvproc*.</span></span> <span data-ttu-id="da10c-144">En los procedimientos almacenados extendidos, este valor es igual que la columna **kpid** de **sys.sysprocesses** y puede cambiar con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="da10c-144">For extended stored procedures, this value is the same as the **kpid** column of **sys.sysprocesses**, and it can change over time.</span></span>|  
|<span data-ttu-id="da10c-145">SRV_SPROC_CODEPAGE</span><span class="sxs-lookup"><span data-stu-id="da10c-145">SRV_SPROC_CODEPAGE</span></span>|<span data-ttu-id="da10c-146">Página de códigos que utiliza el servidor para interpretar datos multibyte.</span><span class="sxs-lookup"><span data-stu-id="da10c-146">Codepage that the server uses to interpret multbyte data.</span></span>|  
|<span data-ttu-id="da10c-147">SRV_STATUS</span><span class="sxs-lookup"><span data-stu-id="da10c-147">SRV_STATUS</span></span>|<span data-ttu-id="da10c-148">El estado actual de *srvproc*: en ejecución o cerrado.</span><span class="sxs-lookup"><span data-stu-id="da10c-148">The current status of *srvproc*: running or closed</span></span>|  
|<span data-ttu-id="da10c-149">SRV_TYPE</span><span class="sxs-lookup"><span data-stu-id="da10c-149">SRV_TYPE</span></span>|<span data-ttu-id="da10c-150">El tipo de conexión de *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="da10c-150">The connection type of *srvproc*.</span></span> <span data-ttu-id="da10c-151">Si se ha devuelto el servidor, *srvproc* procede de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da10c-151">If server is returned, *srvproc* is from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="da10c-152">Si se ha devuelto el cliente, *srvproc* procede de un cliente DB-Library u ODBC.</span><span class="sxs-lookup"><span data-stu-id="da10c-152">If client is returned, *srvproc* is from a DB-Library or ODBC client.</span></span>|  
|<span data-ttu-id="da10c-153">SRV_USER</span><span class="sxs-lookup"><span data-stu-id="da10c-153">SRV_USER</span></span>|<span data-ttu-id="da10c-154">El nombre del usuario de la conexión.</span><span class="sxs-lookup"><span data-stu-id="da10c-154">The user name of the connection.</span></span>|  
|||  
  
 <span data-ttu-id="da10c-155">*terminado*</span><span class="sxs-lookup"><span data-stu-id="da10c-155">*len*</span></span>  
 <span data-ttu-id="da10c-156">Es un puntero a una variable **int** que contiene la longitud del valor *field* devuelto.</span><span class="sxs-lookup"><span data-stu-id="da10c-156">Is a pointer to an **int** variable that contains the length of the returned *field* value.</span></span> <span data-ttu-id="da10c-157">Si *len* es NULL, no se devuelve la longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="da10c-157">If *len* is NULL, the length of the string is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="da10c-158">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="da10c-158">Returns</span></span>  
 <span data-ttu-id="da10c-159">Un puntero a una cadena terminada en NULL que contiene el valor actual del campo especificado en la estructura de SRV_PROC.</span><span class="sxs-lookup"><span data-stu-id="da10c-159">A pointer to a null-terminated string containing the current value for the specified field in the SRV_PROC structure.</span></span> <span data-ttu-id="da10c-160">Si el campo está vacío, se devuelve un puntero válido a una cadena vacía y *len* contiene 0.</span><span class="sxs-lookup"><span data-stu-id="da10c-160">If the field is empty, a valid pointer to an empty string is returned and *len* contains 0.</span></span> <span data-ttu-id="da10c-161">Si el campo es desconocido, se devuelve NULL y *len* contiene el valor -1.</span><span class="sxs-lookup"><span data-stu-id="da10c-161">If the field is unknown, NULL is returned and *len* contains the value -1.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="da10c-162">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="da10c-162">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="da10c-163">Para más información sobre la revisión y las pruebas de seguridad, vea [Security Developer Center](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="da10c-163">For information about security review and testing, see the [Security Developer Center](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
