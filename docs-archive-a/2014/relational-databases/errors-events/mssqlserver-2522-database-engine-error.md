---
title: MSSQLSERVER_2522 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2522 (Database Engine error)
ms.assetid: 19b9b00c-330f-4dd3-9052-9d88bce83849
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60446c21599c02ee9c4bc96789b106b49b71582a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662993"
---
# <a name="mssqlserver_2522"></a>MSSQLSERVER_2522
    
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre de producto|SQL Server|  
|Id. de evento|2522|  
|Origen de eventos|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|DBCC_INDEX_FILEGROUP_IS_INVALID|  
|Texto del mensaje|No se puede procesar el índice I_NAME de la tabla O_NAME porque el grupo de archivos F_NAME no es válido.|  
  
## <a name="explanation"></a>Explicación  
 Este mensaje informativo indica que no se puede comprobar el índice porque uno de los identificadores del grupo de archivos que está almacenado en los metadatos del índice no existe. El Id. del grupo de archivos que no es válido puede pertenecer a los propios datos, a los datos de objetos grandes (LOB) o a los datos de desbordamiento de fila.  
  
 Si no hay ningún problema, todos los demás índices del mismo objeto se comprobarán.  
  
## <a name="user-action"></a>Acción del usuario  
  
### <a name="look-for-hardware-failure"></a>Busque un error de hardware  
 Ejecute un diagnóstico de hardware y corrija cualquier problema. Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware. Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.  
  
 Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema. Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco. Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.  
  
 Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware. Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.  
  
### <a name="restore-from-backup"></a>Restaure mediante la copia de seguridad  
 Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.  
  
### <a name="run-dbcc-checkdb"></a>Ejecute DBCC CHECKDB  
 No aplicable. Este error no puede repararse automáticamente.  
  
  
