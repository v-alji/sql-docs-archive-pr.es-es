---
title: Administrar cachés (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- XMLA, cache
- XML for Analysis, cache
- clearing cache
- cache [Analysis Services]
ms.assetid: afad5c39-d4c3-4307-b3b9-a06617da0028
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdc5bcd2e0500749edfa298a871b6fec7243ddfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671768"
---
# <a name="managing-caches-xmla"></a>Administrar cachés (XMLA)
  Puede usar el comando [ClearCache](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/clearcache-element-xmla) en XML for Analysis (XMLA) para borrar la memoria caché de una dimensión o partición especificada. Al borrar las fuerzas de caché, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] se vuelve a generar la memoria caché para ese objeto.  
  
## <a name="specifying-objects"></a>Especificar objetos  
 La propiedad [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) del `ClearCache` comando solo puede contener una referencia de objeto para uno de los siguientes objetos. Si se utiliza una referencia de objeto para un objeto distinto de los siguientes, se produce un error:  
  
 Base de datos  
 Borra la memoria caché para todas las dimensiones y particiones contenidas en la base de datos.  
  
 Dimensión  
 Borra la memoria caché para la dimensión especificada.  
  
 Cubo  
 Borra la memoria caché para todas las particiones contenidas en los grupos de medida para el cubo.  
  
 Grupo de medida  
 Borra la memoria caché para todas las particiones contenidas en el grupo de medida.  
  
 Partition  
 Borra la memoria caché para la partición especificada.  
  
## <a name="see-also"></a>Consulte también  
 [Desarrollar con XMLA en Analysis Services](developing-with-xmla-in-analysis-services.md)  
  
  
