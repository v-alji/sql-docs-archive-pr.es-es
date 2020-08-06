---
title: Generar script SQL (objetos de replicación) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.generatesqlscript.f1
helpviewer_keywords:
- Generate SQL Script dialog box
ms.assetid: b7ccc34e-1c22-44b8-8eb5-f6423af3164e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 31a4b318eb3a4c0e5d9f79f43efdcf97c42957f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663353"
---
# <a name="generate-sql-script-replication-objects"></a><span data-ttu-id="0e84b-102">Generar script SQL (Objetos de replicación)</span><span class="sxs-lookup"><span data-stu-id="0e84b-102">Generate SQL Script (Replication Objects)</span></span>
  <span data-ttu-id="0e84b-103">Un script de replicación contiene los procedimientos almacenados del sistema [!INCLUDE[tsql](../../includes/tsql-md.md)] necesarios para implementar los componentes de replicación convertidos en scripts, como una publicación o una suscripción.</span><span class="sxs-lookup"><span data-stu-id="0e84b-103">A replication script contains the [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures necessary to implement the replication components scripted, such as a publication or subscription.</span></span> <span data-ttu-id="0e84b-104">Todos los componentes de replicación de una topología deben convertirse en script como parte de un plan de recuperación de desastres y, además, los scripts también pueden utilizarse para automatizar tareas repetitivas.</span><span class="sxs-lookup"><span data-stu-id="0e84b-104">All replication components in a topology should be scripted as part of a disaster recovery plan, and scripts can also be used to automate repetitive tasks.</span></span> <span data-ttu-id="0e84b-105">La replicación ofrece dos cuadros de diálogo para crear script para los objetos de replicación:</span><span class="sxs-lookup"><span data-stu-id="0e84b-105">Replication offers two dialog boxes for scripting replication objects:</span></span>  
  
-   <span data-ttu-id="0e84b-106">**Generar script SQL**, que está disponible en el menú contextual de la carpeta **Replicación** y en todas las subcarpetas de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e84b-106">**Generate SQL Script**, which is available from the context menu of the **Replication** folder and all subfolders in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="0e84b-107">Este cuadro de diálogo permite generar script de todos los objetos de replicación en una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e84b-107">This dialog box allows you to script all replication objects on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="0e84b-108">**Generar script SQL \<ObjectName>** , que está disponible en el menú contextual de publicaciones y suscripciones.</span><span class="sxs-lookup"><span data-stu-id="0e84b-108">**Generate SQL Script \<ObjectName>**, which is available from the context menu for publications and subscriptions.</span></span> <span data-ttu-id="0e84b-109">Este cuadro de diálogo le permitirá convertir en script objetos individuales.</span><span class="sxs-lookup"><span data-stu-id="0e84b-109">This dialog box allows you to script individual objects.</span></span>  
  
 <span data-ttu-id="0e84b-110">Los cuadros de diálogo convierten en script objetos en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; no se conectan a otras instancias para convertir en script los objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="0e84b-110">These dialog boxes script objects on a single instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; they do not connect to other instances to script related objects.</span></span>  
  
## <a name="generate-sql-script-options"></a><span data-ttu-id="0e84b-111">Opciones de Generar script SQL</span><span class="sxs-lookup"><span data-stu-id="0e84b-111">Generate SQL Script Options</span></span>  
 <span data-ttu-id="0e84b-112">**Propiedades del distribuidor**</span><span class="sxs-lookup"><span data-stu-id="0e84b-112">**Distributor properties**</span></span>  
 <span data-ttu-id="0e84b-113">Seleccione esta opción para convertir en script los procedimientos almacenados en: habilitar o deshabilitar el distribuidor, agregar o quitar publicadores asociados al distribuidor y crear o quitar la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="0e84b-113">Select to script stored procedures to: enable or disable the Distributor; add or drop Publishers associated with the Distributor; and create or drop the distribution database.</span></span>  
  
 <span data-ttu-id="0e84b-114">**Publicaciones en los siguientes orígenes de datos**</span><span class="sxs-lookup"><span data-stu-id="0e84b-114">**Publications in the following data sources**</span></span>  
 <span data-ttu-id="0e84b-115">Seleccione esta opción para convertir en script los procedimientos almacenados en: habilitar o deshabilitar para publicar y crear o quitar publicaciones, artículos, suscripciones de inserción y trabajos de replicación.</span><span class="sxs-lookup"><span data-stu-id="0e84b-115">Select to script stored procedures to: enable or disable publishing; and create or drop publications, articles, push subscriptions, and replication jobs.</span></span>  
  
 <span data-ttu-id="0e84b-116">**Suscripciones en los siguientes orígenes de datos**</span><span class="sxs-lookup"><span data-stu-id="0e84b-116">**Subscriptions in the following data sources**</span></span>  
 <span data-ttu-id="0e84b-117">Seleccione esta opción para convertir en script los procedimientos almacenados para crear o quitar suscripciones de extracción y trabajos de replicación.</span><span class="sxs-lookup"><span data-stu-id="0e84b-117">Select to script stored procedures to create or drop pull subscriptions and replication jobs.</span></span>  
  
 <span data-ttu-id="0e84b-118">**Para crear o habilitar componentes** y **Para quitar o deshabilitar componentes**</span><span class="sxs-lookup"><span data-stu-id="0e84b-118">**To create or enable the components** and **To drop or disable the components**</span></span>  
 <span data-ttu-id="0e84b-119">Especifique si desea que el script incluya comandos para crear o quitar un objeto de replicación.</span><span class="sxs-lookup"><span data-stu-id="0e84b-119">Specify whether the script should include commands for creating or dropping a replication object.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="0e84b-120">le recomienda utilizar el cuadro de diálogo para crear un conjunto de scripts para habilitar y deshabilitar componentes.</span><span class="sxs-lookup"><span data-stu-id="0e84b-120">recommends that you use the dialog box to create a set of scripts for enabling and disabling components.</span></span>  
  
 <span data-ttu-id="0e84b-121">**Trabajos de replicación**</span><span class="sxs-lookup"><span data-stu-id="0e84b-121">**Replication jobs**</span></span>  
 <span data-ttu-id="0e84b-122">Seleccione esta opción para convertir en script trabajos de replicación y llamadas a procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="0e84b-122">Select to script replication jobs in addition to stored procedure calls.</span></span> <span data-ttu-id="0e84b-123">Esta opción solo está disponible si genera script desde un distribuidor.</span><span class="sxs-lookup"><span data-stu-id="0e84b-123">This option is available only when scripting from a Distributor.</span></span>  
  
 <span data-ttu-id="0e84b-124">Los procedimientos almacenados de replicación crean los trabajos necesarios mientras se ejecutan, por lo que no es necesario que seleccione esta opción.</span><span class="sxs-lookup"><span data-stu-id="0e84b-124">Replication stored procedures create the necessary jobs when they are executed, so it is not required to select this option.</span></span> <span data-ttu-id="0e84b-125">Sin embargo, puede resultar útil guardar un registro de los trabajos creados por si fuese necesario volver a crear un trabajo individual.</span><span class="sxs-lookup"><span data-stu-id="0e84b-125">However, it can be useful to have a record of the jobs created in case an individual job must be recreated.</span></span>  
  
## <a name="generate-sql-script-objectname-options"></a><span data-ttu-id="0e84b-126">Opciones de Generar script SQL \<ObjectName></span><span class="sxs-lookup"><span data-stu-id="0e84b-126">Generate SQL Script \<ObjectName> Options</span></span>  
 <span data-ttu-id="0e84b-127">**Para crear o habilitar componentes** y **Para quitar o deshabilitar componentes**</span><span class="sxs-lookup"><span data-stu-id="0e84b-127">**To create or enable the components** and **To drop or disable the components**</span></span>  
 <span data-ttu-id="0e84b-128">Especifique si desea que el script incluya comandos para crear o quitar un objeto de replicación.</span><span class="sxs-lookup"><span data-stu-id="0e84b-128">Specify whether the script should include commands for creating or dropping a replication object.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="0e84b-129">le recomienda utilizar el cuadro de diálogo para crear un conjunto de scripts para habilitar y deshabilitar componentes.</span><span class="sxs-lookup"><span data-stu-id="0e84b-129">recommends that you use the dialog box, creating a set of scripts for enabling and disabling components.</span></span>  
  
 <span data-ttu-id="0e84b-130">**Trabajos de replicación**</span><span class="sxs-lookup"><span data-stu-id="0e84b-130">**Replication jobs**</span></span>  
 <span data-ttu-id="0e84b-131">Está opción solo está disponible en el cuadro de diálogo **Generar script SQL** .</span><span class="sxs-lookup"><span data-stu-id="0e84b-131">This option is available only from the **Generate SQL Script** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e84b-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e84b-132">See Also</span></span>  
 [<span data-ttu-id="0e84b-133">Crear script para la replicación</span><span class="sxs-lookup"><span data-stu-id="0e84b-133">Scripting Replication</span></span>](scripting-replication.md)  
  
  
