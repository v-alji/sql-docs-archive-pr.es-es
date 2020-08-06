---
title: MSSQLSERVER_5235 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5235 (Database Engine error)
ms.assetid: 1aa7e6a5-7ccb-43c8-a1fd-d50e92e0a798
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 42c807944d7506a6a118de97ccd8c2c488942c8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749338"
---
# <a name="mssqlserver_5235"></a><span data-ttu-id="8c966-102">MSSQLSERVER_5235</span><span class="sxs-lookup"><span data-stu-id="8c966-102">MSSQLSERVER_5235</span></span>
    
## <a name="details"></a><span data-ttu-id="8c966-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8c966-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8c966-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="8c966-104">Product Name</span></span>|<span data-ttu-id="8c966-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8c966-105">SQL Server</span></span>|  
|<span data-ttu-id="8c966-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8c966-106">Event ID</span></span>|<span data-ttu-id="8c966-107">5235</span><span class="sxs-lookup"><span data-stu-id="8c966-107">5235</span></span>|  
|<span data-ttu-id="8c966-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="8c966-108">Event Source</span></span>|<span data-ttu-id="8c966-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8c966-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8c966-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8c966-110">Component</span></span>|<span data-ttu-id="8c966-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8c966-111">SQLEngine</span></span>|  
|<span data-ttu-id="8c966-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8c966-112">Symbolic Name</span></span>|<span data-ttu-id="8c966-113">DBCC4_ERRORLOG_SUMMARY_PREMATURE_TERMINATION</span><span class="sxs-lookup"><span data-stu-id="8c966-113">DBCC4_ERRORLOG_SUMMARY_PREMATURE_TERMINATION</span></span>|  
|<span data-ttu-id="8c966-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8c966-114">Message Text</span></span>|<span data-ttu-id="8c966-115">[EMERGENCY] DBCC DBCC_COMMAND_DETAILS ejecutado por USER_NAME finalizó de forma anómala debido a un estado de error ERROR_STATE.</span><span class="sxs-lookup"><span data-stu-id="8c966-115">[EMERGENCY] DBCC DBCC_COMMAND_DETAILS executed by USER_NAME terminated abnormally due to error state ERROR_STATE.</span></span> <span data-ttu-id="8c966-116">Tiempo transcurrido: HOURS horas MINUTES minutos SECONDS segundos.</span><span class="sxs-lookup"><span data-stu-id="8c966-116">Elapsed time: HOURS hours MINUTES minutes SECONDS seconds.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8c966-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="8c966-117">Explanation</span></span>  
 <span data-ttu-id="8c966-118">Este es el mensaje de resumen que DBCC imprime en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuando se produce una finalización inesperada mientras se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="8c966-118">This is the summary message that DBCC prints to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log when an unexpected termination occurs while the command is running.</span></span> <span data-ttu-id="8c966-119">El estado de error notificado en el mensaje define el tipo de finalización inesperada.</span><span class="sxs-lookup"><span data-stu-id="8c966-119">The error state reported in the message defines the type of unexpected termination.</span></span>  
  
 <span data-ttu-id="8c966-120">En la siguiente tabla se muestran y se definen los estados de error.</span><span class="sxs-lookup"><span data-stu-id="8c966-120">The following table lists and defines the error states.</span></span>  
  
|<span data-ttu-id="8c966-121">Estado de error</span><span class="sxs-lookup"><span data-stu-id="8c966-121">Error state</span></span>|<span data-ttu-id="8c966-122">Definición</span><span class="sxs-lookup"><span data-stu-id="8c966-122">Definition</span></span>|  
|-----------------|----------------|  
|<span data-ttu-id="8c966-123">State 0</span><span class="sxs-lookup"><span data-stu-id="8c966-123">State 0</span></span>|<span data-ttu-id="8c966-124">La instrucción finalizó debido a un daño grave de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="8c966-124">The statement was terminated because of a fatal metadata corruption.</span></span> <span data-ttu-id="8c966-125">Este mensaje irá acompañado de una o varias instancias de error 8930.</span><span class="sxs-lookup"><span data-stu-id="8c966-125">This message will be accompanied by one or more instances of error 8930.</span></span>|  
|<span data-ttu-id="8c966-126">State 1</span><span class="sxs-lookup"><span data-stu-id="8c966-126">State 1</span></span>|<span data-ttu-id="8c966-127">La instrucción finalizó debido a un error interno de comprobación.</span><span class="sxs-lookup"><span data-stu-id="8c966-127">The statement was terminated because of an internal check failure.</span></span> <span data-ttu-id="8c966-128">Este mensaje irá acompañado de una o varias instancias de error 8967.</span><span class="sxs-lookup"><span data-stu-id="8c966-128">This message will be accompanied by one or more instances of error 8967.</span></span>|  
|<span data-ttu-id="8c966-129">State 2</span><span class="sxs-lookup"><span data-stu-id="8c966-129">State 2</span></span>|<span data-ttu-id="8c966-130">Error en las comprobaciones básicas de las tablas del sistema del motor de almacenamiento principal.</span><span class="sxs-lookup"><span data-stu-id="8c966-130">Basic system table checks of the core storage engine system tables failed.</span></span> <span data-ttu-id="8c966-131">Este mensaje irá acompañado de una o varias instancias de error [7984](mssqlserver-7984-database-engine-error.md), 7985, [7986](mssqlserver-7986-database-engine-error.md), [7987](mssqlserver-7987-database-engine-error.md) o [7988](mssqlserver-7988-database-engine-error.md).</span><span class="sxs-lookup"><span data-stu-id="8c966-131">This message will be accompanied by one or more instances of error [7984](mssqlserver-7984-database-engine-error.md), 7985, [7986](mssqlserver-7986-database-engine-error.md), [7987](mssqlserver-7987-database-engine-error.md), or [7988](mssqlserver-7988-database-engine-error.md).</span></span>|  
|<span data-ttu-id="8c966-132">State 3</span><span class="sxs-lookup"><span data-stu-id="8c966-132">State 3</span></span>|<span data-ttu-id="8c966-133">Error en la reparación del modo de emergencia DBCC debido a que la base de datos no pudo iniciarse después de volver a generar el registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="8c966-133">DBCC emergency-mode repair failed because the database could not be started after rebuilding the transaction log.</span></span> <span data-ttu-id="8c966-134">Este mensaje irá acompañado del error 7909.</span><span class="sxs-lookup"><span data-stu-id="8c966-134">This message will be accompanied by error 7909.</span></span>|  
|<span data-ttu-id="8c966-135">State 4</span><span class="sxs-lookup"><span data-stu-id="8c966-135">State 4</span></span>|<span data-ttu-id="8c966-136">Se produjo un error de aserción o infracción de acceso durante la ejecución del comando.</span><span class="sxs-lookup"><span data-stu-id="8c966-136">A failed assertion or access violation occurred during the execution of the command.</span></span>|  
|<span data-ttu-id="8c966-137">Estado 5</span><span class="sxs-lookup"><span data-stu-id="8c966-137">State 5</span></span>|<span data-ttu-id="8c966-138">Se produjo un error desconocido que canceló inesperadamente el comando DBCC.</span><span class="sxs-lookup"><span data-stu-id="8c966-138">An unknown failure occurred that unexpectedly terminated the DBCC command.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="8c966-139">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8c966-139">User Action</span></span>  
 <span data-ttu-id="8c966-140">En la siguiente tabla se muestra la acción apropiada que debe llevar a cabo el usuario para el estado de error especificado.</span><span class="sxs-lookup"><span data-stu-id="8c966-140">The following table provides the user action that is appropriate for the specified error state.</span></span>  
  
|<span data-ttu-id="8c966-141">Estado de error</span><span class="sxs-lookup"><span data-stu-id="8c966-141">Error state</span></span>|<span data-ttu-id="8c966-142">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8c966-142">User action</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="8c966-143">State 0</span><span class="sxs-lookup"><span data-stu-id="8c966-143">State 0</span></span>|<span data-ttu-id="8c966-144">Restaure mediante la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8c966-144">Restore from backup.</span></span>|  
|<span data-ttu-id="8c966-145">State 1</span><span class="sxs-lookup"><span data-stu-id="8c966-145">State 1</span></span>|<span data-ttu-id="8c966-146">Póngase en contacto con el Servicio de atención al cliente y soporte técnico (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c966-146">Contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>|  
|<span data-ttu-id="8c966-147">State 2</span><span class="sxs-lookup"><span data-stu-id="8c966-147">State 2</span></span>|<span data-ttu-id="8c966-148">Restaure mediante la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8c966-148">Restore from backup.</span></span>|  
|<span data-ttu-id="8c966-149">State 3</span><span class="sxs-lookup"><span data-stu-id="8c966-149">State 3</span></span>|<span data-ttu-id="8c966-150">Restaure mediante la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8c966-150">Restore from backup.</span></span>|  
|<span data-ttu-id="8c966-151">State 4</span><span class="sxs-lookup"><span data-stu-id="8c966-151">State 4</span></span>|<span data-ttu-id="8c966-152">Póngase en contacto con el CSS.</span><span class="sxs-lookup"><span data-stu-id="8c966-152">Contact CSS.</span></span>|  
|<span data-ttu-id="8c966-153">Estado 5</span><span class="sxs-lookup"><span data-stu-id="8c966-153">State 5</span></span>|<span data-ttu-id="8c966-154">Vuelva a ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="8c966-154">Run the command again.</span></span> <span data-ttu-id="8c966-155">Si el problema persiste, póngase en contacto con el CSS.</span><span class="sxs-lookup"><span data-stu-id="8c966-155">If the problem persists, contact CSS.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c966-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c966-156">See Also</span></span>  
 [<span data-ttu-id="8c966-157">DBCC &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8c966-157">DBCC &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-transact-sql)  
  
  
