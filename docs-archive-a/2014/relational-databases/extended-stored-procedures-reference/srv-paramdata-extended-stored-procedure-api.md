---
title: srv_paramdata (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramdata
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramdata
ms.assetid: 3104514d-b404-47c9-b6d7-928106384874
author: rothja
ms.author: jroth
ms.openlocfilehash: 092ca5b811a12c3e6b199a6041ce6e4f8e02f4b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675386"
---
# <a name="srv_paramdata-extended-stored-procedure-api"></a><span data-ttu-id="a51a3-102">srv_paramdata (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="a51a3-102">srv_paramdata (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="a51a3-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a51a3-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="a51a3-104">Devuelve el valor de un parámetro de llamada a un procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="a51a3-104">Returns the value of a remote stored procedure call parameter.</span></span> <span data-ttu-id="a51a3-105">La función **srv_paraminfo** ha reemplazado a esta.</span><span class="sxs-lookup"><span data-stu-id="a51a3-105">This function has been superseded by the **srv_paraminfo** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a51a3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a51a3-106">Syntax</span></span>  
  
```  
  
void * srv_paramdata (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a51a3-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a51a3-107">Arguments</span></span>  
 <span data-ttu-id="a51a3-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="a51a3-108">*srvproc*</span></span>  
 <span data-ttu-id="a51a3-109">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió la llamada al procedimiento almacenado remoto).</span><span class="sxs-lookup"><span data-stu-id="a51a3-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="a51a3-110">La estructura contiene información que la biblioteca de Procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="a51a3-110">The structure contains information the Extended Stored Procedure library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="a51a3-111">*n*</span><span class="sxs-lookup"><span data-stu-id="a51a3-111">*n*</span></span>  
 <span data-ttu-id="a51a3-112">Es el número del parámetro.</span><span class="sxs-lookup"><span data-stu-id="a51a3-112">Is the number of the parameter.</span></span> <span data-ttu-id="a51a3-113">El primer parámetro es número 1.</span><span class="sxs-lookup"><span data-stu-id="a51a3-113">The first parameter is number 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="a51a3-114">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="a51a3-114">Returns</span></span>  
 <span data-ttu-id="a51a3-115">Un puntero al valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="a51a3-115">A pointer to the parameter value.</span></span> <span data-ttu-id="a51a3-116">Si el parámetro *n* es NULL, no hay ningún parámetro de *n* o no hay ningún procedimiento almacenado remoto, devuelve NULL.</span><span class="sxs-lookup"><span data-stu-id="a51a3-116">If the *n*th parameter is NULL, there is no *n*th parameter, or there is no remote stored procedure, returns NULL.</span></span> <span data-ttu-id="a51a3-117">Si el valor del parámetro es una cadena, no podría terminar en NULL.</span><span class="sxs-lookup"><span data-stu-id="a51a3-117">If the parameter value is a string, it might not be null-terminated.</span></span> <span data-ttu-id="a51a3-118">Use **srv_paramlen** para determinar la longitud de la cadena.</span><span class="sxs-lookup"><span data-stu-id="a51a3-118">Use **srv_paramlen** to determine the length of the string.</span></span>  
  
 <span data-ttu-id="a51a3-119">Esta función devuelve los valores siguientes, si el parámetro es uno de los [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de datos de.</span><span class="sxs-lookup"><span data-stu-id="a51a3-119">This function returns the following values, if the parameter is one of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="a51a3-120">Los datos de puntero incluyen si el puntero para el tipo de datos es válido (VP), NULL o no aplicable (N/A) y el contenido al que señalan los datos.</span><span class="sxs-lookup"><span data-stu-id="a51a3-120">Pointer data includes whether the pointer for the data type is valid (VP), NULL, or not applicable (N/A), and the contents of the data pointed to.</span></span>  
  
|<span data-ttu-id="a51a3-121">Nuevos tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a51a3-121">New data types</span></span>|<span data-ttu-id="a51a3-122">Longitud de datos de entrada</span><span class="sxs-lookup"><span data-stu-id="a51a3-122">Input data length</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="a51a3-123">BITN</span><span class="sxs-lookup"><span data-stu-id="a51a3-123">BITN</span></span>|<span data-ttu-id="a51a3-124">**NULL:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="a51a3-124">**NULL:** VP, NULL</span></span><br /><br /> <span data-ttu-id="a51a3-125">**CERO:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="a51a3-125">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="a51a3-126">**>= 255:** N/A</span><span class="sxs-lookup"><span data-stu-id="a51a3-126">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="a51a3-127">**<255:** N/A</span><span class="sxs-lookup"><span data-stu-id="a51a3-127">**<255:** N/A</span></span>|  
|<span data-ttu-id="a51a3-128">BIGVARCHAR</span><span class="sxs-lookup"><span data-stu-id="a51a3-128">BIGVARCHAR</span></span>|<span data-ttu-id="a51a3-129">**NULL:** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="a51a3-129">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="a51a3-130">**CERO:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="a51a3-130">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="a51a3-131">**>=255:** VP, 255 caracteres</span><span class="sxs-lookup"><span data-stu-id="a51a3-131">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="a51a3-132">**<255:** VP, datos reales</span><span class="sxs-lookup"><span data-stu-id="a51a3-132">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="a51a3-133">BIGCHAR</span><span class="sxs-lookup"><span data-stu-id="a51a3-133">BIGCHAR</span></span>|<span data-ttu-id="a51a3-134">**NULL:** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="a51a3-134">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="a51a3-135">**CERO:** VP, 255 espacios</span><span class="sxs-lookup"><span data-stu-id="a51a3-135">**ZERO:** VP, 255 spaces</span></span><br /><br /> <span data-ttu-id="a51a3-136">**>=255:** VP, 255 caracteres</span><span class="sxs-lookup"><span data-stu-id="a51a3-136">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="a51a3-137">**<255:** VP, datos reales + relleno (hasta 255)</span><span class="sxs-lookup"><span data-stu-id="a51a3-137">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="a51a3-138">BIGBINARY</span><span class="sxs-lookup"><span data-stu-id="a51a3-138">BIGBINARY</span></span>|<span data-ttu-id="a51a3-139">**NULL:** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="a51a3-139">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="a51a3-140">**CERO:** VP, 255 0x00</span><span class="sxs-lookup"><span data-stu-id="a51a3-140">**ZERO:** VP, 255 0x00</span></span><br /><br /> <span data-ttu-id="a51a3-141">**>=255:** VP, 255 bytes</span><span class="sxs-lookup"><span data-stu-id="a51a3-141">**>=255:** VP, 255 bytes</span></span><br /><br /> <span data-ttu-id="a51a3-142">**<255:** VP, datos reales + relleno (hasta 255)</span><span class="sxs-lookup"><span data-stu-id="a51a3-142">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="a51a3-143">BIGVARBINARY</span><span class="sxs-lookup"><span data-stu-id="a51a3-143">BIGVARBINARY</span></span>|<span data-ttu-id="a51a3-144">**NULL:** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="a51a3-144">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="a51a3-145">**ZERO:** VP, 0x00</span><span class="sxs-lookup"><span data-stu-id="a51a3-145">**ZERO:** VP, 0x00</span></span><br /><br /> <span data-ttu-id="a51a3-146">**>=255:** VP, 255 bytes</span><span class="sxs-lookup"><span data-stu-id="a51a3-146">**>=255:** VP, 255 bytes</span></span><br /><br /> <span data-ttu-id="a51a3-147">**<255:** VP, datos reales</span><span class="sxs-lookup"><span data-stu-id="a51a3-147">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="a51a3-148">NCHAR</span><span class="sxs-lookup"><span data-stu-id="a51a3-148">NCHAR</span></span>|<span data-ttu-id="a51a3-149">**NULL:** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="a51a3-149">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="a51a3-150">**CERO:** VP, 255 espacios</span><span class="sxs-lookup"><span data-stu-id="a51a3-150">**ZERO:** VP, 255 spaces</span></span><br /><br /> <span data-ttu-id="a51a3-151">**>=255:** VP, 255 caracteres</span><span class="sxs-lookup"><span data-stu-id="a51a3-151">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="a51a3-152">**<255:** VP, datos reales + relleno (hasta 255)</span><span class="sxs-lookup"><span data-stu-id="a51a3-152">**<255:** VP, actual data + padding (up to 255)</span></span>|  
|<span data-ttu-id="a51a3-153">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="a51a3-153">NVARCHAR</span></span>|<span data-ttu-id="a51a3-154">**NULL:** NULL, N/A</span><span class="sxs-lookup"><span data-stu-id="a51a3-154">**NULL:** NULL, N/A</span></span><br /><br /> <span data-ttu-id="a51a3-155">**CERO:** VP, NULL</span><span class="sxs-lookup"><span data-stu-id="a51a3-155">**ZERO:** VP, NULL</span></span><br /><br /> <span data-ttu-id="a51a3-156">**>=255:** VP, 255 caracteres</span><span class="sxs-lookup"><span data-stu-id="a51a3-156">**>=255:** VP, 255 chars</span></span><br /><br /> <span data-ttu-id="a51a3-157">**<255:** VP, datos reales</span><span class="sxs-lookup"><span data-stu-id="a51a3-157">**<255:** VP, actual data</span></span>|  
|<span data-ttu-id="a51a3-158">NTEXT</span><span class="sxs-lookup"><span data-stu-id="a51a3-158">NTEXT</span></span>|<span data-ttu-id="a51a3-159">**NULL:** N/A</span><span class="sxs-lookup"><span data-stu-id="a51a3-159">**NULL:** N/A</span></span><br /><br /> <span data-ttu-id="a51a3-160">**CERO:** N/A</span><span class="sxs-lookup"><span data-stu-id="a51a3-160">**ZERO:** N/A</span></span><br /><br /> <span data-ttu-id="a51a3-161">**>= 255:** N/A</span><span class="sxs-lookup"><span data-stu-id="a51a3-161">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="a51a3-162">\*\* \< 255:\*\* N/A</span><span class="sxs-lookup"><span data-stu-id="a51a3-162">**\<255:** N/A</span></span>|  
  
 <span data-ttu-id="a51a3-163">\*   los datos no terminan en NULL; no se produce ninguna advertencia de truncamiento en los datos >255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a51a3-163">\*   data is not null-terminated; no warning is issued on truncation for data >255 characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a51a3-164">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a51a3-164">Remarks</span></span>  
 <span data-ttu-id="a51a3-165">Si conoce el nombre de parámetro, puede usar **srv_paramnumber** para obtener el número de parámetro.</span><span class="sxs-lookup"><span data-stu-id="a51a3-165">If you know the parameter name, you can use **srv_paramnumber** to get the parameter number.</span></span> <span data-ttu-id="a51a3-166">Para determinar si un parámetro es NULL, use **srv_paramlen**.</span><span class="sxs-lookup"><span data-stu-id="a51a3-166">To determine whether a parameter is NULL, use **srv_paramlen**.</span></span>  
  
 <span data-ttu-id="a51a3-167">Cuando se usan parámetros en una llamada a un procedimiento almacenado remoto, estos pueden pasarse por nombre o por posición (sin nombre).</span><span class="sxs-lookup"><span data-stu-id="a51a3-167">When a remote stored procedure call is made with parameters, the parameters can be passed by name or by position (unnamed).</span></span> <span data-ttu-id="a51a3-168">Se produce un error si la llamada al procedimiento almacenado remoto se realiza con algunos parámetros pasados por nombre y otros pasados por posición.</span><span class="sxs-lookup"><span data-stu-id="a51a3-168">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="a51a3-169">Si se produce un error, se sigue llamando al controlador SRV_RPC, pero aparece como si no hubiera ningún parámetro y **srv_rpcparams** devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="a51a3-169">If an error occurs, the SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a51a3-170">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="a51a3-170">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="a51a3-171">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="a51a3-171">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a51a3-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a51a3-172">See Also</span></span>  
 [<span data-ttu-id="a51a3-173">srv_rpcparams &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="a51a3-173">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
