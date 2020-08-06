---
title: Mejoras de fecha y hora (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- date/time [ODBC]
- ODBC, date/time improvements
ms.assetid: e31d5ca5-2103-498f-954c-1ee93e217186
author: rothja
ms.author: jroth
ms.openlocfilehash: 6ce8f906fc1949a80bfa8e5a541ecf1e83878775
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672934"
---
# <a name="date-and-time-improvements-odbc"></a><span data-ttu-id="335dc-102">Mejoras en la fecha y la hora (ODBC)</span><span class="sxs-lookup"><span data-stu-id="335dc-102">Date and Time Improvements (ODBC)</span></span>
  [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="335dc-103">ha introducido nuevos tipos de datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="335dc-103">introduced new date and time data types.</span></span> <span data-ttu-id="335dc-104">En esta sección se describe la forma en que estos nuevos tipos se exponen como extensiones en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client. </span><span class="sxs-lookup"><span data-stu-id="335dc-104">This section describes how these new types are exposed as extensions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="335dc-105">Para obtener información general de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] la compatibilidad de Native Client con los nuevos tipos de datos de fecha y hora, vea [mejoras de fecha y hora](../native-client/features/date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="335dc-105">For an overview of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client support for the new date and time data types, see [Date and Time Improvements](../native-client/features/date-and-time-improvements.md).</span></span> <span data-ttu-id="335dc-106">Para obtener un ejemplo que muestra la compatibilidad de fecha y hora de ODBC, vea [usar tipos de fecha y hora](../native-client-odbc-how-to/use-date-and-time-types.md).</span><span class="sxs-lookup"><span data-stu-id="335dc-106">For a sample demonstrating ODBC date/time support, see [Use Date and Time Types](../native-client-odbc-how-to/use-date-and-time-types.md).</span></span>  
  
 <span data-ttu-id="335dc-107">Para obtener más información general sobre los tipos de datos de fecha y hora, consulte [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="335dc-107">For more general information about date and time data types, see [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="335dc-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="335dc-108">In This Section</span></span>  
 [<span data-ttu-id="335dc-109">Compatibilidad con tipos de datos para mejoras de fecha y hora de ODBC</span><span class="sxs-lookup"><span data-stu-id="335dc-109">Data Type Support for ODBC Date and Time Improvements</span></span>](../../relational-databases/native-client-odbc-date-time/data-type-support-for-odbc-date-and-time-improvements.md)  
 <span data-ttu-id="335dc-110">Proporciona información sobre los tipos ODBC que admiten tipos de fecha y hora de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="335dc-110">Provides information about ODBC types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span>  
  
 [<span data-ttu-id="335dc-111">Metadatos &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="335dc-111">Metadata &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/metadata-odbc.md)  
 <span data-ttu-id="335dc-112">Describe información devuelta en los campos del descriptor de parámetro de implementación (IPD) y el descriptor de fila de implementación (IRD), así como los metadatos de columna devueltos por `SQLColumns` y `SQLProcedureColumns`.</span><span class="sxs-lookup"><span data-stu-id="335dc-112">Describes information returned in the implementation parameter descriptor (IPD) and implementation row descriptor (IRD) fields, as well as column metadata returned by `SQLColumns` and `SQLProcedureColumns`.</span></span> <span data-ttu-id="335dc-113">También describe metadatos de tipo de datos devueltos por `SQLGetTypeInfo`.</span><span class="sxs-lookup"><span data-stu-id="335dc-113">Also describes data type metadata returned by `SQLGetTypeInfo`.</span></span>  
  
 [<span data-ttu-id="335dc-114">conversiones de tipos de datos datetime &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="335dc-114">datetime Data Type Conversions &#40;ODBC&#41;</span></span>](datetime-data-type-conversions-odbc.md)  
 <span data-ttu-id="335dc-115">Describe cómo convertir entre valores datetime y datetimeoffset.</span><span class="sxs-lookup"><span data-stu-id="335dc-115">Describes how to convert between datetime and datetimeoffset values.</span></span>  
  
 [<span data-ttu-id="335dc-116">Compatibilidad con sql_variant para tipos de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="335dc-116">sql_variant Support for Date and Time Types</span></span>](sql-variant-support-for-date-and-time-types.md)  
 <span data-ttu-id="335dc-117">Describe la compatibilidad de la función SQL_VARIANT con la funcionalidad mejorada de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="335dc-117">Describes SQL_VARIANT function support for enhanced date and time functionality.</span></span>  
  
 [<span data-ttu-id="335dc-118">Cambios de copia masiva para tipos de fecha y hora mejorados &#40;OLE DB y ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="335dc-118">Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;</span></span>](../../relational-databases/native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md)  
 <span data-ttu-id="335dc-119">Describe las mejoras de fecha y hora para admitir operaciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="335dc-119">Describes date/time enhancements to support bulk copy operations.</span></span>  
  
 [<span data-ttu-id="335dc-120">Comportamiento mejorado de tipos de fecha y hora con versiones anteriores de SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="335dc-120">Enhanced Date and Time Type Behavior with Previous SQL Server Versions &#40;ODBC&#41;</span></span>](enhanced-date-and-time-type-behavior-with-previous-sql-server-versions-odbc.md)  
 <span data-ttu-id="335dc-121">Describe el comportamiento esperado cuando una aplicación cliente que usa las características mejoradas de fecha y hora se comunica con una versión anterior de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , y cuando un cliente compilado con una versión anterior de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client envía comandos a un servidor que admite características mejoradas de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="335dc-121">Describes the expected behavior when a client application using enhanced date and time features communicates with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and when a client compiled with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sends commands to a server that supports enhanced date and time features.</span></span>  
  
 [<span data-ttu-id="335dc-122">Las API de ODBC admiten las características mejoradas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="335dc-122">ODBC API Support for Enhanced Date and Time Features</span></span>](odbc-api-support-for-enhanced-date-and-time-features.md)  
 <span data-ttu-id="335dc-123">Hace una lista de las funciones ODBC que admiten la funcionalidad mejorada de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="335dc-123">Lists the ODBC functions that support enhanced date and time functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="335dc-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="335dc-124">See Also</span></span>  
 [<span data-ttu-id="335dc-125">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="335dc-125">SQL Server Native Client &#40;ODBC&#41;</span></span>](../../relational-databases/native-client/odbc/sql-server-native-client-odbc.md)  
  
  
