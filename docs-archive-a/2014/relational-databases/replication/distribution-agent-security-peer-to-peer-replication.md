---
title: Seguridad del Agente de distribución (replicación punto a punto) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.p2pwizard.DA.f1
ms.assetid: def6bf26-c640-4caf-ad30-05d1e649541d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72b5a52fbb3ddc11d0ea6f2c0b26786463e08eaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663391"
---
# <a name="distribution-agent-security-peer-to-peer-replication"></a>Seguridad del Agente de distribución (replicación punto a punto)
  La página **Seguridad del Agente de distribución** permite especificar las cuentas con las que el Agente de distribución se ejecuta y realiza conexiones con los equipos de una topología punto a punto. Para obtener información sobre los permisos requeridos por los agentes y las prácticas recomendadas que se aplican a la seguridad de replicación, vea [Modelo de seguridad del Agente de replicación](security/replication-agent-security-model.md) y [Prácticas recomendadas de seguridad de replicación](security/replication-security-best-practices.md).  
  
> [!NOTE]  
>  Si el Agente de distribución de una suscripción ya se ha configurado en una ejecución anterior de este asistente, no se pueden cambiar las credenciales que utiliza en este asistente. Si especifica credenciales nuevas, se omitirán. Para cambiar las credenciales, utilice el cuadro de diálogo **Propiedades de suscripción** . Para más información, consulte [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).  
  
## <a name="options"></a>Opciones  
 Haga clic en el botón de propiedades ( **...** ) de la fila de cada suscriptor para tener acceso al cuadro de diálogo **Seguridad del Agente de distribución** . Haga clic en **Ayuda** en el cuadro de diálogo **Seguridad del Agente de distribución** que se muestra para obtener más información sobre los permisos requeridos para las cuentas utilizadas por los agentes.  
  
 Una vez especificadas las opciones en uno de los cuadros de diálogo, la información de conexión del suscriptor aparece en la cuadrícula.  
  
 **Agente para el suscriptor**  
 El nombre de cada elemento del mismo nivel.  
  
 **Base de datos del mismo nivel**  
 La base de datos del mismo nivel que servirá tanto de base de datos de publicaciones como de base de datos de suscripciones.  
  
 **Conexión al distribuidor**  
 Contexto en el que se realiza la conexión al distribuidor. Las conexiones locales se realizan siempre utilizando el contexto de la cuenta de Windows con la que se ejecuta el agente. Este asistente crea suscripciones de inserción (la conexión local es la conexión al distribuidor), por lo que este campo muestra siempre: **Impersonate "\<Domain>\\<Login\>"** o **Impersonate "\<Computer>\\<Login\>"** .  
  
 **Conexión al suscriptor**  
 Contexto en el que se realiza la conexión al suscriptor. La conexión se puede realizar utilizando el contexto de una cuenta de Windows con la que se ejecute el agente o en el contexto de un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . En el campo se muestra uno de los siguientes: **Use login "\<Login>"** , **Impersonate "\<Domain>\\<Login\>"** o **Impersonate "\<Computer>\\<Login\>"** . [!INCLUDE[msCoName](../../includes/msconame-md.md)] recomienda que todas las conexiones se realicen utilizando el contexto de la cuenta de Windows.  
  
## <a name="see-also"></a>Consulte también  
 [Administrar una topología punto a punto &#40;programación de la replicación con Transact-SQL&#41;](administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md)   
 [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md)  
  
  
