---
title: MSSQLSERVER_12329 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 12329 (Database Engine error)
ms.assetid: 43f90287-36d5-46c2-ac91-a37202dcf6d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7576e32946ce0a453637273c449bbff20e5b6fac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673039"
---
# <a name="mssqlserver_12329"></a><span data-ttu-id="f1d91-102">MSSQLSERVER_12329</span><span class="sxs-lookup"><span data-stu-id="f1d91-102">MSSQLSERVER_12329</span></span>
    
## <a name="details"></a><span data-ttu-id="f1d91-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f1d91-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f1d91-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="f1d91-104">Product Name</span></span>|<span data-ttu-id="f1d91-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f1d91-105">SQL Server</span></span>|  
|<span data-ttu-id="f1d91-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f1d91-106">Event ID</span></span>|<span data-ttu-id="f1d91-107">12329</span><span class="sxs-lookup"><span data-stu-id="f1d91-107">12329</span></span>|  
|<span data-ttu-id="f1d91-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="f1d91-108">Event Source</span></span>|<span data-ttu-id="f1d91-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f1d91-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f1d91-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f1d91-110">Component</span></span>|<span data-ttu-id="f1d91-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f1d91-111">SQLEngine</span></span>|  
|<span data-ttu-id="f1d91-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f1d91-112">Symbolic Name</span></span>|<span data-ttu-id="f1d91-113">HK_UNSUPPORTED_NON_LATIN_CODEPAGE</span><span class="sxs-lookup"><span data-stu-id="f1d91-113">HK_UNSUPPORTED_NON_LATIN_CODEPAGE</span></span>|  
|<span data-ttu-id="f1d91-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f1d91-114">Message Text</span></span>|<span data-ttu-id="f1d91-115">Los tipos de datos char(n) y varchar(n) que usan una intercalación con una página de códigos distinta de 1252 no se admiten con *construct*.</span><span class="sxs-lookup"><span data-stu-id="f1d91-115">The data types char(n) and varchar(n) using a collation that has a code page other than 1252 are not supported with  *construct*.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f1d91-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="f1d91-116">Explanation</span></span>  
 <span data-ttu-id="f1d91-117">No use los tipos de datos char(n) y varchar(n) que usan una intercalación con una página de códigos distinta de 1252.</span><span class="sxs-lookup"><span data-stu-id="f1d91-117">Do not use the data types char(n) and varchar(n) using a collation that has a code page other than 1252.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f1d91-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f1d91-118">User Action</span></span>  
 <span data-ttu-id="f1d91-119">Una situación inesperada que puede producir este error es:</span><span class="sxs-lookup"><span data-stu-id="f1d91-119">One unexpected situation that can generate this error is:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = 'us_english')  
```  
  
 <span data-ttu-id="f1d91-120">Use esto en su lugar:</span><span class="sxs-lookup"><span data-stu-id="f1d91-120">Use this instead:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'us_english')  
```  
  
  
