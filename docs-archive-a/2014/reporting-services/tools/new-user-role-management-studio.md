---
title: Nuevo rol de usuario (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newrole.f1
ms.assetid: 9f76a235-0b58-479c-8e5b-50588091b71c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 78201c5ebedd0cdb7f8108b9e6effcaa7fbe87b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746125"
---
# <a name="new-user-role-management-studio"></a><span data-ttu-id="bc262-102">Nuevo rol de usuario (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="bc262-102">New User Role (Management Studio)</span></span>
  <span data-ttu-id="bc262-103">Utilice esta página para crear una definición de roles de nivel de elemento.</span><span class="sxs-lookup"><span data-stu-id="bc262-103">Use this page to create an item-level role definition.</span></span> <span data-ttu-id="bc262-104">Una definición de roles de nivel de elemento es una colección con nombre de las tareas que puede realizar un usuario con las carpetas, los informes, los modelos, los recursos y los orígenes de datos compartidos.</span><span class="sxs-lookup"><span data-stu-id="bc262-104">An item-level role definition is a named collection of tasks that enumerate the tasks a user can perform in relation to folders, reports, models, resources, and shared data sources.</span></span> <span data-ttu-id="bc262-105">Un ejemplo de definición de roles de nivel de elemento sería el rol predefinido Explorador, que identifica los tipos de acciones que podría necesitar el usuario final de un informe para navegar por carpetas y ver informes.</span><span class="sxs-lookup"><span data-stu-id="bc262-105">An example of an item-level role definition is the predefined Browser role that identifies the kinds of actions a report end user might require for navigating folders and viewing reports.</span></span>  
  
 <span data-ttu-id="bc262-106">Se pretende que el número de definiciones de roles sea reducido.</span><span class="sxs-lookup"><span data-stu-id="bc262-106">Role definitions are intended to be few in number.</span></span> <span data-ttu-id="bc262-107">La mayoría de las organizaciones solo requieren algunas.</span><span class="sxs-lookup"><span data-stu-id="bc262-107">Most organizations only require a few role definitions.</span></span> <span data-ttu-id="bc262-108">Sin embargo, si las definiciones de roles predefinidos no son suficientes, se pueden modificar o se pueden crear otras nuevas.</span><span class="sxs-lookup"><span data-stu-id="bc262-108">However, if the predefined role definitions are insufficient, you can vary them or create new ones.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc262-109">Las definiciones de roles solo se utilizan en un servidor de informes que se ejecute en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="bc262-109">Role definitions are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="bc262-110">Si el servidor de informes está configurado para la integración con SharePoint, esta página no está disponible.</span><span class="sxs-lookup"><span data-stu-id="bc262-110">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bc262-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="bc262-111">Options</span></span>  
 <span data-ttu-id="bc262-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="bc262-112">**Name**</span></span>  
 <span data-ttu-id="bc262-113">Escriba el nombre de la definición de roles.</span><span class="sxs-lookup"><span data-stu-id="bc262-113">Type the name of the role definition.</span></span> <span data-ttu-id="bc262-114">Un nombre de definición de roles debe ser único en el espacio de nombres del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="bc262-114">A role definition name must be unique within the report server namespace.</span></span> <span data-ttu-id="bc262-115">El nombre debe incluir al menos un carácter alfanumérico.</span><span class="sxs-lookup"><span data-stu-id="bc262-115">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="bc262-116">También puede incluir espacios y algunos símbolos.</span><span class="sxs-lookup"><span data-stu-id="bc262-116">It can also include spaces and some symbols.</span></span> <span data-ttu-id="bc262-117">No utilice los caracteres siguientes al especificar un nombre:</span><span class="sxs-lookup"><span data-stu-id="bc262-117">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="bc262-118">; ?</span><span class="sxs-lookup"><span data-stu-id="bc262-118">; ?</span></span> <span data-ttu-id="bc262-119">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="bc262-119">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="bc262-120">" /</span><span class="sxs-lookup"><span data-stu-id="bc262-120">" /</span></span>  
  
 <span data-ttu-id="bc262-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bc262-121">**Description**</span></span>  
 <span data-ttu-id="bc262-122">Escriba una descripción que explique cómo usar el rol y que especifique el rol que admite.</span><span class="sxs-lookup"><span data-stu-id="bc262-122">Type a description that explains how to use the role and enumerates what the role supports.</span></span>  
  
 <span data-ttu-id="bc262-123">**Task**</span><span class="sxs-lookup"><span data-stu-id="bc262-123">**Task**</span></span>  
 <span data-ttu-id="bc262-124">Seleccione las tareas que se pueden realizar mediante este rol.</span><span class="sxs-lookup"><span data-stu-id="bc262-124">Select the tasks that can be performed through this role.</span></span> <span data-ttu-id="bc262-125">No puede crear nuevas tareas ni modificar las tareas existentes que admite [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc262-125">You cannot create new tasks or modify the existing tasks that are supported by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="bc262-126">Solo las tareas de nivel de elemento pueden utilizarse en una definición de roles de nivel de elemento.</span><span class="sxs-lookup"><span data-stu-id="bc262-126">Only item-level tasks can be used in an item-level role definition.</span></span>  
  
 <span data-ttu-id="bc262-127">**Descripción de la tarea**</span><span class="sxs-lookup"><span data-stu-id="bc262-127">**Task Description**</span></span>  
 <span data-ttu-id="bc262-128">Muestra una descripción de la tarea con las operaciones o los permisos que ésta admite.</span><span class="sxs-lookup"><span data-stu-id="bc262-128">Shows a description of the task that enumerates the operations or permissions that the task supports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc262-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc262-129">See Also</span></span>  
 <span data-ttu-id="bc262-130">[Servidor de informes en Management Studio ayuda F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="bc262-130">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="bc262-131">Definiciones de roles</span><span class="sxs-lookup"><span data-stu-id="bc262-131">Role Definitions</span></span>](../security/role-definitions.md)  
  
  
