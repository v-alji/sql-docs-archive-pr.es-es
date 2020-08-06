---
title: Cuentas de servicio (Asistente para la configuración de seguridad de la creación de reflejo de bases de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.serviceaccounts.f1
ms.assetid: d58d8f93-7888-4d66-af4d-969ef6a2dbee
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 58e49467a28e816c6592b1ded212b5aea0e6bc55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746485"
---
# <a name="service-accounts-configure-database-mirroring-security-wizard"></a>Cuentas de servicio (Asistente para la configuración de seguridad de la creación de reflejo de bases de datos)
  Al utilizar la autenticación de Windows, si las instancias del servidor usan cuentas diferentes, especifique las cuentas de servicio para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Estas cuentas de servicio deben ser cuentas de dominio (en el mismo dominio o en dominios de confianza).  
  
 Si todas las instancias del servidor utilizan la misma cuenta de dominio o la autenticación basada en certificados, deje los campos en blanco. Basta con hacer clic en **Finalizar**y el asistente configura automáticamente las cuentas en función de la cuenta del asistente actual.  
  
> [!IMPORTANT]  
>  Si los extremos de creación de reflejo de la base de datos de las instancias de servidor están configurados para usar certificados, debe dejar vacíos los campos de cuenta de servicio.  
  
 **Para configurar la creación de reflejo de la base de datos mediante SQL Server Management Studio**  
  
-   [Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md)  
  
-   [Iniciar el Asistente para la configuración de seguridad de la creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a>Opciones  
 **Principal**  
 Especifique la cuenta de servicio de la instancia de servidor principal. Escriba el nombre del dominio en mayúsculas:  
  
 *Dominio* \\ de *nombre de usuario*  
  
 **Reflejo**  
 Especifique la cuenta de servicio de la instancia del servidor reflejado. Escriba el nombre del dominio en mayúsculas:  
  
 *Dominio* \\ de *nombre de usuario*  
  
 **Testigo**  
 Especifique la cuenta de servicio de la instancia de servidor testigo. Escriba el nombre del dominio en mayúsculas:  
  
 *Dominio* \\ de *nombre de usuario*  
  
## <a name="see-also"></a>Consulte también  
 [Propiedades de la base de datos &#40;página Creación de reflejo&#41;](../../relational-databases/databases/database-properties-mirroring-page.md)   
 [Iniciar el Monitor de creación de reflejo de la base de datos &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md)   
 [Creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md)   
 [Configurar cuentas de inicio de sesión para la creación de reflejo de la base de datos o Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
  
