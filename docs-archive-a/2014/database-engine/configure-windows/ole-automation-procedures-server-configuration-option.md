---
title: Ole Automation Procedures (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Ole Automation Procedures option
ms.assetid: e8982e05-4984-4406-9760-285e8c028ddf
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d34615ce1f808c1015c9c3d312a38a67dba291b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744299"
---
# <a name="ole-automation-procedures-server-configuration-option"></a><span data-ttu-id="41a0c-102">Ole Automation Procedures (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="41a0c-102">Ole Automation Procedures Server Configuration Option</span></span>
  <span data-ttu-id="41a0c-103">Utilice la opción `Ole Automation Procedures` para especificar si se pueden crear instancias de los objetos de OLE Automation en lotes de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41a0c-103">Use the `Ole Automation Procedures` option to specify whether OLE Automation objects can be instantiated within [!INCLUDE[tsql](../../includes/tsql-md.md)] batches.</span></span> <span data-ttu-id="41a0c-104">Esta opción también se puede configurar usando la administración basada en directivas o el procedimiento almacenado **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="41a0c-104">This option can also be configured using the Policy-Based Management or the **sp_configure** stored procedure.</span></span> <span data-ttu-id="41a0c-105">Para obtener más información, vea [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="41a0c-105">For more information, see [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span></span>  
  
 <span data-ttu-id="41a0c-106">La opción `Ole Automation Procedures` se puede establecer con los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="41a0c-106">The `Ole Automation Procedures` option can be set to the following values.</span></span>  
  
 <span data-ttu-id="41a0c-107">0</span><span class="sxs-lookup"><span data-stu-id="41a0c-107">0</span></span>  
 <span data-ttu-id="41a0c-108">Los procedimientos de automatización OLE están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="41a0c-108">OLE Automation Procedures are disabled.</span></span> <span data-ttu-id="41a0c-109">Valor predeterminado para las nuevas sesiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41a0c-109">Default for new instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="41a0c-110">1</span><span class="sxs-lookup"><span data-stu-id="41a0c-110">1</span></span>  
 <span data-ttu-id="41a0c-111">Los procedimientos de automatización OLE están habilitados.</span><span class="sxs-lookup"><span data-stu-id="41a0c-111">OLE Automation Procedures are enabled.</span></span>  
  
 <span data-ttu-id="41a0c-112">Cuando los procedimientos de automatización OLE están habilitados, una llamada a **sp_OACreate** iniciará el entorno de ejecución compartido OLE.</span><span class="sxs-lookup"><span data-stu-id="41a0c-112">When OLE Automation Procedures are enabled, a call to **sp_OACreate** will start the OLE shared execution environment.</span></span>  
  
 <span data-ttu-id="41a0c-113">El valor actual de la `Ole Automation Procedures` opción se puede ver y cambiar mediante el **sp_configure** procedimiento almacenado del sistema.</span><span class="sxs-lookup"><span data-stu-id="41a0c-113">The current value of the `Ole Automation Procedures` option can be viewed and changed by using the **sp_configure** system stored procedure.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="41a0c-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="41a0c-114">Examples</span></span>  
 <span data-ttu-id="41a0c-115">En el siguiente ejemplo se muestra cómo se ve la configuración actual de OLE Automation Procedures.</span><span class="sxs-lookup"><span data-stu-id="41a0c-115">The following example shows how to view the current setting of OLE Automation procedures.</span></span>  
  
```  
EXEC sp_configure 'Ole Automation Procedures';  
GO  
```  
  
 <span data-ttu-id="41a0c-116">En el ejemplo siguiente se muestra cómo se habilitan los procedimientos de automatización OLE.</span><span class="sxs-lookup"><span data-stu-id="41a0c-116">The following example shows how to enable OLE Automation procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Ole Automation Procedures', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="41a0c-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41a0c-117">See Also</span></span>  
 <span data-ttu-id="41a0c-118">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41a0c-118">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="41a0c-119">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41a0c-119">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="41a0c-120">[Configuración de Área expuesta](../../relational-databases/security/surface-area-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="41a0c-120">[Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md) </span></span>  
 [<span data-ttu-id="41a0c-121">Opciones de configuración de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="41a0c-121">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
