---
title: srv_sendmsg (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_sendmsg
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_sendmsg
ms.assetid: efcb50b9-f8ff-4121-bf67-05830171b928
author: rothja
ms.author: jroth
ms.openlocfilehash: 0821ad88f48313cfadea634a489def9b242a49f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752133"
---
# <a name="srv_sendmsg-extended-stored-procedure-api"></a><span data-ttu-id="fa1ed-102">srv_sendmsg (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="fa1ed-102">srv_sendmsg (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="fa1ed-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="fa1ed-104">Envía un mensaje al cliente.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-104">Sends a message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa1ed-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa1ed-105">Syntax</span></span>  
  
```  
  
int srv_sendmsg (  
SRV_PROC *  
srvproc  
,  
int  
msgtype  
,  
DBINT  
msgnum  
,  
DBTINYINT  
class  
,   
DBTINYINT  
state  
,  
DBCHAR *  
rpcname  
,  
int   
rpcnamelen  
,  
DBUSMALLINT  
linenum  
,  
DBCHAR *  
message  
,  
int  
msglen   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="fa1ed-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fa1ed-106">Arguments</span></span>  
 <span data-ttu-id="fa1ed-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="fa1ed-107">*srvproc*</span></span>  
 <span data-ttu-id="fa1ed-108">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió la solicitud de idioma).</span><span class="sxs-lookup"><span data-stu-id="fa1ed-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="fa1ed-109">La estructura contiene información que la biblioteca de API Procedimiento almacenado extendido utiliza para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="fa1ed-110">*msgtype*</span><span class="sxs-lookup"><span data-stu-id="fa1ed-110">*msgtype*</span></span>  
 <span data-ttu-id="fa1ed-111">Es SRV_MSG_INFO o SRV_MSG_ERROR, dependiendo de si el servidor está enviando un mensaje informativo o de error.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-111">Is either SRV_MSG_INFO or SRV_MSG_ERROR, depending on whether the server is sending an informational or error message.</span></span>  
  
 <span data-ttu-id="fa1ed-112">*msgnum*</span><span class="sxs-lookup"><span data-stu-id="fa1ed-112">*msgnum*</span></span>  
 <span data-ttu-id="fa1ed-113">Es un número de mensaje de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-113">Is a 4-byte message number.</span></span>  
  
 <span data-ttu-id="fa1ed-114">*class*</span><span class="sxs-lookup"><span data-stu-id="fa1ed-114">*class*</span></span>  
 <span data-ttu-id="fa1ed-115">Especifica la gravedad del error.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-115">Specifies the error severity.</span></span> <span data-ttu-id="fa1ed-116">Una gravedad menor o igual a 10 se considera un mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-116">A severity less than or equal to 10 is considered an informational message.</span></span>  
  
 <span data-ttu-id="fa1ed-117">*state*</span><span class="sxs-lookup"><span data-stu-id="fa1ed-117">*state*</span></span>  
 <span data-ttu-id="fa1ed-118">Proporciona el número de estado de error para el mensaje actual.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-118">Provides the error state number for the current message.</span></span> <span data-ttu-id="fa1ed-119">El número de estado de error proporciona información sobre el contexto del error.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-119">The error state number provides information about the context of the error.</span></span> <span data-ttu-id="fa1ed-120">Los números de estado van de 0 a 255.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-120">Valid state numbers are from 0 through 255.</span></span>  
  
 <span data-ttu-id="fa1ed-121">*rpcname*</span><span class="sxs-lookup"><span data-stu-id="fa1ed-121">*rpcname*</span></span>  
 <span data-ttu-id="fa1ed-122">No se admite actualmente.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-122">Is currently not supported.</span></span>  
  
 <span data-ttu-id="fa1ed-123">*rpcnamelen*</span><span class="sxs-lookup"><span data-stu-id="fa1ed-123">*rpcnamelen*</span></span>  
 <span data-ttu-id="fa1ed-124">No se admite actualmente.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-124">Is currently not supported.</span></span>  
  
 <span data-ttu-id="fa1ed-125">*ropa*</span><span class="sxs-lookup"><span data-stu-id="fa1ed-125">*linenum*</span></span>  
 <span data-ttu-id="fa1ed-126">Es el número de línea en el lote de comandos del lenguaje donde se aplica el mensaje.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-126">Is the line number in the language command batch where the message applies.</span></span> <span data-ttu-id="fa1ed-127">Los números de línea empiezan por 1.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-127">Line numbers start at 1.</span></span> <span data-ttu-id="fa1ed-128">Si *linenum* no se aplica al mensaje, se establece en 0.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-128">If *linenum* does not apply to the message, set to 0.</span></span>  
  
 <span data-ttu-id="fa1ed-129">*message*</span><span class="sxs-lookup"><span data-stu-id="fa1ed-129">*message*</span></span>  
 <span data-ttu-id="fa1ed-130">Es un puntero a una cadena de caracteres que se va a enviar al cliente.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-130">Is a pointer to the character string to be sent to the client.</span></span>  
  
 <span data-ttu-id="fa1ed-131">*msglen*</span><span class="sxs-lookup"><span data-stu-id="fa1ed-131">*msglen*</span></span>  
 <span data-ttu-id="fa1ed-132">Especifica la longitud en bytes de *message*.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-132">Specifies the length, in bytes, of *message*.</span></span> <span data-ttu-id="fa1ed-133">Si *message* está terminado en null, establezca *msglen* en SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-133">If *message* is null-terminated, set *msglen* to SRV_NULLTERM.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="fa1ed-134">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="fa1ed-134">Returns</span></span>  
 <span data-ttu-id="fa1ed-135">SUCCEED o FAIL</span><span class="sxs-lookup"><span data-stu-id="fa1ed-135">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa1ed-136">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fa1ed-136">Remarks</span></span>  
 <span data-ttu-id="fa1ed-137">Esta función envía mensajes de error o informativos al cliente.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-137">This function sends error or informational messages to the client.</span></span> <span data-ttu-id="fa1ed-138">Se llama una vez por cada mensaje que se va a enviar.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-138">It is called once for each message to be sent.</span></span>  
  
 <span data-ttu-id="fa1ed-139">Los mensajes se pueden enviar al cliente con **srv_sendmsg** en cualquier orden antes o después de haber enviado todas las filas (si las hubiera) con **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-139">Messages can be sent to the client with **srv_sendmsg** in any order before or after all rows (if any) have been sent with **srv_sendrow**.</span></span> <span data-ttu-id="fa1ed-140">Todos los mensajes, si los hubiera, se deben enviar al cliente antes de enviar el estado de finalización con **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-140">All messages, if any, must be sent to the client before the completion status is sent with **srv_senddone**.</span></span>  
  
 <span data-ttu-id="fa1ed-141">Para enviar mensajes en Unicode, use **srv_wsendmsg** en lugar de **srv_sendmsg**.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-141">To send messages in Unicode, use **srv_wsendmsg** rather than **srv_sendmsg**.</span></span>  
  
 <span data-ttu-id="fa1ed-142">Para más información, vea [Datos Unicode y páginas de códigos de servidor](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="fa1ed-142">For more information see [Unicode Data and Server Code Pages](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fa1ed-143">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="fa1ed-143">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="fa1ed-144">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="fa1ed-144">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
