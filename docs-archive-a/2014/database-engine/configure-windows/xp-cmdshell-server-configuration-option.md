---
title: xp_cmdshell (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- xp_cmdshell
ms.assetid: c147c9e1-b81d-49c8-b800-3019f4d86a13
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a7feec1765cf6ffaa3e46a300a5155ae73fb13db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677868"
---
# <a name="xp_cmdshell-server-configuration-option"></a><span data-ttu-id="68193-102">xp_cmdshell (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="68193-102">xp_cmdshell Server Configuration Option</span></span>
  <span data-ttu-id="68193-103">La opción **xp_cmdshell** es una opción de configuración del servidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que permite a los administradores del sistema controlar si el procedimiento almacenado extendido **xp_cmdshell** se puede ejecutar en un sistema.</span><span class="sxs-lookup"><span data-stu-id="68193-103">The **xp_cmdshell** option is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] server configuration option that enables system administrators to control whether the **xp_cmdshell** extended stored procedure can be executed on a system.</span></span> <span data-ttu-id="68193-104">La opción **xp_cmdshell** está deshabilitada de forma predeterminada en las instalaciones nuevas y se puede habilitar mediante Administración basada en directivas o ejecutando el procedimiento almacenado del sistema **sp_configure** , tal y como se muestra en el ejemplo de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="68193-104">By default, the **xp_cmdshell** option is disabled on new installations and can be enabled by using the Policy-Based Management or by running the **sp_configure** system stored procedure as shown in the following code example:</span></span>  
  
```  
-- To allow advanced options to be changed.  
EXEC sp_configure 'show advanced options', 1;  
GO  
-- To update the currently configured value for advanced options.  
RECONFIGURE;  
GO  
-- To enable the feature.  
EXEC sp_configure 'xp_cmdshell', 1;  
GO  
-- To update the currently configured value for this feature.  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="68193-105">Consulte también</span><span class="sxs-lookup"><span data-stu-id="68193-105">See Also</span></span>  
 <span data-ttu-id="68193-106">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="68193-106">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="68193-107">Administrar servidores mediante administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="68193-107">Administer Servers by Using Policy-Based Management</span></span>](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
