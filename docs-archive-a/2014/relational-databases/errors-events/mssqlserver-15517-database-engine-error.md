---
title: MSSQLSERVER_15517 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15517 (Database Engine error)
ms.assetid: f94287f5-129f-4c52-9d34-62b996088001
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b8e66e211faf03e1457953d0292e711cde1798ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675941"
---
# <a name="mssqlserver_15517"></a><span data-ttu-id="34a0a-102">MSSQLSERVER_15517</span><span class="sxs-lookup"><span data-stu-id="34a0a-102">MSSQLSERVER_15517</span></span>
    
## <a name="details"></a><span data-ttu-id="34a0a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="34a0a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34a0a-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="34a0a-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="34a0a-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="34a0a-105">Event ID</span></span>|<span data-ttu-id="34a0a-106">15517</span><span class="sxs-lookup"><span data-stu-id="34a0a-106">15517</span></span>|  
|<span data-ttu-id="34a0a-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="34a0a-107">Event Source</span></span>|<span data-ttu-id="34a0a-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="34a0a-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="34a0a-109">Componente</span><span class="sxs-lookup"><span data-stu-id="34a0a-109">Component</span></span>|<span data-ttu-id="34a0a-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="34a0a-110">SQLEngine</span></span>|  
|<span data-ttu-id="34a0a-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="34a0a-111">Symbolic Name</span></span>|<span data-ttu-id="34a0a-112">SEC_CANNOTEXECUTEASUSER</span><span class="sxs-lookup"><span data-stu-id="34a0a-112">SEC_CANNOTEXECUTEASUSER</span></span>|  
|<span data-ttu-id="34a0a-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="34a0a-113">Message Text</span></span>|<span data-ttu-id="34a0a-114">No se puede ejecutar como la entidad de seguridad de base de datos porque la entidad "*entidad*" no existe, este tipo de entidad de seguridad no se puede suplantar o el usuario no tiene permiso.</span><span class="sxs-lookup"><span data-stu-id="34a0a-114">Cannot execute as the database principal because the principal "*principal*" does not exist, this type of principal cannot be impersonated, or you do not have permission.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="34a0a-115">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="34a0a-115">User Action</span></span>  
 <span data-ttu-id="34a0a-116">Use el nombre de una entidad de seguridad existente u obtenga el permiso IMPERSONATE para esa entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="34a0a-116">Use the name of an existing principal or get the IMPERSONATE permission on that principal.</span></span>  
  
 <span data-ttu-id="34a0a-117">También puede producirse el evento 15517 después de que alguien que no sea el propietario de la base de datos original adjunte y restaure una base de datos.</span><span class="sxs-lookup"><span data-stu-id="34a0a-117">15517 can also occur after performing an attach and restore of a database by someone other than the original database owner.</span></span> <span data-ttu-id="34a0a-118">Para resolver este error, cambie el db_owner a un inicio de sesión en el servidor mediante el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="34a0a-118">To resolve this error, change the db_owner to a login on your server, by running the following command:</span></span>  
  
```  
ALTER AUTHORIZATION ON DATABASE:: DBName TO [NewLogin]  
```  
  
## <a name="see-also"></a><span data-ttu-id="34a0a-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34a0a-119">See Also</span></span>  
 [<span data-ttu-id="34a0a-120">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="34a0a-120">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
