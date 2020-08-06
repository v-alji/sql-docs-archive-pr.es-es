---
title: srv_setcoldata (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setcoldata
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setcoldata
ms.assetid: 2e19205a-25ca-4d4a-916b-d591cf2c892b
author: rothja
ms.author: jroth
ms.openlocfilehash: b67aa2f7b5a37057d2ed87846689919d84ec4aaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749325"
---
# <a name="srv_setcoldata-extended-stored-procedure-api"></a><span data-ttu-id="74d73-102">srv_setcoldata (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="74d73-102">srv_setcoldata (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="74d73-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="74d73-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="74d73-104">Especifica la dirección actual para los datos de una columna.</span><span class="sxs-lookup"><span data-stu-id="74d73-104">Specifies the current address for a column's data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74d73-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74d73-105">Syntax</span></span>  
  
```  
  
int srv_setcoldata (  
SRV_PROC *  
srvproc  
,  
int   
column  
,  
void *  
data   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="74d73-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="74d73-106">Arguments</span></span>  
 <span data-ttu-id="74d73-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="74d73-107">*srvproc*</span></span>  
 <span data-ttu-id="74d73-108">Es un puntero a la estructura SRV_PROC que es el identificador de una conexión cliente determinada.</span><span class="sxs-lookup"><span data-stu-id="74d73-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="74d73-109">La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="74d73-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="74d73-110">*column*</span><span class="sxs-lookup"><span data-stu-id="74d73-110">*column*</span></span>  
 <span data-ttu-id="74d73-111">Indica el número de la columna para la que se especificó la dirección.</span><span class="sxs-lookup"><span data-stu-id="74d73-111">Indicates the number of the column the address is being specified for.</span></span> <span data-ttu-id="74d73-112">Las columnas se numeran comenzando por 1.</span><span class="sxs-lookup"><span data-stu-id="74d73-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="74d73-113">*data*</span><span class="sxs-lookup"><span data-stu-id="74d73-113">*data*</span></span>  
 <span data-ttu-id="74d73-114">Es un puntero para los datos de una columna.</span><span class="sxs-lookup"><span data-stu-id="74d73-114">Is a pointer for a column's data.</span></span> <span data-ttu-id="74d73-115">La memoria asignada para *data* no se debería liberar hasta que los datos de la columna se sustituyan por otra llamada a **srv_setcoldata**, o hasta que se realice una llamada a **srv_senddone** .</span><span class="sxs-lookup"><span data-stu-id="74d73-115">Memory allocated for *data* should not be freed until the column data is replaced by another call to **srv_setcoldata**, or until **srv_senddone** is called.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="74d73-116">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="74d73-116">Returns</span></span>  
 <span data-ttu-id="74d73-117">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="74d73-117">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74d73-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="74d73-118">Remarks</span></span>  
 <span data-ttu-id="74d73-119">Cada columna de la fila se debe definir antes con **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="74d73-119">Each column of the row must be defined first with **srv_describe**.</span></span> <span data-ttu-id="74d73-120">Las direcciones de datos de columna se establecen inicialmente con **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="74d73-120">Column data addresses are initially set with **srv_describe**.</span></span> <span data-ttu-id="74d73-121">Si la dirección de datos de columna cambia, se debe llamar a **srv_setcoldata** para especificar la nueva dirección de los datos y se debe llamar a **srv_setcoldata** por separado para cada columna modificada.</span><span class="sxs-lookup"><span data-stu-id="74d73-121">If the address of the column data changes, **srv_setcoldata** must be called to specify the new address of the data and **srv_setcoldata** must be called separately for each changed column.</span></span>  
  
 <span data-ttu-id="74d73-122">Los datos nulos se representan estableciendo la longitud de la columna en 0 con **srv_setcollen**.</span><span class="sxs-lookup"><span data-stu-id="74d73-122">Null data is represented by setting the column's length to 0 with **srv_setcollen**.</span></span> <span data-ttu-id="74d73-123">Entonces, se omite la dirección de datos.</span><span class="sxs-lookup"><span data-stu-id="74d73-123">The data address is then ignored.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="74d73-124">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="74d73-124">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="74d73-125">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="74d73-125">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74d73-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74d73-126">See Also</span></span>  
 [<span data-ttu-id="74d73-127">srv_describe &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="74d73-127">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
