---
title: Descripción de las transacciones en tablas optimizadas para memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 06075248-705e-4563-9371-b64cd609793c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0671bba8b7a0bda27ea27cf059cb9e3b1bb87b2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746403"
---
# <a name="understanding-transactions-on-memory-optimized-tables"></a>Descripción de las transacciones en tablas con optimización para memoria
  Las transacciones tienen acceso a las tablas optimizadas para memoria mediante control de simultaneidad optimista multiversión. Esto significa que hay versiones diferentes de los datos. Cada transacción opera en su propia versión coherente de forma transaccional de la base de datos, de forma independiente de otras transacciones que se ejecutan simultáneamente. Además, las transacciones operan con la suposición optimista de que no habrá ningún conflicto con otras transacciones simultáneas. Esto evita la necesidad de utilizar bloqueos, pero requiere que el sistema detecte los conflictos y termine una de las transacciones en conflicto. Los conflictos pueden aparecer solo para las transacciones de escritura contra escritura y para las transacciones de lectura contra escritura. Si hay un conflicto de escritura contra escritura, finaliza una transacción de escritura.  
  
 Hay similitudes entre el control de simultaneidad de las tablas optimizadas para memoria y el control de simultaneidad en las tablas basadas en disco para los niveles de aislamiento de transacción READ_COMMITTED_SNAPSHOT y SNAPSHOT. (Para obtener más información acerca de las tablas basadas en disco, vea [niveles de aislamiento basados en versiones de fila en el motor de base de datos](https://msdn.microsoft.com/library/ms177404\(v=sql.100\).aspx)).  
  
## <a name="topics-in-this-section"></a>Temas de esta sección  
 Esta sección sobre las transacciones en tablas optimizadas para memoria incluye los temas siguientes:  
  
-   [Instrucciones para los niveles de aislamiento de transacciones con tablas con optimización para memoria](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
-   [Instrucciones para la lógica de reintento de transacciones en tablas con optimización para memoria](guidelines-for-retry-logic-for-transactions-on-memory-optimized-tables.md)  
  
-   [Transacciones en tablas con optimización para memoria](transactions-in-memory-optimized-tables.md)  
  
-   [Niveles de aislamiento de transacción](transaction-isolation-levels.md)  
  
-   [Transacciones entre contenedores](cross-container-transactions.md)  
  
 Para saber más, vea [Control de la durabilidad de las transacciones](../relational-databases/logs/control-transaction-durability.md).  
  
## <a name="see-also"></a>Consulte también  
 [Tablas optimizadas para la memoria](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
