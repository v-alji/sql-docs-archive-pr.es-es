---
title: srv_getbindtoken (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_getbindtoken
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_getbindtoken
ms.assetid: c947d011-08ac-4fb8-b925-3da6e0999277
author: rothja
ms.author: jroth
ms.openlocfilehash: d42f95c8a7df87f20ebaa30501b96b5f2a00815a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677104"
---
# <a name="srv_getbindtoken-extended-stored-procedure-api"></a><span data-ttu-id="3da15-102">srv_getbindtoken (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="3da15-102">srv_getbindtoken (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="3da15-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3da15-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="3da15-104">Obtiene un token de enlace de la transacción en la sesión del cliente actual que invoca el procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="3da15-104">Obtains a bind token of the transaction in the current client session that invokes the extended stored procedure.</span></span>  
  
 <span data-ttu-id="3da15-105">Luego el procedimiento almacenado extendido puede usar **sp_bindsession** para enlazar cualquier sesión nueva que cree con el mismo servidor a la transacción existente, de manera que la nueva sesión pueda compartir el mismo espacio de bloqueo de transacción con la sesión cliente que ha invocado el procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="3da15-105">The extended stored procedure can then use **sp_bindsession** to bind any new session it creates against the same server to the existing transaction so that the new session can share the same transaction lock space with the client session that invoked the extended stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3da15-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3da15-106">Syntax</span></span>  
  
```  
  
int srv_getbindtoken (  
SRV_PROC*  
srvproc  
,  
char*  
bindtoken  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="3da15-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3da15-107">Arguments</span></span>  
 <span data-ttu-id="3da15-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="3da15-108">*srvproc*</span></span>  
 <span data-ttu-id="3da15-109">Es un puntero a la estructura SRV_PROC que es el identificador de una conexión cliente determinada.</span><span class="sxs-lookup"><span data-stu-id="3da15-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="3da15-110">La estructura contiene toda la información que la biblioteca de API Procedimiento almacenado extendido usa para administrar las comunicaciones y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="3da15-110">The structure contains all the information that the Extended Stored Procedure API library uses to manage communications and data between the application and the client.</span></span>  
  
 <span data-ttu-id="3da15-111">*bindtoken*</span><span class="sxs-lookup"><span data-stu-id="3da15-111">*bindtoken*</span></span>  
 <span data-ttu-id="3da15-112">Es un puntero a un búfer donde se copiará el token de enlace.</span><span class="sxs-lookup"><span data-stu-id="3da15-112">Is a pointer to a buffer where the bind token will be copied.</span></span> <span data-ttu-id="3da15-113">El token de enlace se representa como una cadena terminada en NULL.</span><span class="sxs-lookup"><span data-stu-id="3da15-113">The bind token is represented as a null-terminated string.</span></span> <span data-ttu-id="3da15-114">El búfer que especifica debería tener por lo menos 255 bytes de longitud.</span><span class="sxs-lookup"><span data-stu-id="3da15-114">The buffer you specify should be at least 255 bytes in length.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="3da15-115">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="3da15-115">Returns</span></span>  
 <span data-ttu-id="3da15-116">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="3da15-116">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3da15-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3da15-117">Remarks</span></span>  
  
### <a name="to-bind-an-extended-stored-procedure-session-to-the-client-session-that-called-it-so-they-share-the-same-transaction-lock-space"></a><span data-ttu-id="3da15-118">Para enlazar una sesión de procedimiento almacenado extendido a la sesión del cliente que lo llamó de modo que compartan el mismo espacio de bloqueo de transacción</span><span class="sxs-lookup"><span data-stu-id="3da15-118">To bind an extended stored procedure session to the client session that called it so they share the same transaction lock space</span></span>  
  
1.  <span data-ttu-id="3da15-119">El procedimiento almacenado extendido llama a **svr_getbindtoken** para obtener el token de enlace de la transacción actual en la sesión.</span><span class="sxs-lookup"><span data-stu-id="3da15-119">The extended stored procedure calls **svr_getbindtoken** to get the bind token for the current transaction in the session.</span></span> <span data-ttu-id="3da15-120">El token se devuelve en el parámetro *bindtoken* determinado.</span><span class="sxs-lookup"><span data-stu-id="3da15-120">The token is returned in the given *bindtoken* parameter.</span></span>  
  
2.  <span data-ttu-id="3da15-121">El procedimiento almacenado extendido abre nuevas sesiones con el mismo servidor.</span><span class="sxs-lookup"><span data-stu-id="3da15-121">The extended stored procedure opens new session(s) against the same server.</span></span> <span data-ttu-id="3da15-122">Dentro de esa sesión, el procedimiento almacenado extendido usa el token de enlace con **sp_bindsession** para enlazar la nueva sesión a la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="3da15-122">Inside that session, the extended stored procedure uses the bind token with **sp_bindsession** to bind the new session to the same transaction.</span></span> <span data-ttu-id="3da15-123">El procedimiento almacenado extendido puede crear varias sesiones y enlazar todas las sesiones a la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="3da15-123">The extended stored procedure can create multiple sessions and bind all the sessions to the same transaction.</span></span>  
  
3.  <span data-ttu-id="3da15-124">Una sesión enlazada se desenlaza cuando finaliza el procedimiento almacenado externo o cuando se llama a **sp_bindsession** con una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="3da15-124">A bound session is unbound when the external stored procedure returns or when **sp_bindsession** is called with an empty string.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3da15-125">Solo una sesión enlazada puede tener cada vez acceso a una conexión compartida.</span><span class="sxs-lookup"><span data-stu-id="3da15-125">Only one bound session at a time can have access to a shared connection.</span></span> <span data-ttu-id="3da15-126">Si una sesión está ejecutando actualmente una instrucción en el servidor o tiene resultados pendientes del servidor, ninguna otra sesión que comparta la misma conexión de enlace puede obtener acceso al servidor hasta que la sesión actual haya finalizado de ejecutar la instrucción actual.</span><span class="sxs-lookup"><span data-stu-id="3da15-126">If one session is currently executing a statement at the server or has results pending from the server, no other sessions sharing the same bound connection can gain access to the server until the current session has finished executing the current statement.</span></span> <span data-ttu-id="3da15-127">Si una sesión intenta obtener acceso a la conexión mientras el servidor no está disponible, se devolverá un error a la sesión en conflicto que indique que la conexión se está usando y que se debería reintentar la sesión más tarde.</span><span class="sxs-lookup"><span data-stu-id="3da15-127">If a session attempts to gain access to the connection while the server is busy, an error is returned to the conflicting session indicating the connection is in use and the session should retry later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3da15-128">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="3da15-128">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="3da15-129">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="3da15-129">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da15-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3da15-130">See Also</span></span>  
 <span data-ttu-id="3da15-131">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3da15-131">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span></span>  
 [<span data-ttu-id="3da15-132">sp_getbindtoken &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3da15-132">sp_getbindtoken &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql)  
  
  
