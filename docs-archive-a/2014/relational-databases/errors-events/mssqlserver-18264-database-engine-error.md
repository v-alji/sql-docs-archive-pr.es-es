---
title: MSSQLSERVER_18264 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18264 (Database Engine error)
ms.assetid: 3050fc56-2be5-43cf-916b-50a3ac5f89aa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3edfeb82601e254c02df87cc4a978b9ab5e653e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674139"
---
# <a name="mssqlserver_18264"></a><span data-ttu-id="fc464-102">MSSQLSERVER_18264</span><span class="sxs-lookup"><span data-stu-id="fc464-102">MSSQLSERVER_18264</span></span>
    
## <a name="details"></a><span data-ttu-id="fc464-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fc464-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fc464-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="fc464-104">Product Name</span></span>|<span data-ttu-id="fc464-105">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="fc464-105">Microsoft SQL Server</span></span>|  
|<span data-ttu-id="fc464-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="fc464-106">Event ID</span></span>|<span data-ttu-id="fc464-107">18264</span><span class="sxs-lookup"><span data-stu-id="fc464-107">18264</span></span>|  
|<span data-ttu-id="fc464-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="fc464-108">Event Source</span></span>|<span data-ttu-id="fc464-109">MSSQLENGINE</span><span class="sxs-lookup"><span data-stu-id="fc464-109">MSSQLENGINE</span></span>|  
|<span data-ttu-id="fc464-110">Componente</span><span class="sxs-lookup"><span data-stu-id="fc464-110">Component</span></span>|<span data-ttu-id="fc464-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fc464-111">SQLEngine</span></span>|  
|<span data-ttu-id="fc464-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fc464-112">Symbolic Name</span></span>|<span data-ttu-id="fc464-113">STRMIO_DBDUMP</span><span class="sxs-lookup"><span data-stu-id="fc464-113">STRMIO_DBDUMP</span></span>|  
|<span data-ttu-id="fc464-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fc464-114">Message Text</span></span>|<span data-ttu-id="fc464-115">Se ha realizado una copia de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fc464-115">Database backed up.</span></span> <span data-ttu-id="fc464-116">Base de datos: %s, fecha de creación (tiempo): %s(%s), páginas volcadas: %d, primer LSN: %s, último LSN: %s, número de dispositivos de volcado: %d, información del dispositivo: (%s).</span><span class="sxs-lookup"><span data-stu-id="fc464-116">Database: %s, creation date(time): %s(%s), pages dumped: %d, first LSN: %s, last LSN: %s, number of dump devices: %d, device information: (%s).</span></span> <span data-ttu-id="fc464-117">Esto es solo un mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="fc464-117">This is an informational message only.</span></span> <span data-ttu-id="fc464-118">No se requiere ninguna acción del usuario.</span><span class="sxs-lookup"><span data-stu-id="fc464-118">No user action is required.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fc464-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="fc464-119">Explanation</span></span>  
 <span data-ttu-id="fc464-120">De forma predeterminada, cada copia de seguridad correcta agrega este mensaje informativo al registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y al registro de eventos del sistema.</span><span class="sxs-lookup"><span data-stu-id="fc464-120">By default, every successful backup adds this informational message to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the system event log.</span></span> <span data-ttu-id="fc464-121">Si hace una copia de seguridad del registro de transacciones con frecuencia, estos mensajes pueden acumularse rápidamente y crear registros de errores muy grandes, que pueden dificultar la búsqueda de otros mensajes.</span><span class="sxs-lookup"><span data-stu-id="fc464-121">If you very frequently back up the transaction log, these messages can accumulate quickly, creating very large error logs that can make finding other messages difficult.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fc464-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fc464-122">User Action</span></span>  
 <span data-ttu-id="fc464-123">Puede suprimir estas entradas de registro usando la marca de seguimiento de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**3226**.</span><span class="sxs-lookup"><span data-stu-id="fc464-123">You can suppress these log entries by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trace flag **3226**.</span></span> <span data-ttu-id="fc464-124">Habilitar esta marca de seguimiento es útil si ejecuta frecuentemente copias de seguridad de los registros y ninguno de los scripts depende de esas entradas.</span><span class="sxs-lookup"><span data-stu-id="fc464-124">Enabling this trace flag is useful if you are running frequent log backups and if none of your scripts depend on those entries.</span></span>  
  
 <span data-ttu-id="fc464-125">Para obtener información sobre cómo usar marcas de seguimiento, vea los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc464-125">For information about using trace flags, see SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc464-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc464-126">See Also</span></span>  
 [<span data-ttu-id="fc464-127">Marcas de seguimiento &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fc464-127">Trace Flags &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  
