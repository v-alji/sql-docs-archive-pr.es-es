---
title: MSSQLSERVER_7901 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7901 (Database Engine error)
ms.assetid: 2d0d19b9-947b-4474-9ff8-7e03019ab93d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fae6e55cbe7170f795aff85400da2c5cdaef780a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673006"
---
# <a name="mssqlserver_7901"></a><span data-ttu-id="17bc9-102">MSSQLSERVER_7901</span><span class="sxs-lookup"><span data-stu-id="17bc9-102">MSSQLSERVER_7901</span></span>
    
## <a name="details"></a><span data-ttu-id="17bc9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="17bc9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="17bc9-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="17bc9-104">Product Name</span></span>|<span data-ttu-id="17bc9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="17bc9-105">SQL Server</span></span>|  
|<span data-ttu-id="17bc9-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="17bc9-106">Event ID</span></span>|<span data-ttu-id="17bc9-107">7901</span><span class="sxs-lookup"><span data-stu-id="17bc9-107">7901</span></span>|  
|<span data-ttu-id="17bc9-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="17bc9-108">Event Source</span></span>|<span data-ttu-id="17bc9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="17bc9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="17bc9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="17bc9-110">Component</span></span>|<span data-ttu-id="17bc9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="17bc9-111">SQLEngine</span></span>|  
|<span data-ttu-id="17bc9-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="17bc9-112">Symbolic Name</span></span>|<span data-ttu-id="17bc9-113">DBCC2_DATABASE_IN_EMERGENCY_MODE</span><span class="sxs-lookup"><span data-stu-id="17bc9-113">DBCC2_DATABASE_IN_EMERGENCY_MODE</span></span>|  
|<span data-ttu-id="17bc9-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="17bc9-114">Message Text</span></span>|<span data-ttu-id="17bc9-115">Instrucción de reparación no procesada.</span><span class="sxs-lookup"><span data-stu-id="17bc9-115">The repair statement was not processed.</span></span> <span data-ttu-id="17bc9-116">No se permite este nivel de reparación cuando la base de datos está en modo de emergencia.</span><span class="sxs-lookup"><span data-stu-id="17bc9-116">This level of repair is not supported when the database is in emergency mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="17bc9-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="17bc9-117">Explanation</span></span>  
 <span data-ttu-id="17bc9-118">La base de datos está en modo de emergencia y se ha especificado un nivel de reparación distinto de REPAIR_ALLOW_DATA_LOSS.</span><span class="sxs-lookup"><span data-stu-id="17bc9-118">The database is in emergency mode and a repair level other than REPAIR_ALLOW_DATA_LOSS has been specified.</span></span> <span data-ttu-id="17bc9-119">Las reparaciones no pueden llevarse a cabo en el modo de emergencia, a menos que se especifique REPAIR_ALLOW_DATA_LOSS.</span><span class="sxs-lookup"><span data-stu-id="17bc9-119">Repairs cannot be made in emergency mode unless REPAIR_ALLOW_DATA_LOSS is specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="17bc9-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="17bc9-120">User Action</span></span>  
 <span data-ttu-id="17bc9-121">Vuelva a ejecutar el comando y especifique la opción REPAIR_ALLOW_DATA_LOSS.</span><span class="sxs-lookup"><span data-stu-id="17bc9-121">Rerun the command and specify the REPAIR_ALLOW_DATA_LOSS option.</span></span>  
  
  
