---
title: srv_wsendmsg (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_wsendmsg
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_wsendmsg
ms.assetid: f2153076-32c9-4a52-8e1b-fc9618153543
author: rothja
ms.author: jroth
ms.openlocfilehash: 4cc915cce0befccb5c5af58e703c11b750af855b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751005"
---
# <a name="srv_wsendmsg-extended-stored-procedure-api"></a><span data-ttu-id="84cda-102">srv_wsendmsg (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="84cda-102">srv_wsendmsg (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="84cda-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="84cda-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="84cda-104">Envía un mensaje Unicode al cliente.</span><span class="sxs-lookup"><span data-stu-id="84cda-104">Sends a Unicode message to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84cda-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84cda-105">Syntax</span></span>  
  
```  
  
int srv_wsendmsg(SRV_PROC *   
srvproc  
, int   
msgnum  
, int   
severity  
, WCHAR *   
message  
, int   
msglen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="84cda-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="84cda-106">Arguments</span></span>  
 <span data-ttu-id="84cda-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="84cda-107">*srvproc*</span></span>  
 <span data-ttu-id="84cda-108">Es un puntero a la estructura SRV_PROC que es el identificador de una conexión cliente determinada.</span><span class="sxs-lookup"><span data-stu-id="84cda-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="84cda-109">La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="84cda-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="84cda-110">*Msgnum*</span><span class="sxs-lookup"><span data-stu-id="84cda-110">*Msgnum*</span></span>  
 <span data-ttu-id="84cda-111">Es un número de mensaje de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="84cda-111">Is a 4-byte message number.</span></span>  
  
 <span data-ttu-id="84cda-112">*Gravedad*</span><span class="sxs-lookup"><span data-stu-id="84cda-112">*Severity*</span></span>  
 <span data-ttu-id="84cda-113">Especifica la gravedad del error.</span><span class="sxs-lookup"><span data-stu-id="84cda-113">Specifies the severity of the error.</span></span> <span data-ttu-id="84cda-114">Una gravedad menor o igual que 10 se considera un mensaje informativo; de lo contrario, se considera un error.</span><span class="sxs-lookup"><span data-stu-id="84cda-114">A severity less than or equal to 10 is considered an informational message; otherwise, it is an error.</span></span>  
  
 <span data-ttu-id="84cda-115">*message*</span><span class="sxs-lookup"><span data-stu-id="84cda-115">*message*</span></span>  
 <span data-ttu-id="84cda-116">Es un puntero a una cadena Unicode que se va a enviar al cliente.</span><span class="sxs-lookup"><span data-stu-id="84cda-116">Is a pointer to a Unicode string to be sent to the client.</span></span>  
  
 <span data-ttu-id="84cda-117">*msglen*</span><span class="sxs-lookup"><span data-stu-id="84cda-117">*msglen*</span></span>  
 <span data-ttu-id="84cda-118">Especifica la longitud en caracteres de *message*.</span><span class="sxs-lookup"><span data-stu-id="84cda-118">Specifies the length, in characters, of *message*.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="84cda-119">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="84cda-119">Returns</span></span>  
 <span data-ttu-id="84cda-120">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="84cda-120">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84cda-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="84cda-121">Remarks</span></span>  
 <span data-ttu-id="84cda-122">Utilice esta función para enviar mensajes en Unicode.</span><span class="sxs-lookup"><span data-stu-id="84cda-122">Use this function to send messages in Unicode.</span></span> <span data-ttu-id="84cda-123">Es similar a **srv_sendmsg**, pero el mensaje que envía es una cadena WCHAR en lugar de una cadena de tipo DBCHAR.</span><span class="sxs-lookup"><span data-stu-id="84cda-123">It is similar to **srv_sendmsg**, but the message it sends is a WCHAR string rather than type DBCHAR string.</span></span> <span data-ttu-id="84cda-124">Tenga en cuenta que la longitud del mensaje se indica en caracteres en lugar de en bytes y que *msglen* nunca será igual a SRV_NULLTERM.</span><span class="sxs-lookup"><span data-stu-id="84cda-124">Note that message length is reported in characters rather than bytes, and *msglen* will never be equal to SRV_NULLTERM.</span></span>  
  
 <span data-ttu-id="84cda-125">La función devuelve FAIL cuando</span><span class="sxs-lookup"><span data-stu-id="84cda-125">The function returns FAIL when</span></span>  
  
-   <span data-ttu-id="84cda-126">El argumento *msglen* proporcionado no está comprendido en el intervalo de 0 a 32242.</span><span class="sxs-lookup"><span data-stu-id="84cda-126">The *msglen* given is not in the range of 0-32242.</span></span>  
  
-   <span data-ttu-id="84cda-127">El argumento *msglen* proporcionado es 0 pero el puntero del mensaje es NULL.</span><span class="sxs-lookup"><span data-stu-id="84cda-127">The *msglen* given is 0 but the message pointer is NULL.</span></span>  
  
-   <span data-ttu-id="84cda-128">Se produce un error al enviar el mensaje de error a través de la red.</span><span class="sxs-lookup"><span data-stu-id="84cda-128">There is error when sending the error message through network.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="84cda-129">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="84cda-129">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="84cda-130">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="84cda-130">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84cda-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84cda-131">See Also</span></span>  
 [<span data-ttu-id="84cda-132">srv_sendmsg &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="84cda-132">srv_sendmsg &#40;Extended Stored Procedure API&#41;</span></span>](srv-sendmsg-extended-stored-procedure-api.md)  
  
  
