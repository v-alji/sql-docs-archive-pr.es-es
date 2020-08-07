---
title: SERVERPROPERTY devuelve el resultado correcto para la propiedad LCID en SQL Server 2005 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SERVERPROPERTY function
ms.assetid: 833a2fc9-b480-4697-aa7b-9677e78ee0b4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ebb125a86e6e30f2c3638004593da7657f02f1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746103"
---
# <a name="serverproperty-returns-correct-result-for-lcid-property-in-sql-server-2005"></a>SERVERPROPERTY devuelve el resultado correcto para la propiedad LCID en SQL Server 2005
  Cuando SERVERPROPERTY('LCID') se ejecuta en servidores de intercalación binaria, la función devuelve un valor de identificador regional de Windows (LCID), independientemente de la intercalación actual del servidor.  
  
> [!NOTE]  
>  Para el caso de los archivos por lotes y archivos de seguimiento que contengan referencias a SERVERPROPERTY ('LCID') y que se ejecuten en otras instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el Asesor de actualizaciones detectará este cambio de comportamiento solo si el resto de instancias tienen la misma intercalación que la instancia actual de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="corrective-action"></a>Acción correctora  
 Modifique las aplicaciones de forma que SERVERPROPERTY('LCID') devuelva el LCID de Windows que corresponda con la intercalación del servidor.  
  
## <a name="see-also"></a>Consulte también  
 [Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md)   
 [SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;](sql-server-2014-upgrade-advisor.md)  
  
  
