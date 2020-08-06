---
title: Opciones (diseñadores-página diseñadores de tablas y bases de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Designers.Table_Designer
ms.assetid: b43f4b97-17b9-4004-a824-f77b9e145741
author: stevestein
ms.author: sstein
ms.openlocfilehash: d8a1218b4ea1ae9c6f9cf734bb33a2a4bebcb167
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675097"
---
# <a name="options-designers-table-and-database-designers-page"></a><span data-ttu-id="8e5b2-102">Opciones (diseñadores-página diseñadores de tablas y bases de datos)</span><span class="sxs-lookup"><span data-stu-id="8e5b2-102">Options (Designers-Table and Database Designers Page)</span></span>
  <span data-ttu-id="8e5b2-103">Utilice esta página para determinar el comportamiento predeterminado del diseñador.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-103">Use this page to determine the default behavior of the designer.</span></span> <span data-ttu-id="8e5b2-104">Para tener acceso a esta configuración, en el menú **Herramientas** , haga clic en **Opciones**, expanda la carpeta **Diseñadores** y haga clic en **Diseñador de tablas**.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-104">To access the settings, on the **Tools** menu, click **Options**, expand the **Designers** folder, and click **Table Designer**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="8e5b2-105">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="8e5b2-105">UI element list</span></span>  
 <span data-ttu-id="8e5b2-106">**Sobrescribir el valor de tiempo de espera de la cadena de conexión para actualizaciones del diseñador de tabla**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-106">**Override connection string time-out value for table designer updates**</span></span>  
 <span data-ttu-id="8e5b2-107">Permite establecer un nuevo valor de tiempo de espera para las acciones del diseñador de tablas.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-107">Permits a new time-out value to be set for the actions of the table designer.</span></span> <span data-ttu-id="8e5b2-108">Esto puede resultar útil si el diseñador de tablas afecta a una tabla grande y requiere más tiempo para completar la modificación.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-108">This can be useful when the table designer affects a large table and requires extra time to complete the table modification.</span></span>  
  
 <span data-ttu-id="8e5b2-109">**Tiempo de espera de transacción después de**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-109">**Transaction time-out after**</span></span>  
 <span data-ttu-id="8e5b2-110">Establece un valor de tiempo de espera para el diseñador de tablas.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-110">Sets a time-out value for the table designer.</span></span>  
  
 <span data-ttu-id="8e5b2-111">**Generar automáticamente Scripts de cambio**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-111">**Auto generate change scripts**</span></span>  
 <span data-ttu-id="8e5b2-112">Crea automáticamente un script para implementar los cambios definidos en el diseñador de tablas.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-112">Automatically creates a script to implement the changes defined in the table designer.</span></span>  
  
 <span data-ttu-id="8e5b2-113">**Advertir si existen claves principales nulas**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-113">**Warn on null primary keys**</span></span>  
 <span data-ttu-id="8e5b2-114">Presenta un cuadro de diálogo de advertencia cuando un campo seleccionado para una clave principal puede contener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-114">Provides a warning dialog box when a field that is selected for a primary key can contain null values.</span></span>  
  
 <span data-ttu-id="8e5b2-115">**Advertir sobre detección de diferencias**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-115">**Warn about difference detection**</span></span>  
 <span data-ttu-id="8e5b2-116">Si activa esta casilla, al guardar los cambios, un cuadro de mensaje mostrará cualquier conflicto que se haya producido entre sus cambios y los realizados por otro usuario.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-116">If you check this box, when you save the changes, a message box will list any conflicts between your changes and changes that were made by another user.</span></span>  
  
 <span data-ttu-id="8e5b2-117">**Advertir sobre las tablas afectadas**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-117">**Warn about tables affected**</span></span>  
 <span data-ttu-id="8e5b2-118">Presenta un cuando de diálogo de advertencia que muestra las tablas a las que va a afectar la acción y solicita confirmación.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-118">Provides a warning dialog box that lists the tables to be affected by the action and prompts for confirmation.</span></span>  
  
 <span data-ttu-id="8e5b2-119">**Impedir guardar cambios que requieran volver a crear tablas**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-119">**Prevent saving changes that require table re-creation**</span></span>  
 <span data-ttu-id="8e5b2-120">Evita que un usuario realice modificaciones que requieran volver a crear la tabla.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-120">Prevents a user from making changes that require re-creating the table.</span></span> <span data-ttu-id="8e5b2-121">Las acciones siguientes pueden requerir que se vuelva a crear una tabla:</span><span class="sxs-lookup"><span data-stu-id="8e5b2-121">The following actions might require a table to be re-created:</span></span>  
  
-   <span data-ttu-id="8e5b2-122">Agregar una nueva columna en la mitad de la tabla</span><span class="sxs-lookup"><span data-stu-id="8e5b2-122">Adding a new column to the middle of the table</span></span>  
  
-   <span data-ttu-id="8e5b2-123">Quitar una columna</span><span class="sxs-lookup"><span data-stu-id="8e5b2-123">Dropping a column</span></span>  
  
-   <span data-ttu-id="8e5b2-124">Cambiar la nulabilidad de columnas</span><span class="sxs-lookup"><span data-stu-id="8e5b2-124">Changing column nullability</span></span>  
  
-   <span data-ttu-id="8e5b2-125">Cambiar el orden de las columnas</span><span class="sxs-lookup"><span data-stu-id="8e5b2-125">Changing the order of the columns</span></span>  
  
-   <span data-ttu-id="8e5b2-126">Cambiar el tipo de datos de una columna</span><span class="sxs-lookup"><span data-stu-id="8e5b2-126">Changing the data type of a column</span></span>  
  
 <span data-ttu-id="8e5b2-127">**Vista de tabla predeterminada**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-127">**Default table view**</span></span>  
 <span data-ttu-id="8e5b2-128">Seleccione la forma en que desea ver las tablas en los diseñadores:</span><span class="sxs-lookup"><span data-stu-id="8e5b2-128">Select the way you want to see tables in the designers:</span></span>  
  
-   <span data-ttu-id="8e5b2-129">**Estándar**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-129">**Standard**</span></span>  
  
     <span data-ttu-id="8e5b2-130">Muestra el encabezado de tablas, todos los nombres de columna, tipos de datos y la configuración Permitir valores NULL.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-130">Shows the table header, all column names, data types, and the Allow Nulls setting.</span></span>  
  
-   <span data-ttu-id="8e5b2-131">**Nombres de columna**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-131">**Column Names**</span></span>  
  
     <span data-ttu-id="8e5b2-132">Muestra los nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-132">Shows the column names.</span></span>  
  
-   <span data-ttu-id="8e5b2-133">**Clave**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-133">**Key**</span></span>  
  
     <span data-ttu-id="8e5b2-134">Muestra el encabezado de tabla y las columnas de clave principal.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-134">Shows the table header and the primary key columns.</span></span>  
  
-   <span data-ttu-id="8e5b2-135">**Solo nombre**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-135">**Name Only**</span></span>  
  
     <span data-ttu-id="8e5b2-136">Solo muestra el encabezado de tabla con su nombre.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-136">Shows only the table header with it's name.</span></span>  
  
-   <span data-ttu-id="8e5b2-137">**Personalizada**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-137">**Custom**</span></span>  
  
     <span data-ttu-id="8e5b2-138">Permite elegir las columnas que se muestran.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-138">Allows you to choose which columns to view.</span></span>  
  
 <span data-ttu-id="8e5b2-139">**Iniciar cuadro de diálogo Agregar tabla en un nuevo diagrama**</span><span class="sxs-lookup"><span data-stu-id="8e5b2-139">**Launch add table dialog on new diagram**</span></span>  
 <span data-ttu-id="8e5b2-140">Abre automáticamente el cuadro de diálogo **Agregar tabla** cuando se abren los diseñadores.</span><span class="sxs-lookup"><span data-stu-id="8e5b2-140">Automatically opens the **Add Table** dialog box when the designers open.</span></span>  
  
  
