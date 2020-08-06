---
title: Propiedades de la programación (página Informes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.scheduleproperties.reports.f1
ms.assetid: 7db728bd-4b08-43ef-a49a-e8dcdd37cf89
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: da0b5255e73522572fa22da8668329a28f108104
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671357"
---
# <a name="schedule-properties-reports-page"></a>Propiedades de la programación (página Informes)
  Utilice esta página para ver una lista de todos los informes que utilizan esta programación compartida. Las programaciones pueden utilizarse para actualizar instantáneas de informe, generar un historial de informes, desencadenar una suscripción o hacer expirar una copia del informe almacenada en caché. Para averiguar cómo se usa la programación, vea la información de propiedad y suscripciones del informe.  
  
 Aunque esta página muestra cada informe que usa la programación compartida, no indica cuántas veces se usa la programación compartida dentro de ese informe único. Por ejemplo, supongamos que 20 diferentes suscriptores al informe Company Sales usan la misma programación compartida para desencadenar el procesamiento de suscripciones. En este caso, el informe Company Sales solamente aparecerá una vez en esta lista, aunque el informe tenga 20 referencias a la programación compartida.  
  
 Para abrir esta página, inicie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conéctese a un servidor de informes, abra la carpeta **Programaciones compartidas** , haga clic con el botón secundario en una programación compartida, seleccione **Propiedades**y, a continuación, haga clic en **Informes**.  
  
> [!NOTE]  
>  Esta característica no está disponible en todas las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Para obtener una lista de las características admitidas por las ediciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vea [características compatibles con las ediciones de SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) ( https://go.microsoft.com/fwlink/?linkid=232473) .  
  
## <a name="options"></a>Opciones  
 **Carpeta**  
 Especifica la ruta de acceso del informe.  
  
 **Report**  
 Especifica el nombre del informe que utiliza la programación.  
  
## <a name="see-also"></a>Consulte también  
 [Crear, modificar y eliminar programaciones](../subscriptions/create-modify-and-delete-schedules.md)   
 [Programaciones](../subscriptions/schedules.md)   
 [Servidor de informes en Management Studio ayuda de F1](report-server-in-management-studio-f1-help.md)   
 [Conectarse a un servidor de informes en Management Studio](connect-to-a-report-server-in-management-studio.md)   
 [Configurar las propiedades generales de un informe &#40;Administrador de informes&#41;](../configure-general-properties-for-a-report-report-manager.md)  
  
  
