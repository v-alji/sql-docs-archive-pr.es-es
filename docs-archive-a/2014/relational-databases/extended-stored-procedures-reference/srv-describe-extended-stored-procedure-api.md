---
title: srv_describe (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_describe
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_describe
ms.assetid: 2115600e-5ce7-4be0-9cd3-a1dd1fab0729
author: rothja
ms.author: jroth
ms.openlocfilehash: 52a397b79f4fcecaa2ccacde7500cb852ae793fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677105"
---
# <a name="srv_describe-extended-stored-procedure-api"></a><span data-ttu-id="b1ac5-102">srv_describe (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="b1ac5-102">srv_describe (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="b1ac5-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="b1ac5-104">Define el nombre de columna y los tipos de datos de origen y destino para una columna específica de una fila.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-104">Defines the column name and source and destination data types for a specific column in a row.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1ac5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1ac5-105">Syntax</span></span>  
  
```  
  
int srv_describe (  
SRV_PROC *  
srvproc  
,  
int  
colnumber  
,  
DBCHAR *  
column_name  
,  
int  
namelen  
,  
DBINT  
desttype  
,  
DBINT  
destlen  
,  
DBINT  
srctype  
,  
DBINT  
srclen  
,  
void *  
srcdata  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="b1ac5-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b1ac5-106">Arguments</span></span>  
 <span data-ttu-id="b1ac5-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="b1ac5-107">*srvproc*</span></span>  
 <span data-ttu-id="b1ac5-108">Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el cliente que envía la fila).</span><span class="sxs-lookup"><span data-stu-id="b1ac5-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the client sending the row).</span></span> <span data-ttu-id="b1ac5-109">La estructura contiene toda la información que la biblioteca de API Procedimiento almacenado extendido usa para administrar las comunicaciones y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-109">The structure contains all the information that the Extended Stored Procedure API library uses to manage communications and data between the application and the client.</span></span>  
  
 <span data-ttu-id="b1ac5-110">*colnumber*</span><span class="sxs-lookup"><span data-stu-id="b1ac5-110">*colnumber*</span></span>  
 <span data-ttu-id="b1ac5-111">No se admite actualmente.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-111">Is currently not supported.</span></span> <span data-ttu-id="b1ac5-112">Las columnas se deben describir en orden.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-112">Columns must be described in order.</span></span> <span data-ttu-id="b1ac5-113">Todas las columnas se deben describir antes de llamar a **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-113">All columns must be described before **srv_sendrow** is called.</span></span>  
  
 <span data-ttu-id="b1ac5-114">*column_name*</span><span class="sxs-lookup"><span data-stu-id="b1ac5-114">*column_name*</span></span>  
 <span data-ttu-id="b1ac5-115">Especifica el nombre de la columna a la que pertenecen los datos.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-115">Specifies the name of the column to which the data belongs.</span></span> <span data-ttu-id="b1ac5-116">Este parámetro puede ser NULL porque no es preciso que una columna tenga nombre.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-116">This parameter can be NULL because a column is not required to have a name.</span></span>  
  
 <span data-ttu-id="b1ac5-117">*namelen*</span><span class="sxs-lookup"><span data-stu-id="b1ac5-117">*namelen*</span></span>  
 <span data-ttu-id="b1ac5-118">Especifica la longitud en bytes de *column_name*.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-118">Specifies the length, in bytes, of *column_name*.</span></span> <span data-ttu-id="b1ac5-119">Si *namelen* es SRV_NULLTERM, *column_name* debe terminar en NULL.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-119">If *namelen* is SRV_NULLTERM, then *column_name* must be null-terminated.</span></span>  
  
 <span data-ttu-id="b1ac5-120">*desttype*</span><span class="sxs-lookup"><span data-stu-id="b1ac5-120">*desttype*</span></span>  
 <span data-ttu-id="b1ac5-121">Especifica el tipo de datos de la columna de fila de destino.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-121">Specifies the data type of the destination row column.</span></span> <span data-ttu-id="b1ac5-122">Éste es el tipo de datos que se envía al cliente.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-122">This is the data type sent to the client.</span></span> <span data-ttu-id="b1ac5-123">Se debe especificar el tipo de datos aunque los datos sean NULL; para más información, vea [Data Types &#40;Extended Stored Procedure API&#41; (Tipos de datos &#40;API de procedimiento almacenado extendido&#41;)](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="b1ac5-123">The data type must be specified even if the data is NULL, for more information, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="b1ac5-124">*destlen*</span><span class="sxs-lookup"><span data-stu-id="b1ac5-124">*destlen*</span></span>  
 <span data-ttu-id="b1ac5-125">Especifica la longitud, en bytes, de los datos que se envían al cliente.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-125">Specifies the length, in bytes, of the data to be sent to the client.</span></span> <span data-ttu-id="b1ac5-126">En los tipos de datos de longitud fija que no permiten valores NULL, *destlen* se omite.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-126">For fixed-length data types that do not allow null values, *destlen* is ignored.</span></span> <span data-ttu-id="b1ac5-127">En los tipos de datos de longitud variable y los tipos de datos de longitud fija que permiten valores NULL, *destlen* especifica la longitud máxima de los datos de destino.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-127">For variable-length data types and fixed-length data types that allow null values, *destlen* specifies the maximum length the destination data can be.</span></span>  
  
 <span data-ttu-id="b1ac5-128">*srctype*</span><span class="sxs-lookup"><span data-stu-id="b1ac5-128">*srctype*</span></span>  
 <span data-ttu-id="b1ac5-129">Especifica el tipo de datos de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-129">Specifies the data type of the source data.</span></span>  
  
 <span data-ttu-id="b1ac5-130">*srclen*</span><span class="sxs-lookup"><span data-stu-id="b1ac5-130">*srclen*</span></span>  
 <span data-ttu-id="b1ac5-131">Especifica la longitud en bytes de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-131">Specifies the length, in bytes, of the source data.</span></span> <span data-ttu-id="b1ac5-132">Este valor se pasa por alto en los tipos de datos de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-132">This value is ignored for fixed-length data types.</span></span>  
  
 <span data-ttu-id="b1ac5-133">*srcdata*</span><span class="sxs-lookup"><span data-stu-id="b1ac5-133">*srcdata*</span></span>  
 <span data-ttu-id="b1ac5-134">Proporciona la dirección de los datos de origen para una columna determinada.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-134">Provides the source data address for a particular column.</span></span> <span data-ttu-id="b1ac5-135">Cuando se llama a **srv_sendrow**, busca los datos de *colnumber* en *srcdata*.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-135">When **srv_sendrow** is called, it looks for the data for *colnumber* at *srcdata*.</span></span> <span data-ttu-id="b1ac5-136">Por consiguiente, no se debería liberar antes de llamar a **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-136">Therefore it should not be freed before a call to **srv_sendrow**.</span></span> <span data-ttu-id="b1ac5-137">La dirección de los datos de origen se puede cambiar entre las llamadas a **srv_sendrow** mediante **srv_setcoldata**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-137">The source data address can be changed between calls to **srv_sendrow** by using **srv_setcoldata**.</span></span> <span data-ttu-id="b1ac5-138">La memoria asignada a *srcdata* no se debe liberar hasta que los datos de la columna se sustituyan por otra llamada a **srv_setcoldata**, o hasta que se realice una llamada a **srv_senddone**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-138">Memory allocated for *srcdata* should not be freed until the column data is replaced by another call to **srv_setcoldata**, or until **srv_senddone** is called.</span></span>  
  
 <span data-ttu-id="b1ac5-139">Si *desttype* es SRVDECIMAL o SRVNUMERIC, el parámetro *srcdata* debe ser un puntero a una estructura DBNUMERIC o DBDECIMAL con los campos de escala y precisión de la estructura ya establecidos en los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-139">If *desttype* is SRVDECIMAL or SRVNUMERIC, the *srcdata* parameter must be a pointer to a DBNUMERIC or DBDECIMAL structure with the precision and scale fields of the structure already set to the values you want.</span></span> <span data-ttu-id="b1ac5-140">Puede usar DEFAULTPRECISION para especificar una precisión predeterminada y DEFAULTSCALE para especificar una escala predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-140">You can use DEFAULTPRECISION to specify a default precision, and DEFAULTSCALE to specify a default scale.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="b1ac5-141">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="b1ac5-141">Returns</span></span>  
 <span data-ttu-id="b1ac5-142">El número de la columna descrita.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-142">The number of the column described.</span></span> <span data-ttu-id="b1ac5-143">La primera columna es la columna 1.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-143">The first column is column 1.</span></span> <span data-ttu-id="b1ac5-144">Si se produce un error, devuelve 0.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-144">If an error occurs, returns 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1ac5-145">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b1ac5-145">Remarks</span></span>  
 <span data-ttu-id="b1ac5-146">Se debe llamar a la función **srv_describe** una vez por cada columna de la fila antes de realizar la primera llamada a **srv_sendrow**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-146">The **srv_describe** function must be called once for each column in the row before the first call to **srv_sendrow**.</span></span> <span data-ttu-id="b1ac5-147">Las columnas de una fila se pueden describir en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-147">The columns of a row can be described in any order.</span></span>  
  
 <span data-ttu-id="b1ac5-148">Para cambiar la ubicación y la longitud de los datos de origen en las filas de columna antes de que se haya enviado el conjunto de resultados completo, use **srv_setcoldata** y **srv_setcollen**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-148">To change the location and length of the source data in column rows before the complete result set has been sent, use **srv_setcoldata** and **srv_setcollen**, respectively.</span></span>  
  
 <span data-ttu-id="b1ac5-149">Para obtener una descripción de tipos de datos y conversiones de tipos de datos de API de procedimiento almacenado extendido, vea [Data Types &#40;Extended Stored Procedure API&#41; (Tipos de datos &#40;API de procedimiento almacenado extendido&#41;)](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="b1ac5-149">For a description of data types and Extended Store Procedure API data type conversions, see[Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="b1ac5-150">Si el nombre de columna de la aplicación se encuentra en formato Unicode, debe convertirlo a la página de códigos multibyte del servidor antes de llamar a **srv_describe**.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-150">If the column name in your application is in Unicode, you need to convert it to the multibyte code page of the server before calling **srv_describe**.</span></span> <span data-ttu-id="b1ac5-151">Para obtener más información, vea [datos Unicode y páginas de códigos de servidor](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="b1ac5-151">For more information, see [Unicode Data and Server Code Pages](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b1ac5-152">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="b1ac5-152">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="b1ac5-153">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="b1ac5-153">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1ac5-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1ac5-154">See Also</span></span>  
 <span data-ttu-id="b1ac5-155">[srv_sendrow API de procedimiento almacenado extendido &#40;&#41;](srv-sendrow-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="b1ac5-155">[srv_sendrow &#40;Extended Stored Procedure API&#41;](srv-sendrow-extended-stored-procedure-api.md) </span></span>  
 <span data-ttu-id="b1ac5-156">[srv_setutype API de procedimiento almacenado extendido &#40;&#41;](srv-setutype-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="b1ac5-156">[srv_setutype &#40;Extended Stored Procedure API&#41;](srv-setutype-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="b1ac5-157">srv_setcoldata &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="b1ac5-157">srv_setcoldata &#40;Extended Stored Procedure API&#41;</span></span>](srv-setcoldata-extended-stored-procedure-api.md)  
  
  
