---
title: srv_pfieldex (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_pfieldex
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_pfieldex
ms.assetid: d4e9a34b-b3a3-434f-8556-768bd20d145a
author: rothja
ms.author: jroth
ms.openlocfilehash: a474eafcb6b6d42161a7e67ce7f93636269c46c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670386"
---
# <a name="srv_pfieldex-extended-stored-procedure-api"></a><span data-ttu-id="f5474-102">srv_pfieldex (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="f5474-102">srv_pfieldex (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="f5474-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f5474-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="f5474-104">Devuelve un puntero a los datos que contienen el campo SRV_PROC solicitado.</span><span class="sxs-lookup"><span data-stu-id="f5474-104">Returns a pointer to data containing the requested SRV_PROC field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5474-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5474-105">Syntax</span></span>  
  
```  
  
void *srv_pfieldex(SRV_PROC *   
srvproc  
, int   
field  
, int *   
len  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="f5474-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f5474-106">Arguments</span></span>  
 <span data-ttu-id="f5474-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="f5474-107">*srvproc*</span></span>  
 <span data-ttu-id="f5474-108">Es un puntero a la estructura SRV_PROC que es el identificador de una conexión cliente determinada.</span><span class="sxs-lookup"><span data-stu-id="f5474-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="f5474-109">La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="f5474-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="f5474-110">*campo*</span><span class="sxs-lookup"><span data-stu-id="f5474-110">*field*</span></span>  
 <span data-ttu-id="f5474-111">Especifica el campo *srvproc* que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="f5474-111">Specifies the *srvproc* field to return.</span></span>  
  
|<span data-ttu-id="f5474-112">Campo</span><span class="sxs-lookup"><span data-stu-id="f5474-112">Field</span></span>|<span data-ttu-id="f5474-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5474-113">Description</span></span>|<span data-ttu-id="f5474-114">Tipo devuelto</span><span class="sxs-lookup"><span data-stu-id="f5474-114">Return-type</span></span>|  
|-----------|-----------------|------------------|  
|<span data-ttu-id="f5474-115">SRV_MSGLCID</span><span class="sxs-lookup"><span data-stu-id="f5474-115">SRV_MSGLCID</span></span>|<span data-ttu-id="f5474-116">LCID de mensaje de la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="f5474-116">Current session message LCID.</span></span>|<span data-ttu-id="f5474-117">ULONG\*</span><span class="sxs-lookup"><span data-stu-id="f5474-117">ULONG\*</span></span>|  
|<span data-ttu-id="f5474-118">SRV_INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="f5474-118">SRV_INSTANCENAME</span></span>|<span data-ttu-id="f5474-119">Nombre de instancia (si tiene nombre); de lo contrario, devuelve NULL.</span><span class="sxs-lookup"><span data-stu-id="f5474-119">Instance name (if named); otherwise, returns NULL.</span></span>|<span data-ttu-id="f5474-120">WCHAR\*</span><span class="sxs-lookup"><span data-stu-id="f5474-120">WCHAR\*</span></span>|  
  
 <span data-ttu-id="f5474-121">*terminado*</span><span class="sxs-lookup"><span data-stu-id="f5474-121">*len*</span></span>  
 <span data-ttu-id="f5474-122">Es un puntero a una variable **int** que contiene la longitud del valor *field* devuelto en bytes.</span><span class="sxs-lookup"><span data-stu-id="f5474-122">Is a pointer to an **int** variable that contains the length of the returned *field* value in bytes.</span></span> <span data-ttu-id="f5474-123">Si *len* es NULL, no se devuelve la longitud.</span><span class="sxs-lookup"><span data-stu-id="f5474-123">If *len* is NULL, the length is not returned.</span></span> <span data-ttu-id="f5474-124">Cuando se devuelve NULL \**len* se establece en 0.</span><span class="sxs-lookup"><span data-stu-id="f5474-124">When NULL is returned \**len* is set to 0.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="f5474-125">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="f5474-125">Returns</span></span>  
 <span data-ttu-id="f5474-126">Un puntero a los datos cuyo tipo depende de *field*.</span><span class="sxs-lookup"><span data-stu-id="f5474-126">A pointer to data whose type depends on *field*.</span></span> <span data-ttu-id="f5474-127">Se devuelve NULL cuando *len* o *srvproc* son NULL.</span><span class="sxs-lookup"><span data-stu-id="f5474-127">NULL is returned when *len* is NULL or *srvproc* is NULL.</span></span> <span data-ttu-id="f5474-128">Si *field* es desconocido, se devuelve NULL.</span><span class="sxs-lookup"><span data-stu-id="f5474-128">If the *field* is unknown, NULL is returned.</span></span> <span data-ttu-id="f5474-129">Cuando se devuelve NULL \**len* se establece en 0.</span><span class="sxs-lookup"><span data-stu-id="f5474-129">When NULL is returned \**len* is set to 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f5474-130">El búfer que se devuelve desde el servidor debe ser de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f5474-130">The buffer returned from the server should be read only.</span></span> <span data-ttu-id="f5474-131">Si no es así, es posible que el estado del servidor esté dañado.</span><span class="sxs-lookup"><span data-stu-id="f5474-131">Otherwise, the server state may be corrupted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5474-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f5474-132">Remarks</span></span>  
 <span data-ttu-id="f5474-133">**Nota de seguridad** Debe revisar cuidadosamente el código fuente de los procedimientos almacenados extendidos y probar las DLL compiladas antes de instalarlas en un servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="f5474-133">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="f5474-134">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="f5474-134">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
