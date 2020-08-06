---
title: srv_paramlen (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramlen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramlen
ms.assetid: d1fe92ff-cad6-4396-8216-125e5642e81e
author: rothja
ms.author: jroth
ms.openlocfilehash: fc2a0fa7f8409767a2afaa9c4c621ea72732b701
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751029"
---
# <a name="srv_paramlen-extended-stored-procedure-api"></a><span data-ttu-id="ad7fe-102">srv_paramlen (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="ad7fe-102">srv_paramlen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="ad7fe-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="ad7fe-104">Devuelve la longitud de datos de un parámetro de llamada a un procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-104">Returns the data length of a remote stored procedure call parameter.</span></span> <span data-ttu-id="ad7fe-105">La función **srv_paraminfo** ha reemplazado a esta.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad7fe-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad7fe-106">Syntax</span></span>  
  
```  
  
int srv_paramlen (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="ad7fe-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ad7fe-107">Arguments</span></span>  
 <span data-ttu-id="ad7fe-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="ad7fe-108">*srvproc*</span></span>  
 <span data-ttu-id="ad7fe-109">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió la llamada al procedimiento almacenado remoto).</span><span class="sxs-lookup"><span data-stu-id="ad7fe-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="ad7fe-110">La estructura contiene información que la biblioteca de API Procedimiento almacenado extendido utiliza para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-110">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="ad7fe-111">*n*</span><span class="sxs-lookup"><span data-stu-id="ad7fe-111">*n*</span></span>  
 <span data-ttu-id="ad7fe-112">Indica el número del parámetro.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-112">Indicates the number of the parameter.</span></span> <span data-ttu-id="ad7fe-113">El primer parámetro es 1.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-113">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="ad7fe-114">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="ad7fe-114">Returns</span></span>  
 <span data-ttu-id="ad7fe-115">La longitud real, en bytes, de los datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-115">The actual length, in bytes, of the parameter data.</span></span> <span data-ttu-id="ad7fe-116">Si no existe ningún parámetro *n*, o no hay ningún procedimiento almacenado remoto, devuelve -1.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-116">If there is no *n*th parameter or there is no remote stored procedure, it returns -1.</span></span> <span data-ttu-id="ad7fe-117">Si el parámetro *n* es NULL, devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-117">If the *n*th parameter is NULL, it returns 0.</span></span>  
  
 <span data-ttu-id="ad7fe-118">Esta función devuelve los valores siguientes, si el parámetro es uno de los siguientes [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] tipos de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-118">This function returns the following values, if the parameter is one of the following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] system data types.</span></span>  
  
|<span data-ttu-id="ad7fe-119">Nuevos tipos de datos</span><span class="sxs-lookup"><span data-stu-id="ad7fe-119">New data types</span></span>|<span data-ttu-id="ad7fe-120">Longitud de datos de entrada</span><span class="sxs-lookup"><span data-stu-id="ad7fe-120">Input data length</span></span>|  
|--------------------|-----------------------|  
|`BITN`|<span data-ttu-id="ad7fe-121">**NULL:** 1</span><span class="sxs-lookup"><span data-stu-id="ad7fe-121">**NULL:** 1</span></span><br /><br /> <span data-ttu-id="ad7fe-122">**Cero:** 1</span><span class="sxs-lookup"><span data-stu-id="ad7fe-122">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="ad7fe-123">**>= 255:** N/A</span><span class="sxs-lookup"><span data-stu-id="ad7fe-123">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="ad7fe-124">**<255:** N/A</span><span class="sxs-lookup"><span data-stu-id="ad7fe-124">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="ad7fe-125">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="ad7fe-125">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="ad7fe-126">**Cero:** 1</span><span class="sxs-lookup"><span data-stu-id="ad7fe-126">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="ad7fe-127">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="ad7fe-127">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="ad7fe-128">\**<255:\*\*\*len* real</span><span class="sxs-lookup"><span data-stu-id="ad7fe-128">**<255:** actual *len*</span></span>|  
|`BIGCHAR`|<span data-ttu-id="ad7fe-129">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="ad7fe-129">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="ad7fe-130">**CERO:** 255</span><span class="sxs-lookup"><span data-stu-id="ad7fe-130">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="ad7fe-131">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="ad7fe-131">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="ad7fe-132">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="ad7fe-132">**<255:** 255</span></span>|  
|`BIGBINARY`|<span data-ttu-id="ad7fe-133">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="ad7fe-133">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="ad7fe-134">**CERO:** 255</span><span class="sxs-lookup"><span data-stu-id="ad7fe-134">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="ad7fe-135">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="ad7fe-135">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="ad7fe-136">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="ad7fe-136">**<255:** 255</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="ad7fe-137">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="ad7fe-137">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="ad7fe-138">**Cero:** 1</span><span class="sxs-lookup"><span data-stu-id="ad7fe-138">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="ad7fe-139">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="ad7fe-139">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="ad7fe-140">\**<255:\*\*\*len* real</span><span class="sxs-lookup"><span data-stu-id="ad7fe-140">**<255:** actual *len*</span></span>|  
|`NCHAR`|<span data-ttu-id="ad7fe-141">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="ad7fe-141">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="ad7fe-142">**CERO:** 255</span><span class="sxs-lookup"><span data-stu-id="ad7fe-142">**ZERO:** 255</span></span><br /><br /> <span data-ttu-id="ad7fe-143">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="ad7fe-143">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="ad7fe-144">**<255:** 255</span><span class="sxs-lookup"><span data-stu-id="ad7fe-144">**<255:** 255</span></span>|  
|`NVARCHAR`|<span data-ttu-id="ad7fe-145">**NULL:** 0</span><span class="sxs-lookup"><span data-stu-id="ad7fe-145">**NULL:** 0</span></span><br /><br /> <span data-ttu-id="ad7fe-146">**Cero:** 1</span><span class="sxs-lookup"><span data-stu-id="ad7fe-146">**ZERO:** 1</span></span><br /><br /> <span data-ttu-id="ad7fe-147">**>= 255:** 255</span><span class="sxs-lookup"><span data-stu-id="ad7fe-147">**>=255:** 255</span></span><br /><br /> <span data-ttu-id="ad7fe-148">\**<255:\*\*\*len* real</span><span class="sxs-lookup"><span data-stu-id="ad7fe-148">**<255:** actual *len*</span></span>|  
|`NTEXT`|<span data-ttu-id="ad7fe-149">**Null:** -1</span><span class="sxs-lookup"><span data-stu-id="ad7fe-149">**NULL:** -1</span></span><br /><br /> <span data-ttu-id="ad7fe-150">**CERO:** -1</span><span class="sxs-lookup"><span data-stu-id="ad7fe-150">**ZERO:** -1</span></span><br /><br /> <span data-ttu-id="ad7fe-151">**>= 255:** -1</span><span class="sxs-lookup"><span data-stu-id="ad7fe-151">**>=255:** -1</span></span><br /><br /> <span data-ttu-id="ad7fe-152">**<255:** -1</span><span class="sxs-lookup"><span data-stu-id="ad7fe-152">**<255:** -1</span></span>|  
  
 <span data-ttu-id="ad7fe-153">\**len* real = longitud de cadena de caracteres multibyte (cch)</span><span class="sxs-lookup"><span data-stu-id="ad7fe-153">\*   actual *len* = Length of multibyte character string (cch)</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad7fe-154">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ad7fe-154">Remarks</span></span>  
 <span data-ttu-id="ad7fe-155">Cada parámetro de procedimiento almacenado remoto tiene una longitud de datos real y una longitud máxima.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-155">Each remote stored procedure parameter has an actual and a maximum data length.</span></span> <span data-ttu-id="ad7fe-156">En los tipos de datos de longitud fija estándar que no permiten valores NULL, las longitudes real y máxima son las mismas.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-156">For standard fixed-length data types that do not allow null values, the actual and maximum lengths are the same.</span></span> <span data-ttu-id="ad7fe-157">En los tipos de datos de longitud variable, las longitudes pueden variar.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-157">For variable-length data types, the lengths can vary.</span></span> <span data-ttu-id="ad7fe-158">Por ejemplo, un parámetro declarado como `varchar(30)` puede tener datos con una longitud de solo 10 bytes.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-158">For example, a parameter declared as `varchar(30)` can have data that is only 10 bytes long.</span></span> <span data-ttu-id="ad7fe-159">La longitud real del parámetro es 10 y su longitud máxima es 30.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-159">The parameter's actual length is 10 and its maximum length is 30.</span></span> <span data-ttu-id="ad7fe-160">La función **srv_paramlen** obtiene la longitud de datos real en bytes de un procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-160">The **srv_paramlen** function gets the actual data length, in bytes, of a remote stored procedure.</span></span> <span data-ttu-id="ad7fe-161">Para obtener la longitud de datos máxima de un parámetro, use **srv_parammaxlen**.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-161">To obtain the maximum data length of a parameter, use **srv_parammaxlen**.</span></span>  
  
 <span data-ttu-id="ad7fe-162">Cuando se usan parámetros en una llamada a un procedimiento almacenado remoto, estos pueden pasarse por nombre o por posición (sin nombre).</span><span class="sxs-lookup"><span data-stu-id="ad7fe-162">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="ad7fe-163">Se produce un error si la llamada al procedimiento almacenado remoto se realiza con algunos parámetros pasados por nombre y otros pasados por posición.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-163">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="ad7fe-164">Todavía se llama al controlador de SRV_RPC, pero aparece como si no hubiera ningún parámetro y **srv_rpcparams** devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-164">The SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ad7fe-165">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="ad7fe-165">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="ad7fe-166">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="ad7fe-166">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad7fe-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad7fe-167">See Also</span></span>  
 <span data-ttu-id="ad7fe-168">[srv_paraminfo API de procedimiento almacenado extendido &#40;&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="ad7fe-168">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="ad7fe-169">srv_rpcparams &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="ad7fe-169">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
