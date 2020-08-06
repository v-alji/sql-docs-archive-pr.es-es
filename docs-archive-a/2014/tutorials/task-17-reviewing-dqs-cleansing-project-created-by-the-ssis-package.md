---
title: 'Tarea 17: revisar el proyecto de limpieza de DQS creado por el paquete SSIS | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fc6cc258-72f5-4593-8edb-9f5bc66de9db
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0876a0b727e810f8834fcf5445958bf9884a87f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743702"
---
# <a name="task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package"></a>Tarea 17: Revisión del proyecto de limpieza de DQS creado por el paquete SSIS
  En esta tarea, abrirá el proyecto de DQS creado por el paquete SSIS en el Cliente DQS, revisará los resultados del proceso de limpieza y, opcionalmente, realizará una limpieza interactiva y exportará los resultados.  
  
1.  Inicie **Data Quality Client**.  
  
2.  Haga clic en **supervisión de actividades** en el panel **Administración** .  
  
3.  Ordene la lista en función de la **hora de inicio** de la actividad para ver el registro más reciente.  
  
4.  Tenga en cuenta que verá un nombre del proyecto con el siguiente formato: **CleanseAndCurate. cleane Supplier Data. GUID**.  
  
     ![Proyecto de limpieza de DQS creado por el paquete SSIS](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "Proyecto de limpieza de DQS creado por el paquete SSIS")  
  
5.  Observe que el valor del campo **es activo** está **activo**.  
  
6.  Haga clic en la pestaña **generador de perfiles** en el panel inferior para ver las estadísticas del generador de perfiles para la actividad de limpieza realizada por el paquete SSIS.  
  
7.  Haga clic en **cerrar** para cerrar la pantalla de **Administración** .  
  
8.  En la Página principal del **cliente DQS**, haga clic en **Abrir proyecto de calidad de datos** en el panel **proyectos de calidad de datos** .  
  
9. En la lista de proyectos, seleccione el proyecto creado por el componente Limpieza de DQS de SSIS. El nombre del proyecto debe tener el formato: **CleanseAndCurate. cleane Supplier Data. GUID (en color rojo)**. Es posible que tenga que ordenar la lista en función de la columna **fecha de creación** y buscar el registro más reciente.  
  
10. Haga clic en **Next**.  
  
11. La página **administrar y ver resultados** debe ser familiar desde la limpieza interactiva que hizo anteriormente en este tutorial.  
  
12. Revise los resultados de la limpieza. También puede hacer una limpieza interactiva y exportar los resultados a un archivo de Excel o a una base de datos en la página siguiente.  
  
13. Haga clic en **Next**. En esta página **exportar** , puede exportar los resultados a un archivo de Excel, a un archivo CSV o a una base de datos SQL.  
  
14. Haga clic en **Finalizar** para finalizar la actividad.  
  
15. En la Página principal del **cliente DQS**, haga clic en **supervisión de actividades** en el panel **Administración** .  
  
16. Observe que el valor del campo **isActive** del proyecto ha **finalizado** ahora.  
  
## <a name="next-step"></a>siguiente paso  
 [Conclusión](../../2014/tutorials/conclusion.md)  
  
  
