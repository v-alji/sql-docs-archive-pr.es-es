---
title: MSSQLSERVER_1793 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 808db1d0-acc1-41d0-9287-8a5455001a02
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 54172adb957c3cbc1dbc221d1cae2a583830a1cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745792"
---
# <a name="mssqlserver_1793"></a><span data-ttu-id="7eded-102">MSSQLSERVER_1793</span><span class="sxs-lookup"><span data-stu-id="7eded-102">MSSQLSERVER_1793</span></span>
    
## <a name="details"></a><span data-ttu-id="7eded-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7eded-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7eded-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="7eded-104">Product Name</span></span>|<span data-ttu-id="7eded-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7eded-105">SQL Server</span></span>|  
|<span data-ttu-id="7eded-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="7eded-106">Event ID</span></span>|<span data-ttu-id="7eded-107">1793</span><span class="sxs-lookup"><span data-stu-id="7eded-107">1793</span></span>|  
|<span data-ttu-id="7eded-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="7eded-108">Event Source</span></span>|<span data-ttu-id="7eded-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7eded-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7eded-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7eded-110">Component</span></span>|<span data-ttu-id="7eded-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7eded-111">SQLEngine</span></span>|  
|<span data-ttu-id="7eded-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7eded-112">Symbolic Name</span></span>|<span data-ttu-id="7eded-113">FILESTREAM_BASEDATA_NEED_SAME_PARTITION</span><span class="sxs-lookup"><span data-stu-id="7eded-113">FILESTREAM_BASEDATA_NEED_SAME_PARTITION</span></span>|  
|<span data-ttu-id="7eded-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7eded-114">Message Text</span></span>|<span data-ttu-id="7eded-115">No se puede quitar el índice '%.\*ls' porque no se ha especificado un esquema de partición para datos de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7eded-115">Cannot drop index '%.\*ls' since a partition scheme is not specified for FILESTREAM data.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7eded-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="7eded-116">Explanation</span></span>  
 <span data-ttu-id="7eded-117">Este mensaje aparece cuando intenta quitar un índice agrupado en una tabla que contiene datos FILESTREAM y especifica una cláusula **MOVE TO** para los datos básicos pero no especifica una cláusula **FILESTREAM_ON** para los datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7eded-117">This message occurs when you try to drop a clustered index on a table that contains FILESTREAM data, and you specify a **MOVE TO** clause for the base data, but you do not specify a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7eded-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7eded-118">User Action</span></span>  
 <span data-ttu-id="7eded-119">Al quitar un índice clúster en una tabla que contiene datos FILESTREAM, use una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="7eded-119">When dropping a clustered index on a table that contains FILESTREAM data, use one of the following options:</span></span>  
  
-   <span data-ttu-id="7eded-120">Especifique tanto una cláusula **MOVE TO** para los datos base como una cláusula **FILESTREAM_ON** para los datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7eded-120">Specify both a **MOVE TO** clause for the base data and a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
-   <span data-ttu-id="7eded-121">No especifique una cláusula **MOVE TO** para los datos base ni una cláusula **FILESTREAM_ON** para los datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7eded-121">Do not specify either a **MOVE TO** clause for the base data or a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
 <span data-ttu-id="7eded-122">En el siguiente ejemplo se produce un error porque un esquema de partición se especifica en los datos básicos, pero no se especifica en los datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7eded-122">The following example fails because a partition scheme is specified for the base data, but is not specified for the FILESTREAM data.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF, MOVE TO [PRIMARY] )  
GO  
```  
  
 <span data-ttu-id="7eded-123">El siguiente ejemplo funciona correctamente debido a que se especifican tanto una cláusula **MOVE TO** para los datos base como una cláusula **FILESTREAM_ON** para los datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7eded-123">The following example succeeds because both a **MOVE TO** clause for the base data and a **FILESTREAM_ON** clause for the FILESTREAM data are specified.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF, MOVE TO [PRIMARY], filestream_on 'default' )  
GO  
```  
  
 <span data-ttu-id="7eded-124">El siguiente ejemplo también funciona correctamente debido a que no se especifican ni una cláusula **MOVE TO** para los datos base ni una cláusula **FILESTREAM_ON** para los datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7eded-124">The following example also succeeds because neither a **MOVE TO** clause for the base data nor a **FILESTREAM_ON** clause for the FILESTREAM data is specified.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF )  
GO  
```  
  
  
