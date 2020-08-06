---
title: srv_paraminfo (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paraminfo
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paraminfo
ms.assetid: ee2afd4e-0d91-462b-9403-98d481546330
author: rothja
ms.author: jroth
ms.openlocfilehash: cc3d51acc2ca560246c46267840db72934223999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751037"
---
# <a name="srv_paraminfo-extended-stored-procedure-api"></a><span data-ttu-id="c8e54-102">srv_paraminfo (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="c8e54-102">srv_paraminfo (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="c8e54-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c8e54-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="c8e54-104">Devuelve información sobre un parámetro.</span><span class="sxs-lookup"><span data-stu-id="c8e54-104">Returns information about a parameter.</span></span> <span data-ttu-id="c8e54-105">Esta función reemplaza a las siguientes funciones: [srv_paramtype](srv-paramtype-extended-stored-procedure-api.md), [srv_paramlen](srv-paramlen-extended-stored-procedure-api.md), [srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md) y [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="c8e54-105">This function supersedes the following functions: [srv_paramtype](srv-paramtype-extended-stored-procedure-api.md), [srv_paramlen](srv-paramlen-extended-stored-procedure-api.md), [srv_parammaxlen](srv-parammaxlen-extended-stored-procedure-api.md), and [srv_paramdata](srv-paramdata-extended-stored-procedure-api.md).</span></span> <span data-ttu-id="c8e54-106">**srv_paraminfo** admite los tipos de datos de [Tipos de datos](data-types-extended-stored-procedure-api.md) y datos de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="c8e54-106">**srv_paraminfo** supports the data types in [Data Types](data-types-extended-stored-procedure-api.md) and zero-length data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8e54-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8e54-107">Syntax</span></span>  
  
```  
  
int srv_paraminfo (  
SRV_PROC *  
srvproc  
,  
int  
n  
,  
BYTE *  
pbType  
,  
ULONG *  
pcbMaxLen  
,  
ULONG *  
pcbActualLen  
,  
BYTE *  
pbData  
,  
BOOL *  
pfNull  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c8e54-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c8e54-108">Arguments</span></span>  
 <span data-ttu-id="c8e54-109">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="c8e54-109">*srvproc*</span></span>  
 <span data-ttu-id="c8e54-110">Un identificador de una conexión cliente.</span><span class="sxs-lookup"><span data-stu-id="c8e54-110">A handle for a client connection.</span></span>  
  
 <span data-ttu-id="c8e54-111">*n*</span><span class="sxs-lookup"><span data-stu-id="c8e54-111">*n*</span></span>  
 <span data-ttu-id="c8e54-112">El número ordinal del parámetro que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="c8e54-112">The ordinal number of the parameter to be set.</span></span> <span data-ttu-id="c8e54-113">El primer parámetro es 1.</span><span class="sxs-lookup"><span data-stu-id="c8e54-113">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="c8e54-114">*pbType*</span><span class="sxs-lookup"><span data-stu-id="c8e54-114">*pbType*</span></span>  
 <span data-ttu-id="c8e54-115">El tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="c8e54-115">The data type of the parameter.</span></span>  
  
 <span data-ttu-id="c8e54-116">*pcbMaxLen*</span><span class="sxs-lookup"><span data-stu-id="c8e54-116">*pcbMaxLen*</span></span>  
 <span data-ttu-id="c8e54-117">Puntero a la longitud máxima del parámetro.</span><span class="sxs-lookup"><span data-stu-id="c8e54-117">Pointer to the maximum length of the parameter.</span></span>  
  
 <span data-ttu-id="c8e54-118">*pcbActualLen*</span><span class="sxs-lookup"><span data-stu-id="c8e54-118">*pcbActualLen*</span></span>  
 <span data-ttu-id="c8e54-119">Puntero a la longitud real del parámetro.</span><span class="sxs-lookup"><span data-stu-id="c8e54-119">Pointer to the actual length of the parameter.</span></span> <span data-ttu-id="c8e54-120">Un valor de 0 (\**pcbActualLen* == 0) significa datos de longitud cero si \**pfNull* está establecido en FALSE.</span><span class="sxs-lookup"><span data-stu-id="c8e54-120">A value of 0 (\**pcbActualLen* == 0) signifies zero-length data if \**pfNull* is set to FALSE.</span></span>  
  
 <span data-ttu-id="c8e54-121">*pbData*</span><span class="sxs-lookup"><span data-stu-id="c8e54-121">*pbData*</span></span>  
 <span data-ttu-id="c8e54-122">Puntero al búfer para los datos de parámetro.</span><span class="sxs-lookup"><span data-stu-id="c8e54-122">Pointer to the buffer for parameter data.</span></span> <span data-ttu-id="c8e54-123">Si *pbData* no es NULL, la API de procedimiento almacenado extendido escribe \**pcbActualLen* bytes de datos en \**pbData*.</span><span class="sxs-lookup"><span data-stu-id="c8e54-123">If *pbData* is not NULL, the Extended Store Procedure API writes \**pcbActualLen* bytes of data to \**pbData*.</span></span> <span data-ttu-id="c8e54-124">Si *pbData* es NULL, no se escriben datos en \**pbData*, pero la función devuelve \**pbType*, \**pcbMaxLen*, \**pcbActualLen* y \**pfNull*.</span><span class="sxs-lookup"><span data-stu-id="c8e54-124">If *pbData* is NULL, no data is written to \**pbData* but the function returns \**pbType*, \**pcbMaxLen*, \**pcbActualLen*, and \**pfNull*.</span></span> <span data-ttu-id="c8e54-125">La aplicación debe administrar la memoria para este búfer.</span><span class="sxs-lookup"><span data-stu-id="c8e54-125">The memory for this buffer must be managed by the application.</span></span>  
  
 <span data-ttu-id="c8e54-126">*pfNull*</span><span class="sxs-lookup"><span data-stu-id="c8e54-126">*pfNull*</span></span>  
 <span data-ttu-id="c8e54-127">Puntero a una marca nula.</span><span class="sxs-lookup"><span data-stu-id="c8e54-127">Pointer to a null flag.</span></span><span data-ttu-id="c8e54-128">\ **pfNull* se establece en TRUE si el valor del parámetro es NULL.</span><span class="sxs-lookup"><span data-stu-id="c8e54-128">\ **pfNull* is set to TRUE if the value of the parameter is NULL.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c8e54-129">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="c8e54-129">Returns</span></span>  
 <span data-ttu-id="c8e54-130">Si la información de los parámetros se obtiene correctamente, se devuelve SUCCEED; de lo contrario, se devuelve FAIL.</span><span class="sxs-lookup"><span data-stu-id="c8e54-130">If the parameter information was successfully obtained, SUCCEED is returned; otherwise, FAIL.</span></span> <span data-ttu-id="c8e54-131">Se devuelve FAIL cuando no hay ningún procedimiento almacenado remoto actual y cuando no hay ningún parámetro *n* de procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="c8e54-131">FAIL is returned when there is no current remote stored procedure and when there is no *n*th remote stored procedure parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8e54-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c8e54-132">Remarks</span></span>  
 <span data-ttu-id="c8e54-133">**Nota de seguridad** Debe revisar cuidadosamente el código fuente de los procedimientos almacenados extendidos y probar las DLL compiladas antes de instalarlas en un servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="c8e54-133">**Security Note** You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="c8e54-134">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="c8e54-134">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e54-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8e54-135">See Also</span></span>  
 [<span data-ttu-id="c8e54-136">Referencia del programador de procedimientos almacenados extendidos</span><span class="sxs-lookup"><span data-stu-id="c8e54-136">Extended Stored Procedures Programmer's Reference</span></span>](database-engine-extended-stored-procedures-reference.md)  
  
  
