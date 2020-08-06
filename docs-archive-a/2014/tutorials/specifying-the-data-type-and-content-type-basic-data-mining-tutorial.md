---
title: Especificar el tipo de datos y el tipo de contenido (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 72484d27-3ef1-4f16-813c-2f43231fc2da
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 73ff61dbe439b9f2fb50f3a8004f4e7bcad8369a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747761"
---
# <a name="specifying-the-data-type-and-content-type-basic-data-mining-tutorial"></a>Especificar el tipo de datos y el tipo de contenido (Tutorial básico de minería de datos)
  Ahora que ha seleccionado qué columnas utilizar para generar la estructura y entrenar los modelos, realice los cambios necesarios en los datos predeterminados y tipos de contenido que establece el asistente.  
  
#### <a name="review-and-modify-content-type-and-data-type-for-each-column"></a>Revisar y modificar el tipo de contenido y el tipo de datos de cada columna  
  
1.  En la página **especificar el contenido y el tipo de datos de las columnas** , haga clic en **detectar** para ejecutar un algoritmo que determine los datos y los tipos de contenido predeterminados para cada columna.  
  
2.  Revise las entradas de las columnas tipo de **contenido** y **tipo de datos** y cámbielas si es necesario para asegurarse de que la configuración sea la misma que la que se muestra en la tabla siguiente.  
  
     Normalmente, el asistente detectará números y asignará un tipo de datos numérico adecuado, pero hay varias situaciones en las que podría desear tratar un número como texto. Por ejemplo, el **GeographyKey** se debe tratar como texto, porque no sería apropiado realizar operaciones matemáticas en este identificador.  
  
    |Columna|Tipo de contenido|Tipo de datos|  
    |------------|------------------|---------------|  
    |**Dirección línea1**|**Discrete**|**Texto**|  
    |**Dirección línea2**|**Discrete**|**Texto**|  
    |**Age**|**Continua**|**Long**|  
    |**Bike Buyer**|**Discrete**|**Long**|  
    |**Commute Distance**|**Discrete**|**Texto**|  
    |**CustomerKey**|**Clave**|**Long**|  
    |**DateLastPurchase**|**Continua**|**Date**|  
    |**Dirección de correo electrónico**|**Discrete**|**Texto**|  
    |**English Education**|**Discrete**|**Texto**|  
    |**English Occupation**|**Discrete**|**Texto**|  
    |**Nombre**|**Discrete**|**Texto**|  
    |**Mujer**|**Discrete**|**Texto**|  
    |**Geography Key**|**Discrete**|**Texto**|  
    |**House Owner Flag**|**Discrete**|**Texto**|  
    |**Last Name**|**Discrete**|**Texto**|  
    |**Marital Status**|**Discrete**|**Texto**|  
    |**Number Cars Owned**|**Discrete**|**Long**|  
    |**Number Children At Home**|**Discrete**|**Long**|  
    |**Región**|**Discrete**|**Texto**|  
    |**Total Children**|**Discrete**|**Long**|  
    |**Yearly Income**|**Continua**|**Double**|  
  
3.  Haga clic en **Next**.  
  
## <a name="next-task-in-lesson"></a>Siguiente tarea de la lección  
 [Especificar un conjunto de datos de prueba para la estructura &#40;tutorial básico de minería de datos&#41;](../../2014/tutorials/specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a>Tarea anterior de la lección  
 [Crear una estructura de modelo de minería de datos de destino &#40;tutorial básico de minería de datos&#41;](../../2014/tutorials/creating-a-targeted-mailing-mining-model-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a>Consulte también  
 [Tipos de contenido &#40;minería de datos&#41;](../../2014/analysis-services/data-mining/content-types-data-mining.md)   
 [Tipos de datos &#40;minería de datos&#41;](../../2014/analysis-services/data-mining/data-types-data-mining.md)  
  
  
