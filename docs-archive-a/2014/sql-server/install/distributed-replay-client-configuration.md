---
title: Configuración del cliente de Distributed Replay | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ccf03e32-6bd9-43c0-b9b6-9fe0d9163339
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 53124029483c25ed7894b279283e1de02c647350
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677400"
---
# <a name="distributed-replay-client-configuration"></a>Configuración de Distributed Replay Client
  Use la página **Configuración de Distributed Replay Client** del Asistente para la instalación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el fin de especificar los usuarios a los que desee conceder permisos administrativos para el servicio Distributed Replay Client.  
  
 Los usuarios con permisos administrativos tendrán acceso ilimitado al servicio Distributed Replay Client.  
  
## <a name="options"></a>Opciones  
 **Nombre del controlador**  
 Este es un parámetro opcional y el valor predeterminado es \<*blank*> .  
  
 Escriba el nombre del controlador con el que se comunicará el equipo cliente para el servicio Distributed Replay Client. Tenga en cuenta lo siguiente:  
  
-   El nombre debe ser un nombre de dominio completo (FQDN). Por ejemplo, un llamado servidor1 en la jerarquía de productos de Microsoft puede tener un FQDN de servidor1.productos.microsoft.com.  
  
-   Si ya ha configurado un controlador, escriba el nombre del controlador mientras configura cada cliente.  
  
-   Si aún no ha configurado ningún controlador, puede dejar el nombre del controlador en blanco. Sin embargo, debe escribir manualmente el nombre del controlador en el archivo de **configuración de cliente** .  
  
 **Directorio de trabajo**  
 Especifique el directorio de trabajo para el servicio Distributed Replay Client.  
  
 El directorio de trabajo predeterminado es \<*drive letter*>:\Archivos de programa\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\WorkingDir\\.  
  
 **Directorio de resultados**  
 Especifique el directorio de resultados para el servicio Distributed Replay Client.  
  
 El directorio de resultados predeterminado es \<*drive letter*>:\Archivos de programa\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\ResultDir\\.  
  
  
