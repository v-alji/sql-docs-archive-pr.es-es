---
title: MSSQLSERVER_4064 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4064 (Database Engine error)
ms.assetid: 32112b90-0a2f-4834-a027-756811732be7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 201098aadeb6bd091f0312532138f692ae8079b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676507"
---
# <a name="mssqlserver_4064"></a><span data-ttu-id="01b65-102">MSSQLSERVER_4064</span><span class="sxs-lookup"><span data-stu-id="01b65-102">MSSQLSERVER_4064</span></span>
    
## <a name="details"></a><span data-ttu-id="01b65-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="01b65-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01b65-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="01b65-104">Product Name</span></span>|<span data-ttu-id="01b65-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="01b65-105">SQL Server</span></span>|  
|<span data-ttu-id="01b65-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="01b65-106">Event ID</span></span>|<span data-ttu-id="01b65-107">4064</span><span class="sxs-lookup"><span data-stu-id="01b65-107">4064</span></span>|  
|<span data-ttu-id="01b65-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="01b65-108">Event Source</span></span>|<span data-ttu-id="01b65-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="01b65-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="01b65-110">Componente</span><span class="sxs-lookup"><span data-stu-id="01b65-110">Component</span></span>|<span data-ttu-id="01b65-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="01b65-111">SQLEngine</span></span>|  
|<span data-ttu-id="01b65-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="01b65-112">Symbolic Name</span></span>|<span data-ttu-id="01b65-113">DB_UFAIL_FATAL</span><span class="sxs-lookup"><span data-stu-id="01b65-113">DB_UFAIL_FATAL</span></span>|  
|<span data-ttu-id="01b65-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="01b65-114">Message Text</span></span>|<span data-ttu-id="01b65-115">No se puede abrir la base de datos predeterminada del usuario.</span><span class="sxs-lookup"><span data-stu-id="01b65-115">Cannot open user default database.</span></span> <span data-ttu-id="01b65-116">Error de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="01b65-116">Login failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="01b65-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="01b65-117">Explanation</span></span>  
 <span data-ttu-id="01b65-118">El inicio de sesión de SQL Server no pudo conectarse debido a un problema con su base de datos predeterminada.</span><span class="sxs-lookup"><span data-stu-id="01b65-118">The SQL Server login was unable to connect because of a problem with its default database.</span></span> <span data-ttu-id="01b65-119">Bien la propia base de datos no es válida o el inicio de sesión no tiene permiso CONNECT para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="01b65-119">Either the database itself is invalid or the login lacks CONNECT permission on the database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="01b65-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="01b65-120">User Action</span></span>  
 <span data-ttu-id="01b65-121">Use ALTER LOGIN para cambiar la base de datos predeterminada del inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="01b65-121">Use ALTER LOGIN to change the login's default database.</span></span> <span data-ttu-id="01b65-122">Conceda el permiso CONNECT al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="01b65-122">Grant CONNECT permission to the login.</span></span>  
  
  
