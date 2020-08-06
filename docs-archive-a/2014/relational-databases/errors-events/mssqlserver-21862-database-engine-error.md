---
title: MSSQLSERVER_21862 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21862 (Database Engine error)
ms.assetid: a1d393dd-453b-4d45-9aa5-7d371213e32b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b945350d9c7a862d4274f464afbd7fc5472f732c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745785"
---
# <a name="mssqlserver_21862"></a><span data-ttu-id="1fe34-102">MSSQLSERVER_21862</span><span class="sxs-lookup"><span data-stu-id="1fe34-102">MSSQLSERVER_21862</span></span>
    
## <a name="details"></a><span data-ttu-id="1fe34-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1fe34-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1fe34-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="1fe34-104">Product Name</span></span>|<span data-ttu-id="1fe34-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1fe34-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1fe34-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1fe34-106">Event ID</span></span>|<span data-ttu-id="1fe34-107">21862</span><span class="sxs-lookup"><span data-stu-id="1fe34-107">21862</span></span>|  
|<span data-ttu-id="1fe34-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="1fe34-108">Event Source</span></span>|<span data-ttu-id="1fe34-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1fe34-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1fe34-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1fe34-110">Component</span></span>|<span data-ttu-id="1fe34-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1fe34-111">SQLEngine</span></span>|  
|<span data-ttu-id="1fe34-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1fe34-112">Symbolic Name</span></span>|<span data-ttu-id="1fe34-113">SQLErrorNum21862</span><span class="sxs-lookup"><span data-stu-id="1fe34-113">SQLErrorNum21862</span></span>|  
|<span data-ttu-id="1fe34-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1fe34-114">Message Text</span></span>|<span data-ttu-id="1fe34-115">Las columnas FILESTREAM no se pueden publicar en una publicación con el método de sincronización 'database snapshot' o 'database snapshot character'.</span><span class="sxs-lookup"><span data-stu-id="1fe34-115">FILESTREAM columns cannot be published in a publication by using a synchronization method of either 'database snapshot' or 'database snapshot character'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1fe34-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="1fe34-116">Explanation</span></span>  
 <span data-ttu-id="1fe34-117">Dado que no se puede acceder a los datos FILESTREAM mediante una instantánea de base de datos, el Agente de instantáneas no podrá leer los datos FILESTREAM cuando se especifique el parámetro *database snapshot* o *database_snapshot_character* para el método de sincronización de la publicación.</span><span class="sxs-lookup"><span data-stu-id="1fe34-117">Because FILESTREAM data cannot be accessed through a database snapshot, the snapshot agent will be unable to read FILESTREAM data when either the *database snapshot* or *database_snapshot_character* parameter is specified for the synchronization method of the publication.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1fe34-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1fe34-118">User Action</span></span>  
 <span data-ttu-id="1fe34-119">Cambie el método de sincronización de la publicación para que no sea *database snapshot* ni *database_snapshot_character*, o simplemente excluya la columna FILESTREAM de la publicación.</span><span class="sxs-lookup"><span data-stu-id="1fe34-119">Change the publication synchronization method to something other than *database snapshot* or *database_snapshot_character*, or just exclude the FILESTREAM column from the publication.</span></span>  
  
  
