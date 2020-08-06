---
title: MSSQLSERVER_3271 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3271 (Database Engine error)
ms.assetid: 21b8de4b-6624-4163-9561-1a6cc8fe3d51
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56bdb5875dbba3fbe5037a308d713170a9b6f9ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672057"
---
# <a name="mssqlserver_3271"></a><span data-ttu-id="3c98f-102">MSSQLSERVER_3271</span><span class="sxs-lookup"><span data-stu-id="3c98f-102">MSSQLSERVER_3271</span></span>
    
## <a name="details"></a><span data-ttu-id="3c98f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3c98f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c98f-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="3c98f-104">Product Name</span></span>|<span data-ttu-id="3c98f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3c98f-105">SQL Server</span></span>|  
|<span data-ttu-id="3c98f-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="3c98f-106">Event ID</span></span>|<span data-ttu-id="3c98f-107">3271</span><span class="sxs-lookup"><span data-stu-id="3c98f-107">3271</span></span>|  
|<span data-ttu-id="3c98f-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="3c98f-108">Event Source</span></span>|<span data-ttu-id="3c98f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3c98f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3c98f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3c98f-110">Component</span></span>|<span data-ttu-id="3c98f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3c98f-111">SQLEngine</span></span>|  
|<span data-ttu-id="3c98f-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3c98f-112">Symbolic Name</span></span>|<span data-ttu-id="3c98f-113">DMPIO_IO_ERROR</span><span class="sxs-lookup"><span data-stu-id="3c98f-113">DMPIO_IO_ERROR</span></span>|  
|<span data-ttu-id="3c98f-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3c98f-114">Message Text</span></span>|<span data-ttu-id="3c98f-115">Error de E/S irrecuperable en el archivo "%ls:" %ls.</span><span class="sxs-lookup"><span data-stu-id="3c98f-115">A nonrecoverable I/O error occurred on file "%ls:" %ls.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3c98f-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="3c98f-116">Explanation</span></span>  
 <span data-ttu-id="3c98f-117">Se trata de un error general que ocurre cuando el sistema operativo genera un error mientras se realiza una E/S durante una operación de copia de seguridad o de restauración.</span><span class="sxs-lookup"><span data-stu-id="3c98f-117">This is a general error that occurs when the operating system raises an error while performing I/O during a backup or restore operation.</span></span> <span data-ttu-id="3c98f-118">En la mayoría de los casos, la causa es simplemente que el medio de copia de seguridad está lleno.</span><span class="sxs-lookup"><span data-stu-id="3c98f-118">In most situations the cause is simply that the backup medium is full.</span></span>  
  
 <span data-ttu-id="3c98f-119">El error puede incluir texto adicional del sistema operativo indicando que el disco está lleno.</span><span class="sxs-lookup"><span data-stu-id="3c98f-119">The error may include additional text from the operating system indicating that the disk is full.</span></span> <span data-ttu-id="3c98f-120">Al realizar una operación de copia de seguridad o restauración con software de copia de seguridad de otros fabricantes, puede aparecer un mensaje adicional que indica que se ha producido un error en la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3c98f-120">When performing a backup or restore operation with third-party backup software an additional message may occur indicating that the backup failed.</span></span> <span data-ttu-id="3c98f-121">El mensaje puede ser similar al siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="3c98f-121">The message may look similar to the following text:</span></span>  
  
```  
"2005-08-02 16:05:16.04 spid55 Error: 18210, Severity: 16, State: 1.  
 2005-08-02 16:05:16.04 spid55 BackupVirtualDeviceFile  
::RequestDurableMedia: Flush failure on backup device 'VDINULL'.   
Operating system error 995(The I/O operation has been aborted because   
of either a thread exit or an application request.)."  
```  
  
 <span data-ttu-id="3c98f-122">Se trata de una indicación de que el software de copia de seguridad ha solicitado la finalización de la operación de copia de seguridad o de restauración.</span><span class="sxs-lookup"><span data-stu-id="3c98f-122">This is an indication that the backup software requested a termination of the backup or restore operation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c98f-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3c98f-123">User Action</span></span>  
 <span data-ttu-id="3c98f-124">Realice las siguientes tareas, según corresponda:</span><span class="sxs-lookup"><span data-stu-id="3c98f-124">Perform the following tasks as appropriate:</span></span>  
  
-   <span data-ttu-id="3c98f-125">Revise los mensajes de error subyacentes del sistema y los mensajes de error de SQL Server anteriores a éste para identificar la causa del error.</span><span class="sxs-lookup"><span data-stu-id="3c98f-125">Review the underlying system error messages and SQL Server error messages preceding this one to identify the cause of the failure.</span></span>  
  
-   <span data-ttu-id="3c98f-126">Asegúrese de que el medio para las copias de seguridad y restauración tenga suficiente espacio.</span><span class="sxs-lookup"><span data-stu-id="3c98f-126">Ensure that the backup and restore medium has sufficient space.</span></span>  
  
-   <span data-ttu-id="3c98f-127">Corrija cualquier error generado por el software de copias de seguridad y restauración de otros fabricantes.</span><span class="sxs-lookup"><span data-stu-id="3c98f-127">Correct any errors raised by third-party backup and restore software.</span></span>  
  
  
