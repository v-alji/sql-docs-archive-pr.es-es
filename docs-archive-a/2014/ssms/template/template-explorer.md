---
title: Explorador de plantillas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.wb.templates.f1
- sql12.swb.templates.explorer.f1
helpviewer_keywords:
- templates [SQL Server]
- SQL Server Management Studio [SQL Server], Template Explorer
- Template Explorer
- templates [Transact-SQL]
- templates [SQL Server], Template Explorer
ms.assetid: b9ee55c5-bb44-4f76-90ac-792d8d83b4c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35e7ee1e6261c759580df3a836f9cc4b500a77ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674504"
---
# <a name="template-explorer"></a><span data-ttu-id="1f0a3-102">Template Explorer</span><span class="sxs-lookup"><span data-stu-id="1f0a3-102">Template Explorer</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1f0a3-103">proporciona una variedad de plantillas.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-103">provides a variety of templates.</span></span> <span data-ttu-id="1f0a3-104">Las plantillas son archivos estereotipados que contienen scripts SQL que ayudan a crear objetos en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-104">Templates are boilerplate files containing SQL scripts that help you create objects in a database.</span></span> <span data-ttu-id="1f0a3-105">La primera vez que se abre el explorador de plantillas, se coloca una copia de las plantillas en la carpeta del usuario en C:\Users, en AppData\Roaming\Microsoft\SQL Server Management Studio\120\Templates.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-105">The first time the template explorer is opened, a copy of the templates are placed in the user's folder in C:\Users, under AppData\Roaming\Microsoft\SQL Server Management Studio\120\Templates.</span></span>  
  
 <span data-ttu-id="1f0a3-106">Puede examinar las plantillas disponibles en el explorador de plantillas; a continuación abra una plantilla para escribir el código en una ventana del editor de código.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-106">You can browse the available templates in Template Explorer, then open a template to incorporate the code into a code editor window.</span></span> <span data-ttu-id="1f0a3-107">También puede crear plantillas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-107">You can also create custom templates.</span></span>  
  
## <a name="benefits-of-templates"></a><span data-ttu-id="1f0a3-108">Ventajas de las plantillas</span><span class="sxs-lookup"><span data-stu-id="1f0a3-108">Benefits of Templates</span></span>  
 <span data-ttu-id="1f0a3-109">Las plantillas están disponibles para las soluciones, los proyectos y diversos tipos de editores de código.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-109">Templates are available for solutions, projects, and various types of code editors.</span></span> <span data-ttu-id="1f0a3-110">Las plantillas están disponibles para crear objetos como bases de datos, tablas, vistas, índices, procedimientos almacenados, desencadenadores, estadísticas y funciones.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-110">Templates are available to create objects like databases, tables, views, indexes, stored procedures, triggers, statistics, and functions.</span></span> <span data-ttu-id="1f0a3-111">Además, existen plantillas que ayudan a administrar el servidor al crear propiedades extendidas, servidores vinculados, inicios de sesión, roles, usuarios y plantillas para [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f0a3-111">In addition, there are templates that help you to manage your server by creating extended properties, linked servers, logins, roles, users, and templates for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1f0a3-112">Los scripts de las plantillas que se proporcionan con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] contienen parámetros para ayudarle a personalizar el código.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-112">The template scripts provided with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] contain parameters to help you customize the code.</span></span> <span data-ttu-id="1f0a3-113">Cuando abra una plantilla, use el cuadro de diálogo **Reemplazar parámetros de plantilla** para insertar valores en el script.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-113">When you open a template, Use the **Replace Template Parameters** dialog box to insert values into the script.</span></span>  
  
 <span data-ttu-id="1f0a3-114">Cree plantillas personalizadas para aquellas tareas que realice con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-114">Create custom templates for tasks you perform frequently.</span></span> <span data-ttu-id="1f0a3-115">Organice los scripts personalizados en las carpetas existentes o cree una nueva estructura de carpetas.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-115">Organize your custom scripts into the existing folders or create a new folder structure.</span></span>  
  
 <span data-ttu-id="1f0a3-116">El editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] también admite snippets de código que se pueden insertar en ubicaciones concretas de un script haciendo clic con el botón secundario en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-116">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query editor also supports code snippets, which can be inserted at specific locations in a script by right-clicking at that location.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="1f0a3-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="1f0a3-117">Related Tasks</span></span>  
 <span data-ttu-id="1f0a3-118">Use los temas siguientes para empezar a trabajar con las plantillas</span><span class="sxs-lookup"><span data-stu-id="1f0a3-118">Use the following topics to get started with templates</span></span>  
  
|<span data-ttu-id="1f0a3-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1f0a3-119">**Description**</span></span>|<span data-ttu-id="1f0a3-120">**Tema.**</span><span class="sxs-lookup"><span data-stu-id="1f0a3-120">**Topic**</span></span>|  
|---------------------|---------------|  
|<span data-ttu-id="1f0a3-121">Describe cómo incorporar el código de una plantilla en una ventana del editor de código.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-121">Describes how to incorporate the code from a template into a code editor window.</span></span>|[<span data-ttu-id="1f0a3-122">Abrir una plantilla</span><span class="sxs-lookup"><span data-stu-id="1f0a3-122">Open a Template</span></span>](open-a-template.md)|  
|<span data-ttu-id="1f0a3-123">Describe cómo reemplazar valores de parámetros de plantilla después de abrir una plantilla en un editor de código.</span><span class="sxs-lookup"><span data-stu-id="1f0a3-123">Describes how to replace template parameter values after opening a template in a code editor.</span></span>|[<span data-ttu-id="1f0a3-124">Reemplazar parámetros de plantilla</span><span class="sxs-lookup"><span data-stu-id="1f0a3-124">Replace Template Parameters</span></span>](replace-template-parameters.md)|  
  
  
