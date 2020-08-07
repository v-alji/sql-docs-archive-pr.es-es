---
title: MSSQLSERVER_21898 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21898 (Database Engine error)
ms.assetid: 02405b21-3d4e-4c2d-b4b3-d7b1ec05edb4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 78ce7eacf7f026bf9977af2c367b954a3639b357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745780"
---
# <a name="mssqlserver_21898"></a><span data-ttu-id="51521-102">MSSQLSERVER_21898</span><span class="sxs-lookup"><span data-stu-id="51521-102">MSSQLSERVER_21898</span></span>
    
## <a name="details"></a><span data-ttu-id="51521-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="51521-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="51521-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="51521-104">Product Name</span></span>|<span data-ttu-id="51521-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="51521-105">SQL Server</span></span>|  
|<span data-ttu-id="51521-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="51521-106">Event ID</span></span>|<span data-ttu-id="51521-107">21898</span><span class="sxs-lookup"><span data-stu-id="51521-107">21898</span></span>|  
|<span data-ttu-id="51521-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="51521-108">Event Source</span></span>|<span data-ttu-id="51521-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="51521-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="51521-110">Componente</span><span class="sxs-lookup"><span data-stu-id="51521-110">Component</span></span>|<span data-ttu-id="51521-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="51521-111">SQLEngine</span></span>|  
|<span data-ttu-id="51521-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="51521-112">Symbolic Name</span></span>|<span data-ttu-id="51521-113">SQLErrorNum21898</span><span class="sxs-lookup"><span data-stu-id="51521-113">SQLErrorNum21898</span></span>|  
|<span data-ttu-id="51521-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="51521-114">Message Text</span></span>|<span data-ttu-id="51521-115">El publicador '%s' usa la base de datos de distribución '%s' y no '%s', que se requiere para hospedar la base de datos de publicación '%s'.</span><span class="sxs-lookup"><span data-stu-id="51521-115">The publisher '%s' uses distribution database '%s' and not '%s' which is required in order to host the publishing database '%s'.</span></span> <span data-ttu-id="51521-116">Ejecute `sp_changedistpublisher` en el distribuidor para cambiar la base de datos de distribución que usa el publicador por '%s'.</span><span class="sxs-lookup"><span data-stu-id="51521-116">Run `sp_changedistpublisher` at distributor '%s' to change the distribution database used by the publisher to '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="51521-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="51521-117">Explanation</span></span>  
 <span data-ttu-id="51521-118">`sp_validate_redirected_publisher` consulta msdb.dbo.MSdistpublishers en el distribuidor local para comprobar que la base de datos de distribución usada por el nuevo editor es la misma que la base de datos de distribución usada por el publicador original.</span><span class="sxs-lookup"><span data-stu-id="51521-118">`sp_validate_redirected_publisher` queries msdb.dbo.MSdistpublishers at the local distributor to verify that the distribution database used by the new publisher is the same as the distribution database used by the original publisher.</span></span> <span data-ttu-id="51521-119">Este error se devuelve cuando estas bases de datos son distintas, con lo que el editor no es un host adecuado para la base de datos del publicador.</span><span class="sxs-lookup"><span data-stu-id="51521-119">This error is returned when these databases are different, making the publisher an unsuitable host for the publisher database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="51521-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="51521-120">User Action</span></span>  
 <span data-ttu-id="51521-121">Ejecute el procedimiento almacenado `sp_changedistpublisher` para cambiar la base de datos de distribución para el nuevo publicador por la usada por el publicador original.</span><span class="sxs-lookup"><span data-stu-id="51521-121">Execute stored procedure `sp_changedistpublisher` to change the distribution database for the new publisher to that used by the original publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="51521-122">La ejecución de `sp_changedistpublisher` corregirá el problema si se ha especificado una base de datos de distribución errónea cuando `sp_adddistpublisher` se ejecutó en el distribuidor para el publicador.</span><span class="sxs-lookup"><span data-stu-id="51521-122">Running `sp_changedistpublisher` will address the problem if the wrong distribution database was entered when `sp_adddistpublisher` was run at the distributor for the publisher.</span></span> <span data-ttu-id="51521-123">No obstante, si el publicador remoto tiene publicaciones existentes de otra base de datos de publicación que haga uso de la base de datos de distribución identificada, este cambio no resulta adecuado.</span><span class="sxs-lookup"><span data-stu-id="51521-123">However, if the remote publisher has existing publications from another publishing database that make use of the identified distribution database, this change is not appropriate.</span></span> <span data-ttu-id="51521-124">La replicación con la base de datos de distribución con nombre se debe quitar sistemáticamente y, después, se debe volver a establecer con la base de datos de distribución del publicador original para que el publicador nuevo funcione como un host adecuado.</span><span class="sxs-lookup"><span data-stu-id="51521-124">Replication using the named distribution database needs to be systematically removed and then reestablished using the original publisher's distribution database in order for the new publisher to function as a suitable host.</span></span>  
  
  
