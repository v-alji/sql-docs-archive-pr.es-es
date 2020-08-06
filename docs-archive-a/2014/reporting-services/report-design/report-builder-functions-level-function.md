---
title: Función Level (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 41235402-bb9e-4cb7-b91e-431e77db19cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dedbf00ce8330242c95e9592f649d95171f0987a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672708"
---
# <a name="level-function-report-builder-and-ssrs"></a>Función Level (Generador de informes y SSRS)
  Devuelve el nivel actual de profundidad de una jerarquía recursiva.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
Level(scope)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *scope*  
 ( `String` ) (Opcional). Nombre de un conjunto de datos, un grupo o una región de datos que contiene los elementos de informe a los que se va a aplicar la función de agregado. Si no se especifica el parámetro *scope* , se usa el ámbito actual.  
  
## <a name="return-type"></a>Tipo de valor devuelto  
 Devuelve un valor `Integer`. Si el *ámbito* especifica un conjunto de datos o una región de datos, o especifica una agrupación de no recursiva (es decir, una agrupación sin `Parent` elemento), `Level` devuelve 0. Si se omite el parámetro *scope* , devuelve el nivel del ámbito actual.  
  
## <a name="remarks"></a>Observaciones  
 El valor que devuelve la función `Level` se basa en cero; es decir, el primer nivel de una jerarquía es 0.  
  
 La función `Level` puede utilizarse para aplicar sangría en una jerarquía recursiva, como puede ser una lista de empleados.  
  
 Para más información sobre jerarquías recursivas, vea [Crear grupos de jerarquía recursiva &#40;Generador de informes y SSRS&#41;](creating-recursive-hierarchy-groups-report-builder-and-ssrs.md).  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código devuelve el nivel de fila del grupo Employees:  
  
```  
=Level("Employees")  
```  
  
## <a name="see-also"></a>Consulte también  
 [Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md)   
 [Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](expression-examples-report-builder-and-ssrs.md)   
 [Tipos de datos en expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md)   
 [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
