---
title: srv_rpcparams (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcparams
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcparams
ms.assetid: 96a5e6f6-d320-4623-b96e-0a856e3abebb
author: rothja
ms.author: jroth
ms.openlocfilehash: 443b9ea8a67341afdb92f0c384148c8b1b42f752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752138"
---
# <a name="srv_rpcparams-extended-stored-procedure-api"></a><span data-ttu-id="d3a39-102">srv_rpcparams (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="d3a39-102">srv_rpcparams (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="d3a39-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d3a39-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="d3a39-104">Devuelve el número de parámetros del procedimiento almacenado remoto actual.</span><span class="sxs-lookup"><span data-stu-id="d3a39-104">Returns the number of parameters for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3a39-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3a39-105">Syntax</span></span>  
  
```  
  
int srv_rpcparams ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d3a39-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d3a39-106">Arguments</span></span>  
 <span data-ttu-id="d3a39-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="d3a39-107">*srvproc*</span></span>  
 <span data-ttu-id="d3a39-108">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió el procedimiento almacenado remoto).</span><span class="sxs-lookup"><span data-stu-id="d3a39-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="d3a39-109">La estructura contiene información que la biblioteca de API Procedimiento almacenado extendido utiliza para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="d3a39-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d3a39-110">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="d3a39-110">Returns</span></span>  
 <span data-ttu-id="d3a39-111">El número de parámetros en el procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="d3a39-111">The number of parameters in the remote stored procedure.</span></span> <span data-ttu-id="d3a39-112">Si no hay ningún parámetro en el procedimiento almacenado remoto o si no hay un procedimiento almacenado remoto actual, se devuelve -1 y se produce un error de la información.</span><span class="sxs-lookup"><span data-stu-id="d3a39-112">If there are no parameters in the remote stored procedure or if there is not a current remote stored procedure, -1 is returned and an information error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3a39-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d3a39-113">Remarks</span></span>  
 <span data-ttu-id="d3a39-114">Esta función devuelve el número de parámetros en el procedimiento almacenado remoto el actual.</span><span class="sxs-lookup"><span data-stu-id="d3a39-114">This function returns the number of parameters in the current remote stored procedure.</span></span> <span data-ttu-id="d3a39-115">Normalmente se realiza la llamada desde el procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="d3a39-115">It is usually called from the remote stored procedure.</span></span>  
  
 <span data-ttu-id="d3a39-116">Cuando se usan parámetros en una llamada a un procedimiento almacenado remoto, estos pueden pasarse por nombre o por posición (sin nombre).</span><span class="sxs-lookup"><span data-stu-id="d3a39-116">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="d3a39-117">Se producirá un error en la llamada al procedimiento almacenado remoto si algunos parámetros se pasan por nombre y otros por posición.</span><span class="sxs-lookup"><span data-stu-id="d3a39-117">If the remote stored procedure call was made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="d3a39-118">Cuando se produce este error, se llama al controlador del procedimiento almacenado remoto, pero no recibe los parámetros y **srv_rpcparams** devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="d3a39-118">When this error occurs, the remote stored procedure handler is called, but it does not receive the parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d3a39-119">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="d3a39-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="d3a39-120">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="d3a39-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
