---
title: conversiones de tipos de datos de fecha y hora (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- conversions [ODBC]
- bindings [ODBC]
- ODBC, bindings and conversions
ms.assetid: 66b9d282-c88d-40e5-93c2-fd5499a74458
author: rothja
ms.author: jroth
ms.openlocfilehash: 142e4388cb87055ddbc6faa7d5b1a92a627738c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675327"
---
# <a name="datetime-data-type-conversions-odbc"></a><span data-ttu-id="4013e-102">Conversiones del tipo de datos de fecha y hora (ODBC)</span><span class="sxs-lookup"><span data-stu-id="4013e-102">datetime Data Type Conversions (ODBC)</span></span>
  <span data-ttu-id="4013e-103">Las conversiones siguientes ya están definidas por ODBC o son una extensión coherente de ODBC.</span><span class="sxs-lookup"><span data-stu-id="4013e-103">The following conversions are either already defined by ODBC or are a consistent extension of ODBC.</span></span> <span data-ttu-id="4013e-104">La comunidad atendida por el proveedor determina las conversiones proporcionadas por cada proveedor y, a consecuencia de ello, hay incoherencias a menudo entre los proveedores.</span><span class="sxs-lookup"><span data-stu-id="4013e-104">The conversions supplied by each provider are determined by the community served by the provider, and there are often inconsistencies between providers as a result.</span></span> <span data-ttu-id="4013e-105">Los valores entre corchetes son opcionales.</span><span class="sxs-lookup"><span data-stu-id="4013e-105">Values in square brackets are optional.</span></span>  
  
-   <span data-ttu-id="4013e-106">El formato de las cadenas de fecha y hora es 'aaaa-mm-dd [hh:mm:ss [,9999999] [más/menos hh:mm]]'</span><span class="sxs-lookup"><span data-stu-id="4013e-106">The format of datetime strings is 'yyyy-mm-dd[ hh:mm:ss[.9999999][ plus/minus hh:mm]]'</span></span>  
  
-   <span data-ttu-id="4013e-107">El formato de las cadenas de hora es 'hh:mm:ss [,9999999]'</span><span class="sxs-lookup"><span data-stu-id="4013e-107">The format of time strings is 'hh:mm:ss[.9999999]'</span></span>  
  
-   <span data-ttu-id="4013e-108">El formato de las cadenas de fecha es 'aaaa-mm-dd'</span><span class="sxs-lookup"><span data-stu-id="4013e-108">The format of date strings is 'yyyy-mm-dd'</span></span>  
  
 <span data-ttu-id="4013e-109">Las conversiones de las cadenas permiten flexibilidad en los espacios en blanco y el ancho de campo.</span><span class="sxs-lookup"><span data-stu-id="4013e-109">Conversions from strings allow flexibility in white space and field width.</span></span> <span data-ttu-id="4013e-110">Para obtener más información, vea la sección "formatos de datos: cadenas y literales" del [tipo de datos compatibilidad con las mejoras de fecha y hora de ODBC](data-type-support-for-odbc-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="4013e-110">For more information, see the "Data Formats: Strings and Literals" section of [Data Type Support for ODBC Date and Time Improvements](data-type-support-for-odbc-date-and-time-improvements.md).</span></span>  
  
 <span data-ttu-id="4013e-111">A continuación figuran las reglas de conversión generales:</span><span class="sxs-lookup"><span data-stu-id="4013e-111">The following are general conversion rules:</span></span>  
  
-   <span data-ttu-id="4013e-112">Si no está presente la hora pero el receptor puede almacenar la hora, esta última se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="4013e-112">If no time is present but the receiver can store time, the time is set to zero.</span></span>  
  
-   <span data-ttu-id="4013e-113">Si no está presente la fecha pero el receptor puede almacenar fechas, se utiliza la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="4013e-113">If no date is present but the receiver can store date, the current date is used.</span></span>  
  
-   <span data-ttu-id="4013e-114">Si no está presente la zona horaria en el tipo de datos que el cliente utiliza pero el servidor puede almacenar la zona horaria, se almacena la fecha en la zona horaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="4013e-114">If no timezone is present in the data type that the client is using but the server can store timezone, the date is stored in the client timezone.</span></span> <span data-ttu-id="4013e-115">Observe que esto difiere del comportamiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="4013e-115">Note that this differs from the server behavior.</span></span>  
  
-   <span data-ttu-id="4013e-116">Si no está presente la zona horaria en el tipo de servidor pero el tipo de cliente tiene una zona horaria, la hora se convierte en UTC antes de almacenarse en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4013e-116">If no timezone is present in the server type but the client type has a timezone, time is converted to UTC before being stored on the server.</span></span>  
  
-   <span data-ttu-id="4013e-117">Si está presente la hora pero el receptor no puede almacenar la hora, se omite el componente de hora.</span><span class="sxs-lookup"><span data-stu-id="4013e-117">If time is present but the receiver cannot store time, the time component is ignored.</span></span>  
  
-   <span data-ttu-id="4013e-118">Si está presente la fecha pero el receptor no puede almacenar la fecha, se omite el componente de fecha.</span><span class="sxs-lookup"><span data-stu-id="4013e-118">If a date is present but the receiver cannot store the date, the date component is ignored.</span></span>  
  
-   <span data-ttu-id="4013e-119">Si se produce una truncación de segundos o fracciones de segundo al convertir de C a SQL, se genera un registro de diagnóstico con SQLSTATE 22008 y el mensaje "Desbordamiento del campo DateTime".</span><span class="sxs-lookup"><span data-stu-id="4013e-119">If truncation of seconds or fractional seconds occurs when converting from C to SQL, a diagnostic record is generated with SQLSTATE 22008 and the message "Datetime field overflow".</span></span>  
  
-   <span data-ttu-id="4013e-120">Si se produce una truncación de segundos o fracciones de segundo al convertir de SQL a C, se genera un registro de diagnóstico con SQLSTATE 01S07 y el mensaje "Truncamiento fraccionario".</span><span class="sxs-lookup"><span data-stu-id="4013e-120">If truncation of seconds or fractional seconds occurs when converting from SQL to C, a diagnostic record is generated with SQLSTATE 01S07 and the message "Fractional truncation".</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4013e-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4013e-121">In This Section</span></span>  
 [<span data-ttu-id="4013e-122">Conversiones de C a SQL</span><span class="sxs-lookup"><span data-stu-id="4013e-122">Conversions from C to SQL</span></span>](datetime-data-type-conversions-from-c-to-sql.md)  
 <span data-ttu-id="4013e-123">Se enumeran los problemas a tener en cuenta al convertir de tipos de C a tipos de fecha y hora de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4013e-123">Lists issues to consider when you convert from C types to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data/time types.</span></span>  
  
 [<span data-ttu-id="4013e-124">Conversiones de SQL a C</span><span class="sxs-lookup"><span data-stu-id="4013e-124">Conversions from SQL to C</span></span>](datetime-data-type-conversions-from-sql-to-c.md)  
 <span data-ttu-id="4013e-125">Se enumeran los problemas a tener en cuenta al convertir de tipos de fecha y hora de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a tipos de C.</span><span class="sxs-lookup"><span data-stu-id="4013e-125">Lists issues to consider when you convert from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data/time types to C types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4013e-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4013e-126">See Also</span></span>  
 [<span data-ttu-id="4013e-127">Mejoras de fecha y hora &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="4013e-127">Date and Time Improvements &#40;ODBC&#41;</span></span>](date-and-time-improvements-odbc.md)  
  
  
