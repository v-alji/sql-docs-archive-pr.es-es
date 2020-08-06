---
title: MSSQLSERVER_833 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 833 (Database Engine error)
ms.assetid: 14129cc4-be80-4772-9e3f-0e5da4d0696b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8e20018c0fe1cd0748f4930e0022622adcbfad10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672981"
---
# <a name="mssqlserver_833"></a><span data-ttu-id="93dec-102">MSSQLSERVER_833</span><span class="sxs-lookup"><span data-stu-id="93dec-102">MSSQLSERVER_833</span></span>
    
## <a name="details"></a><span data-ttu-id="93dec-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="93dec-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="93dec-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="93dec-104">Product Name</span></span>|<span data-ttu-id="93dec-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="93dec-105">SQL Server</span></span>|  
|<span data-ttu-id="93dec-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="93dec-106">Event ID</span></span>|<span data-ttu-id="93dec-107">833</span><span class="sxs-lookup"><span data-stu-id="93dec-107">833</span></span>|  
|<span data-ttu-id="93dec-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="93dec-108">Event Source</span></span>|<span data-ttu-id="93dec-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="93dec-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="93dec-110">Componente</span><span class="sxs-lookup"><span data-stu-id="93dec-110">Component</span></span>|<span data-ttu-id="93dec-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="93dec-111">SQLEngine</span></span>|  
|<span data-ttu-id="93dec-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="93dec-112">Symbolic Name</span></span>|<span data-ttu-id="93dec-113">BUF_LONG_IO</span><span class="sxs-lookup"><span data-stu-id="93dec-113">BUF_LONG_IO</span></span>|  
|<span data-ttu-id="93dec-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="93dec-114">Message Text</span></span>|<span data-ttu-id="93dec-115">SQL Server ha encontrado% d repeticiones de solicitudes de e/s que tardan más de% d segundos en completarse en el archivo [% LS] de la base de datos `[%ls] (%d)` .</span><span class="sxs-lookup"><span data-stu-id="93dec-115">SQL Server has encountered %d occurrence(s) of I/O requests taking longer than %d seconds to complete on file [%ls] in database`[%ls] (%d)`.</span></span>  <span data-ttu-id="93dec-116">El identificador de archivo del SO es 0x%p.</span><span class="sxs-lookup"><span data-stu-id="93dec-116">The OS file handle is 0x%p.</span></span>  <span data-ttu-id="93dec-117">El desplazamiento de la operación de E/S más reciente y más larga es: %#016I64x.</span><span class="sxs-lookup"><span data-stu-id="93dec-117">The offset of the latest long I/O is: %#016I64x.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="93dec-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="93dec-118">Explanation</span></span>  
 <span data-ttu-id="93dec-119">Este mensaje indica que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha emitido una solicitud de lectura o escritura desde el disco y que la solicitud ha tardado más de 15 segundos en volver.</span><span class="sxs-lookup"><span data-stu-id="93dec-119">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has issued a read or write request from disk, and that the request has taken longer than 15 seconds to return.</span></span> <span data-ttu-id="93dec-120">Este error ha sido notificado por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e indica un problema con el subsistema de E/S.</span><span class="sxs-lookup"><span data-stu-id="93dec-120">This error is reported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and indicates a problem with the IO subsystem.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="93dec-121">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="93dec-121">Possible Causes</span></span>  
 <span data-ttu-id="93dec-122">Este problema puede producirse debido a problemas de rendimiento del sistema, errores de hardware y de firmware, problemas de los controladores de dispositivos o intervención de los controladores de filtro en el proceso de E/S.</span><span class="sxs-lookup"><span data-stu-id="93dec-122">This problem can be caused system performance issues, hardware errors, firmware errors, device driver problems, or filter driver intervention in the IO process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="93dec-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="93dec-123">User Action</span></span>  
 <span data-ttu-id="93dec-124">Solucione este error examinando el registro de eventos del sistema para localizar mensajes de error relacionados con el hardware.</span><span class="sxs-lookup"><span data-stu-id="93dec-124">Troubleshoot this error by examining the system event log for hardware-related error messages.</span></span> <span data-ttu-id="93dec-125">Examine también registros específicos de hardware si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="93dec-125">Also, examine hardware-specific logs if they are available.</span></span>  
  
 <span data-ttu-id="93dec-126">Use el Monitor de rendimiento para examinar los siguientes contadores:</span><span class="sxs-lookup"><span data-stu-id="93dec-126">Use Performance Monitor to examine the following counters:</span></span>  
  
-   <span data-ttu-id="93dec-127">**Average Disk Sec/Transfer**</span><span class="sxs-lookup"><span data-stu-id="93dec-127">**Average Disk Sec/Transfer**</span></span>  
  
-   <span data-ttu-id="93dec-128">**Average Disk Queue Length**</span><span class="sxs-lookup"><span data-stu-id="93dec-128">**Average Disk Queue Length**</span></span>  
  
-   <span data-ttu-id="93dec-129">**Current Disk Queue Length**</span><span class="sxs-lookup"><span data-stu-id="93dec-129">**Current Disk Queue Length**</span></span>  
  
 <span data-ttu-id="93dec-130">Por ejemplo, el tiempo de **Average Disk Sec/Transfer** en un equipo que ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] suele ser inferior a 15 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="93dec-130">For example, the **Average Disk Sec/Transfer** time on a computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is typically less than 15 milliseconds.</span></span> <span data-ttu-id="93dec-131">Si el valor de la **Average Disk Sec/Transfer** aumenta, esto indica que el subsistema de E/S no se mantiene al nivel de forma óptima de la demanda de E/S.</span><span class="sxs-lookup"><span data-stu-id="93dec-131">If the **Average Disk Sec/Transfer** value increases, this indicates that the I/O subsystem is not optimally keeping up with the I/O demand.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93dec-132">El acceso al disco puede ralentizarse debido a un programa antivirus.</span><span class="sxs-lookup"><span data-stu-id="93dec-132">Disk access can be slowed by an antivirus program.</span></span> <span data-ttu-id="93dec-133">Para aumentar la velocidad de acceso, excluya los archivos de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se especifican en el mensaje de error de las búsquedas de virus activos.</span><span class="sxs-lookup"><span data-stu-id="93dec-133">To increase access speed, exclude the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data files that are specified in the error message from active virus scans.</span></span>  
  
 <span data-ttu-id="93dec-134">Para obtener más información sobre de los errores de E/S, vea el [capítulo 2 del documento sobre elementos fundamentales de E/S de Microsoft SQL Server ](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) y el artículo de Knowledge Base en [https://support.microsoft.com/kb/897284](https://support.microsoft.com/kb/897284).</span><span class="sxs-lookup"><span data-stu-id="93dec-134">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) and the Knowledge Base article at [https://support.microsoft.com/kb/897284](https://support.microsoft.com/kb/897284).</span></span>  
  
  
