---
title: Editor del administrador de conexiones MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msmqconnectionmanager.f1
helpviewer_keywords:
- MSMQ Connection Manager Editor
ms.assetid: ef842cb4-82da-4550-85fe-9bedbc1e77c7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41d4231ce121d596c8d818485eccf5ddf6127470
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663574"
---
# <a name="msmq-connection-manager-editor"></a>administrador de conexiones MSMQ, editor del
  Use el cuadro de diálogo **Administrador de conexiones MSMQ** para especificar la ruta de acceso a una cola de mensajes de Message Queuing (que también recibe el nombre de MSMQ).  
  
 Para obtener más información acerca del administrador de conexiones MSMQ, vea [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md).  
  
> [!NOTE]  
>  El administrador de conexiones MSMQ admite colas públicas y privadas locales, además de colas públicas remotas. No admite colas privadas remotas. Para obtener una solución que utilice la tarea Script, vea [Enviar a una cola de mensajes privada remota con la tarea Script](control-flow/script-task.md).  
  
## <a name="options"></a>Opciones  
 **Nombre**  
 Proporcione un nombre único para el administrador de conexiones MSMQ en el flujo de trabajo. El nombre que indique se mostrará en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .  
  
 **Descripción**  
 Describa el administrador de conexiones. Como método recomendado, describa el administrador de conexiones desde el punto de vista de su propósito, para que los paquetes estén autodocumentados y sean más fáciles de mantener.  
  
 **Path**  
 Escriba la ruta de acceso completa de la cola de mensajes. El formato de la ruta de acceso depende del tipo de cola.  
  
|Tipo de cola|Ruta de acceso de ejemplo|  
|----------------|-----------------|  
|Público|\<computer name>\\<queue name\>|  
|Privada|\<computer name>\Private$\\<queue name\>|  
  
 Puede utilizar "." para representar el equipo local.  
  
 **Test**  
 Después de configurar el Administrador de conexiones MSMQ, confirme que la conexión es viable haciendo clic en **Probar**.  
  
## <a name="see-also"></a>Consulte también  
 [Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
