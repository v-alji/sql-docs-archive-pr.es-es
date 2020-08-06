---
title: Mejoras de fecha y hora (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- date/time [OLE DB]
- OLE DB, date/time improvements
ms.assetid: 71614aaf-0fa4-4fe0-b522-68e2e0b66f43
author: rothja
ms.author: jroth
ms.openlocfilehash: 16bb9e98691aea829eb71a16ddabddb371d7bcf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749283"
---
# <a name="date-and-time-improvements-ole-db"></a><span data-ttu-id="3d626-102">Mejoras en la fecha y la hora (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="3d626-102">Date and Time Improvements (OLE DB)</span></span>
  [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="3d626-103">introduce nuevos tipos de datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="3d626-103">introduces new date and time data types.</span></span> <span data-ttu-id="3d626-104">En esta sección se describe la forma en que estos nuevos tipos se exponen como extensiones en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client. </span><span class="sxs-lookup"><span data-stu-id="3d626-104">This section describes how these new types are exposed as extensions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="3d626-105">Para obtener información general de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] compatibilidad de Native Client con los nuevos tipos de datos de fecha y hora, vea [mejoras de fecha y hora](../native-client/features/date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="3d626-105">For an overview of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client support for the new date and time data types, see [Date and Time Improvements](../native-client/features/date-and-time-improvements.md).</span></span> <span data-ttu-id="3d626-106">Para obtener un ejemplo, consulte [Usar las características mejoradas de fecha y hora &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-enhanced-date-and-time-features-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="3d626-106">For a sample, see [Use Enhanced Date and Time Features &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-enhanced-date-and-time-features-ole-db.md).</span></span>  
  
 <span data-ttu-id="3d626-107">Para obtener más información general sobre los tipos de datos de fecha y hora, consulte [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3d626-107">For more general information about date and time data types, see [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3d626-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3d626-108">In This Section</span></span>  
 [<span data-ttu-id="3d626-109">Compatibilidad con tipos de datos para mejoras de fecha y hora de OLE DB</span><span class="sxs-lookup"><span data-stu-id="3d626-109">Data Type Support for OLE DB Date and Time Improvements</span></span>](../../relational-databases/native-client-ole-db-date-time/data-type-support-for-ole-db-date-and-time-improvements.md)  
 <span data-ttu-id="3d626-110">Proporciona información sobre los tipos de OLE DB ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) que admiten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="3d626-110">Provides information about OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span>  
  
 [<span data-ttu-id="3d626-111">Metadatos &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3d626-111">Metadata &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/metadata-ole-db.md)  
 <span data-ttu-id="3d626-112">Contiene información sobre la estructura DBBINDING, `ICommandWithParameters::GetParameterInfo` , `ICommandWithParameters::SetParameterInfo` , `IColumnsRowset::GetColumnsRowset` y I `ColumnsInfo::GetColumnInfo` . También proporciona información sobre las actualizaciones para OLE DB conjuntos de filas de esquema.</span><span class="sxs-lookup"><span data-stu-id="3d626-112">Contains information about the DBBINDING structure, `ICommandWithParameters::GetParameterInfo`, `ICommandWithParameters::SetParameterInfo`, `IColumnsRowset::GetColumnsRowset`, and I`ColumnsInfo::GetColumnInfo`. Also provides information about updates to OLE DB schema rowsets.</span></span>  
  
 [<span data-ttu-id="3d626-113">Enlaces y conversiones &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3d626-113">Bindings and Conversions &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-date-time/conversions-ole-db.md)  
 <span data-ttu-id="3d626-114">Describe las reglas para realizar conversiones entre el servidor y el cliente tanto para tipos de datos existentes como nuevos.</span><span class="sxs-lookup"><span data-stu-id="3d626-114">Describes the rules for conversion between server and client for both existing and new date types.</span></span>  
  
 [<span data-ttu-id="3d626-115">Cambios de copia masiva para tipos de fecha y hora mejorados &#40;OLE DB y ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3d626-115">Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;</span></span>](../../relational-databases/native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md)  
 <span data-ttu-id="3d626-116">Describe las mejoras de fecha y hora para admitir operaciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="3d626-116">Describes date/time enhancements to support bulk copy operations.</span></span>  
  
 [<span data-ttu-id="3d626-117">Compatibilidad de API de OLE DB con las mejoras de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="3d626-117">OLE DB API Support for Date and Time Enhancements</span></span>](ole-db-api-support-for-date-and-time-enhancements.md)  
 <span data-ttu-id="3d626-118">Describe las API de OLE DB que admiten las características mejoradas de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="3d626-118">Describes the OLE DB APIs that support enhanced date/time features.</span></span>  
  
 [<span data-ttu-id="3d626-119">Comparaciones en IRowsetFind</span><span class="sxs-lookup"><span data-stu-id="3d626-119">Comparability for IRowsetFind</span></span>](../../relational-databases/native-client-ole-db-date-time/comparability-for-irowsetfind.md)  
 <span data-ttu-id="3d626-120">Describe los tipos de fecha y hora e `IRowsetFind`.</span><span class="sxs-lookup"><span data-stu-id="3d626-120">Describes date/time types and `IRowsetFind`.</span></span>  
  
 [<span data-ttu-id="3d626-121">Nuevas características de fecha y hora con versiones anteriores de SQL Server &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3d626-121">New Date and Time Features with Previous SQL Server Versions &#40;OLE DB&#41;</span></span>](new-date-and-time-features-with-previous-sql-server-versions-ole-db.md)  
 <span data-ttu-id="3d626-122">Describe el comportamiento que se espera cuando una aplicación cliente que utiliza características mejoradas de fecha y hora se comunica con una versión anterior de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y cuando un cliente compilado con una versión anterior de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client envía comandos a un servidor que admite características mejoradas de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="3d626-122">Describes the expected behavior when a client application that uses enhanced date and time features communicates with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and when a client compiled with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sends commands to a server that supports enhanced date and time features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d626-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3d626-123">See Also</span></span>  
 [<span data-ttu-id="3d626-124">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3d626-124">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
