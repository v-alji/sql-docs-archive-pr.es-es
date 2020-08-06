---
title: MSSQLSERVER_15661 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15661 (Database Engine error)
ms.assetid: 88b01bfb-74ce-4aa0-aec0-7885261c7ef3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 966e23e8d970c36eba81253228cc18ed4af3ff77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662070"
---
# <a name="mssqlserver_15661"></a><span data-ttu-id="46c9a-102">MSSQLSERVER_15661</span><span class="sxs-lookup"><span data-stu-id="46c9a-102">MSSQLSERVER_15661</span></span>
    
## <a name="details"></a><span data-ttu-id="46c9a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="46c9a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46c9a-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="46c9a-104">Product Name</span></span>|<span data-ttu-id="46c9a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="46c9a-105">SQL Server</span></span>|  
|<span data-ttu-id="46c9a-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="46c9a-106">Event ID</span></span>|<span data-ttu-id="46c9a-107">15661</span><span class="sxs-lookup"><span data-stu-id="46c9a-107">15661</span></span>|  
|<span data-ttu-id="46c9a-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="46c9a-108">Event Source</span></span>|<span data-ttu-id="46c9a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="46c9a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="46c9a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="46c9a-110">Component</span></span>|<span data-ttu-id="46c9a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="46c9a-111">SQLEngine</span></span>|  
|<span data-ttu-id="46c9a-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="46c9a-112">Symbolic Name</span></span>|<span data-ttu-id="46c9a-113">SQLErrorNum15661</span><span class="sxs-lookup"><span data-stu-id="46c9a-113">SQLErrorNum15661</span></span>|  
|<span data-ttu-id="46c9a-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="46c9a-114">Message Text</span></span>|<span data-ttu-id="46c9a-115">El procedimiento almacenado sp_estimate_data_compression_savings no se puede utilizar para las tablas temporales.</span><span class="sxs-lookup"><span data-stu-id="46c9a-115">The sp_estimate_data_compression_savings stored procedure cannot be used for temporary tables.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="46c9a-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="46c9a-116">Explanation</span></span>  
 <span data-ttu-id="46c9a-117">Se utilizó una tabla temporal como argumento para el procedimiento almacenado sp_estimate_data_compression_savings.</span><span class="sxs-lookup"><span data-stu-id="46c9a-117">A temporary table was used as an argument for the sp_estimate_data_compression_savings stored procedure.</span></span> <span data-ttu-id="46c9a-118">Aunque se admite la compresión de tablas temporales, no se puede utilizar sp_estimate_data_compression_savings para estimar los ahorros obtenidos con la compresión.</span><span class="sxs-lookup"><span data-stu-id="46c9a-118">Although the compression of temporary tables is supported, you cannot use sp_estimate_data_compression_savings to estimate the compression savings.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="46c9a-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="46c9a-119">User Action</span></span>  
 <span data-ttu-id="46c9a-120">Quite la tabla temporal como argumento para sp_estimate_data_compression_savings.</span><span class="sxs-lookup"><span data-stu-id="46c9a-120">Remove the temporary table as an argument for sp_estimate_data_compression_savings.</span></span>  
  
  
