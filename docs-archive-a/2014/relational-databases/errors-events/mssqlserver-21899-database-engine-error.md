---
title: MSSQLSERVER_21899 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21899 (Database Engine error)
ms.assetid: 32b87a7c-5380-4638-b147-dd78618f6625
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cb1af04b56685d0e1b5a703b812d08d88909b693
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745778"
---
# <a name="mssqlserver_21899"></a><span data-ttu-id="19e19-102">MSSQLSERVER_21899</span><span class="sxs-lookup"><span data-stu-id="19e19-102">MSSQLSERVER_21899</span></span>
    
## <a name="details"></a><span data-ttu-id="19e19-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="19e19-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19e19-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="19e19-104">Product Name</span></span>|<span data-ttu-id="19e19-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="19e19-105">SQL Server</span></span>|  
|<span data-ttu-id="19e19-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="19e19-106">Event ID</span></span>|<span data-ttu-id="19e19-107">21899</span><span class="sxs-lookup"><span data-stu-id="19e19-107">21899</span></span>|  
|<span data-ttu-id="19e19-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="19e19-108">Event Source</span></span>|<span data-ttu-id="19e19-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="19e19-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="19e19-110">Componente</span><span class="sxs-lookup"><span data-stu-id="19e19-110">Component</span></span>|<span data-ttu-id="19e19-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="19e19-111">SQLEngine</span></span>|  
|<span data-ttu-id="19e19-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="19e19-112">Symbolic Name</span></span>|<span data-ttu-id="19e19-113">SQLErrorNum21899</span><span class="sxs-lookup"><span data-stu-id="19e19-113">SQLErrorNum21899</span></span>|  
|<span data-ttu-id="19e19-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="19e19-114">Message Text</span></span>|<span data-ttu-id="19e19-115">La consulta en el publicador redireccionado '%s' para determinar si hay entradas de sysserver para los suscriptores del publicador original '%s' no se ha realizado por el error '%d', mensaje de error '%s.</span><span class="sxs-lookup"><span data-stu-id="19e19-115">The query at the redirected publisher '%s' to determine whether there were sysserver entries for the subscribers of the original publisher '%s' failed with error '%d', error message '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="19e19-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="19e19-116">Explanation</span></span>  
 <span data-ttu-id="19e19-117">`sp_validate_redirected_publisher` consulta las tablas de metadatos de suscripción de la base de datos del publicador en el servidor remoto para determinar los suscriptores asociados.</span><span class="sxs-lookup"><span data-stu-id="19e19-117">`sp_validate_redirected_publisher` queries the subscription metadata tables of the publisher database at the remote server to determine its associated subscribers.</span></span> <span data-ttu-id="19e19-118">Se devuelve el error 21899 si no se puede realizar esta consulta.</span><span class="sxs-lookup"><span data-stu-id="19e19-118">Error 21899 is returned if this query fails.</span></span> <span data-ttu-id="19e19-119">La consulta de validación requiere acceso a la base de datos publicada en el publicador redirigido.</span><span class="sxs-lookup"><span data-stu-id="19e19-119">The validation query requires access to the published database at the redirected publisher.</span></span> <span data-ttu-id="19e19-120">Si el inicio de sesión especificado cuando se llama a `sp_adddistpublisher` para el publicador original no está autorizado para tener acceso a la base de datos publicada en el publicador redirigido, se devuelve el error 21899.</span><span class="sxs-lookup"><span data-stu-id="19e19-120">If the login specified when `sp_adddistpublisher` is called for the original publisher is not authorized to access the published database at the redirected publisher, error 21899 is returned.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="19e19-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="19e19-121">User Action</span></span>  
 <span data-ttu-id="19e19-122">Revise el mensaje de error citado para determinar la causa del error y llevar a cabo una acción correctora adecuada</span><span class="sxs-lookup"><span data-stu-id="19e19-122">Review the cited error message to determine the cause of the failure and take appropriate corrective action</span></span>  
  
  
