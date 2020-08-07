---
title: MSSQLSERVER_50000 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 50000 [SQL Server Native Client setup error]
ms.assetid: 5426d87a-d5d9-4984-b211-b07d69e834a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3cc805042bff7259a311ca3f2acf4c26db59381b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746300"
---
# <a name="mssqlserver_50000"></a><span data-ttu-id="08cd1-102">MSSQLSERVER_50000</span><span class="sxs-lookup"><span data-stu-id="08cd1-102">MSSQLSERVER_50000</span></span>
    
## <a name="details"></a><span data-ttu-id="08cd1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="08cd1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08cd1-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="08cd1-104">Product Name</span></span>|<span data-ttu-id="08cd1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="08cd1-105">SQL Server</span></span>|  
|<span data-ttu-id="08cd1-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="08cd1-106">Product Version</span></span>|<span data-ttu-id="08cd1-107">11.0</span><span class="sxs-lookup"><span data-stu-id="08cd1-107">11.0</span></span>|  
|<span data-ttu-id="08cd1-108">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="08cd1-108">Event ID</span></span>|<span data-ttu-id="08cd1-109">50000</span><span class="sxs-lookup"><span data-stu-id="08cd1-109">50000</span></span>|  
|<span data-ttu-id="08cd1-110">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="08cd1-110">Event Source</span></span>|<span data-ttu-id="08cd1-111">SETUP</span><span class="sxs-lookup"><span data-stu-id="08cd1-111">SETUP</span></span>|  
|<span data-ttu-id="08cd1-112">Componente</span><span class="sxs-lookup"><span data-stu-id="08cd1-112">Component</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="08cd1-113">Native Client</span><span class="sxs-lookup"><span data-stu-id="08cd1-113">Native Client</span></span>|  
|<span data-ttu-id="08cd1-114">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="08cd1-114">Symbolic Name</span></span>||  
|<span data-ttu-id="08cd1-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="08cd1-115">Message Text</span></span>|<span data-ttu-id="08cd1-116">Error de red al intentar leer el archivo '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="08cd1-116">A network error occurred while attempting to read from the file '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="08cd1-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="08cd1-117">Explanation</span></span>  
 <span data-ttu-id="08cd1-118">Se ha realizado un intento de instalación (o actualización) de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client en un equipo donde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ya está instalado y donde la instalación existente se realizó desde un archivo MSI al que se le cambió el nombre desde sqlncli.msi.</span><span class="sxs-lookup"><span data-stu-id="08cd1-118">An attempt was made to install (or update) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client on a computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is already installed, and where the existing installation was from an MSI file that was renamed from sqlncli.msi.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="08cd1-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="08cd1-119">User Action</span></span>  
 <span data-ttu-id="08cd1-120">Para resolver este error, desinstale la versión existente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="08cd1-120">To resolve this error, uninstall the existing version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="08cd1-121">Para evitar este error, no instale [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client desde un archivo MSI que no se denomine sqlncli.msi.</span><span class="sxs-lookup"><span data-stu-id="08cd1-121">To prevent this error, do not install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client from an MSI file that is not named sqlncli.msi.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="08cd1-122">Solo para uso interno</span><span class="sxs-lookup"><span data-stu-id="08cd1-122">Internal-Only</span></span>  
  
