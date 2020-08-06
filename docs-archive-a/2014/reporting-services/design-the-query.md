---
title: Diseñar la consulta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptwizard.designquery.f1
ms.assetid: 2dad800f-10a1-453c-8761-2935b9826d84
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b56d99ec11b50ce53ef223a01eb5fc2766238ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747505"
---
# <a name="design-the-query"></a>Diseñar la consulta
  Utilice esta página del Asistente para informes para crear una consulta escribiéndola manualmente, usando el Generador de consultas para crear una consulta de forma interactiva, o importando una consulta de otro informe.  
  
 El tipo de origen de datos seleccionado en la página Seleccionar el origen de datos, una página anterior del Asistente para informes, determina la consulta que se puede escribir en esta página. Por ejemplo, si el tipo de origen de datos es [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , puede escribir [!INCLUDE[tsql](../includes/tsql-md.md)] instrucciones o nombres de procedimientos almacenados. Si el tipo de origen de datos es [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , el panel consulta está deshabilitado y no se puede escribir una consulta directamente. Puede especificar la consulta mediante el Generador de consultas.  
  
## <a name="options"></a>Opciones  
 **Cadena de consulta**  
 Escriba una consulta que recupere los datos que desea utilizar en el informe.  
  
 **Generador de consultas**  
 Haga clic en **Generador de consultas** para abrir un diseñador de consultas para el origen de datos o para importar una consulta de otro informe.  
  
 Para obtener más información acerca de los diseñadores de consultas, vea [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).  
  
## <a name="example"></a>Ejemplo  
 En el caso del tipo de origen de datos **Microsoft SQL Server**, la siguiente consulta recupera una lista de los apellidos de la tabla de base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] `Person` .  
  
```  
SELECT LastName FROM Person.Person;  
```  
  
 En el caso del tipo de origen de datos **Microsoft SQL Server**, la siguiente consulta ejecuta el [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] procedimiento almacenado `uspGetEmployeeManagers` para el empleado con el número de identificación 1:  
  
```  
EXEC uspgetEmployeeManagers '1';  
```  
  
## <a name="see-also"></a>Consulte también  
 [Ayuda del Asistente para informes](../../2014/reporting-services/report-wizard-help.md)   
 [Conjuntos de valores integrados de informe y conjuntos de recursos compartidos &#40;Generador de informes y SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)   
 [Agregar datos a un informe &#40;Generador de informes y SSRS&#41;](report-data/report-datasets-ssrs.md)  
  
  
