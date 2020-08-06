---
title: MSSQL_ENG018456 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG018456 error
ms.assetid: 3daa8144-d81f-445a-b6c3-4bb3e9fd1526
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b05ca549781215e0c4f247110fee87f6def56f04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746935"
---
# <a name="mssql_eng018456"></a><span data-ttu-id="d9643-102">MSSQL_ENG018456</span><span class="sxs-lookup"><span data-stu-id="d9643-102">MSSQL_ENG018456</span></span>
    
## <a name="message-details"></a><span data-ttu-id="d9643-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="d9643-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d9643-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="d9643-104">Product Name</span></span>|<span data-ttu-id="d9643-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d9643-105">SQL Server</span></span>|  
|<span data-ttu-id="d9643-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d9643-106">Event ID</span></span>|<span data-ttu-id="d9643-107">18456</span><span class="sxs-lookup"><span data-stu-id="d9643-107">18456</span></span>|  
|<span data-ttu-id="d9643-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="d9643-108">Event Source</span></span>|<span data-ttu-id="d9643-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d9643-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d9643-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d9643-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="d9643-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d9643-111">Symbolic Name</span></span>||  
|<span data-ttu-id="d9643-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d9643-112">Message Text</span></span>|<span data-ttu-id="d9643-113">Error de inicio de sesión del usuario '%.\*ls'.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="d9643-113">Login failed for user '%.\*ls'.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d9643-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="d9643-114">Explanation</span></span>  
 <span data-ttu-id="d9643-115">El error MSSQL_ENG018456 se produce cuando no se puede iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="d9643-115">Error MSSQL_ENG018456 is raised whenever a login attempt fails.</span></span> <span data-ttu-id="d9643-116">Si el mensaje de error incluye la cuenta **distributor_admin** (Error de inicio de sesión del usuario 'distributor_admin'.), el problema reside en la cuenta utilizada en la replicación.</span><span class="sxs-lookup"><span data-stu-id="d9643-116">If the error message includes the account **distributor_admin** (Login failed for user 'distributor_admin'.), the issue is with an account used by replication.</span></span> <span data-ttu-id="d9643-117">La replicación crea un servidor remoto, **repl_distributor**, que permite la comunicación entre el distribuidor y el publicador.</span><span class="sxs-lookup"><span data-stu-id="d9643-117">Replication creates a remote server, **repl_distributor**, which allows communication between the Distributor and Publisher.</span></span> <span data-ttu-id="d9643-118">El inicio de sesión **distributor_admin** se asocia con este servidor remoto y debe tener una contraseña válida.</span><span class="sxs-lookup"><span data-stu-id="d9643-118">The login **distributor_admin** is associated with this remote server and must have a valid password.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d9643-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d9643-119">User Action</span></span>  
 <span data-ttu-id="d9643-120">Asegúrese de que ha especificado una contraseña para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="d9643-120">Ensure that you have specified a password for this account.</span></span> <span data-ttu-id="d9643-121">Para más información, vea [Proteger el distribuidor](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="d9643-121">For more information, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9643-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d9643-122">See Also</span></span>  
 [<span data-ttu-id="d9643-123">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="d9643-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
