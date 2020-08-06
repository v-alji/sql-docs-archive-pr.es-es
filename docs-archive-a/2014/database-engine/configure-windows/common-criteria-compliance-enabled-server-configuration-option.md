---
title: common criteria compliance enabled (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- common criteria compliance
helpviewer_keywords:
- CC (common criteria) [Database Engine]
- common criteria compliance [Database Engine]
- Risidual Information Protection [Database Engine]
- RIP (Residual Information Protection)
ms.assetid: 61766eea-c450-408d-af33-fbe7ef8c9ff2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6722d05351b8b9e80240abb4edef0633a97b6da0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663118"
---
# <a name="common-criteria-compliance-enabled-server-configuration-option"></a><span data-ttu-id="4b548-102">common criteria compliance enabled (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="4b548-102">common criteria compliance enabled Server Configuration Option</span></span>
  <span data-ttu-id="4b548-103">La opción common criteria compliance enabled habilita los siguientes elementos necesarios para Criterio común.</span><span class="sxs-lookup"><span data-stu-id="4b548-103">The common criteria compliance enabled option enables the following elements that are required for the Common Criteria.</span></span>  
  
|<span data-ttu-id="4b548-104">Criterios</span><span class="sxs-lookup"><span data-stu-id="4b548-104">Criteria</span></span>|<span data-ttu-id="4b548-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b548-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="4b548-106">Protección de información residual (RIP)</span><span class="sxs-lookup"><span data-stu-id="4b548-106">Residual Information Protection (RIP)</span></span>|<span data-ttu-id="4b548-107">RIP requiere que una asignación de memoria se sobrescriba con un patrón de bits conocido antes de que la memoria se reasigne a un nuevo recurso.</span><span class="sxs-lookup"><span data-stu-id="4b548-107">RIP requires a memory allocation to be overwritten with a known pattern of bits before memory is reallocated to a new resource.</span></span> <span data-ttu-id="4b548-108">Ajustarse al estándar RIP puede contribuir a mejorar la seguridad; sin embargo, sobrescribir la asignación de memoria puede ralentizar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4b548-108">Meeting the RIP standard can contribute to improved security; however, overwriting the memory allocation can slow performance.</span></span> <span data-ttu-id="4b548-109">Una vez habilitada la opción common criteria compliance enabled, se produce la sobrescritura.</span><span class="sxs-lookup"><span data-stu-id="4b548-109">After the common criteria compliance enabled option is enabled, the overwriting occurs.</span></span>|  
|<span data-ttu-id="4b548-110">La capacidad para ver estadísticas de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="4b548-110">The ability to view login statistics</span></span>|<span data-ttu-id="4b548-111">Una vez habilitada la opción common criteria compliance enabled, se habilita la auditoría de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="4b548-111">After the common criteria compliance enabled option is enabled, login auditing is enabled.</span></span> <span data-ttu-id="4b548-112">Cada vez que un usuario inicia sesión correctamente en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], se muestra la información acerca del último inicio de sesión correcto, el último inicio de sesión incorrecto y el número de intentos realizados entre la hora del último inicio de sesión correcto y la hora actual.</span><span class="sxs-lookup"><span data-stu-id="4b548-112">Each time a user successfully logs in to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], information about the last successful login time, the last unsuccessful login time, and the number of attempts between the last successful and current login times is made available.</span></span> <span data-ttu-id="4b548-113">Estas estadísticas de inicio de sesión se pueden ver consultando la vista de administración dinámica [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="4b548-113">These login statistics can be viewed by querying the [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) dynamic management view.</span></span>|  
|<span data-ttu-id="4b548-114">La columna GRANT no debe invalidar la tabla DENY</span><span class="sxs-lookup"><span data-stu-id="4b548-114">That column GRANT should not override table DENY</span></span>|<span data-ttu-id="4b548-115">Una vez habilitada la opción common criteria compliance enabled, una instrucción DENY de nivel de tabla tiene prioridad sobre una instrucción GRANT de nivel de columna.</span><span class="sxs-lookup"><span data-stu-id="4b548-115">After the common criteria compliance enabled option is enabled, a table-level DENY takes precedence over a column-level GRANT.</span></span> <span data-ttu-id="4b548-116">Cuando no está habilitada la opción, una instrucción GRANT de columna tiene prioridad sobre una instrucción DENY de tabla.</span><span class="sxs-lookup"><span data-stu-id="4b548-116">When the option is not enabled, a column-level GRANT takes precedence over a table-level DENY.</span></span>|  
  
 <span data-ttu-id="4b548-117">La opción common criteria compliance enabled es una opción avanzada.</span><span class="sxs-lookup"><span data-stu-id="4b548-117">The common criteria compliance enabled option is an advanced option.</span></span> <span data-ttu-id="4b548-118">Solo se evalúan y certifican los criterios comunes para las ediciones Enterprise y Datacenter.</span><span class="sxs-lookup"><span data-stu-id="4b548-118">Common criteria is only evaluated and certified for the Enterprise edition and Datacenter edition.</span></span> <span data-ttu-id="4b548-119">Para obtener el estado más reciente de la certificación de criterios comunes, consulte el sitio web [Criterios comunes de Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkId=616319) .</span><span class="sxs-lookup"><span data-stu-id="4b548-119">For the latest status of common criteria certification, see the [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) Web site.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4b548-120">Además de habilitar la opción common criteria compliance enabled, también debe descargar y ejecutar un script que termine la configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para cumplir con el nivel de garantía de evaluación 4+ (EAL4+) de Criterio común.</span><span class="sxs-lookup"><span data-stu-id="4b548-120">In addition to enabling the common criteria compliance enabled option, you also must download and run a script that finishes configuring [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to comply with Common Criteria Evaluation Assurance Level 4+ (EAL4+).</span></span> <span data-ttu-id="4b548-121">Este script se puede descargar desde el sitio web sobre [Criterio común de Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkId=616319) .</span><span class="sxs-lookup"><span data-stu-id="4b548-121">You can download this script from the [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) Web site.</span></span>  
  
 <span data-ttu-id="4b548-122">Si está utilizando el procedimiento almacenado del sistema sp_configure para cambiar la configuración, solo podrá cambiar la opción common criteria compliance enabled si Mostrar opciones avanzadas está establecido en 1.</span><span class="sxs-lookup"><span data-stu-id="4b548-122">If you are using the sp_configure system stored procedure to change the setting, you can change common criteria compliance enabled only when show advanced options is set to 1.</span></span> <span data-ttu-id="4b548-123">La configuración surte efecto cuando se reinicia el servidor.</span><span class="sxs-lookup"><span data-stu-id="4b548-123">The setting takes effect after the server is restarted.</span></span> <span data-ttu-id="4b548-124">Los valores posibles son 0 y 1:</span><span class="sxs-lookup"><span data-stu-id="4b548-124">The possible values are 0 and 1:</span></span>  
  
-   <span data-ttu-id="4b548-125">0 indica que no está habilitada la opción de cumplimiento del criterio común.</span><span class="sxs-lookup"><span data-stu-id="4b548-125">0 indicates that common criteria compliance is not enabled.</span></span> <span data-ttu-id="4b548-126">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4b548-126">This is the default.</span></span>  
  
-   <span data-ttu-id="4b548-127">1 indica que está habilitada la opción de cumplimiento del criterio común.</span><span class="sxs-lookup"><span data-stu-id="4b548-127">1 indicates that common criteria compliance is enabled.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4b548-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4b548-128">Examples</span></span>  
 <span data-ttu-id="4b548-129">El siguiente ejemplo habilita el cumplimiento del criterio común.</span><span class="sxs-lookup"><span data-stu-id="4b548-129">The following example enables common criteria compliance.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'common criteria compliance enabled', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b548-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b548-130">See Also</span></span>  
 [<span data-ttu-id="4b548-131">Opciones de configuración de servidor &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4b548-131">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
