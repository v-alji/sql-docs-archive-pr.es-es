---
title: PreConnect:Starting, clase de eventos |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- PreConnect:Starting Event Class
ms.assetid: d43ed0ad-3dbd-42e0-9cef-8320b8d87497
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67b642d369c73cc144af31f835786613766045f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674804"
---
# <a name="preconnectstarting-event-class"></a><span data-ttu-id="60b22-102">PreConnect:Starting, clase de eventos</span><span class="sxs-lookup"><span data-stu-id="60b22-102">PreConnect:Starting Event Class</span></span>
  <span data-ttu-id="60b22-103">La clase de eventos PreConnect:Starting indica cuándo se inicia la ejecución un desencadenador de LOGON o la función clasificadora del regulador de recursos.</span><span class="sxs-lookup"><span data-stu-id="60b22-103">The PreConnect:Starting event class indicates when a LOGON trigger or the Resource Governor classifier function starts execution.</span></span>  
  
## <a name="preconnectstarting-event-class-data-columns"></a><span data-ttu-id="60b22-104">Columnas de datos de la clase de eventos PreConnect:Starting</span><span class="sxs-lookup"><span data-stu-id="60b22-104">PreConnect:Starting Event Class Data Columns</span></span>  
  
|<span data-ttu-id="60b22-105">Nombre de columna de datos</span><span class="sxs-lookup"><span data-stu-id="60b22-105">Data column name</span></span>|<span data-ttu-id="60b22-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="60b22-106">Data type</span></span>|<span data-ttu-id="60b22-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="60b22-107">Description</span></span>|<span data-ttu-id="60b22-108">Identificador de columna</span><span class="sxs-lookup"><span data-stu-id="60b22-108">Column ID</span></span>|<span data-ttu-id="60b22-109">Filtrable</span><span class="sxs-lookup"><span data-stu-id="60b22-109">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="60b22-110">EventClass</span><span class="sxs-lookup"><span data-stu-id="60b22-110">EventClass</span></span>|`int`|<span data-ttu-id="60b22-111">215</span><span class="sxs-lookup"><span data-stu-id="60b22-111">215</span></span>|<span data-ttu-id="60b22-112">27</span><span class="sxs-lookup"><span data-stu-id="60b22-112">27</span></span>|<span data-ttu-id="60b22-113">No</span><span class="sxs-lookup"><span data-stu-id="60b22-113">No</span></span>|  
|<span data-ttu-id="60b22-114">SPID</span><span class="sxs-lookup"><span data-stu-id="60b22-114">SPID</span></span>|`int`|<span data-ttu-id="60b22-115">El Id. del proceso de servidor que dispara este evento.</span><span class="sxs-lookup"><span data-stu-id="60b22-115">The ID of server process that fires this event.</span></span>|<span data-ttu-id="60b22-116">12</span><span class="sxs-lookup"><span data-stu-id="60b22-116">12</span></span>|<span data-ttu-id="60b22-117">Sí</span><span class="sxs-lookup"><span data-stu-id="60b22-117">Yes</span></span>|  
|<span data-ttu-id="60b22-118">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="60b22-118">EventSubClass</span></span>|`int`|<span data-ttu-id="60b22-119">1 para la función clasificadora definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="60b22-119">1 for the user-defined classifier function.</span></span>|<span data-ttu-id="60b22-120">21</span><span class="sxs-lookup"><span data-stu-id="60b22-120">21</span></span>|<span data-ttu-id="60b22-121">Sí</span><span class="sxs-lookup"><span data-stu-id="60b22-121">Yes</span></span>|  
|<span data-ttu-id="60b22-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="60b22-122">StartTime</span></span>|`datetime`|<span data-ttu-id="60b22-123">La hora en la que se inicia la función clasificadora definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="60b22-123">The time when the user-defined classifier function starts.</span></span>|<span data-ttu-id="60b22-124">14</span><span class="sxs-lookup"><span data-stu-id="60b22-124">14</span></span>|<span data-ttu-id="60b22-125">Sí</span><span class="sxs-lookup"><span data-stu-id="60b22-125">Yes</span></span>|  
|<span data-ttu-id="60b22-126">ObjectID</span><span class="sxs-lookup"><span data-stu-id="60b22-126">ObjectID</span></span>|`int`|<span data-ttu-id="60b22-127">El Id. del objeto clasificador definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="60b22-127">The ID of the user-defined classifier object.</span></span>|<span data-ttu-id="60b22-128">22</span><span class="sxs-lookup"><span data-stu-id="60b22-128">22</span></span>|<span data-ttu-id="60b22-129">Sí</span><span class="sxs-lookup"><span data-stu-id="60b22-129">Yes</span></span>|  
|<span data-ttu-id="60b22-130">ObjectName</span><span class="sxs-lookup"><span data-stu-id="60b22-130">ObjectName</span></span>|`nvarchar(256)`|<span data-ttu-id="60b22-131">El nombre de dos partes de la función del clasificador definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="60b22-131">The two-part name of the classifier user-defined function.</span></span> <span data-ttu-id="60b22-132">Por ejemplo, dbo.classifier.</span><span class="sxs-lookup"><span data-stu-id="60b22-132">For example, dbo.classifier.</span></span>|<span data-ttu-id="60b22-133">34</span><span class="sxs-lookup"><span data-stu-id="60b22-133">34</span></span>|<span data-ttu-id="60b22-134">Sí</span><span class="sxs-lookup"><span data-stu-id="60b22-134">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60b22-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="60b22-135">See Also</span></span>  
 <span data-ttu-id="60b22-136">[Eventos extendidos](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="60b22-136">[Extended Events](../extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="60b22-137">[Preconnect: Completed (clase de eventos)](preconnect-completed-event-class.md) </span><span class="sxs-lookup"><span data-stu-id="60b22-137">[PreConnect:Completed Event Class](preconnect-completed-event-class.md) </span></span>  
 [<span data-ttu-id="60b22-138">Regulador de recursos</span><span class="sxs-lookup"><span data-stu-id="60b22-138">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  
