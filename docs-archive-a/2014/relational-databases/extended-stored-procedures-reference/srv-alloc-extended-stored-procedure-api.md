---
title: srv_alloc (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_alloc
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_alloc
ms.assetid: 91505c59-a273-452f-b71d-5e8205c21863
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b372c1b43987e5bebd1fb82e995dc6d262455ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670391"
---
# <a name="srv_alloc-extended-stored-procedure-api"></a><span data-ttu-id="c4c9b-102">srv_alloc (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="c4c9b-102">srv_alloc (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="c4c9b-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c4c9b-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="c4c9b-104">Asigna la memoria de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="c4c9b-104">Allocates memory dynamically.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4c9b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4c9b-105">Syntax</span></span>  
  
```  
  
void * srv_alloc ( DBINT  
size  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c4c9b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c4c9b-106">Arguments</span></span>  
 <span data-ttu-id="c4c9b-107">*size*</span><span class="sxs-lookup"><span data-stu-id="c4c9b-107">*size*</span></span>  
 <span data-ttu-id="c4c9b-108">Especifica el número de bytes para asignar.</span><span class="sxs-lookup"><span data-stu-id="c4c9b-108">Specifies the number of bytes to allocate.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c4c9b-109">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="c4c9b-109">Returns</span></span>  
 <span data-ttu-id="c4c9b-110">Un puntero al el espacio asignado más reciente.</span><span class="sxs-lookup"><span data-stu-id="c4c9b-110">A pointer to the newly allocated space.</span></span> <span data-ttu-id="c4c9b-111">Si no se pueden asignar *size* bytes, se devuelve un puntero nulo.</span><span class="sxs-lookup"><span data-stu-id="c4c9b-111">If *size* bytes cannot be allocated, a null pointer is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4c9b-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c4c9b-112">Remarks</span></span>  
 <span data-ttu-id="c4c9b-113">La función **srv_alloc** es equivalente a la función **GlobalAlloc** de la API de [!INCLUDE[msCoName](../../includes/msconame-md.md)]Windows.</span><span class="sxs-lookup"><span data-stu-id="c4c9b-113">The **srv_alloc** function is equivalent to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows API  **GlobalAlloc** function.</span></span> <span data-ttu-id="c4c9b-114">Las funciones normales de administración de memoria en tiempo de ejecución de la API de Windows C, se pueden usar en una aplicación API de procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="c4c9b-114">Normal Windows API C run-time memory management functions can be used in an Extended Stored Procedure API application.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c4c9b-115">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="c4c9b-115">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="c4c9b-116">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="c4c9b-116">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
