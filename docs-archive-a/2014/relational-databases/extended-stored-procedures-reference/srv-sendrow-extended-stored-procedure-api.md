---
title: srv_sendrow (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_sendrow
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_sendrow
ms.assetid: a08f608a-10e6-4bff-9b48-0d02e8026cdb
author: rothja
ms.author: jroth
ms.openlocfilehash: df40348b8792a70f84719abfb42152fda9487e6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752130"
---
# <a name="srv_sendrow-extended-stored-procedure-api"></a><span data-ttu-id="ce0b0-102">srv_sendrow (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="ce0b0-102">srv_sendrow (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="ce0b0-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ce0b0-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="ce0b0-104">Transmite una fila de datos al cliente.</span><span class="sxs-lookup"><span data-stu-id="ce0b0-104">Transmits a row of data to the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce0b0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce0b0-105">Syntax</span></span>  
  
```  
  
int srv_sendrow ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="ce0b0-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ce0b0-106">Arguments</span></span>  
 <span data-ttu-id="ce0b0-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="ce0b0-107">*srvproc*</span></span>  
 <span data-ttu-id="ce0b0-108">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió la solicitud de idioma).</span><span class="sxs-lookup"><span data-stu-id="ce0b0-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the language request).</span></span> <span data-ttu-id="ce0b0-109">La estructura contiene información que la biblioteca de API Procedimiento almacenado extendido utiliza para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="ce0b0-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="ce0b0-110">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="ce0b0-110">Returns</span></span>  
 <span data-ttu-id="ce0b0-111">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="ce0b0-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce0b0-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ce0b0-112">Remarks</span></span>  
 <span data-ttu-id="ce0b0-113">Se llama a la función **srv_sendrow** una vez por cada fila enviada al cliente.</span><span class="sxs-lookup"><span data-stu-id="ce0b0-113">The **srv_sendrow** function is called once for each row sent to the client.</span></span> <span data-ttu-id="ce0b0-114">Todas las filas se deben enviar al cliente antes de se envíe cualquier mensaje, valor de estado o estado de finalización con **srv_sendmsg**, **srv_status**o **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="ce0b0-114">All rows must be sent to the client before any messages, status values, or completion statuses are sent with **srv_sendmsg**, **srv_status**, or **srv_senddone**.</span></span>  
  
 <span data-ttu-id="ce0b0-115">El envío de una fila en la que no se han definido todas sus columnas con **srv_describe** hace que la aplicación API Procedimiento almacenado extendido provoque un mensaje de error informativo y devuelva FAIL al cliente.</span><span class="sxs-lookup"><span data-stu-id="ce0b0-115">Sending a row that has not had all its columns defined with **srv_describe** causes the Extended Stored Procedure API application to raise an informational error message and return FAIL to the client.</span></span> <span data-ttu-id="ce0b0-116">En este caso, la fila no se envía.</span><span class="sxs-lookup"><span data-stu-id="ce0b0-116">In this case, the row is not sent.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ce0b0-117">La API Procedimiento almacenado extendido no permite enviar las filas de cálculo al cliente.</span><span class="sxs-lookup"><span data-stu-id="ce0b0-117">The Extended Stored Procedure API does not support sending compute rows to the client.</span></span> <span data-ttu-id="ce0b0-118">Además, si se envía al cliente una fila que contiene datos `ntext`, `text` o `image`, no se incluyen el puntero de texto ni la marca de tiempo del texto.</span><span class="sxs-lookup"><span data-stu-id="ce0b0-118">Also, if a row containing `ntext`, `text`, or `image` data is sent to the client, the text pointer and text timestamp are not included.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ce0b0-119">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="ce0b0-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="ce0b0-120">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="ce0b0-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce0b0-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce0b0-121">See Also</span></span>  
 [<span data-ttu-id="ce0b0-122">srv_describe &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="ce0b0-122">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
