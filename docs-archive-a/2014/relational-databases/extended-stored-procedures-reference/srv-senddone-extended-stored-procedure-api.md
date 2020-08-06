---
title: srv_senddone (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_senddone
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_senddone
ms.assetid: 1fc4f1d5-56d4-43f6-b5e4-0c0cc295cba3
author: rothja
ms.author: jroth
ms.openlocfilehash: 877acdc1b666c7f4cbaab737590a1c55e474eb05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752137"
---
# <a name="srv_senddone-extended-stored-procedure-api"></a><span data-ttu-id="57f54-102">srv_senddone (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="57f54-102">srv_senddone (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="57f54-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="57f54-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="57f54-104">Envía un mensaje de finalización del resultado al cliente.</span><span class="sxs-lookup"><span data-stu-id="57f54-104">Sends a result completion message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57f54-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57f54-105">Syntax</span></span>  
  
```  
  
int srv_senddone (  
SRV_PROC *  
srvproc  
,  
DBUSMALLINT   
status  
,  
DBUSMALLINT  
info  
,  
DBINT  
count   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="57f54-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="57f54-106">Arguments</span></span>  
 <span data-ttu-id="57f54-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="57f54-107">*srvproc*</span></span>  
 <span data-ttu-id="57f54-108">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió la solicitud de idioma).</span><span class="sxs-lookup"><span data-stu-id="57f54-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="57f54-109">La estructura contiene información que la biblioteca de API Procedimiento almacenado extendido utiliza para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="57f54-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="57f54-110">*status*</span><span class="sxs-lookup"><span data-stu-id="57f54-110">*status*</span></span>  
 <span data-ttu-id="57f54-111">Es un campo de 2 bytes para varias marcas *status* .</span><span class="sxs-lookup"><span data-stu-id="57f54-111">Is a 2-byte field for various *status* flags.</span></span> <span data-ttu-id="57f54-112">Varias marcas se pueden establecer mediante los operadores lógicos AND y OR con valores de marca *status* .</span><span class="sxs-lookup"><span data-stu-id="57f54-112">Multiple flags can be set by using the AND and OR logical operators with *status* flag values.</span></span> <span data-ttu-id="57f54-113">En la tabla siguiente se enumeran las marcas posibles *status* .</span><span class="sxs-lookup"><span data-stu-id="57f54-113">The following table lists possible *status* flags.</span></span>  
  
|<span data-ttu-id="57f54-114">Marca de estado</span><span class="sxs-lookup"><span data-stu-id="57f54-114">Status flag</span></span>|<span data-ttu-id="57f54-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="57f54-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="57f54-116">SRV_DONE_COUNT</span><span class="sxs-lookup"><span data-stu-id="57f54-116">SRV_DONE_COUNT</span></span>|<span data-ttu-id="57f54-117">El parámetro *count* contiene un recuento válido.</span><span class="sxs-lookup"><span data-stu-id="57f54-117">The *count* parameter contains a valid count.</span></span>|  
|<span data-ttu-id="57f54-118">SRV_DONE_ERROR</span><span class="sxs-lookup"><span data-stu-id="57f54-118">SRV_DONE_ERROR</span></span>|<span data-ttu-id="57f54-119">El comando de cliente actual recibió un error.</span><span class="sxs-lookup"><span data-stu-id="57f54-119">The current client command received an error.</span></span>|  
  
 <span data-ttu-id="57f54-120">*info*</span><span class="sxs-lookup"><span data-stu-id="57f54-120">*info*</span></span>  
 <span data-ttu-id="57f54-121">Es un campo reservado de 2 bytes.</span><span class="sxs-lookup"><span data-stu-id="57f54-121">Is a reserved, 2-byte field.</span></span> <span data-ttu-id="57f54-122">Establezca este valor en 0.</span><span class="sxs-lookup"><span data-stu-id="57f54-122">Set this value to 0.</span></span>  
  
 <span data-ttu-id="57f54-123">*count*</span><span class="sxs-lookup"><span data-stu-id="57f54-123">*count*</span></span>  
 <span data-ttu-id="57f54-124">Es un campo de 4 bytes que se usa para indicar un recuento para el conjunto de resultados actual.</span><span class="sxs-lookup"><span data-stu-id="57f54-124">Is a 4-byte field used to indicate a count for the current result set.</span></span> <span data-ttu-id="57f54-125">Si la marca SRV_DONE_COUNT se establece en el campo *status* , *count* contiene un recuento válido.</span><span class="sxs-lookup"><span data-stu-id="57f54-125">If the SRV_DONE_COUNT flag is set in the *status* field, *count* holds a valid count.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="57f54-126">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="57f54-126">Returns</span></span>  
 <span data-ttu-id="57f54-127">SUCCEED o FAIL</span><span class="sxs-lookup"><span data-stu-id="57f54-127">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57f54-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="57f54-128">Remarks</span></span>  
 <span data-ttu-id="57f54-129">Una solicitud de cliente puede ocasionar que el servidor ejecute varios comandos y que devuelva varios conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="57f54-129">A client request can cause the server to execute a number of commands and to return a number of result sets.</span></span> <span data-ttu-id="57f54-130">Para cada conjunto de resultados, **srv_senddone** debe devolver un mensaje de finalización del resultado al cliente.</span><span class="sxs-lookup"><span data-stu-id="57f54-130">For each result set, **srv_senddone** must return a result completion message to the client.</span></span>  
  
 <span data-ttu-id="57f54-131">El campo *count* indica el número de filas afectadas por un comando.</span><span class="sxs-lookup"><span data-stu-id="57f54-131">The *count* field indicates the number of rows affected by a command.</span></span> <span data-ttu-id="57f54-132">Si el campo *count* contiene un recuento, la marca SRV_DONE_COUNT se debería establecer en el campo *status* .</span><span class="sxs-lookup"><span data-stu-id="57f54-132">If the *count* field contains a count, the SRV_DONE_COUNT flag should be set in the *status* field.</span></span> <span data-ttu-id="57f54-133">Este valor permite al cliente distinguir entre un valor *count* de 0 y un campo *count* no usado.</span><span class="sxs-lookup"><span data-stu-id="57f54-133">This setting allows the client to distinguish between a *count* value of 0 and an unused *count* field.</span></span>  
  
 <span data-ttu-id="57f54-134">No llame a **srv_senddone** desde el controlador SRV_CONNECT.</span><span class="sxs-lookup"><span data-stu-id="57f54-134">Do not call **srv_senddone** from the SRV_CONNECT handler.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="57f54-135">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="57f54-135">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="57f54-136">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="57f54-136">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
