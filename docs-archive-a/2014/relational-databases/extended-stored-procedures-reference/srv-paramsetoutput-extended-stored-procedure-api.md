---
title: srv_paramsetoutput (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramsetoutput
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramsetoutput
ms.assetid: f2810e19-e513-458b-8925-5756b6ee1313
author: rothja
ms.author: jroth
ms.openlocfilehash: 2847367fe5d6052728cebf30467b68cb14fb8e63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663480"
---
# <a name="srv_paramsetoutput-extended-stored-procedure-api"></a><span data-ttu-id="d1552-102">srv_paramsetoutput (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="d1552-102">srv_paramsetoutput (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="d1552-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d1552-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="d1552-104">Establece el valor de un parámetro de devolución.</span><span class="sxs-lookup"><span data-stu-id="d1552-104">Sets the value of a return parameter.</span></span> <span data-ttu-id="d1552-105">Esta función reemplaza a **srv_paramset**.</span><span class="sxs-lookup"><span data-stu-id="d1552-105">This function supersedes the **srv_paramset** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1552-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1552-106">Syntax</span></span>  
  
```  
  
int srv_paramsetoutput (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbData  
,  
ULONG   
cbLen  
,  
BOOL  
fNull   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d1552-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d1552-107">Arguments</span></span>  
 <span data-ttu-id="d1552-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="d1552-108">*srvproc*</span></span>  
 <span data-ttu-id="d1552-109">Es un identificador de una conexión cliente.</span><span class="sxs-lookup"><span data-stu-id="d1552-109">Is a handle for a client connection.</span></span>  
  
 <span data-ttu-id="d1552-110">*n*</span><span class="sxs-lookup"><span data-stu-id="d1552-110">*n*</span></span>  
 <span data-ttu-id="d1552-111">Es el número ordinal del parámetro que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="d1552-111">Is the ordinal number of the parameter to be set.</span></span> <span data-ttu-id="d1552-112">El primer parámetro es 1.</span><span class="sxs-lookup"><span data-stu-id="d1552-112">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="d1552-113">*pbData*</span><span class="sxs-lookup"><span data-stu-id="d1552-113">*pbData*</span></span>  
 <span data-ttu-id="d1552-114">Es un puntero al valor de datos que se va a devolver al cliente como parámetro de devolución del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d1552-114">Is a pointer to the data value to be sent back to the client as a procedure return parameter.</span></span>  
  
 <span data-ttu-id="d1552-115">*cbLen*</span><span class="sxs-lookup"><span data-stu-id="d1552-115">*cbLen*</span></span>  
 <span data-ttu-id="d1552-116">Es la longitud real de los datos que se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="d1552-116">Is the actual length of the data to be returned.</span></span> <span data-ttu-id="d1552-117">Si el tipo de datos del parámetro especifica valores de una longitud constante y no permite valores null (por ejemplo, *srvbit* o *srvint1*), se omite *cbLen*.</span><span class="sxs-lookup"><span data-stu-id="d1552-117">If the data type of the parameter specifies values of a constant length and does not allow null values (for example, *srvbit* or *srvint1*), *cbLen* is ignored.</span></span> <span data-ttu-id="d1552-118">Un valor de 0 indica datos de longitud cero si *fNull* es FALSE.</span><span class="sxs-lookup"><span data-stu-id="d1552-118">A value of 0 signifies zero-length data if *fNull* is FALSE.</span></span>  
  
 <span data-ttu-id="d1552-119">*fNull*</span><span class="sxs-lookup"><span data-stu-id="d1552-119">*fNull*</span></span>  
 <span data-ttu-id="d1552-120">Es una marca que indica si el valor del parámetro de devolución es NULL.</span><span class="sxs-lookup"><span data-stu-id="d1552-120">Is a flag indicating whether the value of the return parameter is NULL.</span></span> <span data-ttu-id="d1552-121">Establezca esta marca en TRUE si el parámetro debe estar establecido en NULL.</span><span class="sxs-lookup"><span data-stu-id="d1552-121">Set this flag to TRUE if the parameter should be set to NULL.</span></span> <span data-ttu-id="d1552-122">El valor predeterminado es FALSE.</span><span class="sxs-lookup"><span data-stu-id="d1552-122">The default value is FALSE.</span></span> <span data-ttu-id="d1552-123">Si *fNull* está establecido en TRUE, *cbLen* debe establecerse en 0 o se produce un error en la función.</span><span class="sxs-lookup"><span data-stu-id="d1552-123">If *fNull* is set to TRUE, *cbLen* should be set to 0 or the function will fail.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d1552-124">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="d1552-124">Returns</span></span>  
 <span data-ttu-id="d1552-125">Si la información de los parámetros está definida correctamente, se devuelve SUCCEED; de lo contrario, se devuelve FAIL.</span><span class="sxs-lookup"><span data-stu-id="d1552-125">If the parameter information was successfully set, SUCCEED is returned; otherwise, FAIL.</span></span> <span data-ttu-id="d1552-126">FAIL se devuelve cuando</span><span class="sxs-lookup"><span data-stu-id="d1552-126">FAIL is returned when</span></span>  
  
-   <span data-ttu-id="d1552-127">el parámetro no es un parámetro de devolución o</span><span class="sxs-lookup"><span data-stu-id="d1552-127">the parameter is not a return parameter, or</span></span>  
  
-   <span data-ttu-id="d1552-128">el argumento *cbLen* no es válido.</span><span class="sxs-lookup"><span data-stu-id="d1552-128">the *cbLen* argument is invalid.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1552-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d1552-129">Remarks</span></span>  
 <span data-ttu-id="d1552-130">**Nota de seguridad** Debe revisar cuidadosamente el código fuente de los procedimientos almacenados extendidos y probar las DLL compiladas antes de instalarlas en un servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="d1552-130">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="d1552-131">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="d1552-131">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
