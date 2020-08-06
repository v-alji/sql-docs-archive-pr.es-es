---
title: Archivos de base de datos de destino | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.destdbfiles.f1
ms.assetid: f6f90417-86fb-4b8c-a790-0b215c344ef6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d0ab2c0ff39fc728afc17b59f0d4bae076e4022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676602"
---
# <a name="destination-database-files"></a><span data-ttu-id="cb2bd-102">Archivos de la base de datos de destino</span><span class="sxs-lookup"><span data-stu-id="cb2bd-102">Destination Database Files</span></span>
  <span data-ttu-id="cb2bd-103">Utilice el cuadro de diálogo **Archivos de la base de datos de destino** para ver o cambiar las ubicaciones y los nombres de archivos de la base de datos en el servidor de destino o para especificar una ubicación de archivo de red para la tarea Transferir bases de datos.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-103">Use the **Destination Database Files** dialog box to view or change the database file names and locations on the destination server, or to specify a network file location for the Transfer Database task.</span></span> <span data-ttu-id="cb2bd-104">Para obtener más información sobre esta tarea, vea [Tarea Transferir bases de datos](control-flow/transfer-database-task.md).</span><span class="sxs-lookup"><span data-stu-id="cb2bd-104">For more information about this task, see [Transfer Database Task](control-flow/transfer-database-task.md).</span></span>  
  
 <span data-ttu-id="cb2bd-105">Para rellenar automáticamente este cuadro de diálogo con las ubicaciones y los nombres de archivos de la base de datos en el servidor de origen, especifique primero **SourceConnection**, **SourceDatabaseName**y **SourceDatabaseFiles** en la página **Bases de datos** del cuadro de diálogo **Editor de la tarea Transferir bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="cb2bd-105">To automatically populate this dialog box with the database file names and locations on the source server, specify the **SourceConnection**, **SourceDatabaseName**, and **SourceDatabaseFiles** first in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cb2bd-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="cb2bd-106">Options</span></span>  
 <span data-ttu-id="cb2bd-107">**Archivo de destino**</span><span class="sxs-lookup"><span data-stu-id="cb2bd-107">**Destination File**</span></span>  
 <span data-ttu-id="cb2bd-108">Nombres de los archivos de base de datos transferidos en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-108">Names of the transferred database files on the destination server.</span></span>  
  
 <span data-ttu-id="cb2bd-109">Escriba el nombre del archivo o haga clic en el nombre para editarlo.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-109">Enter the file name, or click the file name to edit it.</span></span>  
  
 <span data-ttu-id="cb2bd-110">**Carpeta de destino**</span><span class="sxs-lookup"><span data-stu-id="cb2bd-110">**Destination Folder**</span></span>  
 <span data-ttu-id="cb2bd-111">Carpeta del servidor de destino a la que se transferirán los archivos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-111">Folder on the destination server where the database files will be transferred to.</span></span>  
  
 <span data-ttu-id="cb2bd-112">Escriba la ruta a la carpeta, haga clic en la ruta para editarla o bien, haga clic para examinar y buscar la carpeta donde desea transferir los archivos de la base de datos en el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-112">Enter the folder path, click the folder path to edit it, or click browse to locate the folder where you want to transfer the database files on the destination server.</span></span>  
  
 <span data-ttu-id="cb2bd-113">**Recurso compartido de archivos de red**</span><span class="sxs-lookup"><span data-stu-id="cb2bd-113">**Network File Share**</span></span>  
 <span data-ttu-id="cb2bd-114">Carpeta compartida de red en el servidor de destino a la que se transferirán los archivos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-114">Network shared folder on the destination server where the database files will be transferred to.</span></span> <span data-ttu-id="cb2bd-115">Utilice **Recurso compartido de archivos de red** cuando transfiera una base de datos en el modo sin conexión especificando el **Método** **DatabaseOffline** en la página **Bases de datos** del cuadro de diálogo **Editor de la tarea Transferir bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="cb2bd-115">Use **Network file share** when you transfer a database in offline mode by specifying **DatabaseOffline** for **Method** in the **Databases** page of the **Transfer Database Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="cb2bd-116">Escriba la ubicación del recurso compartido de archivos de red o haga clic para examinar y buscar la ubicación del recurso compartido del archivo de red.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-116">Enter the network file share location, or click browse to locate the network file share location.</span></span>  
  
 <span data-ttu-id="cb2bd-117">Cuando transfiera una base de datos en el modo sin conexión, los archivos se copian en la ubicación **Recurso compartido de archivos de red** antes de transferirlos a la ubicación **Carpeta de destino** .</span><span class="sxs-lookup"><span data-stu-id="cb2bd-117">When you transfer a database in offline mode, the database files are copied to the **Network file share** location before they are transferred to the **Destination folder** location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb2bd-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb2bd-118">See Also</span></span>  
 <span data-ttu-id="cb2bd-119">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="cb2bd-119">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="cb2bd-120">[Editor de la tarea transferir bases de datos &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="cb2bd-120">[Transfer Database Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="cb2bd-121">Editor de la tarea Transferir bases de datos &#40;página Bases de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="cb2bd-121">Transfer Database Task Editor &#40;Databases Page&#41;</span></span>](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
