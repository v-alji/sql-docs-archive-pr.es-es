---
title: srv_setcollen (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setcollen
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setcollen
ms.assetid: 3c60f1c3-4562-463a-a259-12df172788bd
author: rothja
ms.author: jroth
ms.openlocfilehash: 8e3023e2ac239e074656329da7d8af3aba3afa88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745300"
---
# <a name="srv_setcollen-extended-stored-procedure-api"></a><span data-ttu-id="62faf-102">srv_setcollen (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="62faf-102">srv_setcollen (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="62faf-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="62faf-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="62faf-104">Especifica la longitud actual de los datos en bytes de una columna de longitud variable o de una columna que permite valores NULL.</span><span class="sxs-lookup"><span data-stu-id="62faf-104">Specifies the current data length in bytes of a variable-length column or a column that allows NULL values.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62faf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62faf-105">Syntax</span></span>  
  
```  
  
int srv_setcollen (  
SRV_PROC *  
srvproc  
,  
int   
column  
,  
int  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="62faf-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="62faf-106">Arguments</span></span>  
 <span data-ttu-id="62faf-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="62faf-107">*srvproc*</span></span>  
 <span data-ttu-id="62faf-108">Es un puntero a la estructura SRV_PROC que es el identificador de una conexión cliente determinada.</span><span class="sxs-lookup"><span data-stu-id="62faf-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="62faf-109">La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="62faf-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="62faf-110">*column*</span><span class="sxs-lookup"><span data-stu-id="62faf-110">*column*</span></span>  
 <span data-ttu-id="62faf-111">Indica el número de la columna para la que se especifica la longitud de datos.</span><span class="sxs-lookup"><span data-stu-id="62faf-111">Indicates the number of the column for which the data length is being specified.</span></span> <span data-ttu-id="62faf-112">Las columnas se numeran comenzando por 1.</span><span class="sxs-lookup"><span data-stu-id="62faf-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="62faf-113">*terminado*</span><span class="sxs-lookup"><span data-stu-id="62faf-113">*len*</span></span>  
 <span data-ttu-id="62faf-114">Indica la longitud, en bytes, de los datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="62faf-114">Indicates the length, in bytes, of the column data.</span></span> <span data-ttu-id="62faf-115">Una longitud de 0 indica que el valor de datos de la columna es NULL.</span><span class="sxs-lookup"><span data-stu-id="62faf-115">A length of 0 means the column data value is null.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="62faf-116">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="62faf-116">Returns</span></span>  
 <span data-ttu-id="62faf-117">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="62faf-117">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62faf-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="62faf-118">Remarks</span></span>  
 <span data-ttu-id="62faf-119">Cada columna de la fila se debe definir antes con **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="62faf-119">Each column of the row must first be defined with **srv_describe**.</span></span> <span data-ttu-id="62faf-120">La longitud de datos de columna se establece mediante la última llamada a **srv_describe** o **srv_setcollen**.</span><span class="sxs-lookup"><span data-stu-id="62faf-120">The column data length is set by the last call to **srv_describe** or **srv_setcollen**.</span></span> <span data-ttu-id="62faf-121">Si en una fila cambian los datos de longitud variable (datos terminados en NULL), se debe usar **srv_setcollen** para establecerlos en la nueva longitud antes de llamar a **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="62faf-121">If variable-length data (null-terminated data) changes for a row, **srv_setcollen** must be used to set it to the new length before calling **srv_sendrow**.</span></span> <span data-ttu-id="62faf-122">En una columna que permite valores NULL, es necesario llamar previamente a **srv_describe** con *desttype* establecido en un tipo de datos que permita valores NULL (como SRVINTN) y especificar datos NULL mediante una llamada a **srv_setcollen** con *len* establecido en 0.</span><span class="sxs-lookup"><span data-stu-id="62faf-122">For a column that allows null values, **srv_describe** must have been called with *desttype* set to a data type that allows nulls (like SRVINTN) and null data is specified by calling **srv_setcollen** with *len* set to 0.</span></span> <span data-ttu-id="62faf-123">Los datos de longitud cero no se pueden especificar mediante la API Procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="62faf-123">Zero length data cannot be specified using the Extended Stored Procedure API.</span></span>  
  
 <span data-ttu-id="62faf-124">Tenga en cuenta que si el tipo de datos de la columna es de longitud variable, no se comprueba *len*.</span><span class="sxs-lookup"><span data-stu-id="62faf-124">Note that when the data type of the column is variable-length, *len* is not checked.</span></span> <span data-ttu-id="62faf-125">Esta función devuelve FAIL si se llama en una columna de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="62faf-125">This function returns FAIL if called for a fixed-length column.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="62faf-126">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="62faf-126">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="62faf-127">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="62faf-127">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62faf-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62faf-128">See Also</span></span>  
 [<span data-ttu-id="62faf-129">srv_describe &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="62faf-129">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
