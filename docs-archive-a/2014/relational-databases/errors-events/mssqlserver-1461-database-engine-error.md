---
title: MSSQLSERVER_1461 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1461 (Database Engine error)
ms.assetid: fce10907-4753-441b-b624-f28e00ed7520
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6667728b2cc134632ddc538b662d73533ee4d6ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675945"
---
# <a name="mssqlserver_1461"></a><span data-ttu-id="60529-102">MSSQLSERVER_1461</span><span class="sxs-lookup"><span data-stu-id="60529-102">MSSQLSERVER_1461</span></span>
    
## <a name="details"></a><span data-ttu-id="60529-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="60529-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60529-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="60529-104">Product Name</span></span>|<span data-ttu-id="60529-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="60529-105">SQL Server</span></span>|  
|<span data-ttu-id="60529-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="60529-106">Event ID</span></span>|<span data-ttu-id="60529-107">1461</span><span class="sxs-lookup"><span data-stu-id="60529-107">1461</span></span>|  
|<span data-ttu-id="60529-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="60529-108">Event Source</span></span>|<span data-ttu-id="60529-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="60529-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="60529-110">Componente</span><span class="sxs-lookup"><span data-stu-id="60529-110">Component</span></span>|<span data-ttu-id="60529-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="60529-111">SQLEngine</span></span>|  
|<span data-ttu-id="60529-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="60529-112">Symbolic Name</span></span>|<span data-ttu-id="60529-113">DBM_SAFETY_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="60529-113">DBM_SAFETY_MISMATCH</span></span>|  
|<span data-ttu-id="60529-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="60529-114">Message Text</span></span>|<span data-ttu-id="60529-115">Se detectaron distintos niveles de seguridad en los servidores para la creación de reflejo de la base de datos "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="60529-115">Different database mirroring safety levels among servers were detected for database "%.\*ls".</span></span> <span data-ttu-id="60529-116">Se utilizará el nivel de seguridad FULL.</span><span class="sxs-lookup"><span data-stu-id="60529-116">The FULL safety level will be used.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="60529-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="60529-117">Explanation</span></span>  
 <span data-ttu-id="60529-118">Las conexiones de creación de reflejo se interrumpieron cuando el nivel de seguridad de la transacción se modificó porque la configuración de seguridad de la transacción era incoherente en las bases de datos principal y reflejada.</span><span class="sxs-lookup"><span data-stu-id="60529-118">Mirroring connections were broken when the transaction safety level was modified because the transaction safety settings were inconsistent on the principal and mirror databases.</span></span> <span data-ttu-id="60529-119">Se usará la configuración de seguridad predeterminada de seguridad de transacciones completa.</span><span class="sxs-lookup"><span data-stu-id="60529-119">The default safety setting of full-transaction safety will be used.</span></span> <span data-ttu-id="60529-120">La sesión se ejecutará en modo de alta seguridad.</span><span class="sxs-lookup"><span data-stu-id="60529-120">The session will run in high-safety mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="60529-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="60529-121">User Action</span></span>  
 <span data-ttu-id="60529-122">Para desactivar la seguridad de transacciones, vuelva a ejecutar la instrucción ALTER DATABASE *nombreDeBaseDeDatos* SET PARTNER SAFETY OFF en la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="60529-122">To set transaction safety off, rerun the ALTER DATABASE *database_name* SET PARTNER SAFETY OFF statement on the principal database.</span></span>  
  
  
