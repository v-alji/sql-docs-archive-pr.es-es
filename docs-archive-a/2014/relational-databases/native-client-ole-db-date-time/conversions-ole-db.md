---
title: Enlaces y conversiones (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- conversions [OLE DB]
- bindings [OLE DB]
- OLE DB, bindings and conversions
ms.assetid: c187df58-a8c8-4c74-a76f-663abbc5f0c1
author: rothja
ms.author: jroth
ms.openlocfilehash: 95c73bdad80b5f948a45235ad208ab307fcceff3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676500"
---
# <a name="bindings-and-conversions-ole-db"></a><span data-ttu-id="67677-102">Enlaces y conversiones (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="67677-102">Bindings and Conversions (OLE DB)</span></span>
  <span data-ttu-id="67677-103">En esta sección se describe cómo convertir entre los valores `datetime` y `datetimeoffset`.</span><span class="sxs-lookup"><span data-stu-id="67677-103">This section discusses how to convert between `datetime` and `datetimeoffset` values.</span></span> <span data-ttu-id="67677-104">OLE DB ya proporciona las conversiones descritas en esta sección o son una extensión coherente de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="67677-104">The conversions described in this section are either already provided by OLE DB or are a consistent extension of OLE DB.</span></span>  
  
 <span data-ttu-id="67677-105">El formato de literales y cadenas para las fechas y horas en OLE DB generalmente sigue la ISO y no depende de la configuración regional del cliente.</span><span class="sxs-lookup"><span data-stu-id="67677-105">The format of literals and strings for dates and times in OLE DB generally follows ISO, and is not dependent on the client locale.</span></span> <span data-ttu-id="67677-106">Una excepción es DBTYPE_DATE, donde la norma es OLE Automation.</span><span class="sxs-lookup"><span data-stu-id="67677-106">One exception is DBTYPE_DATE, where the standard is OLE Automation.</span></span> <span data-ttu-id="67677-107">Sin embargo, debido a que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client solamente convierte entre tipos cuando se transmiten datos a o desde el cliente, no hay ninguna manera de que una aplicación fuerce a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client a convertir entre DBTYPE_DATE y los formatos de cadena.</span><span class="sxs-lookup"><span data-stu-id="67677-107">However, because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client only converts between types when data is transmitted to or from the client, there is no way for an application to force [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client to convert between DBTYPE_DATE and string formats.</span></span> <span data-ttu-id="67677-108">De lo contrario, las cadenas usan los formatos siguientes (el texto entre corchetes indica un elemento opcional):</span><span class="sxs-lookup"><span data-stu-id="67677-108">Otherwise, strings use the following formats (text in brackets indicates an optional element):</span></span>  
  
-   <span data-ttu-id="67677-109">El formato de las cadenas `datetime` y `datetimeoffset` es:</span><span class="sxs-lookup"><span data-stu-id="67677-109">The format of `datetime` and `datetimeoffset` strings is:</span></span>  
  
     <span data-ttu-id="67677-110">*AAAA* - *mm* - *DD*[ *HH*:*mm*:*SS*[.\* 9999999\*] [??</span><span class="sxs-lookup"><span data-stu-id="67677-110">*yyyy*-*mm*-*dd*[ *hh*:*mm*:*ss*[.*9999999*][ ??</span></span> <span data-ttu-id="67677-111">*HH*:*mm*]]</span><span class="sxs-lookup"><span data-stu-id="67677-111">*hh*:*mm*]]</span></span>  
  
-   <span data-ttu-id="67677-112">El formato de las cadenas `time` es:</span><span class="sxs-lookup"><span data-stu-id="67677-112">The format of `time` strings is:</span></span>  
  
     <span data-ttu-id="67677-113">*hh*:*mm*:*ss*[.*9999999*]</span><span class="sxs-lookup"><span data-stu-id="67677-113">*hh*:*mm*:*ss*[.*9999999*]</span></span>  
  
-   <span data-ttu-id="67677-114">El formato de las cadenas `date` es:</span><span class="sxs-lookup"><span data-stu-id="67677-114">The format of `date` strings is:</span></span>  
  
     <span data-ttu-id="67677-115">*aaaa*-*mm*-*dd*</span><span class="sxs-lookup"><span data-stu-id="67677-115">*yyyy*-*mm*-*dd*</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67677-116">Las versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client y de las conversiones OLE implementadas SQLOLEDB, en caso de un error en las conversiones estándar.</span><span class="sxs-lookup"><span data-stu-id="67677-116">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client and SQLOLEDB implemented OLE conversions, in case standard conversions failed.</span></span> <span data-ttu-id="67677-117">Como resultado, algunas conversiones realizadas por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 y posteriores difieren de la especificación OLE DB.</span><span class="sxs-lookup"><span data-stu-id="67677-117">As a result, some conversions performed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 and later differ from the OLE DB specification.</span></span>  
  
 <span data-ttu-id="67677-118">Las conversiones de las cadenas permiten flexibilidad en los espacios en blanco y el ancho de campo.</span><span class="sxs-lookup"><span data-stu-id="67677-118">Conversions from strings allow flexibility in white space and field width.</span></span> <span data-ttu-id="67677-119">Para obtener más información, vea la sección "formatos de datos: cadenas y literales" en [compatibilidad con tipos de datos para obtener OLE DB mejoras de fecha y hora](data-type-support-for-ole-db-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="67677-119">For more information, see the "Data Formats: Strings and Literals" section in [Data Type Support for OLE DB Date and Time Improvements](data-type-support-for-ole-db-date-and-time-improvements.md).</span></span>  
  
 <span data-ttu-id="67677-120">A continuación figuran las reglas de conversión generales:</span><span class="sxs-lookup"><span data-stu-id="67677-120">The following are general conversion rules:</span></span>  
  
-   <span data-ttu-id="67677-121">Cuando una cadena se convierte en un tipo de fecha y hora, la cadena se analiza primero como literal ISO.</span><span class="sxs-lookup"><span data-stu-id="67677-121">When a string is converted to a date/time type, the string is first parsed as an ISO literal.</span></span> <span data-ttu-id="67677-122">Si no ocurre así, la cadena se analiza como literal de fecha OLE, que tiene componentes de hora.</span><span class="sxs-lookup"><span data-stu-id="67677-122">If this fails, the string is parsed as an OLE date literal, which has time components.</span></span>  
  
-   <span data-ttu-id="67677-123">Si no está presente la hora pero el receptor puede almacenar la hora, esta última se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="67677-123">If no time is present but the receiver can store time, the time is set to zero.</span></span> <span data-ttu-id="67677-124">Si no hay ninguna fecha presente pero el receptor puede almacenar una, la fecha se establece en la fecha actual cuando se usan conversiones ISO y en 1899-12-30, cuando se usan conversiones OLE.</span><span class="sxs-lookup"><span data-stu-id="67677-124">If no date is present but the receiver can store a date, the date is set to the current date when ISO conversions are used and to 1899-12-30 when OLE conversions are used.</span></span>  
  
-   <span data-ttu-id="67677-125">Si no hay ninguna zona horaria en el tipo de datos que el cliente usa pero el servidor puede almacenar la zona horaria, se supone que los datos del cliente se encuentran en la zona horaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="67677-125">If no timezone is present in the data type that the client is using, but the server can store timezone, the data on the client is assumed to be in the client timezone.</span></span>  
  
-   <span data-ttu-id="67677-126">Si no hay ninguna zona horaria en el servidor pero el cliente tiene información de la zona horaria, se presupone la zona horaria UTC.</span><span class="sxs-lookup"><span data-stu-id="67677-126">If no timezone is present at the server but the client has timezone information, the UTC timezone is assumed.</span></span> <span data-ttu-id="67677-127">Este comportamiento es diferente al del servidor.</span><span class="sxs-lookup"><span data-stu-id="67677-127">This differs from server behavior.</span></span>  
  
-   <span data-ttu-id="67677-128">Si está presente la hora pero el receptor no puede almacenarla, se omite el componente de hora.</span><span class="sxs-lookup"><span data-stu-id="67677-128">If the time is present but the receiver cannot store time, the time component is ignored.</span></span>  
  
-   <span data-ttu-id="67677-129">Si está presente la fecha pero el receptor no puede almacenarla, se omite el componente de fecha.</span><span class="sxs-lookup"><span data-stu-id="67677-129">If the date is present but the receiver cannot store the date, the date component is ignored.</span></span>  
  
-   <span data-ttu-id="67677-130">Si se produce el truncamiento de segundos o fracciones de segundo al convertir de cliente a servidor, se devuelve DB_E_ERRORSOCCURRED y se establece el estado DBSTATUS_E_DATAOVERFLOW.</span><span class="sxs-lookup"><span data-stu-id="67677-130">If truncation of seconds or fractional seconds occurs when converting from client to server, DB_E_ERRORSOCCURRED is returned and the status DBSTATUS_E_DATAOVERFLOW is set.</span></span>  
  
-   <span data-ttu-id="67677-131">Si el truncamiento de segundos o fracciones de segundo se produce al convertir del servidor al cliente, se establece DBSTATUS_S_TRUNCATED.</span><span class="sxs-lookup"><span data-stu-id="67677-131">If truncation of seconds or fractional seconds occurs when converting from server to client, DBSTATUS_S_TRUNCATED is set</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="67677-132">En esta sección</span><span class="sxs-lookup"><span data-stu-id="67677-132">In This Section</span></span>  
 [<span data-ttu-id="67677-133">Conversiones realizadas de cliente a servidor</span><span class="sxs-lookup"><span data-stu-id="67677-133">Conversions Performed from Client to Server</span></span>](conversions-performed-from-client-to-server.md)  
 <span data-ttu-id="67677-134">Describe las conversiones de fecha y hora realizadas entre una aplicación cliente escrita con OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client y [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (o posterior).</span><span class="sxs-lookup"><span data-stu-id="67677-134">Describes date/time conversions performed between a client application written with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later).</span></span>  
  
 [<span data-ttu-id="67677-135">Conversiones realizadas de servidor a cliente</span><span class="sxs-lookup"><span data-stu-id="67677-135">Conversions Performed from Server to Client</span></span>](conversions-performed-from-server-to-client.md)  
 <span data-ttu-id="67677-136">Describe las conversiones de fecha y hora realizadas entre [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (o posterior) y una aplicación cliente escrita con OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="67677-136">Describes date/time conversions performed between [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later) and a client application written with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67677-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67677-137">See Also</span></span>  
 [<span data-ttu-id="67677-138">Mejoras de fecha y hora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="67677-138">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
