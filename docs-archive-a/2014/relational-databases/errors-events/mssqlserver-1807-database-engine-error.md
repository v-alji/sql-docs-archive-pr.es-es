---
title: MSSQLSERVER_1807 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1807 (Database Engine error)
ms.assetid: 13c1b240-098b-4d9e-89aa-21599548e074
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 261d352084e490fb7f9216e1a7e352542e85a6f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672074"
---
# <a name="mssqlserver_1807"></a><span data-ttu-id="f81ab-102">MSSQLSERVER_1807</span><span class="sxs-lookup"><span data-stu-id="f81ab-102">MSSQLSERVER_1807</span></span>
    
## <a name="details"></a><span data-ttu-id="f81ab-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f81ab-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f81ab-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="f81ab-104">Product Name</span></span>|<span data-ttu-id="f81ab-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f81ab-105">SQL Server</span></span>|  
|<span data-ttu-id="f81ab-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f81ab-106">Event ID</span></span>|<span data-ttu-id="f81ab-107">1807</span><span class="sxs-lookup"><span data-stu-id="f81ab-107">1807</span></span>|  
|<span data-ttu-id="f81ab-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="f81ab-108">Event Source</span></span>|<span data-ttu-id="f81ab-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f81ab-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f81ab-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f81ab-110">Component</span></span>|<span data-ttu-id="f81ab-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f81ab-111">SQLEngine</span></span>|  
|<span data-ttu-id="f81ab-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f81ab-112">Symbolic Name</span></span>|<span data-ttu-id="f81ab-113">CANNOT_EX_LOCK</span><span class="sxs-lookup"><span data-stu-id="f81ab-113">CANNOT_EX_LOCK</span></span>|  
|<span data-ttu-id="f81ab-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f81ab-114">Message Text</span></span>|<span data-ttu-id="f81ab-115">No se puede obtener un bloqueo exclusivo en la base de datos '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="f81ab-115">Could not obtain exclusive lock on database '%.\*ls'.</span></span> <span data-ttu-id="f81ab-116">Intente la operación en otro momento.</span><span class="sxs-lookup"><span data-stu-id="f81ab-116">Retry the operation later.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f81ab-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="f81ab-117">Explanation</span></span>  
 <span data-ttu-id="f81ab-118">Una operación que necesita acceso exclusivo a la base de datos no pudo obtenerlo.</span><span class="sxs-lookup"><span data-stu-id="f81ab-118">An operation that required exclusive access to the database was unable to obtain it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f81ab-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f81ab-119">User Action</span></span>  
 <span data-ttu-id="f81ab-120">Desconecte todas las conexiones a esa base de datos o vuelva a intentar ejecutar la consulta en otro momento.</span><span class="sxs-lookup"><span data-stu-id="f81ab-120">Disconnect all the connections to that database or try the query again later.</span></span>  
  
  
