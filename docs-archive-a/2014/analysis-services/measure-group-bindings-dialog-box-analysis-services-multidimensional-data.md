---
title: Cuadro de diálogo enlaces de grupo de medida (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.dimensionusage.definerelationship.measuregroupbindings.f1
helpviewer_keywords:
- Measure Group Bindings dialog box
ms.assetid: ed642780-5350-438e-af73-b9ceab3f876d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 78693901a5898b140d6efeed16b6f0eaa7577e69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750362"
---
# <a name="measure-group-bindings-dialog-box-analysis-services---multidimensional-data"></a>Cuadro de diálogo Enlaces de grupo de medida (Analysis Services - Datos multidimensionales)
  Use el cuadro de diálogo **Enlaces de grupo de medida** para crear y modificar las relaciones directas entre los atributos que no son de granularidad de una dimensión de cubo y las columnas de un grupo de medida para una relación de dimensión regular, así como para especificar opciones de procesamiento de valores NULL para los atributos de una dimensión de cubo del cuadro de diálogo **Definir relación** .  
  
## <a name="options"></a>Opciones  
 **Tabla de grupos de medida**  
 Muestra el nombre de la tabla de hechos para el grupo de medida seleccionado.  
  
 **Atributos**  
 Muestra una cuadrícula de tablas de atributos y dimensiones. Seleccione un atributo para crear o modificar las propiedades de **Relación** del mismo. La cuadrícula contiene las columnas siguientes:  
  
|Opción|Definición|  
|------------|----------------|  
|**Nombre del atributo**|Muestra el nombre del atributo.|  
|**Tabla de dimensiones**|Muestra el nombre de la tabla de dimensiones en la que se basa el atributo.|  
  
 **Relación**  
 Muestra una cuadrícula de las relaciones existentes entre las columnas de las tablas de dimensiones para el atributo seleccionado y las columnas de las tablas de hechos para el grupo de medida seleccionado, así como la opción de procesamiento de valores NULL para la relación. La cuadrícula contiene las columnas siguientes:  
  
|Opción|Definición|  
|------------|----------------|  
|**Columnas de dimensión**|Muestra las columnas de la tabla de dimensiones en la que se basa el atributo seleccionado en **Atributos** .|  
|**Columnas de grupo de medida**|Seleccione **Heredado de la dimensión** para utilizar la relación de grupo de medida heredado de la dimensión o seleccione una columna de la tabla de hechos en la que se basa el grupo de medida para definir explícitamente una relación.|  
|**Procesamiento de valores NULL**|Seleccione una opción de procesamiento de valores NULL para el atributo. Para más información sobre las opciones de procesamiento de valores NULL, vea [Elemento NullProcessing &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/nullprocessing-element-assl).|  
  
## <a name="see-also"></a>Consulte también  
 [Cuadro de diálogo definir relación &#40;Analysis Services de datos multidimensionales&#41;](define-relationship-dialog-box-analysis-services-multidimensional-data.md)   
 [Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
