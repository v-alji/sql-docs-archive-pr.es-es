---
title: srv_paramname (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramname
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramname
ms.assetid: 1a53d707-7b06-49cc-a0df-ac727cfe953f
author: rothja
ms.author: jroth
ms.openlocfilehash: 2227ac3d46efe7d09abc05964248229f3533d42d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751022"
---
# <a name="srv_paramname-extended-stored-procedure-api"></a><span data-ttu-id="34973-102">srv_paramname (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="34973-102">srv_paramname (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="34973-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="34973-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="34973-104">Devuelve el nombre de un parámetro de llamada a un procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="34973-104">Returns the name of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34973-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34973-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_paramname (  
SRV_PROC * srvproc,intn, int *len );  
```  
  
## <a name="arguments"></a><span data-ttu-id="34973-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="34973-106">Arguments</span></span>  
 <span data-ttu-id="34973-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="34973-107">*srvproc*</span></span>  
 <span data-ttu-id="34973-108">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió la llamada al procedimiento almacenado remoto).</span><span class="sxs-lookup"><span data-stu-id="34973-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="34973-109">La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="34973-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="34973-110">*n*</span><span class="sxs-lookup"><span data-stu-id="34973-110">*n*</span></span>  
 <span data-ttu-id="34973-111">Indica el número del parámetro.</span><span class="sxs-lookup"><span data-stu-id="34973-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="34973-112">El primer parámetro es 1.</span><span class="sxs-lookup"><span data-stu-id="34973-112">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="34973-113">*terminado*</span><span class="sxs-lookup"><span data-stu-id="34973-113">*len*</span></span>  
 <span data-ttu-id="34973-114">Proporciona un puntero a una variable `int` que contiene la longitud (en bytes) del nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="34973-114">Provides a pointer to an `int` variable that contains the length, in bytes, of the parameter name.</span></span> <span data-ttu-id="34973-115">Si *len* es NULL, no se devuelve la longitud del nombre de parámetro del procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="34973-115">If *len* is NULL, the length of the remote stored procedure parameter name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="34973-116">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="34973-116">Returns</span></span>  
 <span data-ttu-id="34973-117">Un puntero a una cadena de caracteres terminada en NULL que contiene el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="34973-117">A pointer to a null-terminated character string that contains the parameter name.</span></span> <span data-ttu-id="34973-118">La longitud del nombre de parámetro se almacena en *len*.</span><span class="sxs-lookup"><span data-stu-id="34973-118">The length of the parameter name is stored in *len*.</span></span> <span data-ttu-id="34973-119">Si no hay ningún parámetro *n* ni ningún procedimiento almacenado remoto, devuelve NULL, *len* se establece en -1 y se envía un mensaje de error informativo.</span><span class="sxs-lookup"><span data-stu-id="34973-119">If there is no *n*th parameter or no remote stored procedure, it returns NULL, *len* is set to -1, and an informational error message is sent.</span></span> <span data-ttu-id="34973-120">Si el nombre de parámetro es NULL, *len* se establece en 0 y se devuelve una cadena vacía terminada en NULL.</span><span class="sxs-lookup"><span data-stu-id="34973-120">If the parameter name is NULL, *len* is set to 0 and a null-terminated empty string is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34973-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="34973-121">Remarks</span></span>  
 <span data-ttu-id="34973-122">Esta función obtiene el nombre de un parámetro de llamada a un procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="34973-122">This function gets the name of a remote stored procedure call parameter.</span></span> <span data-ttu-id="34973-123">Cuando se usan parámetros en una llamada a un procedimiento almacenado remoto, estos pueden pasarse por nombre o por posición (sin nombre).</span><span class="sxs-lookup"><span data-stu-id="34973-123">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="34973-124">Se produce un error si la llamada al procedimiento almacenado remoto se realiza con algunos parámetros pasados por nombre y otros pasados por posición.</span><span class="sxs-lookup"><span data-stu-id="34973-124">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="34973-125">Sigue llamándose al controlador SRV_RPC, pero parece como si no hubiera ningún parámetro y **srv_rpcparams** devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="34973-125">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="34973-126">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="34973-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="34973-127">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="34973-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34973-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34973-128">See Also</span></span>  
 [<span data-ttu-id="34973-129">srv_rpcparams &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="34973-129">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
