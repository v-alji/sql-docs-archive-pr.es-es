---
title: srv_convert (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_convert
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_convert
ms.assetid: 216b4a31-786e-4361-8a33-e5f6e9790f90
author: rothja
ms.author: jroth
ms.openlocfilehash: 30a0ea356f017ed3d1b3ecc85cf483b4553e120a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677106"
---
# <a name="srv_convert-extended-stored-procedure-api"></a><span data-ttu-id="ad719-102">srv_convert (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="ad719-102">srv_convert (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="ad719-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ad719-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="ad719-104">Cambia los datos de un tipo de datos a otro.</span><span class="sxs-lookup"><span data-stu-id="ad719-104">Changes data from one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad719-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad719-105">Syntax</span></span>  
  
```  
  
int srv_convert (  
SRV_PROC *  
srvproc  
,  
int  
srctype  
,  
void *  
src  
,  
DBINT  
srclen  
,  
int  
desttype  
,  
void *  
dest  
,  
DBINT  
destlen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="ad719-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ad719-106">Arguments</span></span>  
 <span data-ttu-id="ad719-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="ad719-107">*srvproc*</span></span>  
 <span data-ttu-id="ad719-108">Es un puntero a la estructura SRV_PROC que es el identificador de una conexión cliente determinada.</span><span class="sxs-lookup"><span data-stu-id="ad719-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="ad719-109">La estructura contiene toda la información de control que Procedimiento almacenado extendido usa para administrar las comunicaciones y los datos entre la aplicación y el cliente.</span><span class="sxs-lookup"><span data-stu-id="ad719-109">The structure contains all the control information that the Extended Stored Procedure API uses to manage communications and data between the application and the client.</span></span> <span data-ttu-id="ad719-110">Si se proporciona el identificador *srvproc*, se pasa a la función del controlador de errores de la API de procedimiento almacenado extendido cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="ad719-110">If the *srvproc* handle is supplied, it is passed to the Extended Stored Procedure API error handler function when an error occurs.</span></span>  
  
 <span data-ttu-id="ad719-111">*srctype*</span><span class="sxs-lookup"><span data-stu-id="ad719-111">*srctype*</span></span>  
 <span data-ttu-id="ad719-112">Especifica el tipo de datos de los datos que se van a convertir.</span><span class="sxs-lookup"><span data-stu-id="ad719-112">Specifies the data type of the data to be converted.</span></span> <span data-ttu-id="ad719-113">Este parámetro puede ser cualquiera de los tipos de datos de API Procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="ad719-113">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="ad719-114">*src*</span><span class="sxs-lookup"><span data-stu-id="ad719-114">*src*</span></span>  
 <span data-ttu-id="ad719-115">Es un puntero a los datos que se van a convertir.</span><span class="sxs-lookup"><span data-stu-id="ad719-115">Is a pointer to the data to be converted.</span></span> <span data-ttu-id="ad719-116">Este parámetro puede ser cualquiera de los tipos de datos de API Procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="ad719-116">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="ad719-117">*srclen*</span><span class="sxs-lookup"><span data-stu-id="ad719-117">*srclen*</span></span>  
 <span data-ttu-id="ad719-118">Especifica la longitud, en bytes, de los datos que se van a convertir.</span><span class="sxs-lookup"><span data-stu-id="ad719-118">Specifies the length, in bytes, of the data to be converted.</span></span> <span data-ttu-id="ad719-119">Si *srclen* es 0, **srv_convert** coloca un valor NULL en la variable de destino.</span><span class="sxs-lookup"><span data-stu-id="ad719-119">If *srclen* is 0, **srv_convert** places a null value in the destination variable.</span></span> <span data-ttu-id="ad719-120">A menos que sea 0, los tipos de datos de longitud fija pasan por alto este parámetro, en cuyo caso se supone que los datos de origen son NULL.</span><span class="sxs-lookup"><span data-stu-id="ad719-120">Unless it is 0, this parameter is ignored for fixed-length data types, in which case the source data is assumed to be NULL.</span></span> <span data-ttu-id="ad719-121">Para los datos del tipo de datos SRVCHAR, una longitud de -1 indica que la cadena termina en NULL.</span><span class="sxs-lookup"><span data-stu-id="ad719-121">For data of the SRVCHAR data type, a length of -1 indicates the string is null-terminated.</span></span>  
  
 <span data-ttu-id="ad719-122">*desttype*</span><span class="sxs-lookup"><span data-stu-id="ad719-122">*desttype*</span></span>  
 <span data-ttu-id="ad719-123">Especifica el tipo de datos para convertir el origen.</span><span class="sxs-lookup"><span data-stu-id="ad719-123">Specifies the data type to convert the source to.</span></span> <span data-ttu-id="ad719-124">Este parámetro puede ser cualquiera de los tipos de datos de API Procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="ad719-124">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="ad719-125">*dest*</span><span class="sxs-lookup"><span data-stu-id="ad719-125">*dest*</span></span>  
 <span data-ttu-id="ad719-126">Es un puntero a la variable de destino que recibe los datos convertidos.</span><span class="sxs-lookup"><span data-stu-id="ad719-126">Is a pointer to the destination variable that receives converted data.</span></span> <span data-ttu-id="ad719-127">Si este puntero es NULL, **srv_convert** llama al controlador de errores proporcionado por el usuario, si lo hubiera, y devuelve -1.</span><span class="sxs-lookup"><span data-stu-id="ad719-127">If this pointer is NULL, **srv_convert** calls the user-supplied error handler ,if any, and returns -1.</span></span>  
  
 <span data-ttu-id="ad719-128">Si *desttype* es SRVDECIMAL o SRVNUMERIC, el parámetro *dest* debe ser un puntero a una estructura DBNUMERIC o DBDECIMAL con los campos de escala y precisión de la estructura ya establecidos en los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="ad719-128">If *desttype* is SRVDECIMAL or SRVNUMERIC, the *dest* parameter must be a pointer to a DBNUMERIC or DBDECIMAL structure with the precision and scale fields of the structure already set to the desired values.</span></span> <span data-ttu-id="ad719-129">Puede usar DEFAULTPRECISION para especificar una precisión predeterminada y DEFAULTSCALE para especificar una escala predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ad719-129">You can use DEFAULTPRECISION to specify a default precision, and DEFAULTSCALE to specify a default scale.</span></span>  
  
 <span data-ttu-id="ad719-130">*destlen*</span><span class="sxs-lookup"><span data-stu-id="ad719-130">*destlen*</span></span>  
 <span data-ttu-id="ad719-131">Especifica la longitud, en bytes, de la variable de destino.</span><span class="sxs-lookup"><span data-stu-id="ad719-131">Specifies the length, in bytes, of the destination variable.</span></span> <span data-ttu-id="ad719-132">Este parámetro se pasa por alto en los tipos de datos de longitud fija.</span><span class="sxs-lookup"><span data-stu-id="ad719-132">This parameter is ignored for fixed-length data types.</span></span> <span data-ttu-id="ad719-133">Para una variable de destino de tipo SRVCHAR, el valor de *destlen* debe ser la longitud total del espacio en búfer de destino.</span><span class="sxs-lookup"><span data-stu-id="ad719-133">For a destination variable of type SRVCHAR, the value of *destlen* must be the total length of the destination buffer space.</span></span> <span data-ttu-id="ad719-134">Una longitud de -1 para una variable de destino de tipo SRVCHAR o SRVBINARY indica que hay suficiente espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="ad719-134">A length of -1 for a destination variable of type SRVCHAR or SRVBINARY indicates there is sufficient space available.</span></span> <span data-ttu-id="ad719-135">Para una variable de destino de tipo *srvchar*, una longitud de -1 hace que la cadena de caracteres termine en NULL.</span><span class="sxs-lookup"><span data-stu-id="ad719-135">For a destination variable of type *srvchar*, a length of -1 causes the character string to be null-terminated.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="ad719-136">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="ad719-136">Returns</span></span>  
 <span data-ttu-id="ad719-137">La longitud de los datos convertidos, en bytes, si la conversión de tipos de datos es correcta.</span><span class="sxs-lookup"><span data-stu-id="ad719-137">The length of the converted data, in bytes, if the data type conversion succeeds.</span></span> <span data-ttu-id="ad719-138">Cuando **srv_convert** encuentra una solicitud de conversión que no admite, llama al controlador de errores proporcionado por el desarrollador, si lo hubiera, establece un número de error global y devuelve -1.</span><span class="sxs-lookup"><span data-stu-id="ad719-138">When **srv_convert** encounters a request for a conversion it does not support, it calls the developer-supplied error handler, if any, sets a global error number, and returns -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad719-139">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ad719-139">Remarks</span></span>  
 <span data-ttu-id="ad719-140">La función **srv_willconvert** determina si se permite una conversión determinada.</span><span class="sxs-lookup"><span data-stu-id="ad719-140">The **srv_willconvert** function determines whether a particular conversion is allowed.</span></span>  
  
 <span data-ttu-id="ad719-141">La conversión a los tipos de datos numéricos aproximados SRVFLT4 o SRVFLT8 puede producir alguna pérdida de precisión.</span><span class="sxs-lookup"><span data-stu-id="ad719-141">Converting to the approximate numeric data types SRVFLT4 or SRVFLT8 can result in some loss of precision.</span></span> <span data-ttu-id="ad719-142">La conversión de los tipos de datos numéricos aproximados SRVFLT4 o SRVFLT8 a SRVCHAR o SRVTEXT también puede producir alguna pérdida de precisión.</span><span class="sxs-lookup"><span data-stu-id="ad719-142">Converting from the approximate numeric data types SRVFLT4 or SRVFLT8 to SRVCHAR or SRVTEXT can also result in some loss of precision.</span></span>  
  
 <span data-ttu-id="ad719-143">La conversión a SRVFLT*x*, SRVINT*x*, SRVMONEY, SRVMONEY4, SRVDECIMAL o SRVNUMERIC puede producir un desbordamiento si el número es mayor que el valor máximo del destino, o un subdesbordamiento si el número es menor que el valor mínimo del destino.</span><span class="sxs-lookup"><span data-stu-id="ad719-143">Converting to SRVFLT*x*, SRVINT*x*, SRVMONEY, SRVMONEY4, SRVDECIMAL, or SRVNUMERIC can result in overflow if the number is larger than the maximum value of the destination, or in underflow if the number is smaller than the minimum value of the destination.</span></span> <span data-ttu-id="ad719-144">Si el desbordamiento se produce al convertir a SRVCHAR o SRVTEXT, el primer carácter del valor resultante contiene un asterisco (\*) que indica el error.</span><span class="sxs-lookup"><span data-stu-id="ad719-144">If overflow occurs when converting to SRVCHAR or SRVTEXT, the first character of the resulting value contains an asterisk (\*) to indicate the error.</span></span>  
  
 <span data-ttu-id="ad719-145">Al convertir SRVCHAR en SRVBINARY, **srv_convert** interpreta SRVCHAR como hexadecimal, tanto si la cadena contiene un 0 inicial como si no.</span><span class="sxs-lookup"><span data-stu-id="ad719-145">When converting SRVCHAR to SRVBINARY, **srv_convert** interprets SRVCHAR as hexadecimal, whether or not the string contains a leading 0.</span></span> <span data-ttu-id="ad719-146">Al convertir SRVBINARY en SRVCHAR, **srv_convert** crea una cadena hexadecimal sin un 0 inicial.</span><span class="sxs-lookup"><span data-stu-id="ad719-146">When converting SRVBINARY to SRVCHAR, **srv_convert** creates a hexadecimal string without a leading 0.</span></span> <span data-ttu-id="ad719-147">En todos los otros casos, una conversión a o desde el tipo de datos SRVBINARY es una copia de bits directa.</span><span class="sxs-lookup"><span data-stu-id="ad719-147">In all other cases, a conversion to or from the SRVBINARY data type is a straight bit-copy.</span></span>  
  
 <span data-ttu-id="ad719-148">En ciertos casos, puede ser útil para convertir un tipo de datos en sí mismo.</span><span class="sxs-lookup"><span data-stu-id="ad719-148">In certain cases, it can be useful to convert a data type to itself.</span></span> <span data-ttu-id="ad719-149">Por ejemplo, al convertir SRVCHAR en SRVCHAR con un valor *destlen* de -1, se agrega un terminador NULL a una cadena.</span><span class="sxs-lookup"><span data-stu-id="ad719-149">For example, converting SRVCHAR to SRVCHAR with a *destlen* of -1 adds a null terminator to a string.</span></span>  
  
 <span data-ttu-id="ad719-150">Para obtener una descripción de tipos de datos y conversiones de tipos de datos de API de procedimiento almacenado extendido, vea [Data Types &#40;Extended Stored Procedure API&#41; (Tipos de datos &#40;API de procedimiento almacenado extendido&#41;)](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="ad719-150">For a description of data types and Extended Store Procedure API data type conversions, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="ad719-151">Se puede producir un error en la función **srv_convert** por varias razones:</span><span class="sxs-lookup"><span data-stu-id="ad719-151">The **srv_convert** function can fail for several reasons:</span></span>  
  
-   <span data-ttu-id="ad719-152">La conversión solicitada no está disponible.</span><span class="sxs-lookup"><span data-stu-id="ad719-152">The requested conversion is not available.</span></span>  
  
-   <span data-ttu-id="ad719-153">La conversión producía el truncamiento, desbordamiento o pérdida de precisión en la variable de destino.</span><span class="sxs-lookup"><span data-stu-id="ad719-153">The conversion resulted in truncation, overflow, or loss of precision in the destination variable.</span></span>  
  
-   <span data-ttu-id="ad719-154">Se produjo un error de sintaxis al convertir una cadena de caracteres en un tipo de datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="ad719-154">A syntax error occurred while converting a character string to a numeric data type.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ad719-155">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="ad719-155">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="ad719-156">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="ad719-156">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad719-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad719-157">See Also</span></span>  
 <span data-ttu-id="ad719-158">[srv_setutype API de procedimiento almacenado extendido &#40;&#41;](srv-setutype-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="ad719-158">[srv_setutype &#40;Extended Stored Procedure API&#41;](srv-setutype-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="ad719-159">srv_willconvert &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="ad719-159">srv_willconvert &#40;Extended Stored Procedure API&#41;</span></span>](srv-willconvert-extended-stored-procedure-api.md)  
  
  
