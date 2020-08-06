---
title: Quitar una extensión de representación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting rendering extensions
- removing rendering extensions
- rendering extensions [Reporting Services], removing
ms.assetid: 2abfebfb-065f-45cc-a904-c914394cf900
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77a8a9ac44b35f338f978913985617e4f264ddb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673524"
---
# <a name="removing-a-rendering-extension"></a>Quitar una extensión de representación
  Para quitar una [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] extensión de representación, solo tiene que quitar el elemento de la `Extension` extensión de representación del archivo rsreportserver.config, ubicado en **%programfiles%\microsoft SQL Server \ MSRS10_50. \<Instance Name> \Reporting Services\ReportServer** . Si ha realizado entradas para un Diseñador de informes, así como un servidor de informes, quite `Extension` también el elemento del [archivo de configuración RSReportDesigner](../../report-server/rsreportdesigner-configuration-file.md) . Después de quitar la información de configuración, la extensión de representación de datos ya no estará disponible en el componente.  
  
## <a name="see-also"></a>Consulte también  
 [Archivos de configuración de Reporting Services](../../report-server/reporting-services-configuration-files.md)   
 [Implementar una extensión de representación](implementing-a-rendering-extension.md)   
 [Información general de las extensiones de representación](rendering-extensions-overview.md)   
 [Implementar la interfaz IRenderingExtension](implementing-the-irenderingextension-interface.md)   
 [Consideraciones de seguridad para las extensiones](../security-considerations-for-extensions.md)   
 [Implementación de una extensión de representación](deploying-a-rendering-extension.md)  
  
  
