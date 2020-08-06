---
title: Ver el registro de errores de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cycling SQL Server error log
- viewing SQL Server error log
- errors [SQL Server], logs
- SQL Server error log
- displaying SQL Server error log
- logs [SQL Server], SQL Server error logs
ms.assetid: 6908c21a-65e3-458f-a272-fee256d86448
author: stevestein
ms.author: sstein
ms.openlocfilehash: 822ae4fba589f005aaee41857a9db3388a309254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661738"
---
# <a name="viewing-the-sql-server-error-log"></a><span data-ttu-id="6fb72-102">Ver el registro de errores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6fb72-102">Viewing the SQL Server Error Log</span></span>
  <span data-ttu-id="6fb72-103">Eche un vistazo al registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para asegurarse de que los procesos se han completado correctamente (por ejemplo, operaciones de copias de seguridad y restauración, comandos de un proceso por lotes u otros scripts o procesos).</span><span class="sxs-lookup"><span data-stu-id="6fb72-103">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to ensure that processes have completed successfully (for example, backup and restore operations, batch commands, or other scripts and processes).</span></span> <span data-ttu-id="6fb72-104">Esto puede resultar útil para detectar áreas con problemas actuales o posibles, incluidos mensajes de recuperación automática (especialmente si se ha detenido y reiniciado una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ), mensajes del kernel u otros mensajes de error de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="6fb72-104">This can be helpful to detect any current or potential problem areas, including automatic recovery messages (particularly if an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been stopped and restarted), kernel messages, or other server-level error messages.</span></span>  
  
 <span data-ttu-id="6fb72-105">Para ver el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , utilice [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o cualquier procesador de texto.</span><span class="sxs-lookup"><span data-stu-id="6fb72-105">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any text editor.</span></span> <span data-ttu-id="6fb72-106">Para obtener más información sobre cómo ver el registro de errores, vea [Open Log File Viewer](../../relational-databases/logs/log-file-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="6fb72-106">For more information about how to view the error log, see [Open Log File Viewer](../../relational-databases/logs/log-file-viewer.md).</span></span> <span data-ttu-id="6fb72-107">De forma predeterminada, el registro de error se encuentra en los archivos `Program Files\Microsoft SQL Server\MSSQL.`*n*`\MSSQL\LOG\ERRORLOG` y `ERRORLOG.`*n* .</span><span class="sxs-lookup"><span data-stu-id="6fb72-107">By default, the error log is located at `Program Files\Microsoft SQL Server\MSSQL.`*n*`\MSSQL\LOG\ERRORLOG` and `ERRORLOG.`*n* files.</span></span>  
  
 <span data-ttu-id="6fb72-108">Cada vez que se inicia una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , se crea un registro de errores, pero se puede usar el procedimiento almacenado del sistema [sp_cycle_errorlog](/sql/relational-databases/system-stored-procedures/sp-cycle-errorlog-transact-sql) para cambiar los archivos de registro de errores sin tener que reiniciar la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6fb72-108">A new error log is created each time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started, although the [sp_cycle_errorlog](/sql/relational-databases/system-stored-procedures/sp-cycle-errorlog-transact-sql) system stored procedure can be used to cycle the error log files without having to restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6fb72-109">Normalmente, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conserva copias de seguridad de los últimos seis registros y asigna a la copia de seguridad de registros más reciente la extensión .1, a la segunda más reciente la extensión .2 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="6fb72-109">Typically, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retains backups of the previous six logs and gives the most recent log backup the extension .1, the second most recent the extension .2, and so on.</span></span> <span data-ttu-id="6fb72-110">El registro de errores actual no tiene ninguna extensión.</span><span class="sxs-lookup"><span data-stu-id="6fb72-110">The current error log has no extension.</span></span>  
  
 <span data-ttu-id="6fb72-111">Tenga en cuenta que también puede ver las instancias del registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que están sin conexión o no se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="6fb72-111">Be aware that you can also view the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log on instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are offline or cannot start.</span></span> <span data-ttu-id="6fb72-112">Para obtener más información, vea [Ver sin conexión archivos de registro](../../relational-databases/logs/view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="6fb72-112">For more information, see [View Offline Log Files](../../relational-databases/logs/view-offline-log-files.md).</span></span>  
  
  
