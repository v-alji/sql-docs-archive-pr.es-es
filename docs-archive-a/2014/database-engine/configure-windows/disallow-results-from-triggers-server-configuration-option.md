---
title: disallow results from triggers (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- triggers [SQL Server], result sets
- result sets [SQL Server], triggers
- disallow results from triggers option
ms.assetid: 47149073-307d-47a5-b7d2-66a737d3231d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f162a6e06706561d861bfc54a1ae4027f2c3466e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743631"
---
# <a name="disallow-results-from-triggers-server-configuration-option"></a><span data-ttu-id="98e35-102">disallow results from triggers (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="98e35-102">disallow results from triggers Server Configuration Option</span></span>
  <span data-ttu-id="98e35-103">Utilice la opción **disallow results from triggers** para controlar si los desencadenadores devuelven conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="98e35-103">Use the **disallow results from triggers** option to control whether triggers return result sets.</span></span> <span data-ttu-id="98e35-104">Los desencadenadores que devuelven conjuntos de resultados pueden provocar un comportamiento inesperado en aplicaciones que no estén diseñadas para utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="98e35-104">Triggers that return result sets may cause unexpected behavior in applications that are not designed to work with them.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] <span data-ttu-id="98e35-105">Se recomienda establecer este valor en 1.</span><span class="sxs-lookup"><span data-stu-id="98e35-105">We recommend that you set this value to 1.</span></span>  
  
 <span data-ttu-id="98e35-106">Si se asigna el valor 1, la opción **disallow results from triggers** se establece en el valor ON.</span><span class="sxs-lookup"><span data-stu-id="98e35-106">When set to 1, the **disallow results from triggers** option is set to ON.</span></span> <span data-ttu-id="98e35-107">El valor predeterminado para esta opción es 0 (OFF).</span><span class="sxs-lookup"><span data-stu-id="98e35-107">The default setting for this option is 0 (OFF).</span></span> <span data-ttu-id="98e35-108">Si a esta opción se le asigna el valor 1 (ON), se producirá un error cuando un desencadenador intente devolver un conjunto de resultados y el usuario recibirá el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="98e35-108">If this option is set to 1 (ON), any attempt by a trigger to return a result set fails, and the user receives the following error message:</span></span>  
  
 <span data-ttu-id="98e35-109">"Mensaje 524, nivel 16, estado 1, procedimiento \<Procedure Name>, línea \<Line#></span><span class="sxs-lookup"><span data-stu-id="98e35-109">"Msg 524, Level 16, State 1, Procedure \<Procedure Name>, Line \<Line#></span></span>  
  
 <span data-ttu-id="98e35-110">"Un desencadenador devolvió un conjunto de resultados pero la opción de servidor 'disallow_results_from_triggers' es true."</span><span class="sxs-lookup"><span data-stu-id="98e35-110">"A trigger returned a resultset and the server option 'disallow_results_from_triggers' is true."</span></span>  
  
 <span data-ttu-id="98e35-111">La opción **disallow results from triggers** se aplica en el nivel de instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y determina el comportamiento de todos los desencadenadores existentes en la instancia.</span><span class="sxs-lookup"><span data-stu-id="98e35-111">The **disallow results from triggers** option is applied at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance level, and it will determine behavior for all existing triggers within the instance.</span></span>  
  
 <span data-ttu-id="98e35-112">**disallow results from triggers** es una opción avanzada.</span><span class="sxs-lookup"><span data-stu-id="98e35-112">The **disallow results from triggers** option is an advanced option.</span></span> <span data-ttu-id="98e35-113">Si va a usar el procedimiento almacenado del sistema **sp_configure** para cambiar la configuración, solo puede cambiar el valor No permitir resultados de desencadenadores si **Mostrar opciones avanzadas** está establecido en 1.</span><span class="sxs-lookup"><span data-stu-id="98e35-113">If you are using the **sp_configure** system stored procedure to change the setting, you can change disallow results from triggers only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="98e35-114">La configuración surte efecto inmediatamente, sin necesidad de reiniciar un servidor.</span><span class="sxs-lookup"><span data-stu-id="98e35-114">The setting takes effect immediately without a server restart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e35-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98e35-115">See Also</span></span>  
 <span data-ttu-id="98e35-116">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="98e35-116">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="98e35-117">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98e35-117">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="98e35-118">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="98e35-118">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
