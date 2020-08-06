---
title: srv_got_attention (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_got_attention
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_got_attention
ms.assetid: 805e68e1-d17f-41bd-8b9f-a27283bb6fbe
author: rothja
ms.author: jroth
ms.openlocfilehash: bb5432e2f5e259187e506237842fbb9110e27a69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751038"
---
# <a name="srv_got_attention-extended-stored-procedure-api"></a><span data-ttu-id="967bc-102">srv_got_attention (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="967bc-102">srv_got_attention (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="967bc-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="967bc-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="967bc-104">Comprueba si es necesario anular la conexión o tarea actual y devuelve TRUE si se cancela la conexión o se anula el lote.</span><span class="sxs-lookup"><span data-stu-id="967bc-104">Checks whether the current connection or task needs to be aborted and returns TRUE if the connection is killed or the batch is aborted</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="967bc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="967bc-105">Syntax</span></span>  
  
```  
  
BOOL srv_got_attention  
(SRV_PROC *  
srvproc  
);  
  
```  
  
#### <a name="parameters"></a><span data-ttu-id="967bc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="967bc-106">Parameters</span></span>  
 <span data-ttu-id="967bc-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="967bc-107">*srvproc*</span></span>  
 <span data-ttu-id="967bc-108">Puntero que identifica una conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="967bc-108">Pointer identifying a database connection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="967bc-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="967bc-109">Return Value</span></span>  
 <span data-ttu-id="967bc-110">TRUE si se cancela la conexión o se anula el lote.</span><span class="sxs-lookup"><span data-stu-id="967bc-110">TRUE if the connection is killed or the batch is aborted.</span></span> <span data-ttu-id="967bc-111">FALSE si la conexión o el lote están activos.</span><span class="sxs-lookup"><span data-stu-id="967bc-111">FALSE if the connection or batch is active.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="967bc-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="967bc-112">Remarks</span></span>  
 <span data-ttu-id="967bc-113">Un procedimiento almacenado extendido de ejecución prolongada debe comprobar la atención del servidor al llamar periódicamente a **srv_got_attention** para que el procedimiento termine automáticamente cuando se cancele la conexión o se anule el lote.</span><span class="sxs-lookup"><span data-stu-id="967bc-113">A long-running extended stored procedure should check the server attention by calling **srv_got_attention** periodically so that the procedure may terminate itself when the connection is killed or the batch is aborted.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="967bc-114">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="967bc-114">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="967bc-115">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="967bc-115">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
