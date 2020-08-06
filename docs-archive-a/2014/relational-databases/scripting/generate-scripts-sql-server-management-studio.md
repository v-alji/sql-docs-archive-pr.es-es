---
title: Generar scripts
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 9711c617-3c68-4e5a-aea3-befc64d51524
author: rothja
ms.author: jroth
ms.openlocfilehash: 199d5e0c98d220861ee0dfb48a44a71675d8ba87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677013"
---
# <a name="generate-scripts-sql-server-management-studio"></a><span data-ttu-id="5e467-102">Generar scripts (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5e467-102">Generate Scripts (SQL Server Management Studio)</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="5e467-103">proporciona dos mecanismos para generar scripts de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5e467-103">provides two mechanisms for generating [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="5e467-104">Puede crear scripts para varios objetos mediante el **Asistente generar y publicar scripts.**</span><span class="sxs-lookup"><span data-stu-id="5e467-104">You can create scripts for multiple objects by using the **Generate and Publish Scripts Wizard.**.</span></span> <span data-ttu-id="5e467-105">También puede generar un script para objetos individuales o varios objetos con el menú **Incluir como** del **Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="5e467-105">You can also generate a script for individual objects or multiple objects by using the **Script as** menu in **Object Explorer**.</span></span>  
  
1.  <span data-ttu-id="5e467-106">**Elegir un método:**  [Asistente generar y publicar scripts](#GenPubScriptWiz), [Menú Incluir como del Explorador de objetos](#OEScriptAsMenu)</span><span class="sxs-lookup"><span data-stu-id="5e467-106">**Choose a method:**  [Generate and Publish Scripts Wizard](#GenPubScriptWiz), [Object Explorer Script As Menu](#OEScriptAsMenu)</span></span>  
  
2.  <span data-ttu-id="5e467-107">**Para usar el script como menú:**  [Generar un script de un solo objeto](#ScriptSingleObject), [Generar un script de dos objetos mediante el Explorador de objetos](#ScriptTwoObjectsOE), [Generar un script de dos objetos usando los detalles del Explorador de objetos](#ScriptTwoObjectsOED)</span><span class="sxs-lookup"><span data-stu-id="5e467-107">**To use the Script As menu:**  [Script a Single Object](#ScriptSingleObject), [Script Two Objects Using Object Explorer](#ScriptTwoObjectsOE), [Script Two Objects Using Object Explorer Details](#ScriptTwoObjectsOED)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="5e467-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="5e467-108">Before You Begin</span></span>  
 <span data-ttu-id="5e467-109">Elija el mecanismo que mejor cumpla sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="5e467-109">Choose the mechanism that best meets your requirements.</span></span>  
  
###  <a name="generate-and-publish-scripts-wizard"></a><a name="GenPubScriptWiz"></a> <span data-ttu-id="5e467-110">Asistente generar y publicar scripts</span><span class="sxs-lookup"><span data-stu-id="5e467-110">Generate and Publish Scripts Wizard</span></span>  
 <span data-ttu-id="5e467-111">Use el **Asistente Generar y publicar scripts** para crear un script [!INCLUDE[tsql](../../includes/tsql-md.md)] para muchos objetos.</span><span class="sxs-lookup"><span data-stu-id="5e467-111">Use the **Generate and Publish Scripts Wizard** to create a [!INCLUDE[tsql](../../includes/tsql-md.md)] script for many objects.</span></span> <span data-ttu-id="5e467-112">El asistente genera un script de todos los objetos de una base de datos o un subconjunto de los objetos que seleccione.</span><span class="sxs-lookup"><span data-stu-id="5e467-112">The wizard generates a script of all the objects in a database, or a subset of the objects that you select.</span></span> <span data-ttu-id="5e467-113">El asistente dispone de muchas opciones para los scripts, como la posibilidad de incluir permisos, la intercalación, las restricciones, etc.</span><span class="sxs-lookup"><span data-stu-id="5e467-113">The wizard has many options for your scripts, such as whether to include permissions, collation, constraints, and so on.</span></span> <span data-ttu-id="5e467-114">Para obtener instrucciones acerca de cómo usar el asistente, vea [Generate and Publish Scripts Wizard](generate-and-publish-scripts-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="5e467-114">For instructions on using the wizard, see [Generate and Publish Scripts Wizard](generate-and-publish-scripts-wizard.md).</span></span>  
  
###  <a name="object-explorer-script-as-menu"></a><a name="OEScriptAsMenu"></a> <span data-ttu-id="5e467-115">Menú Incluir como del Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="5e467-115">Object Explorer Script As Menu</span></span>  
 <span data-ttu-id="5e467-116">Puede usar el menú **Incluir como del Explorador de objetos** para generar un script de un solo objeto, de varios objetos o de varias instrucciones para un único objeto.</span><span class="sxs-lookup"><span data-stu-id="5e467-116">You can use the **Object Explorer Script as** menu to script a single object, script multiple objects, or script multible statements for a single objects.</span></span> <span data-ttu-id="5e467-117">Puede elegir uno de varios tipos de scripts; por ejemplo crear, modificar o quitar el objeto.</span><span class="sxs-lookup"><span data-stu-id="5e467-117">You can choose one of several types of scripts; for example to create, alter, or drop the object.</span></span> <span data-ttu-id="5e467-118">Puede guardar un script en una ventana del Editor de consultas, en un archivo o en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="5e467-118">You can save the script in a Query Editor window, to a file, or to the Clipboard.</span></span> <span data-ttu-id="5e467-119">El script se crea en formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="5e467-119">The script is created in Unicode format.</span></span>  
  
##  <a name="to-generate-a-script-of-a-single-object"></a><a name="ScriptSingleObject"></a> <span data-ttu-id="5e467-120">Para generar un script de un solo objeto</span><span class="sxs-lookup"><span data-stu-id="5e467-120">To generate a script of a single object</span></span>  
 <span data-ttu-id="5e467-121">**Para generar un script de un solo objeto**</span><span class="sxs-lookup"><span data-stu-id="5e467-121">**To script a single object**</span></span>  
  
1.  <span data-ttu-id="5e467-122">En el Explorador de objetos, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="5e467-122">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5e467-123">Expanda **Bases de datos**, y a continuación expanda la base de datos que contiene el objeto que se debe incluir en un script.</span><span class="sxs-lookup"><span data-stu-id="5e467-123">Expand **Databases**, and then expand the database containing the object to be scripted.</span></span>  
  
3.  <span data-ttu-id="5e467-124">Expanda la categoría del objeto.</span><span class="sxs-lookup"><span data-stu-id="5e467-124">Expand the category of the object.</span></span> <span data-ttu-id="5e467-125">Por ejemplo, expanda el nodo **Vistas** o **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="5e467-125">For example, expand the **Tables** or **Views** node.</span></span>  
  
4.  <span data-ttu-id="5e467-126">Haga clic con el botón secundario en el objeto, seleccione **incluir \<object type> como**, por ejemplo, incluir **tabla como**.</span><span class="sxs-lookup"><span data-stu-id="5e467-126">Right-click the object, point to **Script \<object type> as**, For example, point to **Script Table as**.</span></span>  
  
5.  <span data-ttu-id="5e467-127">Seleccione el tipo de script, como **Create to** o **Alter to**.</span><span class="sxs-lookup"><span data-stu-id="5e467-127">Point to the script type, such as **Create to** or **Alter to**.</span></span>  
  
6.  <span data-ttu-id="5e467-128">Seleccione la ubicación para guardar el script, como **Nueva ventana del Editor de consultas** o **Portapapeles**.</span><span class="sxs-lookup"><span data-stu-id="5e467-128">Select the location to save the script, such as **New Query Editor Window** or **Clipboard**.</span></span>  
  
##  <a name="to-generate-a-script-of-two-objects-using-object-explorer"></a><a name="ScriptTwoObjectsOE"></a> <span data-ttu-id="5e467-129">Para generar un script de dos objetos usando el Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="5e467-129">To generate a script of two objects using Object Explorer</span></span>  
 <span data-ttu-id="5e467-130">**Para generar un script de dos objetos usando el Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="5e467-130">**To script two objects using Object Explorer**</span></span>  
  
 <span data-ttu-id="5e467-131">En ocasiones, es posible que necesite un script que ofrezca varias opciones como, por ejemplo, quitar un procedimiento y, a continuación, crear otro, o bien crear una tabla y modificarla posteriormente.</span><span class="sxs-lookup"><span data-stu-id="5e467-131">Sometimes you may want a script with multiple options, such as drop a procedure and then create a procedure, or create a table and then alter a table.</span></span> <span data-ttu-id="5e467-132">Los siguientes procesos de generación de scripts de varios objetos también funcionan si necesita crear un script que haga referencia a tipos diferentes de objetos, como tablas, vistas y procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="5e467-132">The processes below for generating scripts of multiple objects also work if you need to create a script that references different types of objects, such as tables, views, and stored procedures.</span></span>  
  
1.  <span data-ttu-id="5e467-133">En el Explorador de objetos, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="5e467-133">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5e467-134">Expanda **Bases de datos**, y a continuación expanda la base de datos que contiene los objetos que se deben incluir en un script.</span><span class="sxs-lookup"><span data-stu-id="5e467-134">Expand **Databases**, and then expand the database containing the objects to be scripted.</span></span>  
  
3.  <span data-ttu-id="5e467-135">Haga clic con el botón derecho en el primer objeto que se va a incluir en el script, seleccione **incluir \<object type> como**y, en las selecciones **Guardar como** , elija **nueva ventana del editor de consultas** como destino de salida.</span><span class="sxs-lookup"><span data-stu-id="5e467-135">Right-click the first object to be scripted, point to **Script \<object type> as**, and in the **Save as** selections chooses **New Query Editor Window** as the output destination.</span></span>  
  
4.  <span data-ttu-id="5e467-136">Navegue hasta el segundo objeto que desea incluir en el script.</span><span class="sxs-lookup"><span data-stu-id="5e467-136">Navigate to the second object you want to script.</span></span>  
  
5.  <span data-ttu-id="5e467-137">Haga clic con el botón derecho en el objeto, seleccione **incluir \<object type> como**y, en las selecciones **Guardar como** , elija **portapapeles** como el destino de salida.</span><span class="sxs-lookup"><span data-stu-id="5e467-137">Right-click the object, point to **Script \<object type> as**, and in the **Save as** selections chooses **Clipboard** as the output destination.</span></span>  
  
6.  <span data-ttu-id="5e467-138">En la ventana Editor de consultas abierta para el primer objeto, pegue el script para el segundo objeto del Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="5e467-138">In the Query Editor window opened for the first object, paste the script for the second object from the clipboard.</span></span>  
  
##  <a name="to-generate-a-script-of-two-objects-using-object-explorer-details"></a><a name="ScriptTwoObjectsOED"></a><span data-ttu-id="5e467-139">Para generar un script de dos objetos con detalles de Explorador de objetos</span><span class="sxs-lookup"><span data-stu-id="5e467-139">To generate a script of two objects using Object Explorer Details</span></span>  
 <span data-ttu-id="5e467-140">**Para generar un script de dos objetos usando Detalles del Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="5e467-140">**To script two objects using Object Explorer Details**</span></span>  
  
 <span data-ttu-id="5e467-141">Puede usar el panel **Detalles del Explorador de objetos** para generar un script para varios objetos de la misma categoría.</span><span class="sxs-lookup"><span data-stu-id="5e467-141">You can use the **Object Explorer Details** pane to generate a script for mutliple objects of the same category.</span></span>  
  
1.  <span data-ttu-id="5e467-142">En el Explorador de objetos, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="5e467-142">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="5e467-143">Expanda **Bases de datos**, y a continuación expanda la base de datos que contiene los objetos que se deben incluir en un script.</span><span class="sxs-lookup"><span data-stu-id="5e467-143">Expand **Databases**, and then expand the database containing the objects to be scripted.</span></span>  
  
3.  <span data-ttu-id="5e467-144">Expanda el nodo de categoría de los tipos de objeto que desea incluir en el script, como el nodo **Tablas** .</span><span class="sxs-lookup"><span data-stu-id="5e467-144">Expand the category node of the types of object you want to script, such as the **Tables** node.</span></span>  
  
4.  <span data-ttu-id="5e467-145">Abra el panel **Detalles del Explorador de objetos** seleccionando **F7**o abriendo el menú **Ver** y seleccionando **Detalles del Explorador de objetos**.</span><span class="sxs-lookup"><span data-stu-id="5e467-145">Open the **Object Explorer Details** pane by either selecting **F7**, or opening the **View** menu and selecting **Object Explorer Details**.</span></span>  
  
5.  <span data-ttu-id="5e467-146">Haga clic con el botón primario en uno de los objetos que desea incluir en el script.</span><span class="sxs-lookup"><span data-stu-id="5e467-146">Left-click one of the objects you want to script.</span></span>  
  
6.  <span data-ttu-id="5e467-147">Presione Crtl y haga clic con el botón primario en el segundo objeto que desea incluir en el script.</span><span class="sxs-lookup"><span data-stu-id="5e467-147">Crtl + left-click the second object you want to script.</span></span>  
  
7.  <span data-ttu-id="5e467-148">Haga clic con el botón secundario en uno de los objetos seleccionados y seleccione **incluir \<object type> como**.</span><span class="sxs-lookup"><span data-stu-id="5e467-148">Right-click one of the selected objects, and select **Script \<object type> as**.</span></span>  
  
  
