---
title: in-doubt xact resolution (opción de configuración del servidor) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- distributed transactions [SQL Server], unresolved transactions
- unresolved transactions
- in-doubt xact resolution option
ms.assetid: 3426fd32-cad2-4f2f-8ca9-e0296cc12703
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6b8db57ef2a4ee85d65e8c25de28ff7ada7994e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744870"
---
# <a name="in-doubt-xact-resolution-server-configuration-option"></a><span data-ttu-id="fd94b-102">in-doubt xact resolution (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="fd94b-102">in-doubt xact resolution Server Configuration Option</span></span>
  <span data-ttu-id="fd94b-103">Use la opción **in-doubt xact resolution** para controlar el resultado predeterminado de las transacciones que el Coordinador de transacciones distribuidas de [!INCLUDE[msCoName](../../includes/msconame-md.md)] (MS DTC) no consigue resolver.</span><span class="sxs-lookup"><span data-stu-id="fd94b-103">Use the **in-doubt xact resolution** option to control the default outcome of transactions that the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) is unable to resolve.</span></span> <span data-ttu-id="fd94b-104">La incapacidad de resolver estas transacciones puede estar relacionada con un tiempo de inactividad de MS DTC o con un resultado de transacción inesperado en el momento de la recuperación.</span><span class="sxs-lookup"><span data-stu-id="fd94b-104">Inability to resolve transactions may be related to the MS DTC down time or an unknown transaction outcome at the time of recovery.</span></span>  
  
 <span data-ttu-id="fd94b-105">La siguiente tabla enumera los valores de resultado posibles para resolver una transacción dudosa.</span><span class="sxs-lookup"><span data-stu-id="fd94b-105">The following table lists the possible outcome values for resolving an in-doubt transaction.</span></span>  
  
|<span data-ttu-id="fd94b-106">Valor del resultado</span><span class="sxs-lookup"><span data-stu-id="fd94b-106">Outcome value</span></span>|<span data-ttu-id="fd94b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd94b-107">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="fd94b-108">0</span><span class="sxs-lookup"><span data-stu-id="fd94b-108">0</span></span>|<span data-ttu-id="fd94b-109">Ninguna suposición.</span><span class="sxs-lookup"><span data-stu-id="fd94b-109">No presumption.</span></span> <span data-ttu-id="fd94b-110">La recuperación no es correcta si MS DTC no puede resolver ninguna transacción dudosa.</span><span class="sxs-lookup"><span data-stu-id="fd94b-110">Recovery fails if MS DTC cannot resolve any in-doubt transactions.</span></span>|  
|<span data-ttu-id="fd94b-111">1</span><span class="sxs-lookup"><span data-stu-id="fd94b-111">1</span></span>|<span data-ttu-id="fd94b-112">Suponer la confirmación.</span><span class="sxs-lookup"><span data-stu-id="fd94b-112">Presume commit.</span></span> <span data-ttu-id="fd94b-113">Se presupone que las transacciones MS DTC dudosas se han confirmado.</span><span class="sxs-lookup"><span data-stu-id="fd94b-113">Any MS DTC in-doubt transactions are presumed to have committed.</span></span>|  
|<span data-ttu-id="fd94b-114">2</span><span class="sxs-lookup"><span data-stu-id="fd94b-114">2</span></span>|<span data-ttu-id="fd94b-115">Suponer anulación.</span><span class="sxs-lookup"><span data-stu-id="fd94b-115">Presume abort.</span></span> <span data-ttu-id="fd94b-116">Se presupone que las transacciones MS DTC dudosas se han anulado.</span><span class="sxs-lookup"><span data-stu-id="fd94b-116">Any MS DTC in-doubt transactions are presumed to have aborted.</span></span>|  
  
 <span data-ttu-id="fd94b-117">Para minimizar la posibilidad de sufrir tiempos de inactividad prolongados, un administrador puede configurar esta opción para suponer una confirmación o una anulación, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fd94b-117">To minimize the possibility of extended down time, an administrator might choose to configure this option either to presume commit or presume abort, as shown in the following example.</span></span>  
  
```  
sp_configure 'show advanced options', 1  
GO  
RECONFIGURE  
GO  
sp_configure 'in-doubt xact resolution', 2 -- presume abort  
GO  
RECONFIGURE  
GO  
sp_configure 'show advanced options', 0  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="fd94b-118">De forma alternativa, un administrador puede dejar el valor predeterminado (ninguna suposición) y permitir que la recuperación no sea correcta para dejar constancia del error del DTC, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fd94b-118">Alternatively, the administrator might want to leave the default (no presumption) and allow recovery to fail in order to be made aware of a DTC failure, as shown in the following example.</span></span>  
  
```  
sp_configure 'show advanced options', 1  
GO  
RECONFIGURE  
GO  
sp_configure 'in-doubt xact resolution', 1 -- presume commit  
GO  
reconfigure  
GO  
ALTER DATABASE pubs SET ONLINE -- run recovery again  
GO  
sp_configure 'in-doubt xact resolution', 0 -- back to no assumptions  
GO  
sp_configure 'show advanced options', 0  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="fd94b-119">**in-doubt xact resolution** es una opción avanzada.</span><span class="sxs-lookup"><span data-stu-id="fd94b-119">The **in-doubt xact resolution** option is an advanced option.</span></span> <span data-ttu-id="fd94b-120">Si está usando el procedimiento almacenado del sistema **sp_configure** para cambiar la configuración, solo podrá cambiar el valor de **in-doubt xact resolution** si **show advanced options** se establece en 1.</span><span class="sxs-lookup"><span data-stu-id="fd94b-120">If you are using the **sp_configure** system stored procedure to change the setting, you can change **in-doubt xact resolution** only when **show advanced options** is set to 1.</span></span> <span data-ttu-id="fd94b-121">La configuración surte efecto inmediatamente, sin necesidad de reiniciar un servidor.</span><span class="sxs-lookup"><span data-stu-id="fd94b-121">The setting takes effect immediately without a server restart.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fd94b-122">La configuración coherente de esta opción en todas las instancias de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implicadas en cualquier transacción distribuida ayuda a evitar incoherencias en los datos.</span><span class="sxs-lookup"><span data-stu-id="fd94b-122">Consistent configuration of this option across all [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances involved in any distributed transactions will help avoid data inconsistencies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd94b-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd94b-123">See Also</span></span>  
 <span data-ttu-id="fd94b-124">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fd94b-124">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="fd94b-125">[Opciones de configuración de servidor &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fd94b-125">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="fd94b-126">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd94b-126">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
