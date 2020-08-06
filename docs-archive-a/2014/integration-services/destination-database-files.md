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
# <a name="destination-database-files"></a>Archivos de la base de datos de destino
  Utilice el cuadro de diálogo **Archivos de la base de datos de destino** para ver o cambiar las ubicaciones y los nombres de archivos de la base de datos en el servidor de destino o para especificar una ubicación de archivo de red para la tarea Transferir bases de datos. Para obtener más información sobre esta tarea, vea [Tarea Transferir bases de datos](control-flow/transfer-database-task.md).  
  
 Para rellenar automáticamente este cuadro de diálogo con las ubicaciones y los nombres de archivos de la base de datos en el servidor de origen, especifique primero **SourceConnection**, **SourceDatabaseName**y **SourceDatabaseFiles** en la página **Bases de datos** del cuadro de diálogo **Editor de la tarea Transferir bases de datos** .  
  
## <a name="options"></a>Opciones  
 **Archivo de destino**  
 Nombres de los archivos de base de datos transferidos en el servidor de destino.  
  
 Escriba el nombre del archivo o haga clic en el nombre para editarlo.  
  
 **Carpeta de destino**  
 Carpeta del servidor de destino a la que se transferirán los archivos de la base de datos.  
  
 Escriba la ruta a la carpeta, haga clic en la ruta para editarla o bien, haga clic para examinar y buscar la carpeta donde desea transferir los archivos de la base de datos en el servidor de destino.  
  
 **Recurso compartido de archivos de red**  
 Carpeta compartida de red en el servidor de destino a la que se transferirán los archivos de la base de datos. Utilice **Recurso compartido de archivos de red** cuando transfiera una base de datos en el modo sin conexión especificando el **Método** **DatabaseOffline** en la página **Bases de datos** del cuadro de diálogo **Editor de la tarea Transferir bases de datos** .  
  
 Escriba la ubicación del recurso compartido de archivos de red o haga clic para examinar y buscar la ubicación del recurso compartido del archivo de red.  
  
 Cuando transfiera una base de datos en el modo sin conexión, los archivos se copian en la ubicación **Recurso compartido de archivos de red** antes de transferirlos a la ubicación **Carpeta de destino** .  
  
## <a name="see-also"></a>Consulte también  
 [Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor de la tarea transferir bases de datos &#40;página general&#41;](general-page-of-integration-services-designers-options.md)   
 [Editor de la tarea Transferir bases de datos &#40;página Bases de datos&#41;](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
