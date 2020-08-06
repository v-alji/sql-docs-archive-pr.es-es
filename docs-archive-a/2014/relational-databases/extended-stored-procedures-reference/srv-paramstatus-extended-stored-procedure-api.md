---
title: srv_paramstatus (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramstatus
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramstatus
ms.assetid: 86cecd45-0b09-42e9-8152-32a12a1c2b7a
author: rothja
ms.author: jroth
ms.openlocfilehash: d89d4ccbb6a97ff47669ad4ed9c0b4c22ac934eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744078"
---
# <a name="srv_paramstatus-extended-stored-procedure-api"></a><span data-ttu-id="26f90-102">srv_paramstatus (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="26f90-102">srv_paramstatus (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="26f90-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="26f90-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="26f90-104">Devuelve el estado de un parámetro de llamada a un procedimiento almacenado remoto determinado.</span><span class="sxs-lookup"><span data-stu-id="26f90-104">Returns the status of a particular remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26f90-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26f90-105">Syntax</span></span>  
  
```  
  
int srv_paramstatus (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="26f90-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="26f90-106">Arguments</span></span>  
 <span data-ttu-id="26f90-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="26f90-107">*srvproc*</span></span>  
 <span data-ttu-id="26f90-108">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió la llamada al procedimiento almacenado remoto).</span><span class="sxs-lookup"><span data-stu-id="26f90-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="26f90-109">La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="26f90-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="26f90-110">*n*</span><span class="sxs-lookup"><span data-stu-id="26f90-110">*n*</span></span>  
 <span data-ttu-id="26f90-111">Indica el número del parámetro.</span><span class="sxs-lookup"><span data-stu-id="26f90-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="26f90-112">El primer parámetro es número 1.</span><span class="sxs-lookup"><span data-stu-id="26f90-112">The first parameter is number 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="26f90-113">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="26f90-113">Returns</span></span>  
 <span data-ttu-id="26f90-114">Un `int` que contiene marcas de estado para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="26f90-114">An `int` that contains status flags for the parameter.</span></span> <span data-ttu-id="26f90-115">Actualmente solo hay una marca: si el bit 0 está establecido en 1, el parámetro es un parámetro de retorno.</span><span class="sxs-lookup"><span data-stu-id="26f90-115">Currently, there is only one flag: If bit 0 is set to 1, the parameter is a return parameter.</span></span> <span data-ttu-id="26f90-116">Si no existe ningún parámetro *n* o no hay ningún procedimiento almacenado remoto, devuelve -1.</span><span class="sxs-lookup"><span data-stu-id="26f90-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26f90-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="26f90-117">Remarks</span></span>  
 <span data-ttu-id="26f90-118">Esta rutina devuelve las marcas de estado de un parámetro de llamada a un procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="26f90-118">This routine returns the status flags for a remote stored procedure call parameter.</span></span>  
  
 <span data-ttu-id="26f90-119">Los parámetros contienen datos que se pasan entre los clientes y la aplicación con procedimientos almacenados remotos.</span><span class="sxs-lookup"><span data-stu-id="26f90-119">Parameters contain data passed between clients and the application with remote stored procedures.</span></span> <span data-ttu-id="26f90-120">El cliente puede especificar ciertos parámetros como parámetros de retorno.</span><span class="sxs-lookup"><span data-stu-id="26f90-120">The client can specify certain parameters as return parameters.</span></span> <span data-ttu-id="26f90-121">Estos parámetros de retorno pueden contener valores que la aplicación devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="26f90-121">These return parameters can contain values that the application passes back to the client.</span></span>  
  
 <span data-ttu-id="26f90-122">Actualmente, la única marca de estado es una que indica si el parámetro es un parámetro de retorno.</span><span class="sxs-lookup"><span data-stu-id="26f90-122">Currently, the only status flag is one that indicates whether the parameter is a return parameter.</span></span>  
  
 <span data-ttu-id="26f90-123">Cuando se usan parámetros en una llamada a un procedimiento almacenado remoto, estos pueden pasarse por nombre o por posición (sin nombre).</span><span class="sxs-lookup"><span data-stu-id="26f90-123">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="26f90-124">Se produce un error si la llamada al procedimiento almacenado remoto se realiza con algunos parámetros pasados por nombre y otros pasados por posición.</span><span class="sxs-lookup"><span data-stu-id="26f90-124">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="26f90-125">Si se produce un error, se sigue llamando al controlador de SRV_RPC, pero aparece como si no hubiera ningún parámetro y **srv_rpcparams** devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="26f90-125">If an error occurs, the SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="26f90-126">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="26f90-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="26f90-127">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="26f90-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26f90-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26f90-128">See Also</span></span>  
 [<span data-ttu-id="26f90-129">srv_rpcparams &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="26f90-129">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
