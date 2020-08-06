---
title: srv_paramset (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramset
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramset
ms.assetid: 2a509206-a1b8-4b20-b0a2-ef680cef7bd8
author: rothja
ms.author: jroth
ms.openlocfilehash: 9ebe308e5e0c8fc24382582fb71db2f48c77541e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663483"
---
# <a name="srv_paramset-extended-stored-procedure-api"></a><span data-ttu-id="9c74f-102">srv_paramset (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="9c74f-102">srv_paramset (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="9c74f-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9c74f-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="9c74f-104">Establece el valor de un parámetro devuelto a una llamada de un procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="9c74f-104">Sets the value of a remote stored procedure call return parameter.</span></span> <span data-ttu-id="9c74f-105">La función **srv_paramsetoutput** ha reemplazado a esta función.</span><span class="sxs-lookup"><span data-stu-id="9c74f-105">This function has been superseded by the **srv_paramsetoutput** function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c74f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c74f-106">Syntax</span></span>  
  
```  
  
int srv_paramset (  
SRV_PROC *  
srvproc  
,  
int  
n  
,   
void *  
data  
,  
int  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="9c74f-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9c74f-107">Arguments</span></span>  
 <span data-ttu-id="9c74f-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="9c74f-108">*srvproc*</span></span>  
 <span data-ttu-id="9c74f-109">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió la llamada al procedimiento almacenado remoto).</span><span class="sxs-lookup"><span data-stu-id="9c74f-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="9c74f-110">La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="9c74f-110">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="9c74f-111">*n*</span><span class="sxs-lookup"><span data-stu-id="9c74f-111">*n*</span></span>  
 <span data-ttu-id="9c74f-112">Indica el número del parámetro para establecer.</span><span class="sxs-lookup"><span data-stu-id="9c74f-112">Indicates the number of the parameter to set.</span></span> <span data-ttu-id="9c74f-113">El primer parámetro es 1.</span><span class="sxs-lookup"><span data-stu-id="9c74f-113">The first parameter is 1.</span></span>  
  
 <span data-ttu-id="9c74f-114">*data*</span><span class="sxs-lookup"><span data-stu-id="9c74f-114">*data*</span></span>  
 <span data-ttu-id="9c74f-115">Es un puntero hacia el valor de datos que se va a devolver al cliente como el parámetro de retorno de procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="9c74f-115">Is a pointer to the data value to be sent back to the client as the remote stored procedure return parameter.</span></span>  
  
 <span data-ttu-id="9c74f-116">*terminado*</span><span class="sxs-lookup"><span data-stu-id="9c74f-116">*len*</span></span>  
 <span data-ttu-id="9c74f-117">Especifica la longitud real de los datos que se devolverán.</span><span class="sxs-lookup"><span data-stu-id="9c74f-117">Specifies the actual length of the data to be returned.</span></span> <span data-ttu-id="9c74f-118">Si el tipo de datos del parámetro es de una longitud constante y no permite valores null (por ejemplo, *srvbit* o *srvint1*), se omite *len*.</span><span class="sxs-lookup"><span data-stu-id="9c74f-118">If the data type of the parameter is of a constant length and does not allow null values (for example, *srvbit* or *srvint1*), *len* is ignored.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="9c74f-119">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="9c74f-119">Returns</span></span>  
 <span data-ttu-id="9c74f-120">SUCCEED si el valor del parámetro se ha establecido correctamente; de lo contrario, FAIL.</span><span class="sxs-lookup"><span data-stu-id="9c74f-120">SUCCEED if the parameter value was successfully set; otherwise, FAIL.</span></span> <span data-ttu-id="9c74f-121">Se devuelve FAIL cuando no hay ningún procedimiento almacenado remoto actual, cuando no hay ningún parámetro *n* de procedimiento almacenado remoto, cuando el parámetro no es un parámetro de devolución y cuando el argumento *len* no es legal.</span><span class="sxs-lookup"><span data-stu-id="9c74f-121">FAIL is returned when there is no current remote stored procedure, when there is no *n*th remote stored procedure parameter, when the parameter is not a return parameter, and when the *len* argument is not legal.</span></span>  
  
 <span data-ttu-id="9c74f-122">Si *len* es 0, devuelve NULL.</span><span class="sxs-lookup"><span data-stu-id="9c74f-122">If *len*is 0, it returns NULL.</span></span> <span data-ttu-id="9c74f-123">La única manera de devolver NULL al cliente es establecer *len* en 0.</span><span class="sxs-lookup"><span data-stu-id="9c74f-123">Setting *len* to 0 is the only way to return NULL to the client.</span></span>  
  
 <span data-ttu-id="9c74f-124">Esta función devuelve los valores siguientes, si el parámetro es uno de los [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] tipos de datos de.</span><span class="sxs-lookup"><span data-stu-id="9c74f-124">This function returns the following values, if the parameter is one of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] data types.</span></span>  
  
|<span data-ttu-id="9c74f-125">Nuevos tipos de datos</span><span class="sxs-lookup"><span data-stu-id="9c74f-125">New data types</span></span>|<span data-ttu-id="9c74f-126">Devuelve la longitud de datos</span><span class="sxs-lookup"><span data-stu-id="9c74f-126">Return data length</span></span>|  
|--------------------|------------------------|  
|`BITN`|<span data-ttu-id="9c74f-127">**NULL:** *len* = 0, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-127">**NULL:** *len* = 0, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-128">**CERO:** N/A</span><span class="sxs-lookup"><span data-stu-id="9c74f-128">**ZERO:** N/A</span></span><br /><br /> <span data-ttu-id="9c74f-129">**>= 255:** N/A</span><span class="sxs-lookup"><span data-stu-id="9c74f-129">**>=255:** N/A</span></span><br /><br /> <span data-ttu-id="9c74f-130">**<255:** N/A</span><span class="sxs-lookup"><span data-stu-id="9c74f-130">**<255:** N/A</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="9c74f-131">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="9c74f-131">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="9c74f-132">**CERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-132">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-133">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-133">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-134">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="9c74f-134">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGCHAR`|<span data-ttu-id="9c74f-135">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="9c74f-135">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="9c74f-136">**CERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-136">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-137">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-137">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-138">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="9c74f-138">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGBINARY`|<span data-ttu-id="9c74f-139">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="9c74f-139">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="9c74f-140">**CERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-140">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-141">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-141">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-142">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="9c74f-142">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="9c74f-143">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="9c74f-143">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="9c74f-144">**CERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-144">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-145">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-145">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-146">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="9c74f-146">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|<span data-ttu-id="9c74f-147">NCHAR</span><span class="sxs-lookup"><span data-stu-id="9c74f-147">NCHAR</span></span>|<span data-ttu-id="9c74f-148">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="9c74f-148">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="9c74f-149">**CERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-149">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-150">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-150">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-151">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="9c74f-151">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|<span data-ttu-id="9c74f-152">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="9c74f-152">NVARCHAR</span></span>|<span data-ttu-id="9c74f-153">**NULL:** *len* = 0, data = IG, RET = 1</span><span class="sxs-lookup"><span data-stu-id="9c74f-153">**NULL:** *len* = 0, data = IG, RET = 1</span></span><br /><br /> <span data-ttu-id="9c74f-154">**CERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-154">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-155">**>=255:** *len* = max8k, data = valid, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-155">**>=255:** *len* = max8k, data = valid, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-156">**<255:** *len* = <8k, data = valid, RET = 1</span><span class="sxs-lookup"><span data-stu-id="9c74f-156">**<255:** *len* = <8k, data = valid, RET = 1</span></span>|  
|`NTEXT`|<span data-ttu-id="9c74f-157">**NULL:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-157">**NULL:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-158">**CERO:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-158">**ZERO:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-159">**>=255:** *len* = IG, data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-159">**>=255:** *len* = IG, data = IG, RET = 0</span></span><br /><br /> <span data-ttu-id="9c74f-160">\*\* \< 255:\*\* *Len* = IG, Data = IG, RET = 0</span><span class="sxs-lookup"><span data-stu-id="9c74f-160">**\<255:** *len* = IG, data = IG, RET = 0</span></span>|  
|<span data-ttu-id="9c74f-161">RET = valor devuelto de srv_paramset</span><span class="sxs-lookup"><span data-stu-id="9c74f-161">RET = Return value of srv_paramset</span></span>||  
|<span data-ttu-id="9c74f-162">IG = El valor se omitirá</span><span class="sxs-lookup"><span data-stu-id="9c74f-162">IG = Value will be ignored</span></span>||  
|<span data-ttu-id="9c74f-163">válido = Cualquier puntero válido a datos</span><span class="sxs-lookup"><span data-stu-id="9c74f-163">valid = Any valid pointer to data</span></span>||  
  
## <a name="remarks"></a><span data-ttu-id="9c74f-164">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9c74f-164">Remarks</span></span>  
 <span data-ttu-id="9c74f-165">Los parámetros contienen datos que se pasan entre los clientes y la aplicación con procedimientos almacenados remotos.</span><span class="sxs-lookup"><span data-stu-id="9c74f-165">Parameters contain data passed between clients and the application with remote stored procedures.</span></span> <span data-ttu-id="9c74f-166">El cliente puede especificar ciertos parámetros como parámetros de retorno.</span><span class="sxs-lookup"><span data-stu-id="9c74f-166">The client can specify certain parameters as return parameters.</span></span> <span data-ttu-id="9c74f-167">Estos parámetros de retorno pueden contener valores que la aplicación de servidor Servicios abiertos de datos devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="9c74f-167">These return parameters can contain values that the Open Data Services server application passes back to the client.</span></span> <span data-ttu-id="9c74f-168">Usar parámetros de retorno es equivalente a pasar parámetros por referencia.</span><span class="sxs-lookup"><span data-stu-id="9c74f-168">Using return parameters is analogous to passing parameters by reference.</span></span>  
  
 <span data-ttu-id="9c74f-169">No puede establecer el valor devuelto para un parámetro que no se invocó como un parámetro de retorno.</span><span class="sxs-lookup"><span data-stu-id="9c74f-169">You cannot set the return value for a parameter that wasn't invoked as a return parameter.</span></span> <span data-ttu-id="9c74f-170">Puede usar **srv_paramstatus** para determinar cómo se ha invocado al parámetro.</span><span class="sxs-lookup"><span data-stu-id="9c74f-170">You can use **srv_paramstatus** to determine how the parameter was invoked.</span></span>  
  
 <span data-ttu-id="9c74f-171">Esta función establece el valor devuelto para un parámetro pero realmente no envía el valor devuelto al cliente.</span><span class="sxs-lookup"><span data-stu-id="9c74f-171">This function sets the return value for a parameter but it does not actually send the return value to the client.</span></span> <span data-ttu-id="9c74f-172">Todos los parámetros de devolución, tanto si sus valores devueltos se han establecido con **srv_paramset** como si no, se envían automáticamente al cliente cuando se llama a **srv_senddone** con la marca de estado SRV_DONE_FINAL establecida.</span><span class="sxs-lookup"><span data-stu-id="9c74f-172">All return parameters, whether their return values have been set with **srv_paramset** or not, are automatically sent to the client when **srv_senddone** is called with the status flag SRV_DONE_FINAL set.</span></span>  
  
 <span data-ttu-id="9c74f-173">Cuando se usan parámetros en una llamada a un procedimiento almacenado remoto, estos pueden pasarse por nombre o por posición (sin nombre).</span><span class="sxs-lookup"><span data-stu-id="9c74f-173">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="9c74f-174">Se produce un error si la llamada al procedimiento almacenado remoto se realiza con algunos parámetros pasados por nombre y otros pasados por posición.</span><span class="sxs-lookup"><span data-stu-id="9c74f-174">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="9c74f-175">Sigue llamándose al controlador SRV_RPC, pero parece como si no hubiera ningún parámetro y **srv_rpcparams** devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="9c74f-175">The SRV_RPC handler is still called, but it appears as if there were no parameters, and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9c74f-176">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="9c74f-176">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="9c74f-177">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="9c74f-177">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c74f-178">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c74f-178">See Also</span></span>  
 [<span data-ttu-id="9c74f-179">srv_paramsetoutput &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="9c74f-179">srv_paramsetoutput &#40;Extended Stored Procedure API&#41;</span></span>](srv-paramsetoutput-extended-stored-procedure-api.md)  
  
  
