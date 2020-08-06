---
title: clr enabled (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- assemblies [CLR integration], verifying can run
- clr enabled option
ms.assetid: 0722d382-8fd3-4fac-b4a8-cd2b7a7e0293
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b83cd0e00bdd32c8b44667209544c8e81b1e90c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663116"
---
# <a name="clr-enabled-server-configuration-option"></a><span data-ttu-id="9f07a-102">clr enabled (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="9f07a-102">clr enabled Server Configuration Option</span></span>
  <span data-ttu-id="9f07a-103">Utilice la opción clr enabled para especificar si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]puede ejecutar ensamblados de usuario.</span><span class="sxs-lookup"><span data-stu-id="9f07a-103">Use the clr enabled option to specify whether user assemblies can be run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9f07a-104">La opción clr enabled proporciona los valores que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="9f07a-104">The clr enabled option provides the following values.</span></span>  
  
|<span data-ttu-id="9f07a-105">Value</span><span class="sxs-lookup"><span data-stu-id="9f07a-105">Value</span></span>|<span data-ttu-id="9f07a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f07a-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9f07a-107">0</span><span class="sxs-lookup"><span data-stu-id="9f07a-107">0</span></span>|<span data-ttu-id="9f07a-108">Ejecución de ensamblado no permitida en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f07a-108">Assembly execution not allowed on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|<span data-ttu-id="9f07a-109">1</span><span class="sxs-lookup"><span data-stu-id="9f07a-109">1</span></span>|<span data-ttu-id="9f07a-110">Ejecución de ensamblado permitida en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f07a-110">Assembly execution allowed on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
  
 <span data-ttu-id="9f07a-111">Los servidores WOW64 se deben reiniciar antes de que los cambios de este valor surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="9f07a-111">WOW64 servers must be restarted before the changes to this setting will take effect.</span></span> <span data-ttu-id="9f07a-112">El reinicio no se requiere para otros tipos de servidor.</span><span class="sxs-lookup"><span data-stu-id="9f07a-112">Restart is not required for other server types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f07a-113">Cuando se ejecuta RECONFIGURE y se cambia el valor de ejecución de la opción clr enabled de 1 a 0, se descargan inmediatamente todos los dominios de aplicación que incluyen ensamblados de usuario.</span><span class="sxs-lookup"><span data-stu-id="9f07a-113">When RECONFIGURE is run and the run value of the clr enabled option is changed from 1 to 0, all application domains containing user assemblies are immediately unloaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9f07a-114">No se admite la ejecución de Common Language Runtime (CLR) con "agrupación ligera".</span><span class="sxs-lookup"><span data-stu-id="9f07a-114">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="9f07a-115">Deshabilite una de las dos opciones: "clr enabled" o "agrupación ligera".</span><span class="sxs-lookup"><span data-stu-id="9f07a-115">Disable one of two options: "clr enabled" or "lightweight pooling.</span></span> <span data-ttu-id="9f07a-116">Entre las características que dependen de CLR y que no funcionan correctamente en modo de fibra se incluyen el tipo de datos `hierarchy`, la replicación y la administración basada en directivas.</span><span class="sxs-lookup"><span data-stu-id="9f07a-116">Features that rely upon CLR and that do not work properly in fiber mode include the `hierarchy` data type, replication, and Policy-Based Management.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f07a-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f07a-117">Example</span></span>  
 <span data-ttu-id="9f07a-118">El ejemplo siguiente muestra primero la configuración actual de la opción clr enabled y después habilita la opción estableciendo su valor en 1.</span><span class="sxs-lookup"><span data-stu-id="9f07a-118">The following example first displays the current setting of the clr enabled option and then enables the option by setting the option value to 1.</span></span> <span data-ttu-id="9f07a-119">Para deshabilitar la opción, establezca el valor en 0.</span><span class="sxs-lookup"><span data-stu-id="9f07a-119">To disable the option, set the value to 0.</span></span>  
  
```  
EXEC sp_configure 'clr enabled';  
EXEC sp_configure 'clr enabled' , '1';  
RECONFIGURE;  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f07a-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9f07a-120">See Also</span></span>  
 <span data-ttu-id="9f07a-121">[lightweight pooling (opción de configuración del servidor)](lightweight-pooling-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="9f07a-121">[lightweight pooling Server Configuration Option](lightweight-pooling-server-configuration-option.md) </span></span>  
 <span data-ttu-id="9f07a-122">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9f07a-122">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="9f07a-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9f07a-123">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="9f07a-124">lightweight pooling (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="9f07a-124">lightweight pooling Server Configuration Option</span></span>](lightweight-pooling-server-configuration-option.md)  
  
  
