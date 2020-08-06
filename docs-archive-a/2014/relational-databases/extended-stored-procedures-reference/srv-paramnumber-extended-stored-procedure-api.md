---
title: srv_paramnumber (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramnumber
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramnumber
ms.assetid: d7a6dbff-71d9-4297-8a4f-bfd2876fe204
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e621101c909ef251c40f38713e438d8e40d08a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675383"
---
# <a name="srv_paramnumber-extended-stored-procedure-api"></a><span data-ttu-id="49125-102">srv_paramnumber (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="49125-102">srv_paramnumber (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="49125-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="49125-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="49125-104">Devuelve el número de un parámetro de llamada a un procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="49125-104">Returns the number of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49125-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49125-105">Syntax</span></span>  
  
```  
  
int srv_paramnumber (  
SRV_PROC *  
srvproc  
,  
DBCHAR *  
name  
,   
int  
namelen   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="49125-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="49125-106">Arguments</span></span>  
 <span data-ttu-id="49125-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="49125-107">*srvproc*</span></span>  
 <span data-ttu-id="49125-108">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió la llamada al procedimiento almacenado remoto).</span><span class="sxs-lookup"><span data-stu-id="49125-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="49125-109">La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="49125-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="49125-110">*name*</span><span class="sxs-lookup"><span data-stu-id="49125-110">*name*</span></span>  
 <span data-ttu-id="49125-111">Es un puntero al parámetro *name*.</span><span class="sxs-lookup"><span data-stu-id="49125-111">Is a pointer to the parameter *name*.</span></span>  
  
 <span data-ttu-id="49125-112">*namelen*</span><span class="sxs-lookup"><span data-stu-id="49125-112">*namelen*</span></span>  
 <span data-ttu-id="49125-113">Es la longitud de *name*.</span><span class="sxs-lookup"><span data-stu-id="49125-113">Is the length of *name*.</span></span> <span data-ttu-id="49125-114">Si *name* está terminado en null, establezca *namelen* en SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="49125-114">If *name* is null-terminated, set *namelen* to SRV_NULLTERM.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="49125-115">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="49125-115">Returns</span></span>  
 <span data-ttu-id="49125-116">Es el número de parámetro del parámetro nombrado.</span><span class="sxs-lookup"><span data-stu-id="49125-116">The parameter number of the named parameter.</span></span> <span data-ttu-id="49125-117">El primer parámetro es 1.</span><span class="sxs-lookup"><span data-stu-id="49125-117">The first parameter is 1.</span></span> <span data-ttu-id="49125-118">Si no hay ningún parámetro denominado *name* o ningún procedimiento almacenado remoto, se devuelve 0 y se genera un mensaje.</span><span class="sxs-lookup"><span data-stu-id="49125-118">If there is no parameter named *name* or no remote stored procedure, 0 is returned and a message is generated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49125-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="49125-119">Remarks</span></span>  
 <span data-ttu-id="49125-120">Cuando se usan parámetros en una llamada a un procedimiento almacenado remoto, estos pueden pasarse por nombre o por posición (sin nombre).</span><span class="sxs-lookup"><span data-stu-id="49125-120">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="49125-121">Se produce un error si la llamada al procedimiento almacenado remoto se realiza con algunos parámetros pasados por nombre y otros pasados por posición.</span><span class="sxs-lookup"><span data-stu-id="49125-121">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="49125-122">Sigue llamándose al controlador SRV_RPC, pero parece como si no hubiera ningún parámetro y **srv_rpcparams** devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="49125-122">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="49125-123">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="49125-123">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="49125-124">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="49125-124">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49125-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49125-125">See Also</span></span>  
 [<span data-ttu-id="49125-126">srv_rpcparams &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="49125-126">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
