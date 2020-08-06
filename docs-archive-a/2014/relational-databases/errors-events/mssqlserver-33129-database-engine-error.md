---
title: MSSQLSERVER_33129 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33129 (Database Engine error)
ms.assetid: 83b5f368-f1a1-4a40-9bb6-c77e2dec690f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da7735889dce8bfc33e624115e8245f8a02f46b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672051"
---
# <a name="mssqlserver_33129"></a><span data-ttu-id="a2f33-102">MSSQLSERVER_33129</span><span class="sxs-lookup"><span data-stu-id="a2f33-102">MSSQLSERVER_33129</span></span>
    
## <a name="details"></a><span data-ttu-id="a2f33-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a2f33-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a2f33-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a2f33-104">Product Name</span></span>|<span data-ttu-id="a2f33-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a2f33-105">SQL Server</span></span>|  
|<span data-ttu-id="a2f33-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a2f33-106">Event ID</span></span>|<span data-ttu-id="a2f33-107">33129</span><span class="sxs-lookup"><span data-stu-id="a2f33-107">33129</span></span>|  
|<span data-ttu-id="a2f33-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a2f33-108">Event Source</span></span>|<span data-ttu-id="a2f33-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a2f33-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a2f33-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a2f33-110">Component</span></span>|<span data-ttu-id="a2f33-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a2f33-111">SQLEngine</span></span>|  
|<span data-ttu-id="a2f33-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a2f33-112">Symbolic Name</span></span>|<span data-ttu-id="a2f33-113">SEC_CANNOT_DISABLE_WIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="a2f33-113">SEC_CANNOT_DISABLE_WIN_GROUP</span></span>|  
|<span data-ttu-id="a2f33-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a2f33-114">Message Text</span></span>|<span data-ttu-id="a2f33-115">No se puede usar ALTER_LOGIN con el argumento DISABLE para denegar el acceso a un grupo de Windows.</span><span class="sxs-lookup"><span data-stu-id="a2f33-115">Cannot use ALTER_LOGIN with the DISABLE argument to deny access to a Windows group.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a2f33-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="a2f33-116">Explanation</span></span>  
 <span data-ttu-id="a2f33-117">Este mensaje se produce cuando se intenta deshabilitar el inicio de sesión de un grupo de Windows.</span><span class="sxs-lookup"><span data-stu-id="a2f33-117">This message occurs when attempting to disable the login of a Windows Group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a2f33-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a2f33-118">User Action</span></span>  
 <span data-ttu-id="a2f33-119">El inicio de sesión de un grupo de Windows no se puede deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="a2f33-119">The login of a Windows Group cannot be disabled.</span></span> <span data-ttu-id="a2f33-120">Para quitar temporalmente un permiso de acceso concedido a un grupo de Windows, REVOQUE el permiso CONNECT del inicio de sesión del grupo de Windows.</span><span class="sxs-lookup"><span data-stu-id="a2f33-120">To temporarily remove access permission granted to a Windows Group, REVOKE the CONNECT permission of the login for the Windows Group.</span></span> <span data-ttu-id="a2f33-121">Los usuarios de Windows quizá sigan teniendo acceso a través de su inicio de sesión individual o de otro grupo de Windows.</span><span class="sxs-lookup"><span data-stu-id="a2f33-121">Windows users might still have access through their individual login or through another Windows Group.</span></span> <span data-ttu-id="a2f33-122">En el siguiente ejemplo se revoca el permiso de conexión al grupo de contabilidad del dominio WESTCOAST.</span><span class="sxs-lookup"><span data-stu-id="a2f33-122">The following example revokes the connect permission to the Accounting Group of the WESTCOAST domain.</span></span>  
  
```sql  
REVOKE CONNECT TO [WESTCOAST\Accounting];  
```  
  
  
