---
title: Propiedades de Agente SQL Server (página Sistema de trabajo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.job.f1
ms.assetid: e171d13e-1302-4f0e-88be-67d656aec8d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 743a8d558e97e9ad83cfc66e9ef1adf2e1bc0c2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676299"
---
# <a name="sql-server-agent-properties-job-system-page"></a>Propiedades de Agente SQL Server (página Sistema de trabajo)
  Utilice esta página para ver y modificar la forma en que el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servicio del agente administra los trabajos.  
  
## <a name="options"></a>Opciones  
 **Intervalo de tiempo de espera de cierre (en segundos)**  
 Especifica el número de segundos que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] espera a que los trabajos finalicen antes del cierre. Si el trabajo sigue en ejecución después del intervalo especificado, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] detendrá de manera obligatoria el trabajo.  
  
 **Usar una cuenta de proxy de usuarios que no sean administradores**  
 Establece una cuenta de proxy de usuarios que no sean administradores para el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]y las versiones posteriores admiten varios servidores proxy; por lo tanto, esta opción solo es aplicable al administrar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Versiones del agente anteriores a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .  
  
 **Nombre de usuario**  
 Escriba el nombre del usuario de la cuenta proxy de usuarios que no sean administradores. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admite varios servidores proxy; por tanto, esta opción solo es aplicable al administrar versiones del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].  
  
 **Contraseña**  
 Escriba la contraseña del usuario de la cuenta proxy de usuarios que no sean administradores. [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y las versiones posteriores admiten varios servidores proxy; por tanto, esta opción solo es aplicable al administrar versiones del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].  
  
 **Dominio**  
 Escriba el dominio del usuario de la cuenta proxy de usuarios que no sean administradores. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admite varios servidores proxy; por tanto, esta opción solo es aplicable al administrar versiones del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].  
  
## <a name="see-also"></a>Consulte también  
 [Implementar trabajos](implement-jobs.md)  
  
  
