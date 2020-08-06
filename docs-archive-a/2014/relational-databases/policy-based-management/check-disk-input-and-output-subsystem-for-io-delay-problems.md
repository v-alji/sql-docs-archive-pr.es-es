---
title: Comprobación del subsistema de entrada y salida de disco para problemas de retraso de E/S | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 23863340-d8e0-48d6-928b-462745885d37
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a0ae8dc0d1a93f8150ccbeab73ed8aa918d1f495
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745720"
---
# <a name="check-disk-input-and-output-subsystem-for-io-delay-problems"></a><span data-ttu-id="777a8-102">Check Disk Input and Output Subsystem for IO Delay Problems</span><span class="sxs-lookup"><span data-stu-id="777a8-102">Check Disk Input and Output Subsystem for IO Delay Problems</span></span>
  <span data-ttu-id="777a8-103">Esta regla comprueba si existe el mensaje de error 833 en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="777a8-103">This rule checks the event log for error message 833.</span></span> <span data-ttu-id="777a8-104">Este mensaje indica que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha emitido una solicitud de lectura o escritura desde el disco y que la solicitud ha tardado más de 15 segundos en volver.</span><span class="sxs-lookup"><span data-stu-id="777a8-104">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has issued a read or write request from disk, and that the request has taken longer than 15 seconds to return.</span></span> <span data-ttu-id="777a8-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] notifica este error, que indica un problema con el subsistema de E/S de disco.</span><span class="sxs-lookup"><span data-stu-id="777a8-105">This error is reported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and indicates a problem with the disk I/O subsystem.</span></span> <span data-ttu-id="777a8-106">Estos largos retrasos pueden dañar gravemente el rendimiento del entorno de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="777a8-106">Delays this long can severely damage the performance of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="777a8-107">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="777a8-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="777a8-108">Solucione este error examinando el registro de eventos del sistema para localizar mensajes de error relacionados con el hardware.</span><span class="sxs-lookup"><span data-stu-id="777a8-108">Troubleshoot this error by examining the system event log for hardware-related error messages.</span></span> <span data-ttu-id="777a8-109">Examine también registros específicos de hardware si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="777a8-109">Also, examine hardware-specific logs if they are available.</span></span>  
  
 <span data-ttu-id="777a8-110">Use el Monitor de rendimiento para examinar los siguientes contadores:</span><span class="sxs-lookup"><span data-stu-id="777a8-110">Use Performance Monitor to examine the following counters:</span></span>  
  
-   <span data-ttu-id="777a8-111">Average Disk Sec/Transfer</span><span class="sxs-lookup"><span data-stu-id="777a8-111">Average Disk Sec/Transfer</span></span>  
  
-   <span data-ttu-id="777a8-112">Average Disk Queue Length</span><span class="sxs-lookup"><span data-stu-id="777a8-112">Average Disk Queue Length</span></span>  
  
-   <span data-ttu-id="777a8-113">Current Disk Queue Length</span><span class="sxs-lookup"><span data-stu-id="777a8-113">Current Disk Queue Length</span></span>  
  
 <span data-ttu-id="777a8-114">Por ejemplo, el tiempo de Average Disk Sec/Transfer en un equipo que ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suele ser inferior a 15 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="777a8-114">For example, the Average Disk Sec/Transfer time on a computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is typically less than 15 milliseconds.</span></span> <span data-ttu-id="777a8-115">Si el valor de Average Disk Sec/Transfer aumenta, esto indica que el subsistema de E/S de disco no está tratando la demanda de E/S de forma óptima.</span><span class="sxs-lookup"><span data-stu-id="777a8-115">If the Average Disk Sec/Transfer value increases, this indicates that the disk I/O subsystem is not optimally keeping up with the I/O demand.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="777a8-116">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="777a8-116">For More Information</span></span>  
 [<span data-ttu-id="777a8-117">MSSQLSERVER_833</span><span class="sxs-lookup"><span data-stu-id="777a8-117">MSSQLSERVER_833</span></span>](../errors-events/mssqlserver-833-database-engine-error.md)  
  
 [<span data-ttu-id="777a8-118">Artículo 897284 de Microsoft Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="777a8-118">Microsoft Knowledge Base article 897284</span></span>](https://go.microsoft.com/fwlink/?linkid=117743)  
  
 <span data-ttu-id="777a8-119">[Elementos fundamentales de E/S de SQL Server, capítulo 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="777a8-119">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span></span>  
  
  
