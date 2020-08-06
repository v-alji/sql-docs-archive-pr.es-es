---
title: srv_rpcoptions (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcoptions
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcoptions
ms.assetid: dbcce5d1-d5a1-4379-9597-04e43af5923d
author: rothja
ms.author: jroth
ms.openlocfilehash: f5ebe4ab48721002e679ce149293b474a934e348
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752146"
---
# <a name="srv_rpcoptions-extended-stored-procedure-api"></a><span data-ttu-id="87b31-102">srv_rpcoptions (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="87b31-102">srv_rpcoptions (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="87b31-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="87b31-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="87b31-104">Devuelve las opciones de tiempo de ejecución para el procedimiento almacenado remoto actual.</span><span class="sxs-lookup"><span data-stu-id="87b31-104">Returns run-time options for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87b31-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87b31-105">Syntax</span></span>  
  
```  
  
DBUSMALLINT srv_rpcoptions ( SRV_PROC *  
srvproc   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="87b31-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="87b31-106">Arguments</span></span>  
 <span data-ttu-id="87b31-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="87b31-107">*srvproc*</span></span>  
 <span data-ttu-id="87b31-108">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió el procedimiento almacenado remoto).</span><span class="sxs-lookup"><span data-stu-id="87b31-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="87b31-109">La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="87b31-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="87b31-110">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="87b31-110">Returns</span></span>  
 <span data-ttu-id="87b31-111">Un mapa de bits que contiene las marcas en tiempo de ejecución combinadas en un OR lógico para el procedimiento almacenado remoto actual.</span><span class="sxs-lookup"><span data-stu-id="87b31-111">A bitmap that contains the run-time flags joined in a logical OR for the current remote stored procedure.</span></span> <span data-ttu-id="87b31-112">Si no hay un procedimiento almacenado remoto actual, se devuelve 0 y se genera un mensaje.</span><span class="sxs-lookup"><span data-stu-id="87b31-112">If there is not a current remote stored procedure, 0 is returned and a message is generated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87b31-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="87b31-113">Remarks</span></span>  
 <span data-ttu-id="87b31-114">En la tabla siguiente se describen las marcas de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="87b31-114">The following table describes each run-time flag.</span></span>  
  
|<span data-ttu-id="87b31-115">Marca de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="87b31-115">Run-time flag</span></span>|<span data-ttu-id="87b31-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="87b31-116">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="87b31-117">SRV_NOMETADATA</span><span class="sxs-lookup"><span data-stu-id="87b31-117">SRV_NOMETADATA</span></span>|<span data-ttu-id="87b31-118">El cliente ha solicitado resultados sin información de metadatos.</span><span class="sxs-lookup"><span data-stu-id="87b31-118">The client has requested results without metadata information.</span></span> <span data-ttu-id="87b31-119">Esta marca solo se utiliza cuando el cliente se está comunicando con una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="87b31-119">This flag is only used when the client is communicating with an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="87b31-120">Una aplicación API de procedimiento almacenado extendido no puede omitir información de metadatos.</span><span class="sxs-lookup"><span data-stu-id="87b31-120">An Extended Stored Procedure API application cannot omit metadata information.</span></span>|  
|<span data-ttu-id="87b31-121">SRV_RECOMPILE</span><span class="sxs-lookup"><span data-stu-id="87b31-121">SRV_RECOMPILE</span></span>|<span data-ttu-id="87b31-122">El cliente ha solicitado volver a compilar el procedimiento almacenado remoto antes de ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="87b31-122">The client has requested to recompile the remote stored procedure before executing it.</span></span> <span data-ttu-id="87b31-123">Esta marca no se puede aplicar a una aplicación API de procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="87b31-123">This flag may not apply to an Extended Stored Procedure API application.</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="87b31-124">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="87b31-124">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="87b31-125">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="87b31-125">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
