---
title: SQL Errors (objeto de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQL Errors object
- SQLServer:SQL Errors
ms.assetid: 6e5273ca-29cb-4618-88a2-70b9b8d6cf76
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 11bfb728e79b4fc175fb8a2fe16c9f1662a205ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744656"
---
# <a name="sql-server-sql-errors-object"></a><span data-ttu-id="f00ce-102">SQL Errors (objeto de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f00ce-102">SQL Server, SQL Errors Object</span></span>
  <span data-ttu-id="f00ce-103">El objeto **SQLServer:SQL Errors** de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporciona contadores para supervisar los **errores de SQL**.</span><span class="sxs-lookup"><span data-stu-id="f00ce-103">The **SQLServer:SQL Errors** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor **SQL Errors**.</span></span>  
  
 <span data-ttu-id="f00ce-104">En esta tabla se describen los contadores de **errores de SQL** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f00ce-104">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **SQL Errors** counters.</span></span>  
  
|<span data-ttu-id="f00ce-105">Contadores de errores de SQL de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f00ce-105">SQL Server SQL Errors counters</span></span>|<span data-ttu-id="f00ce-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f00ce-106">Description</span></span>|  
|------------------------------------|-----------------|  
|<span data-ttu-id="f00ce-107">**Errores/seg.**</span><span class="sxs-lookup"><span data-stu-id="f00ce-107">**Errors/sec**</span></span>|<span data-ttu-id="f00ce-108">Número de errores/seg.</span><span class="sxs-lookup"><span data-stu-id="f00ce-108">Number of errors/sec.</span></span>|  
  
 <span data-ttu-id="f00ce-109">Cada contador del objeto contiene las instancias siguientes:</span><span class="sxs-lookup"><span data-stu-id="f00ce-109">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="f00ce-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="f00ce-110">Item</span></span>|<span data-ttu-id="f00ce-111">Definición</span><span class="sxs-lookup"><span data-stu-id="f00ce-111">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="f00ce-112">**_Total**</span><span class="sxs-lookup"><span data-stu-id="f00ce-112">**_Total**</span></span>|<span data-ttu-id="f00ce-113">Información sobre todos los errores.</span><span class="sxs-lookup"><span data-stu-id="f00ce-113">Information for all errors.</span></span>|  
|<span data-ttu-id="f00ce-114">**DB Offline Errors**</span><span class="sxs-lookup"><span data-stu-id="f00ce-114">**DB Offline Errors**</span></span>|<span data-ttu-id="f00ce-115">Hace un seguimiento de los errores graves que hacen que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deje sin conexión la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="f00ce-115">Tracks severe errors that cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to take the current database offline.</span></span>|  
|<span data-ttu-id="f00ce-116">**Info Errors**</span><span class="sxs-lookup"><span data-stu-id="f00ce-116">**Info Errors**</span></span>|<span data-ttu-id="f00ce-117">Información relacionada con los mensajes de error que proporcionan información a los usuarios pero no causan errores.</span><span class="sxs-lookup"><span data-stu-id="f00ce-117">Information related to error messages that provide information to users but do not cause errors.</span></span>|  
|<span data-ttu-id="f00ce-118">**Kill Connection Errors**</span><span class="sxs-lookup"><span data-stu-id="f00ce-118">**Kill Connection Errors**</span></span>|<span data-ttu-id="f00ce-119">Hace un seguimiento de los errores graves que hacen que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] elimine la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="f00ce-119">Tracks severe errors that cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to kill the current connection.</span></span>|  
|<span data-ttu-id="f00ce-120">**User Errors**</span><span class="sxs-lookup"><span data-stu-id="f00ce-120">**User Errors**</span></span>|<span data-ttu-id="f00ce-121">Información sobre los errores de usuario.</span><span class="sxs-lookup"><span data-stu-id="f00ce-121">Information about user errors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f00ce-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f00ce-122">See Also</span></span>  
 [<span data-ttu-id="f00ce-123">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="f00ce-123">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
