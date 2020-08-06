---
title: srv_paramtype (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_paramtype
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_paramtype
ms.assetid: badc6d36-8a87-42b5-b28c-9c4f5ded8552
author: rothja
ms.author: jroth
ms.openlocfilehash: 0c4b4006f8214670e3bd2bddfbaabe917fb9d778
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670387"
---
# <a name="srv_paramtype-extended-stored-procedure-api"></a><span data-ttu-id="34d9b-102">srv_paramtype (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="34d9b-102">srv_paramtype (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="34d9b-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="34d9b-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="34d9b-104">Devuelve el tipo de datos de un parámetro de llamada a un procedimiento almacenado remoto.</span><span class="sxs-lookup"><span data-stu-id="34d9b-104">Returns the data type of a remote stored procedure call parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34d9b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34d9b-105">Syntax</span></span>  
  
```  
  
int srv_paramtype (  
SRV_PROC *  
srvproc  
,  
int  
n   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="34d9b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="34d9b-106">Arguments</span></span>  
 <span data-ttu-id="34d9b-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="34d9b-107">*srvproc*</span></span>  
 <span data-ttu-id="34d9b-108">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió la llamada al procedimiento almacenado remoto).</span><span class="sxs-lookup"><span data-stu-id="34d9b-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure call).</span></span> <span data-ttu-id="34d9b-109">La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="34d9b-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="34d9b-110">*n*</span><span class="sxs-lookup"><span data-stu-id="34d9b-110">*n*</span></span>  
 <span data-ttu-id="34d9b-111">Indica el número del parámetro.</span><span class="sxs-lookup"><span data-stu-id="34d9b-111">Indicates the number of the parameter.</span></span> <span data-ttu-id="34d9b-112">El primer parámetro es 1.</span><span class="sxs-lookup"><span data-stu-id="34d9b-112">The first parameter is 1.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="34d9b-113">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="34d9b-113">Returns</span></span>  
 <span data-ttu-id="34d9b-114">En valor de token para el tipo de dato del parámetro.</span><span class="sxs-lookup"><span data-stu-id="34d9b-114">A token value for the data type of the parameter.</span></span> <span data-ttu-id="34d9b-115">Para más información sobre tipos de datos, vea [Data Types &#40;Extended Stored Procedure API&#41; (Tipos de datos &#40;API de procedimiento almacenado extendido&#41;)](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="34d9b-115">For information about data types, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span> <span data-ttu-id="34d9b-116">Si no existe ningún parámetro *n* o no hay ningún procedimiento almacenado remoto, devuelve -1.</span><span class="sxs-lookup"><span data-stu-id="34d9b-116">If there is no *n*th parameter or if there is no remote stored procedure, it returns - 1.</span></span>  
  
 <span data-ttu-id="34d9b-117">Esta función devuelve los valores siguientes, si el parámetro es uno de los [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] tipos de datos de.</span><span class="sxs-lookup"><span data-stu-id="34d9b-117">This function returns the following values, if the parameter is one of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] data types.</span></span>  
  
|<span data-ttu-id="34d9b-118">Nuevos tipos de datos</span><span class="sxs-lookup"><span data-stu-id="34d9b-118">New data types</span></span>|<span data-ttu-id="34d9b-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="34d9b-119">Return value</span></span>|  
|--------------------|------------------|  
|`BITN`|<span data-ttu-id="34d9b-120">SRVBIT</span><span class="sxs-lookup"><span data-stu-id="34d9b-120">SRVBIT</span></span>|  
|`BIGVARCHAR`|<span data-ttu-id="34d9b-121">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="34d9b-121">VARCHAR</span></span>|  
|`BIGCHAR`|<span data-ttu-id="34d9b-122">CHAR</span><span class="sxs-lookup"><span data-stu-id="34d9b-122">CHAR</span></span>|  
|`BIGBINARY`|<span data-ttu-id="34d9b-123">BINARY</span><span class="sxs-lookup"><span data-stu-id="34d9b-123">BINARY</span></span>|  
|`BIGVARBINARY`|<span data-ttu-id="34d9b-124">VARBINARY</span><span class="sxs-lookup"><span data-stu-id="34d9b-124">VARBINARY</span></span>|  
|`NCHAR`|<span data-ttu-id="34d9b-125">CHAR</span><span class="sxs-lookup"><span data-stu-id="34d9b-125">CHAR</span></span>|  
|`NVARCHAR`|<span data-ttu-id="34d9b-126">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="34d9b-126">VARCHAR</span></span>|  
|`NTEXT`|<span data-ttu-id="34d9b-127">-1</span><span class="sxs-lookup"><span data-stu-id="34d9b-127">-1</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34d9b-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="34d9b-128">Remarks</span></span>  
 <span data-ttu-id="34d9b-129">Cuando se usan parámetros en una llamada a un procedimiento almacenado remoto, estos pueden pasarse por nombre o por posición (sin nombre).</span><span class="sxs-lookup"><span data-stu-id="34d9b-129">When a remote stored procedure call is made with parameters, the parameters can be passed either by name or by position (unnamed).</span></span> <span data-ttu-id="34d9b-130">Se produce un error si la llamada al procedimiento almacenado remoto se realiza con algunos parámetros pasados por nombre y otros pasados por posición.</span><span class="sxs-lookup"><span data-stu-id="34d9b-130">If the remote stored procedure call is made with some parameters passed by name and some passed by position, an error occurs.</span></span> <span data-ttu-id="34d9b-131">Todavía se llama al controlador de SRV_RPC, pero aparece como si no hubiera ningún parámetro y **srv_rpcparams** devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="34d9b-131">The SRV_RPC handler is still called, but it appears as if there were no parameters and **srv_rpcparams** returns 0.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="34d9b-132">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="34d9b-132">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="34d9b-133">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="34d9b-133">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34d9b-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34d9b-134">See Also</span></span>  
 <span data-ttu-id="34d9b-135">[srv_paraminfo API de procedimiento almacenado extendido &#40;&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="34d9b-135">[srv_paraminfo &#40;Extended Stored Procedure API&#41;](srv-paraminfo-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="34d9b-136">srv_rpcparams &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="34d9b-136">srv_rpcparams &#40;Extended Stored Procedure API&#41;</span></span>](srv-rpcparams-extended-stored-procedure-api.md)  
  
  
