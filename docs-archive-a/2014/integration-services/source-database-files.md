---
title: Archivos de base de datos de origen | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.sourcedbfiles.f1
ms.assetid: 7dc6bfeb-37c1-45e8-a705-a87564922265
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 31f0c0e0c633ead0c093bdc8e1f20c9b8f23cc28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751241"
---
# <a name="source-database-files"></a><span data-ttu-id="cd51e-102">Archivos de base de datos de origen</span><span class="sxs-lookup"><span data-stu-id="cd51e-102">Source database files</span></span>
  <span data-ttu-id="cd51e-103">Utilice el cuadro de diálogo **Archivos de base de datos de origen** para ver los nombres y las ubicaciones de los archivos de la base de datos en el servidor de origen o para especificar una ubicación del recurso compartido de archivos de red para la tarea Transferir bases de datos.</span><span class="sxs-lookup"><span data-stu-id="cd51e-103">Use the **Source Database Files** dialog box to view the database file names and locations on the source server, or to specify a network file share location for the Transfer Database task.</span></span> <span data-ttu-id="cd51e-104">Para obtener más información sobre esta tarea, vea [Tarea Transferir bases de datos](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="cd51e-104">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
 <span data-ttu-id="cd51e-105">Para llenar este cuadro de diálogo con los nombres y las ubicaciones de los archivos de la base de datos del servidor de origen, especifique **SourceConnection** y **SourceDatabaseName** primero en la página **Bases de datos** del cuadro de diálogo **Editor de la tarea Transferir bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="cd51e-105">To populate this dialog box with the database file names and locations on the source server, specify the **SourceConnection** and **SourceDatabaseName** first in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cd51e-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="cd51e-106">Options</span></span>  
 <span data-ttu-id="cd51e-107">**Archivo de origen**</span><span class="sxs-lookup"><span data-stu-id="cd51e-107">**Source File**</span></span>  
 <span data-ttu-id="cd51e-108">Nombres de los archivos de la base de datos del servidor de origen que se van a transferir.</span><span class="sxs-lookup"><span data-stu-id="cd51e-108">Database file names on the source server that will be transferred.</span></span> <span data-ttu-id="cd51e-109">El**Archivo de origen** es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="cd51e-109">**Source File** is read only.</span></span>  
  
 <span data-ttu-id="cd51e-110">**Carpeta de origen**</span><span class="sxs-lookup"><span data-stu-id="cd51e-110">**Source Folder**</span></span>  
 <span data-ttu-id="cd51e-111">Carpeta del servidor de origen en la que se encuentran los archivos de la base de datos que se van a transferir.</span><span class="sxs-lookup"><span data-stu-id="cd51e-111">Folder on the source server where the database files to be transferred reside.</span></span> <span data-ttu-id="cd51e-112">La**Carpeta de origen** es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="cd51e-112">**Source Folder** is read only.</span></span>  
  
 <span data-ttu-id="cd51e-113">**Recurso compartido de archivos de red**</span><span class="sxs-lookup"><span data-stu-id="cd51e-113">**Network File Share**</span></span>  
 <span data-ttu-id="cd51e-114">Carpeta compartida de red del servidor de origen desde donde se transferirán los archivos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cd51e-114">Network shared folder on the source server from where the database files will be transferred.</span></span> <span data-ttu-id="cd51e-115">Utilice **Recurso compartido de archivos de red** cuando transfiera una base de datos en el modo sin conexión especificando el **Método** **DatabaseOffline** en la página **Bases de datos** del cuadro de diálogo **Editor de la tarea Transferir bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="cd51e-115">Use **Network File Share** when you transfer a database in offline mode by specifying **DatabaseOffline** for **Method** in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="cd51e-116">Especifique la ubicación del recurso compartido de archivos de red, o bien haga clic en el botón Examinar **(…)** para buscar la ubicación del recurso compartido de archivos de red.</span><span class="sxs-lookup"><span data-stu-id="cd51e-116">Enter the network file share location, or click the browse button **(...)** to locate the network file share location.</span></span>  
  
 <span data-ttu-id="cd51e-117">Cuando transfiere una base de datos en modo sin conexión, los archivos de la base de datos se copian a la ubicación **Recurso compartido de archivos de red** del servidor de origen antes de ser transferidos al servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="cd51e-117">When you transfer a database in offline mode, the database files are copied to the **Network file share** location on the source server before they are transferred to the destination server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd51e-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd51e-118">See Also</span></span>  
 <span data-ttu-id="cd51e-119">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="cd51e-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="cd51e-120">[Editor de la tarea transferir bases de datos &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="cd51e-120">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="cd51e-121">Editor de la tarea Transferir bases de datos &#40;página Bases de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="cd51e-121">Transfer Database Task Editor &#40;Databases Page&#41;</span></span>](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
