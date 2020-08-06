---
title: MSSQLSERVER_15404 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15404 (Database Engine error)
ms.assetid: 69677f02-bc81-4e4a-99b8-5c1bd1de36df
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: beb854c866256728574e06f8c9efb50fb354e15a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675942"
---
# <a name="mssqlserver_15404"></a><span data-ttu-id="a7353-102">MSSQLSERVER_15404</span><span class="sxs-lookup"><span data-stu-id="a7353-102">MSSQLSERVER_15404</span></span>
    
## <a name="details"></a><span data-ttu-id="a7353-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a7353-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a7353-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a7353-104">Product Name</span></span>|<span data-ttu-id="a7353-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a7353-105">SQL Server</span></span>|  
|<span data-ttu-id="a7353-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a7353-106">Event ID</span></span>|<span data-ttu-id="a7353-107">15404</span><span class="sxs-lookup"><span data-stu-id="a7353-107">15404</span></span>|  
|<span data-ttu-id="a7353-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a7353-108">Event Source</span></span>|<span data-ttu-id="a7353-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a7353-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a7353-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a7353-110">Component</span></span>|<span data-ttu-id="a7353-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a7353-111">SQLEngine</span></span>|  
|<span data-ttu-id="a7353-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a7353-112">Symbolic Name</span></span>|<span data-ttu-id="a7353-113">SEC_NTGRP_ERROR</span><span class="sxs-lookup"><span data-stu-id="a7353-113">SEC_NTGRP_ERROR</span></span>|  
|<span data-ttu-id="a7353-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a7353-114">Message Text</span></span>|<span data-ttu-id="a7353-115">No se pudo obtener información sobre el grupo o usuario de Windows NT '*user*', código de error *code*.</span><span class="sxs-lookup"><span data-stu-id="a7353-115">Could not obtain information about Windows NT group/user '*user*', error code *code*.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a7353-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="a7353-116">Explanation</span></span>  
 <span data-ttu-id="a7353-117">Se usa 15404 en la autenticación cuando se especifica una entidad de seguridad no válida.</span><span class="sxs-lookup"><span data-stu-id="a7353-117">15404 is used in authentication when an invalid principal is specified.</span></span> <span data-ttu-id="a7353-118">O bien, la suplantación de una cuenta de Windows genera errores porque no hay ninguna relación de plena confianza entre la cuenta de servicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el dominio de la cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="a7353-118">Or, impersonation of a Windows account fails because there is no full trust relationship between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the domain of the Windows account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a7353-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a7353-119">User Action</span></span>  
 <span data-ttu-id="a7353-120">Compruebe que la entidad de seguridad de Windows existe y está escrita correctamente.</span><span class="sxs-lookup"><span data-stu-id="a7353-120">Check that the Windows principal exists and is not misspelled.</span></span>  
  
 <span data-ttu-id="a7353-121">Si este error se debe a que no hay una relación de plena confianza entre la cuenta de servicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el dominio de la cuenta de Windows, una de las acciones siguientes puede resolver el error:</span><span class="sxs-lookup"><span data-stu-id="a7353-121">If this error is the result of a lack of a full trust relationship between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the domain of the Windows account, one of the following actions can resolve the error:</span></span>  
  
-   <span data-ttu-id="a7353-122">Use una cuenta del mismo dominio que el usuario de Windows para el servicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7353-122">Use an account from the same domain as the Windows user for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="a7353-123">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] emplea una cuenta de equipo como Network Service o Local System, el dominio que contiene el usuario de Windows debe confiar en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a7353-123">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is using a machine account such as Network Service or Local System, the machine must be trusted by the domain containing the Windows User.</span></span>  
  
-   <span data-ttu-id="a7353-124">Use una cuenta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7353-124">Use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
  
