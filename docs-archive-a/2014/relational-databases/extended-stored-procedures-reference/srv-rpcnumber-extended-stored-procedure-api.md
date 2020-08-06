---
title: srv_rpcnumber (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcnumber
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcnumber
ms.assetid: 3094085e-fe9e-423d-bf87-7852352c2d26
author: rothja
ms.author: jroth
ms.openlocfilehash: 25f30f8288125cf64d6b10a867d6af03c0f8ee91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751013"
---
# <a name="srv_rpcnumber-extended-stored-procedure-api"></a><span data-ttu-id="196fa-102">srv_rpcnumber (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="196fa-102">srv_rpcnumber (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="196fa-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="196fa-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="196fa-104">Devuelve el componente de nombre de la llamada a procedimiento almacenado remoto actual.</span><span class="sxs-lookup"><span data-stu-id="196fa-104">Returns the number component for the current remote stored procedure call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="196fa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="196fa-105">Syntax</span></span>  
  
```  
  
int srv_rpcnumber ( SRV_PROC *  
srvproc   
)  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="196fa-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="196fa-106">Arguments</span></span>  
 <span data-ttu-id="196fa-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="196fa-107">*srvproc*</span></span>  
 <span data-ttu-id="196fa-108">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió el procedimiento almacenado remoto).</span><span class="sxs-lookup"><span data-stu-id="196fa-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="196fa-109">La estructura contiene información que la biblioteca de API Procedimiento almacenado extendido utiliza para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="196fa-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="196fa-110">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="196fa-110">Returns</span></span>  
 <span data-ttu-id="196fa-111">El componente de número para el procedimiento almacenado remoto actual.</span><span class="sxs-lookup"><span data-stu-id="196fa-111">The number component for the current remote stored procedure.</span></span> <span data-ttu-id="196fa-112">Si el cliente no usa un componente de número al ejecutar el procedimiento almacenado remoto o si no hay ningún procedimiento almacenado remoto actual, devuelve - 1.</span><span class="sxs-lookup"><span data-stu-id="196fa-112">If the client does not use a number component when running the remote stored procedure or if there is no current remote stored procedure, it returns - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="196fa-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="196fa-113">Remarks</span></span>  
 <span data-ttu-id="196fa-114">Esta función únicamente devuelve el componente de número del procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="196fa-114">This function returns only the number component of the remote stored procedure.</span></span> <span data-ttu-id="196fa-115">No incluye los especificadores opcionales propietario, nombre del procedimiento almacenado remoto y nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="196fa-115">It does not include the optional specifiers for owner, remote stored procedure name, and database name.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="196fa-116">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="196fa-116">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="196fa-117">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="196fa-117">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
