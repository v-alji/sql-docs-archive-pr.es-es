---
title: MSSQLSERVER_102 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 102 (Database Engine error)
ms.assetid: 264dc1a2-c8a0-4c89-b5f6-951baf950299
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 18c330b8d6a534ca11e2ad2c03f89793f8c832e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663009"
---
# <a name="mssqlserver_102"></a>MSSQLSERVER_102
    
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre de producto|SQL Server|  
|Id. de evento|102|  
|Origen de eventos|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|P_SYNTAXERR2|  
|Texto del mensaje|Sintaxis incorrecta cerca de '%.*ls'.|  
  
## <a name="explanation"></a>Explicación  
 Indica un error de sintaxis. La información adicional no está disponible porque el error impide que [!INCLUDE[ssDE](../../includes/ssde-md.md)] procese la instrucción.  
  
 Puede deberse a un intento de crear una clave simétrica mediante el cifrado RC4 desusado o RC4_128, cuando no está en el modo de compatibilidad 90 o 100.  
  
## <a name="user-action"></a>Acción del usuario  
 Busque la instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] para los errores de sintaxis.  
  
 Si creó una clave simétrica mediante RC4 o RC4_128, seleccione un cifrado más reciente como, por ejemplo, uno de los algoritmos de AES. (Se recomienda). Si debe usar RC4, emplee ALTER DATABASE SET COMPATIBILITY_LEVEL para establecer el nivel de compatibilidad de la base de datos en 90 o 100. (No se recomienda).  
  
  
