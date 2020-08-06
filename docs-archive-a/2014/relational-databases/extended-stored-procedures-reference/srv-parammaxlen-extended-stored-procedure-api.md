---
title: srv_parammaxlen (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_parammaxlen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_parammaxlen
ms.assetid: 49bfc29d-f76a-4963-b0e6-b8532dfda850
author: rothja
ms.author: jroth
ms.openlocfilehash: b289743b3de4b115a67a029dcc0261854ee3a40b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751025"
---
# <a name="srv_parammaxlen-extended-stored-procedure-api"></a><span data-ttu-id="22bcf-102">srv_parammaxlen (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="22bcf-102">srv_parammaxlen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="22bcf-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="22bcf-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="22bcf-104">Devuelve la longitud máxima de datos de un parámetro de llamada a un procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="22bcf-104">Returns the maximum data length of a remote stored procedure call parameter.</span></span> <span data-ttu-id="22bcf-105">La función **srv_paraminfo** ha reemplazado a esta.</span><span class="sxs-lookup"><span data-stu-id="22bcf-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22bcf-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22bcf-106">Syntax</span></span>  
  
```  
  
int srv_parammaxlen (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="22bcf-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="22bcf-107">Arguments</span></span>  
 <span data-ttu-id="22bcf-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="22bcf-108">*srvproc*</span></span>  
 <span data-ttu-id="22bcf-109">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió la llamada al procedimiento almacenado remoto).</span><span class="sxs-lookup"><span data-stu-id="22bcf-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="22bcf-110">La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="22bcf-110">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="22bcf-111">*n*</span><span class="sxs-lookup"><span data-stu-id="22bcf-111">*n*</span></span>  
 <span data-ttu-id="22bcf-112">Indica el número del parámetro.</span><span class="sxs-lookup"><span data-stu-id="22bcf-112">Indicates the number of the parameter.</span></span> <span data-ttu-id="22bcf-113">El primer parámetro es 1.</span><span class="sxs-lookup"><span data-stu-id="22bcf-113">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="22bcf-114">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="22bcf-114">Returns</span></span>  
 <span data-ttu-id="22bcf-115">La longitud máxima, en bytes, de los datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="22bcf-115">The maximum length, in bytes, of the parameter data.</span></span> <span data-ttu-id="22bcf-116">Si no existe ningún parámetro *n* o no hay ningún procedimiento almacenado remoto, devuelve -1.</span><span class="sxs-lookup"><span data-stu-id="22bcf-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns -1.</span></span>  
  
 <span data-ttu-id="22bcf-117">Esta función devuelve los valores siguientes, si el parámetro es uno de los siguientes [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="22bcf-117">This function returns the following values, if the parameter is one of the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span>  
  
|<span data-ttu-id="22bcf-118">Nuevos tipos de datos</span><span class="sxs-lookup"><span data-stu-id="22bcf-118">New data types</span></span>|<span data-ttu-id="22bcf-119">Longitud de datos de entrada</span><span class="sxs-lookup"><span data-stu-id="22bcf-119">Input data length</span></span>|  
|--------------------|-----------------------|  
|`BITN`|<span data-ttu-id="22bcf-120">**NULL:** 1</span><span class="sxs-lookup"><span data-stu-id="22bcf-120">**NULL:** 1</span></span><br /><br /> <span data-ttu-id="22bcf-121">**Cero:** 1</span><span class="sxs-lookup"><span data-stu-id="22bcf-121">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="22bcf-122">**>= 255:** N/A</span><span class="sxs-lookup"><span data-stu-id="22bcf-122">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="22bcf-123">**<255:** N/A</span><span class="sxs-lookup"><span data-stu-id="22bcf-123">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="22bcf-124">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-124">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-125">**CERO:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-125">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-126">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-126">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-127">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-127">**<255:** 255</span></span>|  
|`BIGCHAR`|<span data-ttu-id="22bcf-128">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-128">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-129">**CERO:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-129">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-130">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-130">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-131">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-131">**<255:** 255</span></span>|  
|`BIGBINARY`|<span data-ttu-id="22bcf-132">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-132">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-133">**CERO:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-133">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-134">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-134">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-135">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-135">**<255:** 255</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="22bcf-136">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-136">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-137">**CERO:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-137">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-138">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-138">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-139">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-139">**<255:** 255</span></span>|  
|`NCHAR`|<span data-ttu-id="22bcf-140">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-140">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-141">**CERO:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-141">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-142">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-142">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-143">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-143">**<255:** 255</span></span>|  
|`NVARCHAR`|<span data-ttu-id="22bcf-144">**NULL:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-144">**NULL:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-145">**CERO:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-145">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-146">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-146">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="22bcf-147">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="22bcf-147">**<255:** 255</span></span>|  
|`NTEXT`|<span data-ttu-id="22bcf-148">**Null:** -1</span><span class="sxs-lookup"><span data-stu-id="22bcf-148">**NULL:** -1</span></span><br /><br /> <span data-ttu-id="22bcf-149">**CERO:** -1</span><span class="sxs-lookup"><span data-stu-id="22bcf-149">**ZERO:** -1</span></span><br /><br /> <span data-ttu-id="22bcf-150">**>= 255:** -1</span><span class="sxs-lookup"><span data-stu-id="22bcf-150">**>=255:** -1</span></span><br /><br /> <span data-ttu-id="22bcf-151">\*\* \< 255:\*\* -1</span><span class="sxs-lookup"><span data-stu-id="22bcf-151">**\<255:** -1</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22bcf-152">Observaciones</span><span class="sxs-lookup"><span data-stu-id="22bcf-152">Remarks</span></span>  
 <span data-ttu-id="22bcf-153">Cada parámetro de procedimiento almacenado remoto tiene una longitud de datos real y una longitud máxima.</span><span class="sxs-lookup"><span data-stu-id="22bcf-153">Each remote stored procedure parameter has an actual and a maximum data length.</span></span> <span data-ttu-id="22bcf-154">En los tipos de datos de longitud fija estándar que no permiten valores NULL, las longitudes real y máxima son las mismas.</span><span class="sxs-lookup"><span data-stu-id="22bcf-154">For standard fixed-length data types that do not allow null values, the actual and maximum lengths are the same.</span></span> <span data-ttu-id="22bcf-155">En los tipos de datos de longitud variable, las longitudes pueden variar.</span><span class="sxs-lookup"><span data-stu-id="22bcf-155">For variable-length data types, the lengths can vary.</span></span> <span data-ttu-id="22bcf-156">Por ejemplo, un parámetro declarado como **varchar(30)** puede tener datos con una longitud de solo 10 bytes.</span><span class="sxs-lookup"><span data-stu-id="22bcf-156">For example, a parameter declared as **varchar(30)** can have data that is only 10 bytes long.</span></span> <span data-ttu-id="22bcf-157">La longitud real del parámetro es 10 y su longitud máxima es 30.</span><span class="sxs-lookup"><span data-stu-id="22bcf-157">The parameter's actual length is 10 and its maximum length is 30.</span></span> <span data-ttu-id="22bcf-158">La función **srv_parammaxlen** obtiene la longitud máxima de los datos de un procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="22bcf-158">The **srv_parammaxlen** function gets the maximum data length of a remote stored procedure.</span></span> <span data-ttu-id="22bcf-159">Para obtener la longitud real de un parámetro, use **srv_paramlen**.</span><span class="sxs-lookup"><span data-stu-id="22bcf-159">To obtain the actual length of a parameter, use **srv_paramlen**.</span></span>  
  
 <span data-ttu-id="22bcf-160">Cuando se usan parámetros en una llamada a un procedimiento almacenado remoto, estos pueden pasarse por nombre o por posición (sin nombre).</span><span class="sxs-lookup"><span data-stu-id="22bcf-160">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="22bcf-161">Se produce un error si la llamada al procedimiento almacenado remoto se realiza con algunos parámetros pasados por nombre y otros pasados por posición.</span><span class="sxs-lookup"><span data-stu-id="22bcf-161">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="22bcf-162">Sigue llamándose al controlador SRV_RPC, pero parece como si no hubiera ningún parámetro y **srv_rpcparams** devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="22bcf-162">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="22bcf-163">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="22bcf-163">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="22bcf-164">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="22bcf-164">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22bcf-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22bcf-165">See Also</span></span>  
 <span data-ttu-id="22bcf-166">[srv_paraminfo API de procedimiento almacenado extendido &#40;&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="22bcf-166">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="22bcf-167">srv_rpcparams &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="22bcf-167">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
