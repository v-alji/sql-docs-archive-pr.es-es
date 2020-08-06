---
title: GETDATE (expresión de SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- current date
- GETDATE function
- dates [Integration Services], GETDATE
ms.assetid: 6d20ec93-3244-4d63-baf6-70eff7bd598c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0acb384a8c3c3dfdae55c7172f341f9e32765e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671597"
---
# <a name="getdate-ssis-expression"></a>GETDATE (expresión de SSIS)
  Devuelve la fecha actual del sistema con formato DT_DBTIMESTAMP. La función GETDATE no tiene argumentos.  
  
> [!NOTE]  
>  El resultado devuelto de la función GETDATE tiene una longitud de 29 caracteres.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
GETDATE()  
```  
  
## <a name="arguments"></a>Argumentos  
 None  
  
## <a name="result-types"></a>Tipos de resultado  
 DT_DBTIMESTAMP  
  
## <a name="expression-examples"></a>Ejemplos de expresiones  
 Este ejemplo devuelve el año de la fecha actual.  
  
```  
DATEPART("year",GETDATE())  
```  
  
 Este ejemplo devuelve el número de días entre una fecha de la columna **ModifiedDate** y la fecha actual.  
  
```  
DATEDIFF("dd",ModifiedDate,GETDATE())  
```  
  
 Este ejemplo agrega tres meses a la fecha actual.  
  
```  
DATEADD("Month",3,GETDATE())  
```  
  
## <a name="see-also"></a>Consulte también  
 [GETUTCDATE &#40;expresión de SSIS&#41;](getutcdate-ssis-expression.md)   
 [Funciones &#40;expresión de SSIS&#41;](functions-ssis-expression.md)  
  
  
