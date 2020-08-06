---
title: MSSQLSERVER_18452 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18456 (Database Engine error)
- 18452 (Database Engine error)
ms.assetid: 21da332c-e81d-4dee-a9d2-95598911b3be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5786d5de4748f6bbf59d2bd4acecd7ca77977f11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674141"
---
# <a name="mssqlserver_18452"></a><span data-ttu-id="b8a78-102">MSSQLSERVER_18452</span><span class="sxs-lookup"><span data-stu-id="b8a78-102">MSSQLSERVER_18452</span></span>
    
## <a name="details"></a><span data-ttu-id="b8a78-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b8a78-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8a78-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="b8a78-104">Product Name</span></span>|<span data-ttu-id="b8a78-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b8a78-105">SQL Server</span></span>|  
|<span data-ttu-id="b8a78-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b8a78-106">Event ID</span></span>|<span data-ttu-id="b8a78-107">18452</span><span class="sxs-lookup"><span data-stu-id="b8a78-107">18452</span></span>|  
|<span data-ttu-id="b8a78-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="b8a78-108">Event Source</span></span>|<span data-ttu-id="b8a78-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b8a78-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b8a78-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b8a78-110">Component</span></span>|<span data-ttu-id="b8a78-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b8a78-111">SQLEngine</span></span>|  
|<span data-ttu-id="b8a78-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b8a78-112">Symbolic Name</span></span>|<span data-ttu-id="b8a78-113">LOGON_INVALID_CONNECT</span><span class="sxs-lookup"><span data-stu-id="b8a78-113">LOGON_INVALID_CONNECT</span></span>|  
|<span data-ttu-id="b8a78-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b8a78-114">Message Text</span></span>|<span data-ttu-id="b8a78-115">Error de inicio de sesión del usuario '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="b8a78-115">Login failed for user '%.\*ls'.</span></span> <span data-ttu-id="b8a78-116">El inicio de sesión es un inicio de sesión de SQL Server y no se puede usar con la autenticación de Windows.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="b8a78-116">The login is a SQL Server login and cannot be used with Windows Authentication.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b8a78-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="b8a78-117">Explanation</span></span>  
 <span data-ttu-id="b8a78-118">El usuario intentó iniciar sesión con credenciales que no se pueden validar.</span><span class="sxs-lookup"><span data-stu-id="b8a78-118">The user attempted to login with credentials that cannot be validated.</span></span> <span data-ttu-id="b8a78-119">Las posibles causas son:</span><span class="sxs-lookup"><span data-stu-id="b8a78-119">Possible causes are:</span></span>  
  
-   <span data-ttu-id="b8a78-120">El inicio de sesión puede ser un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pero el servidor solo acepta la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="b8a78-120">The login may be a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login but the server only accepts Windows Authentication.</span></span>  
  
-   <span data-ttu-id="b8a78-121">Intenta conectar utilizando la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pero el inicio de sesión utilizado no existe en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8a78-121">You are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication but the login used does not exist on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="b8a78-122">El inicio de sesión puede utilizar la autenticación de Windows pero el inicio de sesión es una entidad de seguridad de Windows no reconocida.</span><span class="sxs-lookup"><span data-stu-id="b8a78-122">The login may use Windows Authentication but the login is an unrecognized Windows principal.</span></span> <span data-ttu-id="b8a78-123">Una entidad de seguridad de Windows no reconocida significa que Windows no puede comprobar el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="b8a78-123">An unrecognized Windows principal means that the login cannot be verified by Windows.</span></span> <span data-ttu-id="b8a78-124">Esto podría deberse a que el inicio de sesión de Windows procede de un dominio que no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="b8a78-124">This could be because the Windows login is from an untrusted domain.</span></span>  
  
 <span data-ttu-id="b8a78-125">Problemas similares pueden producir el error menos específico 18456.</span><span class="sxs-lookup"><span data-stu-id="b8a78-125">Similar problems can cause the less-specific error 18456.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b8a78-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b8a78-126">User Action</span></span>  
 <span data-ttu-id="b8a78-127">Si intenta establecer conexión usando la Autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], compruebe que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está configurado en modo de autenticación mixto.</span><span class="sxs-lookup"><span data-stu-id="b8a78-127">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured in Mixed Authentication Mode.</span></span>  
  
 <span data-ttu-id="b8a78-128">Si intenta establecer conexión usando la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], compruebe que el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] existe.</span><span class="sxs-lookup"><span data-stu-id="b8a78-128">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login exists.</span></span>  
  
 <span data-ttu-id="b8a78-129">Si intenta establecer conexión usando la Autenticación de Windows, compruebe que está registrado correctamente en el dominio correcto.</span><span class="sxs-lookup"><span data-stu-id="b8a78-129">If you are trying to connect using Windows Authentication, verify that you are properly logged into the correct domain.</span></span>  
  
  
