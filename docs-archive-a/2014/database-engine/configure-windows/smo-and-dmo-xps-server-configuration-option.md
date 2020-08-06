---
title: SMO y DMO XPs (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: bcd945ba-5d81-4124-9a2b-d87491c2a369
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f18fc6fafcf033113c983f990700158a10aec92a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749466"
---
# <a name="smo-and-dmo-xps-server-configuration-option"></a><span data-ttu-id="facf1-102">SMO and DMO XPs (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="facf1-102">SMO and DMO XPs Server Configuration Option</span></span>
  <span data-ttu-id="facf1-103">Utilice la opción SMO y DMO XPs para habilitar en este servidor los procedimientos almacenados de objetos de administración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SMO).</span><span class="sxs-lookup"><span data-stu-id="facf1-103">Use the SMO and DMO XPs option to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Object (SMO) extended stored procedures on this server.</span></span>  
  
 <span data-ttu-id="facf1-104">Tenga en cuenta que, a partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], DMO se ha quitado de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="facf1-104">Note than beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], DMO has been removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="facf1-105">En la siguiente tabla se describen los valores posibles:</span><span class="sxs-lookup"><span data-stu-id="facf1-105">The possible values are described in the following table:</span></span>  
  
|<span data-ttu-id="facf1-106">Value</span><span class="sxs-lookup"><span data-stu-id="facf1-106">Value</span></span>|<span data-ttu-id="facf1-107">Significado</span><span class="sxs-lookup"><span data-stu-id="facf1-107">Meaning</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="facf1-108">0</span><span class="sxs-lookup"><span data-stu-id="facf1-108">0</span></span>|<span data-ttu-id="facf1-109">SMO XPs no está disponible.</span><span class="sxs-lookup"><span data-stu-id="facf1-109">SMO XPs are not available.</span></span>|  
|<span data-ttu-id="facf1-110">1</span><span class="sxs-lookup"><span data-stu-id="facf1-110">1</span></span>|<span data-ttu-id="facf1-111">SMO XPs está disponible.</span><span class="sxs-lookup"><span data-stu-id="facf1-111">SMO XPs are available.</span></span> <span data-ttu-id="facf1-112">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="facf1-112">This is the default.</span></span>|  
  
 <span data-ttu-id="facf1-113">Esta configuración surte efecto inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="facf1-113">The setting takes effect immediately.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="facf1-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="facf1-114">Examples</span></span>  
 <span data-ttu-id="facf1-115">En el ejemplo siguiente se habilitan los procedimientos almacenados extendidos de SMO.</span><span class="sxs-lookup"><span data-stu-id="facf1-115">The following example enables SMO extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'SMO and DMO XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="facf1-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="facf1-116">See Also</span></span>  
 [<span data-ttu-id="facf1-117">Guía de programación para objetos de administración de SQL Server &#40;SMO&#41;</span><span class="sxs-lookup"><span data-stu-id="facf1-117">SQL Server Management Objects &#40;SMO&#41; Programming Guide</span></span>](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md)  
  
  
