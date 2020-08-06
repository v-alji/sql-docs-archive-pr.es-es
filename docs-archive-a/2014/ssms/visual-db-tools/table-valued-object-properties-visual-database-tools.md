---
title: Propiedades de objeto con valores de tabla (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.designers.properties.TVO
ms.assetid: eaf06cbf-8242-4483-894f-80ae02a4840e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6f1c1e6414d0059dfd1d43bbbb40eabdfc9470b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747841"
---
# <a name="table-valued-object-properties-visual-database-tools"></a><span data-ttu-id="bf3c1-102">Propiedades de objeto con valores de tabla (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="bf3c1-102">Table-Valued Object Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="bf3c1-103">Estas propiedades aparecen en la ventana Propiedades cuando selecciona un objeto con valores de tabla en el **Diseñador de vistas y de consultas**.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-103">These properties appear in the Properties window when you select a table-valued object in **Query and View Designer**.</span></span> <span data-ttu-id="bf3c1-104">El objeto con valores de tabla puede ser una vista, un sinónimo, una tabla derivada o una función con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-104">The table-valued object could be a view, synonym, derived table, or table-valued function.</span></span> <span data-ttu-id="bf3c1-105">A menos que se indique lo contrario, estas propiedades son de solo lectura en la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="bf3c1-105">Unless otherwise noted, these properties are read-only in the **Properties** window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf3c1-106">Las propiedades de este tema se ordenan por categoría en lugar de alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-106">The properties in this topic are ordered by category rather than alphabet.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bf3c1-107">Los cuadros de diálogo y comandos de menú que ve podrían diferir de aquellos que se describen en la Ayuda en función de la edición o configuración activa.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bf3c1-108">Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="bf3c1-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="bf3c1-109">**Categoría Identidad**</span><span class="sxs-lookup"><span data-stu-id="bf3c1-109">**Identity Category**</span></span>  
 <span data-ttu-id="bf3c1-110">Se expande para mostrar las propiedades de **Nombre** y **Tipo TVO** .</span><span class="sxs-lookup"><span data-stu-id="bf3c1-110">Expands to show the **Name** and **TVO Type** properties.</span></span>  
  
 <span data-ttu-id="bf3c1-111">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="bf3c1-111">**Name**</span></span>  
 <span data-ttu-id="bf3c1-112">Muestra el nombre del objeto de la tabla con valores seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-112">Shows the name of the selected table-valued object.</span></span>  
  
 <span data-ttu-id="bf3c1-113">**Tipo TVO**</span><span class="sxs-lookup"><span data-stu-id="bf3c1-113">**TVO Type**</span></span>  
 <span data-ttu-id="bf3c1-114">Muestra el tipo del objeto con valores de la tabla.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-114">Shows which type of table-valued object.</span></span> <span data-ttu-id="bf3c1-115">Puede ser una tabla base, una vista, una función con valores de tabla o una tabla derivada.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-115">It can be either a base table, view, table-valued function, or a derived table.</span></span>  
  
 <span data-ttu-id="bf3c1-116">**Categoría del Diseñador de consultas**</span><span class="sxs-lookup"><span data-stu-id="bf3c1-116">**Query DesignerCategory**</span></span>  
 <span data-ttu-id="bf3c1-117">Se expande para mostrar las propiedades de **Alias**, **Lista de columnas**, **Nombre completo**y **Lista de parámetros**.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-117">Expands to show properties for **Alias**, **Column List**, **Full Name**, and **Parameter List**.</span></span>  
  
 <span data-ttu-id="bf3c1-118">**Alias**</span><span class="sxs-lookup"><span data-stu-id="bf3c1-118">**Alias**</span></span>  
 <span data-ttu-id="bf3c1-119">Muestra el alias del objeto de la tabla con valores seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-119">Shows the alias for the selected table-valued object.</span></span> <span data-ttu-id="bf3c1-120">Para agregar o cambiar un alias, escríbalo en el campo.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-120">To add or change an alias, type it into the field.</span></span>  
  
 <span data-ttu-id="bf3c1-121">**Lista de columnas**</span><span class="sxs-lookup"><span data-stu-id="bf3c1-121">**Column List**</span></span>  
 <span data-ttu-id="bf3c1-122">Muestra las columnas incluidas en el objeto de la tabla con valores seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-122">Shows the columns included in the selected table-valued object.</span></span> <span data-ttu-id="bf3c1-123">Para verlas en una ventana independiente, haga clic en la Lista de columnas y después en los puntos suspensivos (...) situados a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-123">To see them in a separate window, click Column List and then click the ellipses (...) to the right of the property.</span></span>  
  
 <span data-ttu-id="bf3c1-124">**Nombre completo**</span><span class="sxs-lookup"><span data-stu-id="bf3c1-124">**Full Name**</span></span>  
 <span data-ttu-id="bf3c1-125">Muestra el nombre del objeto con valores de tabla seleccionado, incluyendo información adicional como el esquema o el origen de datos del objeto.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-125">Shows the name of the selected table-valued object, including additional information such as the schema or data source of the object.</span></span>  
  
 <span data-ttu-id="bf3c1-126">**Lista de parámetros**</span><span class="sxs-lookup"><span data-stu-id="bf3c1-126">**Parameter List**</span></span>  
 <span data-ttu-id="bf3c1-127">Muestra los parámetros definidos para la función con valores de tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-127">Shows the parameters defined for selected table-valued function.</span></span> <span data-ttu-id="bf3c1-128">Para definir un valor para los parámetros, haga clic en la Lista de parámetros y después en los puntos suspensivos (...) situados a la derecha de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-128">To define a value for the parameters, click Parameter List and then click the ellipses (...) to the right of the property.</span></span> <span data-ttu-id="bf3c1-129">En el cuadro de diálogo Parámetros de la función, escriba los valores.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-129">In the Function Parameters dialog box, type in values.</span></span> <span data-ttu-id="bf3c1-130">Esta propiedad solo está disponible cuando se selecciona una función con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="bf3c1-130">This property is only available when a table-valued function is selected.</span></span>  
  
  
