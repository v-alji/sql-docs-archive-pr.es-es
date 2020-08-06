---
title: srv_setutype (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setutype
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setutype
ms.assetid: 6160f15d-1b68-411e-ab6d-491ec288f264
author: rothja
ms.author: jroth
ms.openlocfilehash: e9e02605995e44f5869633d5e8778a955236005f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749324"
---
# <a name="srv_setutype-extended-stored-procedure-api"></a><span data-ttu-id="c822c-102">srv_setutype (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="c822c-102">srv_setutype (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="c822c-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c822c-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="c822c-104">Establece el tipo de datos definido por el usuario para una columna de una fila.</span><span class="sxs-lookup"><span data-stu-id="c822c-104">Sets the user-defined data type for a column in a row.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c822c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c822c-105">Syntax</span></span>  
  
```  
  
int srv_setutype (  
SRV_PROC *  
srvproc  
,  
int   
column  
,   
DBINT  
user_type   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c822c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c822c-106">Arguments</span></span>  
 <span data-ttu-id="c822c-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="c822c-107">*srvproc*</span></span>  
 <span data-ttu-id="c822c-108">Es un puntero a la estructura SRV_PROC que es el identificador de una conexión cliente determinada.</span><span class="sxs-lookup"><span data-stu-id="c822c-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="c822c-109">La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="c822c-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="c822c-110">*column*</span><span class="sxs-lookup"><span data-stu-id="c822c-110">*column*</span></span>  
 <span data-ttu-id="c822c-111">Indica qué columna se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="c822c-111">Indicates which column to set.</span></span> <span data-ttu-id="c822c-112">Las columnas se numeran comenzando por 1.</span><span class="sxs-lookup"><span data-stu-id="c822c-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="c822c-113">*user_type*</span><span class="sxs-lookup"><span data-stu-id="c822c-113">*user_type*</span></span>  
 <span data-ttu-id="c822c-114">Especifica el código del tipo de datos definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c822c-114">Specifies the user-defined data type code.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c822c-115">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="c822c-115">Returns</span></span>  
 <span data-ttu-id="c822c-116">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="c822c-116">SUCCEED or FAIL.</span></span> <span data-ttu-id="c822c-117">Devuelve FAIL si la columna no existe.</span><span class="sxs-lookup"><span data-stu-id="c822c-117">Returns FAIL if the column does not exist.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c822c-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c822c-118">Remarks</span></span>  
 <span data-ttu-id="c822c-119">Una columna tiene dos tipos de datos: el tipo de datos real y el tipo de datos definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c822c-119">A column has two data types: its actual data type and its user-defined data type.</span></span> <span data-ttu-id="c822c-120">Usa el tipo de datos definido por el usuario [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para almacenar el tipo de datos definido por el usuario real de la columna, si existe, y la información de descripción de la columna, como la nulabilidad y la actualización, para la columna.</span><span class="sxs-lookup"><span data-stu-id="c822c-120">The user-defined data type is used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to store the actual user-defined data type of the column, if any, and column description information, such as nullability and updatability, for the column.</span></span>  
  
 <span data-ttu-id="c822c-121">Se puede llamar a la función **srv_setutype** en cualquier momento siempre que se haya definido *column* con **srv_describe** y antes de que se haya enviado la última fila.</span><span class="sxs-lookup"><span data-stu-id="c822c-121">The **srv_setutype** function can be called any time that *column* has been defined with **srv_describe** and before the last row has been sent.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c822c-122">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="c822c-122">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="c822c-123">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="c822c-123">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c822c-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c822c-124">See Also</span></span>  
 [<span data-ttu-id="c822c-125">srv_describe &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="c822c-125">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
