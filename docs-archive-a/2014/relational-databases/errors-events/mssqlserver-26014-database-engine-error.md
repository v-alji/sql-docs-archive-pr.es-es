---
title: MSSQLSERVER_26014 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 26014 (Database Engine error)
ms.assetid: e2b0dfc7-0681-4e5d-8875-1d5f63534086
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8114183b212767d01013eee9387d8b2efa2e0d7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673032"
---
# <a name="mssqlserver_26014"></a><span data-ttu-id="49f0d-102">MSSQLSERVER_26014</span><span class="sxs-lookup"><span data-stu-id="49f0d-102">MSSQLSERVER_26014</span></span>
    
## <a name="details"></a><span data-ttu-id="49f0d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="49f0d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49f0d-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="49f0d-104">Product Name</span></span>|<span data-ttu-id="49f0d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="49f0d-105">SQL Server</span></span>|  
|<span data-ttu-id="49f0d-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="49f0d-106">Event ID</span></span>|<span data-ttu-id="49f0d-107">26014</span><span class="sxs-lookup"><span data-stu-id="49f0d-107">26014</span></span>|  
|<span data-ttu-id="49f0d-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="49f0d-108">Event Source</span></span>|<span data-ttu-id="49f0d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="49f0d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="49f0d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="49f0d-110">Component</span></span>|<span data-ttu-id="49f0d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="49f0d-111">SQLEngine</span></span>|  
|<span data-ttu-id="49f0d-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="49f0d-112">Symbolic Name</span></span>|<span data-ttu-id="49f0d-113">SNI_SSL_USER_CERT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="49f0d-113">SNI_SSL_USER_CERT_FAILURE</span></span>|  
|<span data-ttu-id="49f0d-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="49f0d-114">Message Text</span></span>|<span data-ttu-id="49f0d-115">No se puede cargar el certificado especificado por el usuario [Cert Hash (sha1) "%hs"].</span><span class="sxs-lookup"><span data-stu-id="49f0d-115">Unable to load user-specified certificate [Cert Hash(sha1) "%hs"].</span></span> <span data-ttu-id="49f0d-116">El servidor no acepta una conexión.</span><span class="sxs-lookup"><span data-stu-id="49f0d-116">The server will not accept a connection.</span></span> <span data-ttu-id="49f0d-117">Debe comprobar que el certificado está correctamente instalado.</span><span class="sxs-lookup"><span data-stu-id="49f0d-117">You should verify that the certificate is correctly installed.</span></span> <span data-ttu-id="49f0d-118">Consulte el tema sobre cómo configurar un certificado para usarlo con SSL en los Libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="49f0d-118">See "Configuring Certificate for Use by SSL" in Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="49f0d-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="49f0d-119">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="49f0d-120">trató de cargar el certificado mencionado en el mensaje pero se produjo un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="49f0d-120">attempted to load the certificate named in the message but the operation failed.</span></span> <span data-ttu-id="49f0d-121">Se debe resolver este problema para que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pueda utilizar este certificado.</span><span class="sxs-lookup"><span data-stu-id="49f0d-121">This problem must be resolved before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can use this certificate.</span></span>  
  
 <span data-ttu-id="49f0d-122">Entre las posibles causas del error figuran:</span><span class="sxs-lookup"><span data-stu-id="49f0d-122">Possible causes of the error include:</span></span>  
  
-   <span data-ttu-id="49f0d-123">El certificado puede haber sido movido o eliminado.</span><span class="sxs-lookup"><span data-stu-id="49f0d-123">The certificate could have been moved or deleted.</span></span>  
  
-   <span data-ttu-id="49f0d-124">Si el inicio de sesión usado por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha cambiado, puede que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no disponga de permiso para tener acceso al certificado.</span><span class="sxs-lookup"><span data-stu-id="49f0d-124">If the login used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has changed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] may not have permission to access the certificate.</span></span>  
  
-   <span data-ttu-id="49f0d-125">El certificado puede haber expirado.</span><span class="sxs-lookup"><span data-stu-id="49f0d-125">The certificate may have expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="49f0d-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="49f0d-126">User Action</span></span>  
 <span data-ttu-id="49f0d-127">Asegúrese de que el certificado mencionado en el mensaje existe en el sistema, es accesible y es válido para utilizarse.</span><span class="sxs-lookup"><span data-stu-id="49f0d-127">Make sure the certificate named in the message exists on the system, is accessible, and it is valid for use.</span></span>  
  
  
