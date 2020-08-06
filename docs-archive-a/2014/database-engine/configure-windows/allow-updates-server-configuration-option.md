---
title: allow updates (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- allow updates option
ms.assetid: 3967c3ed-280a-4de8-a2ce-393e82745a7b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d7e3ede317509a2044be90635db46e30a932af66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674341"
---
# <a name="allow-updates-server-configuration-option"></a><span data-ttu-id="661cb-102">allow updates (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="661cb-102">allow updates Server Configuration Option</span></span>
  <span data-ttu-id="661cb-103">Esta opción aún está presente en el procedimiento almacenado **sp_configure** , pero su funcionalidad no está disponible en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="661cb-103">This option is still present in the **sp_configure** stored procedure, although its functionality is unavailable in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="661cb-104">La opción no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="661cb-104">The setting has no effect.</span></span> <span data-ttu-id="661cb-105">No se permiten las actualizaciones directas a las tablas del sistema.</span><span class="sxs-lookup"><span data-stu-id="661cb-105">Direct updates to the system tables are not supported.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="661cb-106">Si se cambia la opción **allow updates** , se producirá un error en la instrucción RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="661cb-106">Changing the **allow updates** option will cause the RECONFIGURE statement to fail.</span></span> <span data-ttu-id="661cb-107">Los cambios en la opción **allow updates** deben eliminarse de todos los scripts.</span><span class="sxs-lookup"><span data-stu-id="661cb-107">Changes to the **allow updates** option should be removed from all scripts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="661cb-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="661cb-108">See Also</span></span>  
 [<span data-ttu-id="661cb-109">Opciones de configuración de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="661cb-109">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
