---
title: MSSQLSERVER_823 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 823 (Database Engine error)
ms.assetid: 0d9fce3c-3772-46ce-a7a3-4f4988dc6cae
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fa5858bbdc9452a33a3d43fdd783e59556a11e57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672991"
---
# <a name="mssqlserver_823"></a><span data-ttu-id="68afa-102">MSSQLSERVER_823</span><span class="sxs-lookup"><span data-stu-id="68afa-102">MSSQLSERVER_823</span></span>
    
## <a name="details"></a><span data-ttu-id="68afa-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="68afa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="68afa-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="68afa-104">Product Name</span></span>|<span data-ttu-id="68afa-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="68afa-105">SQL Server</span></span>|  
|<span data-ttu-id="68afa-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="68afa-106">Event ID</span></span>|<span data-ttu-id="68afa-107">823</span><span class="sxs-lookup"><span data-stu-id="68afa-107">823</span></span>|  
|<span data-ttu-id="68afa-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="68afa-108">Event Source</span></span>|<span data-ttu-id="68afa-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="68afa-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="68afa-110">Componente</span><span class="sxs-lookup"><span data-stu-id="68afa-110">Component</span></span>|<span data-ttu-id="68afa-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="68afa-111">SQLEngine</span></span>|  
|<span data-ttu-id="68afa-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="68afa-112">Symbolic Name</span></span>|<span data-ttu-id="68afa-113">B_HARDERR</span><span class="sxs-lookup"><span data-stu-id="68afa-113">B_HARDERR</span></span>|  
|<span data-ttu-id="68afa-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="68afa-114">Message Text</span></span>|<span data-ttu-id="68afa-115">El sistema operativo ha devuelto el error %ls en SQL Server durante %S_MSG en el desplazamiento %#016I64x del archivo '%ls'.</span><span class="sxs-lookup"><span data-stu-id="68afa-115">The operating system returned error %ls to SQL Server during a %S_MSG at offset %#016I64x in file '%ls'.</span></span> <span data-ttu-id="68afa-116">Encontrará más detalles en los mensajes adicionales del registro de errores de SQL Server y el registro de eventos del sistema.</span><span class="sxs-lookup"><span data-stu-id="68afa-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span></span> <span data-ttu-id="68afa-117">Se trata de una condición de error grave de nivel de sistema que amenaza a la integridad de la base de datos y que debe corregirse inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="68afa-117">This is a severe system-level error condition that threatens database integrity and must be corrected immediately.</span></span> <span data-ttu-id="68afa-118">Ejecute una comprobación de coherencia completa de la base de datos (DBCC CHECKDB).</span><span class="sxs-lookup"><span data-stu-id="68afa-118">Complete a full database consistency check (DBCC CHECKDB).</span></span> <span data-ttu-id="68afa-119">Este error puede deberse a muchos factores. Para obtener más información vea los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68afa-119">This error can be caused by many factors; for more information, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="68afa-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="68afa-120">Explanation</span></span>  
 <span data-ttu-id="68afa-121">Error de solicitud de lectura o escritura de Windows.</span><span class="sxs-lookup"><span data-stu-id="68afa-121">A Windows read or write request has failed.</span></span> <span data-ttu-id="68afa-122">El código de error devuelto por Windows y el texto correspondiente se insertan en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="68afa-122">The error code that is returned by Windows and the corresponding text are inserted into the message.</span></span> <span data-ttu-id="68afa-123">En el caso de la solicitud de lectura, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ya la habrá intentado cuatro veces.</span><span class="sxs-lookup"><span data-stu-id="68afa-123">In the read case, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will have already retried the read request four times.</span></span> <span data-ttu-id="68afa-124">Suele ser el resultado de un error de hardware, pero puede estar causado por el controlador del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="68afa-124">This error is often the result of a hardware error, but may be caused by the device driver.</span></span> <span data-ttu-id="68afa-125">Para obtener más información acerca del error 823, vea [https://support.microsoft.com/kb/828339](https://support.microsoft.com/kb/828339) .</span><span class="sxs-lookup"><span data-stu-id="68afa-125">For more information about error 823, see [https://support.microsoft.com/kb/828339](https://support.microsoft.com/kb/828339).</span></span> <span data-ttu-id="68afa-126">Para obtener más información sobre los errores de E/S, vea el [capítulo 2 del documento sobre conceptos básicos de E/S de Microsoft SQL Server](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="68afa-126">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="68afa-127">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="68afa-127">User Action</span></span>  
 <span data-ttu-id="68afa-128">Busque información adicional en el registro de eventos del sistema.</span><span class="sxs-lookup"><span data-stu-id="68afa-128">Check for additional information in the system event log.</span></span> <span data-ttu-id="68afa-129">Póngase en contacto con el fabricante del hardware o el servicio de Soporte técnico y Atención al cliente de Microsoft para determinar la causa y la acción correctora.</span><span class="sxs-lookup"><span data-stu-id="68afa-129">Contact the hardware manufacturer or Microsoft Customer Services and Support to determine the cause and corrective action.</span></span> <span data-ttu-id="68afa-130">Después de solucionar el error de hardware, restaure todas las bases de datos y ejecute DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="68afa-130">After the hardware error is fixed, restore all databases and run DBCC CHECKDB.</span></span>  
  
  
