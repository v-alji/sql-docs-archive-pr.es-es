---
title: Iniciar sesión en una instancia de SQL Server (símbolo del sistema) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server], named instance of SQL Server
- log ins [SQL Server]
- logins [SQL Server], default instance of SQL Server
- command prompt [SQL Server], logins
- logging in [SQL Server]
ms.assetid: f67c11e3-c519-40c9-82c1-07efa9d9985e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 32028a30786117f2cafa76150867a0e726b07cda
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663104"
---
# <a name="log-in-to-an-instance-of-sql-server-command-prompt"></a>Iniciar una sesión en una instancia de SQL Server (símbolo del sistema)
  En este tema se describe cómo probar la conectividad a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]mediante la utilidad **sqlcmd** .  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-log-in-to-the-default-instance-of-sql-server"></a>Para iniciar una sesión en la instancia predeterminada de SQL Server  
  
1.  En el símbolo del sistema, escriba el siguiente comando para conectarse mediante la autenticación de Windows:  
  
    ```  
    sqlcmd [ /E ] [ /S servername ]  
  
    ```  
  
#### <a name="to-log-in-to-a-named-instance-of-sql-server"></a>Para iniciar una sesión en una instancia con nombre de SQL Server  
  
1.  En el símbolo del sistema, escriba el siguiente comando para conectarse mediante la autenticación de Windows:  
  
    ```  
    sqlcmd [ /E ] /S servername\instancename  
  
    ```  
  
## <a name="see-also"></a>Consulte también  
 [sqlcmd (utilidad)](../../tools/sqlcmd-utility.md)   
 [osql (utilidad)](../../tools/osql-utility.md)  
  
  
